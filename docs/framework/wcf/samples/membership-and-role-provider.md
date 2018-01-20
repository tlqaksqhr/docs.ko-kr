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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4479b10b3e6e4b3c63ac40474fb9ec7cda66e22d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="cb310-102">Membership and Role Provider</span><span class="sxs-lookup"><span data-stu-id="cb310-102">Membership and Role Provider</span></span>
<span data-ttu-id="cb310-103">Membership and Role Provider 샘플에서는 서비스에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 및 역할 공급자를 사용하여 클라이언트를 인증하고 권한을 부여하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-103">The Membership and Role Provider sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="cb310-104">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-104">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb310-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cb310-106">이 샘플에서는 다음과 같은 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-106">The sample demonstrates how:</span></span>  
  
-   <span data-ttu-id="cb310-107">클라이언트에서 사용자 이름/암호 조합을 사용하여 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb310-107">A client can authenticate by using the username-password combination.</span></span>  
  
-   <span data-ttu-id="cb310-108">서버에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자를 기준으로 클라이언트 자격 증명을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb310-108">The server can validate the client credentials against the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
-   <span data-ttu-id="cb310-109">서버의 X.509 인증서를 사용하여 서버를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb310-109">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
-   <span data-ttu-id="cb310-110">서버에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 사용하여 인증된 클라이언트를 역할에 매핑하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb310-110">The server can map the authenticated client to a role by using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider.</span></span>  
  
-   <span data-ttu-id="cb310-111">서버에서 `PrincipalPermissionAttribute`를 사용하여 서비스에 의해 노출되는 특정 메서드에 대한 액세스를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="cb310-111">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="cb310-112">멤버 자격 및 역할 공급자는 SQL Server에서 지원하는 저장소를 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-112">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="cb310-113">연결 문자열과 다양한 옵션이 서비스 구성 파일에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-113">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="cb310-114">멤버 자격 공급자의 이름은 `SqlMembershipProvider`로 지정되고 역할 공급자의 이름은 `SqlRoleProvider`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-114">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
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
  
 <span data-ttu-id="cb310-115">서비스에서는 서비스와의 통신에 사용할 수 있는 단일 끝점을 노출하며, 이 끝점은 Web.config 구성 파일을 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-115">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="cb310-116">끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="cb310-117">바인딩은 표준 `wsHttpBinding`을 사용하여 구성하며 기본값으로 Windows 인증이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-117">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="cb310-118">이 샘플에서는 사용자 이름 인증을 사용하도록 표준 `wsHttpBinding`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-118">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="cb310-119">동작에서는 서비스 인증에 서버 인증서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-119">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="cb310-120">서버 인증서에 대 한 동일한 값이 있어야 합니다.는 `SubjectName` 로 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-120">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="cb310-121">또한 동작에서는 두 공급자에 정의되는 이름을 지정하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자에서 사용자 이름/암호 쌍의 인증을 지정하고 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자에서 역할 매핑을 수행하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-121">In addition the behavior specifies that authentication of username-password pairs is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider and role mapping is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider by specifying the names defined for the two providers.</span></span>  
  
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
  
 <span data-ttu-id="cb310-122">샘플을 실행할 때 클라이언트는 세 개의 서로 다른 사용자 계정 Alice, Bob 및 Charlie 아래에서 다양한 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-122">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="cb310-123">작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-123">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="cb310-124">사용자 "Alice"로 수행한 4개의 호출은 모두 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-124">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="cb310-125">사용자 "Bob"이 Divide 메서드를 호출하려고 할 때는 액세스 거부 오류가 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-125">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="cb310-126">사용자 "Charlie"는 Multiply 메서드를 호출하려 할 때 액세스 거부 오류가 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-126">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="cb310-127">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-127">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cb310-128">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cb310-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cb310-129">지침에 따라 솔루션의 C# 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="cb310-130">구성 했는지 확인 하십시오.는 [ASP.NET 응용 프로그램 서비스 데이터베이스](http://go.microsoft.com/fwlink/?LinkId=94997)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-130">Ensure that you have configured the [ASP.NET Application Services Database](http://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb310-131">SQL Server Express Edition을 실행하는 경우 서버 이름은 .\SQLEXPRESS입니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-131">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="cb310-132">이 서버는 Web.config 연결 문자열에서와 마찬가지로 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 서비스 데이터베이스를 구성할 때에도 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-132">This server should be used when configuring the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb310-133">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작업자 프로세스 계정에는 이 단계에서 만든 데이터베이스에 대한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-133">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="cb310-134">이 작업에는 sqlcmd 유틸리티 또는 SQL Server Management Studio를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-134">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3.  <span data-ttu-id="cb310-135">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-135">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="cb310-136">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cb310-136">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="cb310-137">Makecert.exe가 있는 폴더가 경로에 포함되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-137">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2.  <span data-ttu-id="cb310-138">관리자 권한으로 실행되는 Visual Studio 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-138">Run Setup.bat from the sample install folder in a Visual Studio command prompt run with administrator privileges.</span></span> <span data-ttu-id="cb310-139">이 작업은 샘플 실행에 필요한 서비스 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-139">This installs the service certificates required for running the sample.</span></span>  
  
3.  <span data-ttu-id="cb310-140">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-140">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="cb310-141">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-141">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="cb310-142">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-142">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="cb310-143">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cb310-143">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="cb310-144">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-144">Create a directory on the service computer.</span></span> <span data-ttu-id="cb310-145">IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-145">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="cb310-146">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-146">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="cb310-147">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-147">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="cb310-148">Setup.bat, GetComputerName.vbs 및 Cleanup.bat 파일도 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-148">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="cb310-149">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-149">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="cb310-150">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-150">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="cb310-151">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-151">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="cb310-152">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-152">On the server, open a Visual Studio command prompt with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="cb310-153">실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-153">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="cb310-154">새로운 인증서 이름을 반영 되도록 Web.config를 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-154">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="cb310-155">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-155">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="cb310-156">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-156">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="cb310-157">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-157">On the client, open a Visual Studio command prompt with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="cb310-158">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-158">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="cb310-159">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-159">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="cb310-160">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-160">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="cb310-161">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="cb310-161">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="cb310-162">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-162">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb310-163">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-163">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="cb310-164">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-164">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="cb310-165">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="cb310-165">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="cb310-166">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="cb310-166">The Setup Batch File</span></span>  
 <span data-ttu-id="cb310-167">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-167">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="cb310-168">다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-168">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="cb310-169">아래에는 적절한 구성에서 실행할 수 있도록 배치 파일을 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-169">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
-   <span data-ttu-id="cb310-170">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="cb310-170">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="cb310-171">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-171">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="cb310-172">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-172">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="cb310-173">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-173">Change this variable to specify your own server name.</span></span> <span data-ttu-id="cb310-174">이 배치 파일에서의 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-174">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="cb310-175">인증서는 LocalMachine 저장 위치에 있는 My(개인) 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-175">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="cb310-176">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="cb310-176">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="cb310-177">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="cb310-178">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="cb310-179">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb310-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cb310-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb310-180">See Also</span></span>
