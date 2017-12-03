---
title: "권한 부여 정책"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
caps.latest.revision: "38"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d46be95be90901e51713bc20cd2898e3db069802
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="authorization-policy"></a><span data-ttu-id="e6686-102">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="e6686-102">Authorization Policy</span></span>
<span data-ttu-id="e6686-103">이 샘플에서는 사용자 지정 클레임 권한 부여 정책 및 연관된 사용자 지정 서비스 인증 관리자를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="e6686-104">이 방법은 서비스에서 서비스 작업에 대해 클레임 기반 액세스 검사를 수행하는 경우에 유용하며 액세스 검사 전에 호출자에게 특정 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="e6686-105">이 샘플에서는 클레임을 추가하는 프로세스와 종료된 클레임 집합에 대해 액세스 검사를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="e6686-106">클라이언트와 서버 간의 모든 응용 프로그램 메시지는 서명 및 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="e6686-107">기본적으로 `wsHttpBinding` 바인딩에서는 클라이언트에서 제공하는 사용자 이름과 암호를 사용하여 유효한 Windows NT 계정에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="e6686-108">이 샘플에서는 사용자 지정을 활용 하는 방법을 보여 줍니다. <!--zz <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>--> `System.IdentityModel.Selectors.UsernamePasswordValidator` 클라이언트를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-108">This sample demonstrates how to utilize a custom <!--zz <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>--> `System.IdentityModel.Selectors.UsernamePasswordValidator` to authenticate the client.</span></span> <span data-ttu-id="e6686-109">이 샘플에서는 그 외에도 X.509 인증서를 사용하여 서비스에 대해 클라이언트를 인증하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="e6686-110">이 샘플에서는 서로의 사이에서 특정 사용자에 대해 서비스의 특정 메서드에 대한 액세스 권한을 부여하는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 및 <xref:System.ServiceModel.ServiceAuthorizationManager> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="e6686-111">이 샘플에 따라는 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md), 없지만 이전에 클레임 변환을 수행 하는 방법을 보여 줍니다.는 <xref:System.ServiceModel.ServiceAuthorizationManager> 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6686-112">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e6686-113">즉, 이 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-113">In summary, this sample demonstrates how:</span></span>  
  
-   <span data-ttu-id="e6686-114">사용자 이름 및 암호를 사용하여 클라이언트를 인증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="e6686-114">The client can be authenticated using a user name-password.</span></span>  
  
-   <span data-ttu-id="e6686-115">X.509 인증서를 사용하여 클라이언트를 인증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="e6686-115">The client can be authenticated using an X.509 certificate.</span></span>  
  
-   <span data-ttu-id="e6686-116">서버에서 사용자 지정 `UsernamePassword` 유효성 검사기를 기준으로 클라이언트의 유효성을 검증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="e6686-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>  
  
-   <span data-ttu-id="e6686-117">서버의 X.509 인증서를 사용하여 서버를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="e6686-117">The server is authenticated using the server's X.509 certificate.</span></span>  
  
-   <span data-ttu-id="e6686-118">서버에서 <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 서비스에 있는 특정 메서드에 대한 액세스를 제어하는 방법.</span><span class="sxs-lookup"><span data-stu-id="e6686-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>  
  
