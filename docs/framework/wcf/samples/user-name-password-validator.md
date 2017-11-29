---
title: User Name Password Validator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 07083d7a92f6b4de68cd1d618d57291f64bef0fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="user-name-password-validator"></a><span data-ttu-id="d07bc-102">User Name Password Validator</span><span class="sxs-lookup"><span data-stu-id="d07bc-102">User Name Password Validator</span></span>
<span data-ttu-id="d07bc-103">이 샘플에서는 사용자 지정 UserNamePassword 유효성 검사기를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-103">This sample demonstrates how to implement a custom UserNamePassword Validator.</span></span> <span data-ttu-id="d07bc-104">사용자 이름/암호 쌍이 데이터베이스 같은 외부 저장소에 저장되어 있는 경우처럼 기본 제공되는 UserNamePassword 유효성 검사 모드가 응용 프로그램 요구 사항에 맞지 않는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-104">This is useful in cases where none of the built-in UserNamePassword Validation modes is appropriate for the requirements of the application; for example, when username/password pairs are stored in some external store, such as a database.</span></span> <span data-ttu-id="d07bc-105">이 샘플에서는 두 개의 특정 사용자 이름/암호 쌍을 확인하는 사용자 지정 유효성 검사기가 있는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-105">This sample shows a service that has a custom validator that checks for two particular username/password pairs.</span></span> <span data-ttu-id="d07bc-106">클라이언트에서는 이러한 사용자 이름/암호 쌍을 사용하여 서비스의 인증을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-106">The client uses such a username/password pair to authenticate to the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d07bc-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d07bc-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d07bc-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d07bc-109">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d07bc-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d07bc-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
>  <span data-ttu-id="d07bc-111">사용자 지정 유효성 검사기에서 허용하는 사용자 이름/암호 쌍을 사용한 사용자 이름 자격 증명은 누구나 구성할 수 있기 때문에, 서비스를 사용하면 표준 UserNamePassword 유효성 검사기에서 제공되는 기본 동작을 사용하는 경우보다 보안 수준이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-111">Because anyone can construct a Username credential that uses the username/password pairs that the custom validator accepts, the service is less secure than the default behavior provided by the standard UserNamePassword Validator.</span></span> <span data-ttu-id="d07bc-112">표준 UserNamePassword 유효성 검사기에서는 제공된 사용자 이름/암호 쌍을 Windows 계정에 매핑하며, 이 매핑이 실패하면 인증에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-112">The standard UserNamePassword Validator attempts to map the provided username/password pair to a Windows account and fails authentication if this mapping fails.</span></span> <span data-ttu-id="d07bc-113">이 샘플의 사용자 지정 UserNamePassword 유효성 검사기는 설명을 위해서만 사용되며 프로덕션 코드에 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-113">The custom UserNamePassword Validator in this sample MUST NOT be used in production code, it is for illustration purposes only.</span></span>  
  
 <span data-ttu-id="d07bc-114">요약하면, 이 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-114">In summary this sample demonstrates how:</span></span>  
  
-   <span data-ttu-id="d07bc-115">사용자 이름 토큰을 사용하여 클라이언트를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="d07bc-115">The client can be authenticated using a Username Token.</span></span>  
  
-   <span data-ttu-id="d07bc-116">서버에서 사용자 지정 UserNamePasswordValidator를 기준으로 클라이언트 자격 증명의 유효성을 검사하는 방법과 사용자 이름 및 암호 유효성 검사 논리에서 클라이언트로 사용자 지정 오류를 전파하는 방법</span><span class="sxs-lookup"><span data-stu-id="d07bc-116">The server validates the client credentials against a custom UserNamePasswordValidator and how to propagate custom faults from the username and password validation logic to the client.</span></span>  
  
