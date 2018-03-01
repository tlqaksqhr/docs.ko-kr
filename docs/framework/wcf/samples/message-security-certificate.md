---
title: "메시지 보안 인증서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 9339258c4f5df606db9126c8b4b886b0a26029a6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="message-security-certificate"></a>메시지 보안 인증서
이 샘플에서는 클라이언트에 대해 X.509 v3 인증서를 통한 WS-Security 인증을 사용하며 서버의 X.509 v3 인증서를 사용한 서버 인증을 수행해야 하는 응용 프로그램의 구현 방법을 보여 줍니다. 이 샘플에서는 클라이언트와 서버 간의 모든 응용 프로그램 메시지가 서명 및 암호화되도록 기본 설정을 사용합니다. 이 샘플에 따라는 [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) 인터넷 정보 서비스 (IIS)에서 호스팅하는 서비스 라이브러리 및 클라이언트 콘솔 프로그램으로 구성 됩니다. 이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 다음 샘플 코드에 표시된 것과 같이 구성을 이용하여 인증을 제어하는 방법과 보안 컨텍스트에서 호출자의 ID를 가져오는 방법을 보여 줍니다.  
  
```  
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 서비스에서는 서비스와 통신하기 위한 하나의 끝점과 WS-MetadataExchange 프로토콜을 사용하여 서비스의 WSDL 문서를 노출하기 위한 하나의 끝점을 노출하며 이러한 끝점은 구성 파일(Web.config)을 사용하여 정의합니다. 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다. 표준 바인딩이 구성 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 기본적으로 메시지 보안을 사용 하는 요소입니다. 이 샘플에서는 클라이언트 인증을 요구하도록 `clientCredentialType` 특성을 Certificate로 설정합니다.  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 동작에서는 클라이언트가 서비스를 인증할 때 사용되는 서비스의 자격 증명을 지정합니다. 서버 인증서 주체 이름에 지정 되는 `findValue` 특성에 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 요소입니다.  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 클라이언트 끝점 구성은 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다. 클라이언트 바인딩은 적절한 보안 모드 및 인증 모드를 사용하여 구성됩니다. 다중 컴퓨터 구성에서 실행할 경우 서비스 끝점 주소를 적절하게 변경해야 합니다.  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 클라이언트 구현에서는 구성 파일이나 코드를 통해 사용할 인증서를 설정할 수 있습니다. 다음 샘플에서는 구성 파일에서 사용할 인증서를 설정하는 방법을 보여 줍니다.  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 다음 샘플에서는 프로그램에서 서비스를 호출하는 방법을 보여 줍니다.  
  
```  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 Message Security 샘플에 포함된 Setup.bat 배치 파일을 사용하면 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 클라이언트와 서버를 구성할 수 있습니다. 이 배치 파일을 세 가지 모드로 실행할 수 있습니다. 형식이 단일 컴퓨터 모드에서 실행 하려면 **setup.bat** Visual Studio 명령 프롬프트에서, 서비스 모드 유형에 대 한 **setup.bat service**; 및 클라이언트 모드 형식에 대 한 **setup.bat client** . 다중 컴퓨터 구성에서 샘플을 실행할 경우 클라이언트 및 서버 모드를 사용합니다. 자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요. 다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.  
  