-   <span data-ttu-id="e6686-119"><xref:System.IdentityModel.Policy.IAuthorizationPolicy>를 구현하는 방법.</span><span class="sxs-lookup"><span data-stu-id="e6686-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
 <span data-ttu-id="e6686-120">서비스는 App.config 구성 파일을 사용하여 정의된, 서비스와의 통신에 사용되는 두 개의 끝점을 노출합니다. 각 끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="e6686-121">한 바인딩은 WS-Security 및 클라이언트 사용자 이름 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="e6686-122">다른 바인딩은 WS-Security 및 클라이언트 인증서 인증을 사용하는 표준 `wsHttpBinding` 바인딩으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="e6686-123">[ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 서비스 인증에 사용할 사용자 자격 증명이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="e6686-124">서버 인증서에 대 한 동일한 값이 있어야 합니다.는 `SubjectName` 속성으로는 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <!-- configure base address provided by host -->  
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>  
        </baseAddresses>  
      </host>  
      <!-- use base address provided by host, provide two endpoints -->  
      <endpoint address="username"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      <endpoint address="certificate"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding2"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
    <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
      <!-- X509 certificate binding -->  
      <binding name="Binding2">  
        <security mode="Message">  
          <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior" >  
        <serviceDebug includeExceptionDetailInFaults ="true" />  
        <serviceCredentials>  
          <!--   
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
          -->  
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
          <!--   
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.  
          -->  
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
          <!--   
          The serviceCredentials behavior allows one to define a service certificate.  
          A service certificate is used by a client to authenticate the service and provide message protection.  
          This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
          <!--   
          The serviceAuthorization behavior allows one to specify custom authorization policies.  
          -->  
          <authorizationPolicies>  
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e6686-125">각 클라이언트 끝점 구성은 구성 이름, 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="e6686-126">클라이언트 바인딩은에서 구성 되어 지정 된 대로 적절 한 보안 모드가 경우에 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) 및 `clientCredentialType` 에 지정 된 대로 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e6686-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- Username based endpoint -->  
      <endpoint name="Username"  
            address="http://localhost:8001/servicemodelsamples/service/username"   
    binding="wsHttpBinding"   
    bindingConfiguration="Binding1"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator" >  
      </endpoint>  
      <!-- X509 certificate based endpoint -->  
      <endpoint name="Certificate"  
                        address="http://localhost:8001/servicemodelsamples/service/certificate"   
                binding="wsHttpBinding"   
            bindingConfiguration="Binding2"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
        <!-- X509 certificate binding -->  
        <binding name="Binding2">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
    </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <behavior name="ClientCertificateBehavior">  
        <clientCredentials>  
          <serviceCertificate>  
            <!--   
            Setting the certificateValidationMode to PeerOrChainTrust  
            means that if the certificate   
            is in the user's Trusted People store, then it will be   
            trusted without performing a  
            validation of the certificate's issuer chain. This setting   
            is used here for convenience so that the   
            sample can be run without having to have certificates   
            issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust.   
            The security implications of this   
            setting should be carefully considered before using   
            PeerOrChainTrust in production code.   
            -->  
            <authentication certificateValidationMode = "PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="e6686-127">사용자 이름 기반 끝점의 경우 클라이언트 구현에서 사용할 사용자 이름 및 암호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>  
  
```  
// Create a client with Username endpoint configuration  
CalculatorClient client1 = new CalculatorClient("Username");  
  
client1.ClientCredentials.UserName.UserName = "test1";  
client1.ClientCredentials.UserName.Password = "1tset";  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client1.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client1.Close();  
```  
  
 <span data-ttu-id="e6686-128">인증서 기반 끝점의 경우 클라이언트 구현에서 사용할 클라이언트 인증서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>  
  
```  
// Create a client with Certificate endpoint configuration  
CalculatorClient client2 = new CalculatorClient("Certificate");  
  
client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client2.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client2.Close();  
```  
  
 <span data-ttu-id="e6686-129">이 샘플에서는 사용자 지정 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 사용하여 사용자 이름 및 암호의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="e6686-130">이 샘플에서는 `MyCustomUserNamePasswordValidator`에서 파생된 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="e6686-131">자세한 내용은 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6686-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="e6686-132"><xref:System.IdentityModel.Selectors.UserNamePasswordValidator>와의 통합을 보여 주기 위해 이 사용자 지정 유효성 검사기 샘플에서는 다음 코드에 표시된 것과 같이 사용자 이름과 암호가 일치되는 사용자 이름/암호 쌍을 받도록 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>  
  
```  
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator  
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
      throw new SecurityTokenException("Unknown Username or Password");  
    }  
  }  
}  
```  
  
 <span data-ttu-id="e6686-133">서비스 코드에 유효성 검사기를 구현하고 나면 사용할 유효성 검사기 인스턴스에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="e6686-134">이것은 다음 코드를 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-134">This is done using the following code.</span></span>  
  
```  
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();  
```  
  
 <span data-ttu-id="e6686-135">또는 구성에서도 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-135">Or you can do the same thing in configuration.</span></span>  
  
```xml  
<behavior ...>  
    <serviceCredentials>  
      <!--   
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
      -->  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
    ...  
    </serviceCredentials>  
</behavior>  
```  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="e6686-136">에서는 액세스 검사 수행에 사용할 수 있는 풍부한 클레임 기반 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-136"> provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="e6686-137"><xref:System.ServiceModel.ServiceAuthorizationManager> 개체는 액세스 검사를 수행하는 데 사용되며 클라이언트에 연결된 클레임이 서비스 메서드에 액세스하는 데 필요한 요구 사항을 충족시키는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>  
  
 <span data-ttu-id="e6686-138">이 샘플에서는 데모용으로 <xref:System.ServiceModel.ServiceAuthorizationManager> 메서드를 구현하여 호출이 허용되는 작업의 동작 URI가 값으로 지정된 http://example.com/claims/allowedoperation 형식의 클레임을 기반으로 사용자의 메서드에 대한 액세스를 허용하는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type http://example.com/claims/allowedoperation whose value is the Action URI of the operation that is allowed to be called.</span></span>  
  
```  
public class MyServiceAuthorizationManager : ServiceAuthorizationManager  
{  
  protected override bool CheckAccessCore(OperationContext operationContext)  
  {                  
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;  
    Console.WriteLine("action: {0}", action);  
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)  
    {  
      if ( cs.Issuer == ClaimSet.System )  
      {  
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))  
        {  
          Console.WriteLine("resource: {0}", c.Resource.ToString());  
          if (action == c.Resource.ToString())  
            return true;  
        }  
      }  
    }  
    return false;                   
  }  
}  
```  
  
 <span data-ttu-id="e6686-139">사용자 지정 <xref:System.ServiceModel.ServiceAuthorizationManager>가 구현되면 사용할 <xref:System.ServiceModel.ServiceAuthorizationManager>에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="e6686-140">이 작업은 다음 코드에 표시된 것과 같이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-140">This is done as shown in the following code.</span></span>  
  
```xml  
<behavior ...>  
    ...  
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
        ...  
    </serviceAuthorization>  
</behavior>  
```  
  
 <span data-ttu-id="e6686-141">구현할 중요한 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 메서드는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>  
  
```  
public class MyAuthorizationPolicy : IAuthorizationPolicy  
{  
    string id;  
  
    public MyAuthorizationPolicy()  
    {  
    id =  Guid.NewGuid().ToString();  
    }  
  
    public bool Evaluate(EvaluationContext evaluationContext,   
                                            ref object state)  
    {  
        bool bRet = false;  
        CustomAuthState customstate = null;  
  
        if (state == null)  
        {  
            customstate = new CustomAuthState();  
            state = customstate;  
        }  
        else  
            customstate = (CustomAuthState)state;  
        Console.WriteLine("In Evaluate");  
        if (!customstate.ClaimsAdded)  
        {  
           IList<Claim> claims = new List<Claim>();  
  
           foreach (ClaimSet cs in evaluationContext.ClaimSets)  
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,   
                                         Rights.PossessProperty))  
                  foreach (string s in   
                        GetAllowedOpList(c.Resource.ToString()))  
                  {  
                       claims.Add(new  
               Claim("http://example.com/claims/allowedoperation",   
                                    s, Rights.PossessProperty));  
                            Console.WriteLine("Claim added {0}", s);  
                      }  
                   evaluationContext.AddClaimSet(this,   
                           new DefaultClaimSet(this.Issuer,claims));  
                   customstate.ClaimsAdded = true;  
                   bRet = true;  
                }  
         else  
         {  
              bRet = true;  
         }  
         return bRet;  
     }  
...  
}  
```  
  
 <span data-ttu-id="e6686-142">이전 코드에서는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드가 처리에 영향을 주는 새 클레임이 추가되지 않았는지 확인하고 특정 클레임을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="e6686-143">허용되는 클레임은 사용자가 수행할 수 있는 작업의 특정 목록을 반환하도록 구현된 `GetAllowedOpList` 메서드를 통해 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="e6686-144">권한 부여 정책에서는 특정 작업에 액세스하기 위한 클레임을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="e6686-145">이 값은 나중에 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 액세스 확인 여부를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>  
  
 <span data-ttu-id="e6686-146">사용자 지정 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>가 구현되면 사용할 권한 부여 정책에 대한 정보를 서비스 호스트에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>  
  
```xml  
<serviceAuthorization ...>  
       <authorizationPolicies>   
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />  
       </authorizationPolicies>   
</serviceAuthorization>  
```  
  
 <span data-ttu-id="e6686-147">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e6686-148">클라이언트에서는 Add, Subtract 및 Multiple 메서드를 성공적으로 호출하며 Divide 메서드를 호출하려 하면 "액세스가 거부되었습니다." 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="e6686-149">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-149">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="e6686-150">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="e6686-150">Setup Batch File</span></span>  
 <span data-ttu-id="e6686-151">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>  
  
 <span data-ttu-id="e6686-152">다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>  
  
-   <span data-ttu-id="e6686-153">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="e6686-153">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="e6686-154">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="e6686-155">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="e6686-156">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="e6686-157">기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-157">The default value is localhost.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="e6686-158">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="e6686-158">Installing the server certificate into client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="e6686-159">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e6686-160">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e6686-161">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="e6686-162">클라이언트 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="e6686-162">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="e6686-163">Setup.bat 배치 파일에서 다음 줄은 사용할 클라이언트 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="e6686-164">%USER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="e6686-165">이 값은 `IAuthorizationPolicy`에서 찾는 이름이기 때문에 "test1"으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="e6686-166">%USER_NAME% 값을 변경하는 경우 `IAuthorizationPolicy.Evaluate` 메서드에서 해당 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>  
  
     <span data-ttu-id="e6686-167">인증서는 CurrentUser 저장소 위치에 있는 My (Personal) 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="e6686-168">서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="e6686-168">Installing the client certificate into server's trusted certificate store.</span></span>  
  
     <span data-ttu-id="e6686-169">Setup.bat 배치 파일에서 다음 줄은 신뢰할 수 있는 사용자 저장소로 클라이언트 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="e6686-170">이 단계는 Makecert.exe에서 생성한 인증서를 서버 시스템에서 암시적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="e6686-171">Microsoft에서 발급한 인증서와 같이 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 서버 인증서 저장소를 클라이언트 인증서로 채우는 이 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="e6686-172">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="e6686-172">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="e6686-173">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="e6686-174">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6686-175">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="e6686-176">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e6686-176">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="e6686-177">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트 창을 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-177">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="e6686-178">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-178">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e6686-179">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-179">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="e6686-180">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-180">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="e6686-181">관리자 권한으로 연 Visual Studio 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-181">Run Setup.bat in a Visual Studio command prompt opened with administrator privileges from the sample install folder.</span></span> <span data-ttu-id="e6686-182">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-182">This installs all the certificates required for running the sample.</span></span>  
  
3.  <span data-ttu-id="e6686-183">service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-183">Launch Service.exe from service\bin.</span></span>  
  
4.  <span data-ttu-id="e6686-184">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-184">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="e6686-185">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-185">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="e6686-186">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6686-186">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e6686-187">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e6686-187">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="e6686-188">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-188">Create a directory on the service computer.</span></span>  
  
2.  <span data-ttu-id="e6686-189">서비스 프로그램 파일을 \service\bin에서 서비스 컴퓨터에 있는 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-189">Copy the service program files from \service\bin to the directory on the service computer.</span></span> <span data-ttu-id="e6686-190">Setup.bat, Cleanup.bat, GetComputerName.vbs 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-190">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="e6686-191">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-191">Create a directory on the client computerfor the client binaries.</span></span>  
  
4.  <span data-ttu-id="e6686-192">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-192">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="e6686-193">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-193">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="e6686-194">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-194">On the server, run `setup.bat service` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="e6686-195">실행 `setup.bat` 와 `service` 인수 서비스 인증서를 만듭니다 computerand 내보내기의 정규화 된 도메인 이름 서비스 인증서를 Service.cer 이라는 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-195">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computerand exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="e6686-196">새 인증서 이름을 반영 하도록 Service.exe.config 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-196">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="e6686-197">컴퓨터 이름을 변경할 수도 \<서비스 > /\<baseAddresses > localhost에서 서비스 컴퓨터의 정규화 된 이름으로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-197">Also change the computername in the \<service>/\<baseAddresses> element from localhost to the fully-qualified name of your service computer.</span></span>  
  
7.  <span data-ttu-id="e6686-198">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-198">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="e6686-199">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat client`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-199">On the client, run `setup.bat client` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="e6686-200">실행 `setup.bat` 와 `client` 인수 test1 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-200">Running `setup.bat` with the `client` argument creates a client certificate named test1 and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="e6686-201">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-201">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="e6686-202">이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-202">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="e6686-203">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-203">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="e6686-204">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-204">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="e6686-205">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-205">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="e6686-206">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-206">On the server, run ImportClientCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="e6686-207">이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-207">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="e6686-208">서버 컴퓨터의 명령 프롬프트 창에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-208">On the server computer, launch Service.exe from the command prompt window.</span></span>  
  
14. <span data-ttu-id="e6686-209">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-209">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="e6686-210">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6686-210">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e6686-211">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="e6686-211">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="e6686-212">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="e6686-213">그러면 인증서 저장소에서 서버 및 클라이언트 인증서가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-213">This removes the server and client certificates from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6686-214">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-214">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="e6686-215">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6686-215">If you have run [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="e6686-216">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="e6686-216">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6686-217">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6686-217">See Also</span></span>
