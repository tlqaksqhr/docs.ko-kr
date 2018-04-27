---
title: Message Security Anonymous
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
caps.latest.revision: 52
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: c93aacbe5af47c9094dccdaa15828bfa9fda79c5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="message-security-anonymous"></a><span data-ttu-id="65d7c-102">Message Security Anonymous</span><span class="sxs-lookup"><span data-stu-id="65d7c-102">Message Security Anonymous</span></span>
<span data-ttu-id="65d7c-103">Message Security Anonymous 샘플에서는 클라이언트 인증 없이 메시지 수준 보안을 사용하지만 서버의 X.509 인증서를 사용하는 서버 인증을 요구하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-103">The Message Security Anonymous sample demonstrates how to implement a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span> <span data-ttu-id="65d7c-104">클라이언트와 서버 간의 모든 응용 프로그램 메시지는 서명 및 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="65d7c-105">이 샘플에 따라는 [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="65d7c-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span> <span data-ttu-id="65d7c-106">이 샘플은 IIS(인터넷 정보 서비스)에 의해 호스트되는 클라이언트 콘솔 프로그램(.exe) 및 서비스 라이브러리(.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="65d7c-107">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-107">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65d7c-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="65d7c-109">이 샘플은 클라이언트가 인증되지 않은 경우 `True`를 반환하는 새 작업을 계산기 인터페이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-109">This sample adds a new operation to the calculator interface that returns `True` if the client was not authenticated.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public bool IsCallerAnonymous()  
    {  
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.  
        return ServiceSecurityContext.Current.IsAnonymous;  
    }  
    ...  
}  
```

 <span data-ttu-id="65d7c-110">서비스는 구성 파일(Web.config)을 사용하여 서비스와 통신하기 위한 단일 끝점을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-110">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="65d7c-111">끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-111">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="65d7c-112">바인딩은 `wsHttpBinding` 바인딩을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-112">The binding is configured with a `wsHttpBinding` binding.</span></span> <span data-ttu-id="65d7c-113">`wsHttpBinding` 바인딩의 기본 보안 모드는 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-113">The default security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="65d7c-114">`clientCredentialType` 특성은 `None`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-114">The `clientCredentialType` attribute is set to `None`.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
     <!--   
     <!--This configuration defines the security mode as Message and-->  
     <!--the clientCredentialType as None. This mode provides -- >  
     <!--server authentication only using the service certificate.-->  
  
     <binding>  
       <security mode="Message">  
         <message clientCredentialType="None" />  
       </security>  
     </binding>  
    </wsHttpBinding>  
  </bindings>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="65d7c-115">서비스 인증에 사용할 자격 증명에 지정 된 된 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-115">The credentials to be used for service authentication are specified in the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span></span> <span data-ttu-id="65d7c-116">다음 샘플 코드와 같이 서버 인증서는 `SubjectName` 특성에 지정된 값과 동일한 `findValue` 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-116">The server certificate must contain the same value for the `SubjectName` as the value specified for the `findValue` attribute as shown in the following sample code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>  
      <!--   
    The serviceCredentials behavior allows you to define a service certificate.  
    A service certificate is used by a client to authenticate the service and provide message protection.  
    This configuration references the "localhost" certificate installed during the setup instructions.  
    -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
      </serviceCredentials>  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="65d7c-117">클라이언트 끝점 구성은 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-117">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="65d7c-118">`wsHttpBinding` 바인딩의 클라이언트 보안 모드는 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-118">The client security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="65d7c-119">`clientCredentialType` 특성은 `None`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-119">The `clientCredentialType` attribute is set to `None`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
             address="http://localhost/servicemodelsamples/service.svc"   
             binding="wsHttpBinding"   
             behaviorConfiguration="ClientCredentialsBehavior"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--This configuration defines the security mode as -->  
      <!--Message and the clientCredentialType as None. -->  
      <binding name="Binding1">  
        <security mode = "Message">  
          <message clientCredentialType="None"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>   
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="65d7c-120">서비스의 인증서를 인증하기 위해 샘플에서는 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>가 <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-120">The sample sets the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> to <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> for authenticating the service's certificate.</span></span> <span data-ttu-id="65d7c-121">클라이언트의 App.config 파일에 있는 `behaviors` 섹션에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-121">This is done in the client's App.config file in the `behaviors` section.</span></span> <span data-ttu-id="65d7c-122">이는 인증서가 사용자의 신뢰할 수 있는 사용자 저장소에 있는 경우 인증서의 발급자 체인에 대한 유효성 검사를 수행하지 않고 인증서가 신뢰된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-122">This means that if the certificate is in the user's Trusted People store, then it is trusted without performing a validation of the certificate's issuer chain.</span></span> <span data-ttu-id="65d7c-123">여기서 이 설정은 편의상 사용된 것이므로 CA(인증 기관)에서 발급된 인증서를 요구하지 않고 샘플을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-123">This setting is used here for convenience so that the sample can be run without requiring certificates issued by a certification authority (CA).</span></span> <span data-ttu-id="65d7c-124">이 설정은 기본 ChainTrust보다 덜 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-124">This setting is less secure than the default, ChainTrust.</span></span> <span data-ttu-id="65d7c-125">프로덕션 코드에서 `PeerOrChainTrust`를 사용하기 전에 이 설정의 보안 문제를 신중하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-125">The security implications of this setting should be carefully considered before using `PeerOrChainTrust` in production code.</span></span>  
  
 <span data-ttu-id="65d7c-126">에 대 한 호출을 추가 하는 클라이언트 구현에서 `IsCallerAnonymous` 메서드 그렇지 않은 경우와 동일에서 및는 [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="65d7c-126">The client implementation adds a call to the `IsCallerAnonymous` method and otherwise does not differ from the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  

```csharp
// Create a client with a client endpoint configuration.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity operation.  
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
...  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```

 <span data-ttu-id="65d7c-127">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="65d7c-128">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
IsCallerAnonymous returned: True  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="65d7c-129">Message Security Anonymous 샘플에 포함된 Setup.bat 배치 파일을 사용하면 인증서 기반 보안이 필요한 호스트된 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-129">The Setup.bat batch file included with the Message Security Anonymous sample enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="65d7c-130">배치 파일은 두 가지 모드로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-130">The batch file can be run in two modes.</span></span> <span data-ttu-id="65d7c-131">단일 컴퓨터 모드에서 배치 파일을 실행하려면 명령줄에 `setup.bat`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-131">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="65d7c-132">서비스 모드에서 실행하려면 `setup.bat service`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-132">To run it in service mode, type `setup.bat service`.</span></span> <span data-ttu-id="65d7c-133">다중 컴퓨터 구성에서 샘플을 실행할 경우 이 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-133">Use this mode when running the sample across computers.</span></span> <span data-ttu-id="65d7c-134">자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65d7c-134">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="65d7c-135">다음은 배치 파일의 여러 다른 섹션에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-135">The following provides a brief overview of the different sections of the batch files:</span></span>  
  
-   <span data-ttu-id="65d7c-136">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="65d7c-136">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="65d7c-137">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-137">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="65d7c-138">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-138">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="65d7c-139">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-139">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="65d7c-140">`setup.bat service` 등의 서비스 인수와 함께 설치 배치 파일을 실행하는 경우 %SERVER_NAME%에는 컴퓨터의 정규화된 도메인 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-140">If the setup batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="65d7c-141">그렇지 않은 경우 기본적으로 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-141">Otherwise it defaults to localhost.</span></span>  
  
-   <span data-ttu-id="65d7c-142">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="65d7c-142">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="65d7c-143">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-143">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="65d7c-144">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-144">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="65d7c-145">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-145">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="65d7c-146">인증서의 개인 키에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="65d7c-146">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="65d7c-147">Setup.bat 배치 파일의 다음 줄은 LocalMachine 저장소에 저장된 서버 인증서를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작업자 프로세스 계정에서 액세스할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-147">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="65d7c-148">미국 영어 버전이 아닌 Windows 버전을 사용하는 경우 Setup.bat 파일을 편집하여 `NT AUTHORITY\NETWORK SERVICE` 계정 이름을 해당 국가별 계정 이름으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-148">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65d7c-149">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="65d7c-149">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="65d7c-150">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-150">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="65d7c-151">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="65d7c-152">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="65d7c-152">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="65d7c-153">Makecert.exe 및 FindPrivateKey.exe가 있는 폴더가 경로에 포함되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-153">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2.  <span data-ttu-id="65d7c-154">관리자 권한으로 실행되는 Visual Studio 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-154">Run Setup.bat from the sample install folder in a Visual Studio command prompt run with administrator privileges.</span></span> <span data-ttu-id="65d7c-155">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-155">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65d7c-156">Setup 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-156">The setup batch file is designed to be run from a  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]Command Prompt.</span></span> <span data-ttu-id="65d7c-157">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-157">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="65d7c-158">이 환경 변수는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-158">This environment variable is automatically set within a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]Command Prompt.</span></span>  
  
3.  <span data-ttu-id="65d7c-159">브라우저를 사용 하 여 주소를 입력 하 여 서비스에 대 한 액세스 확인 http://localhost/servicemodelsamples/service.svc합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-159">Verify access to the service using a browser by entering the address http://localhost/servicemodelsamples/service.svc.</span></span>  
  
4.  <span data-ttu-id="65d7c-160">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-160">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="65d7c-161">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-161">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="65d7c-162">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-162">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="65d7c-163">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="65d7c-163">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="65d7c-164">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-164">Create a directory on the service computer.</span></span> <span data-ttu-id="65d7c-165">IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-165">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="65d7c-166">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-166">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="65d7c-167">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-167">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="65d7c-168">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-168">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="65d7c-169">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-169">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="65d7c-170">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-170">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="65d7c-171">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-171">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="65d7c-172">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-172">On the server, run `setup.bat service` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="65d7c-173">실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-173">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="65d7c-174">새로운 인증서 이름을 반영 되도록 Web.config를 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-174">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="65d7c-175">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-175">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="65d7c-176">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-176">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="65d7c-177">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-177">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="65d7c-178">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-178">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="65d7c-179">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-179">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="65d7c-180">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-180">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="65d7c-181">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="65d7c-181">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="65d7c-182">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-182">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65d7c-183">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-183">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="65d7c-184">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d7c-184">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="65d7c-185">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`).</span><span class="sxs-lookup"><span data-stu-id="65d7c-185">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d7c-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65d7c-186">See Also</span></span>