-   클라이언트 인증서 만들기  
  
     배치 파일의 다음 줄에서는 클라이언트 인증서를 만듭니다. 지정된 클라이언트 이름은 만든 인증서의 제목 이름에 사용됩니다. 인증서는 `My` 저장소 위치에 있는 `CurrentUser` 저장소에 저장됩니다.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치  
  
     배치 파일의 다음 줄에서는 서버에서 관련된 신뢰 여부를 결정할 수 있도록 서버의 TrustedPeople 저장소에 클라이언트 인증서를 복사합니다. TrustedPeople 저장소에 설치된 인증서를 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에서 신뢰하려면 클라이언트 인증서 유효성 검사 모드를 `PeerOrChainTrust` 또는 `PeerTrust`로 설정해야 합니다. 구성 파일을 사용하여 이 작업을 수행하는 방법을 보려면 앞서 소개된 서비스 구성 샘플을 참조하십시오.  
  
    ```  
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
-   서버 인증서 만들기  
  
     Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     %SERVER_NAME% 변수는 서버 이름을 지정합니다. 인증서는 LocalMachine 저장소에 저장됩니다. 서비스의 인수와 함께 Setup.bat 배치 파일을 실행할 경우 (예: **setup.bat service**) % SERVER_NAME %는 컴퓨터의 정규화 된 도메인 이름을 포함 합니다. 그렇지 않은 경우 기본적으로 localhost입니다.  
  
-   클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치  
  
     다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다. 이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다. Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   인증서의 개인 키에 대한 사용 권한 부여  
  
     Setup.bat 파일의 다음 줄은 LocalMachine 저장소에 저장된 서버 인증서를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작업자 프로세스 계정에서 액세스할 수 있게 합니다.  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  미국 영어 버전이 아닌 Windows 버전을 사용하는 경우 Setup.bat 파일을 편집하여 "NT AUTHORITY\NETWORK SERVICE" 계정 이름을 해당 국가별 계정 이름으로 바꿔야 합니다.  
  
> [!NOTE]
>  이 배치 파일에서 사용되는 도구는 C:\Program Files\Microsoft Visual Studio 8\Common7\tools 또는 C:\Program Files\Microsoft SDKs\Windows\v6.0\bin에 있습니다. 이러한 디렉터리 중 하나가 시스템 경로에 있어야 합니다. Visual Studio가 설치된 경우 경로에 이 디렉터리를 포함하는 가장 쉬운 방법은 Visual Studio 명령 프롬프트를 여는 것입니다. 클릭 **시작**를 선택한 후 **모든 프로그램**, **Visual Studio 2012**, **도구**합니다. 이 명령 프롬프트에는 이미 구성된 적절한 경로가 있습니다. 그렇지 않을 경우 해당 디렉터리를 경로에 수동으로 추가해야 합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  관리자 권한으로 Visual Studio 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다. 이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.  
  
    > [!NOTE]
    >  Setup.bat 배치 파일은 Visual Studio 명령 프롬프트에서 실행 되도록 설계 되었습니다. PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다. 이 환경 변수는Visual Studio 명령 프롬프트(2010) 내에서 자동으로 설정됩니다.  
  
2.  브라우저를 사용 하 여 주소를 입력 하 여 서비스에 대 한 액세스 확인 `http://localhost/servicemodelsamples/service.svc`합니다.  
  
3.  \client\bin에서 Client.exe를 실행합니다. 클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.  
  
4.  클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스 컴퓨터에 디렉터리를 만듭니다. IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 응용 프로그램을 만듭니다.  
  
2.  \inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다. \bin 하위 디렉터리에 파일을 복사해야 합니다. Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.  
  
3.  클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.  
  
4.  클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다. Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.  
  
5.  서버에서 실행 **setup.bat service** 관리자 권한으로 Visual Studio 명령 프롬프트에서입니다. 실행 **setup.bat** 와 **서비스** 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.  
  
6.  새로운 인증서 이름을 반영 되도록 Web.config를 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 컴퓨터의 정규화 된 도메인 이름과 같습니다.  
  
7.  서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.  
  
8.  클라이언트에서 실행 **setup.bat client** 관리자 권한으로 Visual Studio 명령 프롬프트에서입니다. 실행 **setup.bat** 와 **클라이언트** 인수 client.com 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.  
  
9. 클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다. 이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.  
  
10. 클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.  
  
11. 클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다. 이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.  
  
12. 서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다. 이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.  
  
13. 클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다. 클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.  
  
### <a name="to-clean-up-after-the-sample"></a>샘플 실행 후 정리를 수행하려면  
  
-   샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.  
  
    > [!NOTE]
    >  다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다. 다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다. 이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).  
  
## <a name="see-also"></a>참고 항목
