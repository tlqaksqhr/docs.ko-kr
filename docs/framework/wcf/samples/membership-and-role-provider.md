---
title: Membership and Role Provider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f2107c5ae03330eb82567ab483dcd7003a35e189
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="membership-and-role-provider"></a>Membership and Role Provider
Membership and Role Provider 샘플에서는 서비스에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 및 역할 공급자를 사용하여 클라이언트를 인증하고 권한을 부여하는 방법을 보여 줍니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 다음과 같은 작업을 수행하는 방법을 보여 줍니다.  
  
-   클라이언트에서 사용자 이름/암호 조합을 사용하여 인증하는 방법  
  
-   서버에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자를 기준으로 클라이언트 자격 증명을 확인하는 방법  
  
-   서버의 X.509 인증서를 사용하여 서버를 인증하는 방법  
  
-   서버에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 사용하여 인증된 클라이언트를 역할에 매핑하는 방법  
  
-   서버에서 `PrincipalPermissionAttribute`를 사용하여 서비스에 의해 노출되는 특정 메서드에 대한 액세스를 제어하는 방법  
  
 멤버 자격 및 역할 공급자는 SQL Server에서 지원하는 저장소를 사용하도록 구성됩니다. 연결 문자열과 다양한 옵션이 서비스 구성 파일에 지정됩니다. 멤버 자격 공급자의 이름은 `SqlMembershipProvider`로 지정되고 역할 공급자의 이름은 `SqlRoleProvider`로 지정됩니다.  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"   
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add   
        name="SqlMembershipProvider"   
        type="System.Web.Security.SqlMembershipProvider"   
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"   
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 서비스에서는 서비스와의 통신에 사용할 수 있는 단일 끝점을 노출하며, 이 끝점은 Web.config 구성 파일을 사용하여 정의합니다. 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다. 바인딩은 표준 `wsHttpBinding`을 사용하여 구성하며 기본값으로 Windows 인증이 사용됩니다. 이 샘플에서는 사용자 이름 인증을 사용하도록 표준 `wsHttpBinding`을 설정합니다. 동작에서는 서비스 인증에 서버 인증서를 사용하도록 지정합니다. 서버 인증서에 대 한 동일한 값이 있어야 합니다.는 `SubjectName` 로 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 구성 요소입니다. 또한 동작에서는 두 공급자에 정의되는 이름을 지정하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자에서 사용자 이름/암호 쌍의 인증을 지정하고 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자에서 역할 매핑을 수행하도록 지정합니다.  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"   
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"   
                              storeName ="My"   
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 샘플을 실행할 때 클라이언트는 세 개의 서로 다른 사용자 계정 Alice, Bob 및 Charlie 아래에서 다양한 서비스 작업을 호출합니다. 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 사용자 "Alice"로 수행한 4개의 호출은 모두 성공해야 합니다. 사용자 "Bob"이 Divide 메서드를 호출하려고 할 때는 액세스 거부 오류가 발생해야 합니다. 사용자 "Charlie"는 Multiply 메서드를 호출하려 할 때 액세스 거부 오류가 발생해야 합니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  지침에 따라 솔루션의 C# 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
2.  구성 했는지 확인 하십시오.는 [ASP.NET 응용 프로그램 서비스 데이터베이스](http://go.microsoft.com/fwlink/?LinkId=94997)합니다.  
  
    > [!NOTE]
    >  SQL Server Express Edition을 실행하는 경우 서버 이름은 .\SQLEXPRESS입니다. 이 서버는 Web.config 연결 문자열에서와 마찬가지로 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 서비스 데이터베이스를 구성할 때에도 사용해야 합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작업자 프로세스 계정에는 이 단계에서 만든 데이터베이스에 대한 권한이 있어야 합니다. 이 작업에는 sqlcmd 유틸리티 또는 SQL Server Management Studio를 사용합니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  Makecert.exe가 있는 폴더가 경로에 포함되는지 확인합니다.  
  
2.  관리자 권한으로 실행되는 Visual Studio 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 서비스 인증서를 설치합니다.  
  
3.  \client\bin에서 Client.exe를 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
4.  클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스 컴퓨터에 디렉터리를 만듭니다. IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 응용 프로그램을 만듭니다.  
  
2.  \inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다. \bin 하위 디렉터리에 파일을 복사해야 합니다. Setup.bat, GetComputerName.vbs 및 Cleanup.bat 파일도 서비스 컴퓨터에 복사합니다.  
  
3.  클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.  
  
4.  클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다. Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.  
  
5.  서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다. 실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.  
  
6.  새로운 인증서 이름을 반영 되도록 Web.config를 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), 컴퓨터의 정규화 된 도메인 이름과 같습니다.  
  
7.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
8.  클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.  
  
9. 클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
10. 클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다. 클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
> [!NOTE]
>  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. 다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다. 이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).  
  
## <a name="the-setup-batch-file"></a>설치 배치 파일  
 이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다. 다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.  
  
 아래에는 적절한 구성에서 실행할 수 있도록 배치 파일을 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.  
  
-   서버 인증서 만들기  
  
     Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다. %SERVER_NAME% 변수는 서버 이름을 지정합니다. 이 변수를 변경하여 고유의 서버 이름을 지정합니다. 이 배치 파일에서의 기본값은 localhost입니다.  
  
     인증서는 LocalMachine 저장 위치에 있는 My(개인) 저장소에 저장됩니다.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치  
  
     Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다. 이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다. Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
## <a name="see-also"></a>참고 항목