-   <span data-ttu-id="d07bc-117">서버의 X.509 인증서를 사용하여 서버를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="d07bc-117">The server is authenticated using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="d07bc-118">서비스에서는 서비스와의 통신에 사용할 수 있는 단일 끝점을 노출하며, 이 끝점은 App.config 구성 파일을 사용하여 정의합니다. 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-118">The service exposes a single endpoint for communicating with the service, defined using the configuration file, App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="d07bc-119">표준 바인딩이 구성 된 `wsHttpBinding` WS Securityand 사용자 이름 인증을 사용 하 여 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-119">The binding is configured with a standard `wsHttpBinding` that defaults to using WS-Securityand username authentication.</span></span> <span data-ttu-id="d07bc-120">서비스 동작에서는 클라이언트 사용자 이름/암호 쌍의 유효성 검사를 위해 `Custom` 모드와 유효성 검사기 클래스 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-120">The service behavior specifies the `Custom` mode for validating client username/password pairs along with the type of the validator class.</span></span> <span data-ttu-id="d07bc-121">동작에서는 `serviceCertificate` 요소를 사용하여 서버 인증서도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-121">The behavior also specifies the server certificate using the `serviceCertificate` element.</span></span> <span data-ttu-id="d07bc-122">서버 인증서에 동일한 값을 포함 하는 `SubjectName` 로 `findValue` 에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-122">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <!-- use host/baseAddresses to configure base address provided by host -->  
      <host>  
        <baseAddresses>  
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />  
        </baseAddresses>  
      </host>  
      <!-- use base address specified above, provide one endpoint -->  
      <endpoint address="username"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- username binding -->  
      <binding name="Binding">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceDebug includeExceptionDetailInFaults ="true"/>  
        <serviceCredentials>  
          <!--   
          The serviceCredentials behavior allows one to   
          specify a custom validator for username/password  
          combinations.  
          -->  
          <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />  
          <!--   
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d07bc-123">클라이언트 끝점 구성은 구성 이름, 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-123">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="d07bc-124">클라이언트 바인딩에는 적절한 모드 및 메시지 `clientCredentialType`이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-124">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- Username based endpoint -->  
      <endpoint name="Username"  
address="http://localhost:8001/servicemodelsamples/service/username"   
                binding="wsHttpBinding"   
                bindingConfiguration="Binding"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- Username binding -->  
        <binding name="Binding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="d07bc-125">클라이언트 구현에서는 사용자에게 사용자 이름 및 암호 입력을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-125">The client implementation prompts the user to enter a username and password.</span></span>  
  
```  
// Get the username and password  
Console.WriteLine("Username authentication required.");  
Console.WriteLine("Provide a username.");  
Console.WriteLine("   Enter username: (test1)");  
string username = Console.ReadLine();  
Console.WriteLine("   Enter password:");  
string password = "";  
ConsoleKeyInfo info = Console.ReadKey(true);  
while (info.Key != ConsoleKey.Enter)  
{  
    if (info.Key != ConsoleKey.Backspace)  
    {  
        if (info.KeyChar != '\0')  
        {  
            password += info.KeyChar;  
        }  
        info = Console.ReadKey(true);  
    }  
    else if (info.Key == ConsoleKey.Backspace)  
    {  
        if (password != "")  
        {  
            password = password.Substring(0, password.Length - 1);  
        }  
        info = Console.ReadKey(true);  
    }  
}  
for (int i = 0; i < password.Length; i++)  
{  
    Console.Write("*");  
}  
Console.WriteLine();  
// Create a proxy with Certificate endpoint configuration  
CalculatorProxy proxy = new CalculatorProxy("Username")  
try  
{  
  proxy.ClientCredentials.Username.Username = username;  
  proxy.ClientCredentials.Username.Password = password;  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = proxy.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  }  
  catch (Exception e)  
  {  
      Console.WriteLine("Call failed:");  
      while (e != null)  
      {  
          Console.WriteLine("\t{0}", e.Message);  
          e = e.InnerException;  
      }  
      proxy.Abort();  
  }  
}  
```  
  
 <span data-ttu-id="d07bc-126">이 샘플에서는 사용자 지정 UserNamePasswordValidator를 사용하여 사용자 이름/암호 쌍의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-126">This sample uses a custom UserNamePasswordValidator to validate username/password pairs.</span></span> <span data-ttu-id="d07bc-127">이 샘플에서는 `CustomUserNamePasswordValidator`에서 파생된 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-127">The sample implements `CustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="d07bc-128">자세한 내용은 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>의 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d07bc-128">See the documentation for <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="d07bc-129">이 특정 사용자 지정 유효성 검사기 샘플에서는 `Validate` 메서드를 구현하여 다음 코드에 표시된 것과 같이 두 개의 특정 사용자 이름/암호 쌍을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-129">This particular custom validator sample implements the `Validate` method to accept two particular username/password pairs as shown in the following code.</span></span>  
  
```  
public class CustomUserNameValidator : UserNamePasswordValidator  
{  
 // This method validates users. It allows in two users,  
 // test1 and test2 with passwords 1tset and 2tset respectively.  
 // This code is for illustration purposes only and  
 // MUST NOT be used in a production environment because it  
 // is NOT secure.  
 public override void Validate(string userName, string password)  
 {  
  if (null == userName || null == password)  
  {  
   throw new ArgumentNullException();  
  }  
  
  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))  
  {  
   throw new FaultException("Unknown Username or Incorrect Password");  
   }  
  }  
 }  
```  
  
 <span data-ttu-id="d07bc-130">서비스 코드에 유효성 검사기를 구현하고 나면 사용할 유효성 검사기 인스턴스에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-130">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="d07bc-131">이것은 다음 코드를 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-131">This is done using the following code.</span></span>  
  
```  
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();  
```  
  
 <span data-ttu-id="d07bc-132">또는 다음과 같이 구성에서도 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-132">Or you can do the same thing in configuration as follows.</span></span>  
  
```xml  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="CalculatorServiceBehavior">  
  ...  
   <serviceCredentials>  
    <!--   
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.  
    -->  
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />  
   ...  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="d07bc-133">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-133">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d07bc-134">클라이언트에서 모든 메서드를 성공적으로 호출할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-134">The client should successfully call all the methods.</span></span> <span data-ttu-id="d07bc-135">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-135">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="d07bc-136">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="d07bc-136">Setup Batch File</span></span>  
 <span data-ttu-id="d07bc-137">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-137">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="d07bc-138">다중 컴퓨터 구성이나 자체 호스팅되지 않은 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-138">This batch file must be modified to work across machines or to work in a non-self-hosted case.</span></span>  
  
 <span data-ttu-id="d07bc-139">아래에는 적절한 구성에서 실행할 수 있도록 배치 파일을 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-139">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
-   <span data-ttu-id="d07bc-140">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="d07bc-140">Creating the server certificate:</span></span>  
  
     <span data-ttu-id="d07bc-141">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-141">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="d07bc-142">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-142">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="d07bc-143">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d07bc-144">기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-144">The default value is localhost.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="d07bc-145">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치:</span><span class="sxs-lookup"><span data-stu-id="d07bc-145">Installing the server certificate into client's trusted certificate store:</span></span>  
  
     <span data-ttu-id="d07bc-146">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-146">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d07bc-147">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-147">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d07bc-148">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-148">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="d07bc-149">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="d07bc-149">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="d07bc-150">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-150">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="d07bc-151">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-151">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="d07bc-152">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d07bc-152">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="d07bc-153">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-153">Run Setup.bat from the sample install folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt.</span></span> <span data-ttu-id="d07bc-154">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-154">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d07bc-155">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-155">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="d07bc-156">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-156">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="d07bc-157">service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-157">Launch Service.exe from service\bin.</span></span>  
  
3.  <span data-ttu-id="d07bc-158">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-158">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="d07bc-159">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-159">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="d07bc-160">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d07bc-160">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="d07bc-161">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d07bc-161">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="d07bc-162">서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-162">Create a directory on the service machine for the service binaries.</span></span>  
  
2.  <span data-ttu-id="d07bc-163">서비스 프로그램 파일을 서비스 컴퓨터의 서비스 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-163">Copy the service program files the service directory on the service machine.</span></span> <span data-ttu-id="d07bc-164">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-164">Also copy the Setup.bat and Cleanup.bat files to the service machine.</span></span>  
  
3.  <span data-ttu-id="d07bc-165">컴퓨터의 정규화된 도메인 이름을 포함하는 주체 이름을 가진 서버 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-165">You need a server certificate with the subject name that contains the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="d07bc-166">이 새로운 인증서 이름을 반영하도록 서버의 구성 파일을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-166">The configuration file for the server must be updated to reflect this new certificate name.</span></span>  
  
4.  <span data-ttu-id="d07bc-167">서버 인증서를 클라이언트의 CurrentUser-TrustedPeople 저장소에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-167">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="d07bc-168">신뢰할 수 있는 발급자에 의해 서버 인증서가 발급되지 않은 경우에만 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-168">You need to do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5.  <span data-ttu-id="d07bc-169">서비스 컴퓨터의 App.config 파일에서 기본 주소 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-169">In the App.config file on the service machine, change the value of the base address to specify a fully-qualified machine name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="d07bc-170">서비스 컴퓨터의 명령 프롬프트 창에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-170">On the service machine, launch Service.exe from a command prompt window.</span></span>  
  
7.  <span data-ttu-id="d07bc-171">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 컴퓨터로 클라이언트 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-171">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
8.  <span data-ttu-id="d07bc-172">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-172">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="d07bc-173">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-173">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="d07bc-174">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d07bc-174">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d07bc-175">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d07bc-175">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="d07bc-176">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-176">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="d07bc-177">그러면 인증서 저장소에서 서버 인증서가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07bc-177">This removes the server certificate from the certificate store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07bc-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d07bc-178">See Also</span></span>
