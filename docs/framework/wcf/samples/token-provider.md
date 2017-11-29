---
title: Token Provider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
caps.latest.revision: "22"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 87965b8802dd770d6977154ab805889838e9c5e4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="token-provider"></a><span data-ttu-id="c9971-102">Token Provider</span><span class="sxs-lookup"><span data-stu-id="c9971-102">Token Provider</span></span>
<span data-ttu-id="c9971-103">이 샘플에서는 사용자 지정 토큰 공급자를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-103">This sample demonstrates how to implement a custom token provider.</span></span> <span data-ttu-id="c9971-104">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 토큰 공급자는 보안 인프라에 자격 증명을 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-104">A token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="c9971-105">일반적으로 토큰 공급자는 대상을 검사하고 적절한 자격 증명을 발급하여 보안 인프라에서 메시지의 보안을 유지할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c9971-106">에서는 기본 자격 증명 관리자 토큰 공급자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-106"> ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="c9971-107">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 토큰 공급자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also ships with an [!INCLUDE[infocard](../../../../includes/infocard-md.md)] token provider.</span></span> <span data-ttu-id="c9971-108">사용자 지정 토큰 공급자는 다음과 같은 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-108">Custom token providers are useful in the following cases:</span></span>  
  
-   <span data-ttu-id="c9971-109">이러한 토큰 공급자가 작동되지 않는 자격 증명 저장소가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c9971-109">If you have a credential store that these token providers cannot operate with.</span></span>  
  
-   <span data-ttu-id="c9971-110">사용자가 세부 정보를 제공하는 지점에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 프레임워크에서 자격 증명을 사용하는 지점으로 자격 증명을 변환하는 사용자 지정 메커니즘을 제공하려는 경우</span><span class="sxs-lookup"><span data-stu-id="c9971-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client framework uses the credentials.</span></span>  
  
-   <span data-ttu-id="c9971-111">사용자 지정 토큰을 빌드하고 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c9971-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="c9971-112">이 샘플에서는 사용자의 입력을 다른 형식을 변환하는 사용자 지정 토큰 공급자를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-112">This sample shows how to build a custom token provider that transforms the input from the user into a different format.</span></span>  
  
 <span data-ttu-id="c9971-113">즉, 이 샘플에서는 다음 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-113">To summarize, this sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="c9971-114">클라이언트에서 사용자 이름/암호 쌍을 사용하여 인증하는 방법.</span><span class="sxs-lookup"><span data-stu-id="c9971-114">How a client can authenticate using a username/password pair.</span></span>  
  
-   <span data-ttu-id="c9971-115">사용자 지정 토큰 공급자로 클라이언트를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="c9971-115">How a client can be configured with a custom token provider.</span></span>  
  
-   <span data-ttu-id="c9971-116">사용자 이름과 암호가 일치하는지 확인하는 사용자 지정 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>와 함께 암호를 사용하여 서버에서 클라이언트 자격 증명의 유효성을 검사하는 방법</span><span class="sxs-lookup"><span data-stu-id="c9971-116">How the server can validate the client credentials using a password with a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> that validates that the username and password match.</span></span>  
  
-   <span data-ttu-id="c9971-117">서버의 X.509 인증서를 사용하여 클라이언트에서 서버를 인증하는 방법</span><span class="sxs-lookup"><span data-stu-id="c9971-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="c9971-118">또한 이 샘플에서는 사용자 지정 토큰 인증 프로세스 후에 호출자의 ID에 액세스할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-118">This sample also shows how the caller's identity is accessible after the custom token authentication process.</span></span>  
  
 <span data-ttu-id="c9971-119">서비스에서는 서비스와의 통신에 사용할 수 있는 단일 끝점을 노출하며, 이 끝점은 App.config 구성 파일을 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-119">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="c9971-120">끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-120">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="c9971-121">바인딩은 기본적으로 메시지 보안이 사용되는 표준 `wsHttpBinding`으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-121">The binding is configured with a standard `wsHttpBinding`, which uses message security by default.</span></span> <span data-ttu-id="c9971-122">이 샘플에서는 클라이언트 사용자 이름 인증을 사용하도록 표준 `wsHttpBinding`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-122">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="c9971-123">또한 서비스에서는 serviceCredentials 동작을 사용하여 서비스 인증서를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-123">The service also configures the service certificate using the serviceCredentials behavior.</span></span> <span data-ttu-id="c9971-124">serviceCredentials 동작을 사용하면 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-124">The serviceCredentials behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="c9971-125">서비스 인증서는 클라이언트에서 서비스를 인증하고 메시지 보호를 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-125">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="c9971-126">다음 구성에서는 뒤에 나오는 설치 지침에 설명된 대로 샘플 설치 중에 설치되는 localhost 인증서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-126">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <!-- configure base address provided by host -->  
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
    </services>  
  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="c9971-127">클라이언트 끝점 구성은 구성 이름, 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-127">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="c9971-128">클라이언트 바인딩에는 적절한 `Mode` 및 메시지 `clientCredentialType`이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-128">The client binding is configured with the appropriate `Mode` and message `clientCredentialType`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="http://localhost:8000/servicemodelsamples/service"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator">  
    </endpoint>  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c9971-129">다음 단계에서는 사용자 지정 토큰 공급자를 개발하고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프레임워크와 통합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-129">The following steps show how to develop a custom token provider and integrate it with the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework:</span></span>  
  
1.  <span data-ttu-id="c9971-130">사용자 지정 토큰 공급자를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-130">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="c9971-131">사용자 이름과 암호를 가져오는 사용자 지정 토큰 공급자가 샘플에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-131">The sample implements a custom token provider that obtains the username and password.</span></span> <span data-ttu-id="c9971-132">암호는 이 사용자 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-132">The password must match this username.</span></span> <span data-ttu-id="c9971-133">이 사용자 지정 토큰 공급자는 데모용으로만 제공된 것이므로 실제 배포에서는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-133">This custom token provider is for demonstration purposes only and is not recommended for real world deployment.</span></span>  
  
     <span data-ttu-id="c9971-134">이 작업을 수행하려면 사용자 지정 토큰 공급자가 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 클래스를 파생하고 <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-134">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="c9971-135">이 메서드는 새 `UserNameSecurityToken`을 만들고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-135">This method creates and returns a new `UserNameSecurityToken`.</span></span>  
  
    ```  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
        // obtain username and password from the user using console window  
        string username = GetUserName();  
        string password = GetPassword();  
        Console.WriteLine("username: {0}", username);  
  
        // return new UserNameSecurityToken containing information obtained from user  
        return new UserNameSecurityToken(username, password);  
    }  
    ```  
  
2.  <span data-ttu-id="c9971-136">사용자 지정 보안 토큰 관리자를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-136">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="c9971-137"><xref:System.IdentityModel.Selectors.SecurityTokenManager>는 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 메서드에서 전달되는 특정 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>에 대한 `CreateSecurityTokenProvider`를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-137">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="c9971-138">또한 보안 토큰 관리자는 토큰 인증자와 토큰 serializer를 만드는 데 사용되지만 이 샘플에서는 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-138">Security token manager is also used to create token authenticators and a token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="c9971-139">이 샘플에서 사용자 지정 보안 토큰 관리자는 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스에서 상속되며 `CreateSecurityTokenProvider` 메서드를 재정의하여 전달된 토큰 요구 사항에서 사용자 이름 공급자가 요청됨을 나타낼 때 사용자 지정 사용자 이름 토큰 공급자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-139">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return custom username token provider when the passed token requirements indicate that username provider is requested.</span></span>  
  
    ```  
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager  
    {  
        MyUserNameClientCredentials myUserNameClientCredentials;  
  
        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)  
            : base(myUserNameClientCredentials)  
        {  
            this.myUserNameClientCredentials = myUserNameClientCredentials;  
        }  
  
        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)  
        {  
            // if token requirement matches username token return custom username token provider  
            // otherwise use base implementation  
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)  
            {  
                return new MyUserNameTokenProvider();  
            }  
            else  
            {  
                return base.CreateSecurityTokenProvider(tokenRequirement);  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="c9971-140">사용자 지정 클라이언트 자격 증명을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-140">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="c9971-141">클라이언트 자격 증명 클래스는 클라이언트 프록시에 대해 구성된 자격 증명을 나타내는 데 사용되며 토큰 인증자, 토큰 공급자 및 토큰 serializer를 가져오는 데 사용되는 보안 토큰 관리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-141">Client credentials class is used to represent the credentials that are configured for the client proxy and creates security token manager that is used to obtain token authenticators, token providers and a token serializer.</span></span>  
  
    ```  
    public class MyUserNameClientCredentials : ClientCredentials  
    {  
        public MyUserNameClientCredentials()  
            : base()  
        {  
        }  
  
        protected override ClientCredentials CloneCore()  
        {  
            return new MyUserNameClientCredentials();  
        }  
  
        public override SecurityTokenManager CreateSecurityTokenManager()  
        {  
            // return custom security token manager  
            return new MyUserNameSecurityTokenManager(this);  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="c9971-142">사용자 지정 클라이언트 자격 증명을 사용하도록 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-142">Configure the client to use the custom client credential.</span></span>  
  
     <span data-ttu-id="c9971-143">클라이언트가 사용자 지정 클라이언트 자격 증명을 이용할 수 있도록 이 샘플에서는 기본 클라이언트 자격 증명 클래스를 삭제하고 새 클라이언트 자격 증명 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-143">In order for the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```  
    static void Main()  
    {  
        // ...  
           // Create a client with given client endpoint configuration  
          CalculatorClient client = new CalculatorClient();  
  
          // set new credentials  
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));  
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());  
       // ...  
    }  
    ```  
  
 <span data-ttu-id="c9971-144">서비스에서 호출자의 정보를 표시하려면 다음 코드 예제와 같이 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-144">On the service, to display the caller's information, use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code example.</span></span> <span data-ttu-id="c9971-145"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A>에는 현재 호출자에 대한 클레임 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-145">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tSecurity context identity  :  {0}",   
        ServiceSecurityContext.Current.PrimaryIdentity.Name);  
}  
```  
  
 <span data-ttu-id="c9971-146">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c9971-147">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-147">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="c9971-148">설치 배치 파일</span><span class="sxs-lookup"><span data-stu-id="c9971-148">Setup Batch File</span></span>  
 <span data-ttu-id="c9971-149">이 샘플에 포함된 Setup.bat 배치 파일을 사용하면 관련 인증서로 서버를 구성하여 서버 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-149">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="c9971-150">다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-150">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="c9971-151">다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-151">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>  
  
-   <span data-ttu-id="c9971-152">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c9971-152">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="c9971-153">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-153">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="c9971-154">`%SERVER_NAME%`변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-154">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="c9971-155">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-155">Change this variable to specify your own server name.</span></span> <span data-ttu-id="c9971-156">이 배치 파일의 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-156">The default value in this batch file is localhost.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="c9971-157">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치:</span><span class="sxs-lookup"><span data-stu-id="c9971-157">Installing the server certificate into the client's trusted certificate store:</span></span>  
  
     <span data-ttu-id="c9971-158">Setup.bat 배치 파일에서 다음 행은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-158">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c9971-159">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-159">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c9971-160">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-160">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="c9971-161">Setup.bat 배치 파일은 Windows SDK 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-161">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="c9971-162">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-162">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="c9971-163">이 환경 변수는 Windows SDK 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-163">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="c9971-164">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="c9971-164">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="c9971-165">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-165">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c9971-166">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-166">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c9971-167">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c9971-167">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="c9971-168">관리자 권한으로 연 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-168">Run Setup.bat from the sample installation folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt opened with administrator privileges.</span></span> <span data-ttu-id="c9971-169">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-169">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c9971-170">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-170">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="c9971-171">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-171">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="c9971-172">service\bin에서 service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-172">Launch service.exe from service\bin.</span></span>  
  
3.  <span data-ttu-id="c9971-173">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-173">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c9971-174">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-174">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="c9971-175">사용자 이름 프롬프트에서 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-175">At the username prompt, type a user name.</span></span>  
  
5.  <span data-ttu-id="c9971-176">암호 프롬프트에서 사용자 이름 프롬프트에 입력한 것과 동일한 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-176">At the password prompt, use the same string that was typed for the username prompt.</span></span>  
  
6.  <span data-ttu-id="c9971-177">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9971-177">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c9971-178">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c9971-178">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="c9971-179">서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-179">Create a directory on the service computer for the service binaries.</span></span>  
  
2.  <span data-ttu-id="c9971-180">서비스 프로그램 파일을 서비스 컴퓨터의 서비스 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-180">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="c9971-181">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-181">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="c9971-182">컴퓨터의 정규화된 도메인 이름을 포함하는 주체 이름을 가진 서버 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-182">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="c9971-183">이 새로운 인증서 이름을 반영하도록 Service.exe.config 파일을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-183">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="c9971-184">Setup.bat 배치 파일을 수정하여 서버 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-184">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="c9971-185">관리자 권한으로 연 Visual Studio 명령 프롬프트에서 Setup.bat 파일을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-185">Note that the setup.bat file must be run from a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="c9971-186">서비스를 호스팅하는 데 사용되는 컴퓨터의 정규화된 호스트 이름으로 `%SERVER_NAME%` 변수를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-186">You must set `%SERVER_NAME%` variable to fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4.  <span data-ttu-id="c9971-187">서버 인증서를 클라이언트의 CurrentUser-TrustedPeople 저장소에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-187">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="c9971-188">서버 인증서가 클라이언트의 신뢰할 수 있는 발급자에 의해 발급된 경우 이 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-188">You do not need to do this when the server certificate is issued by a client trusted issuer.</span></span>  
  
5.  <span data-ttu-id="c9971-189">서비스 컴퓨터의 Service.exe.config 파일에서 기본 주소 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-189">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="c9971-190">서비스 컴퓨터의 명령 프롬프트에서 service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-190">On the service computer, run service.exe from a command prompt.</span></span>  
  
7.  <span data-ttu-id="c9971-191">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-191">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8.  <span data-ttu-id="c9971-192">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-192">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="c9971-193">클라이언트 컴퓨터의 명령 프롬프트 창에서 `Client.exe`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-193">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="c9971-194">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9971-194">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c9971-195">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="c9971-195">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="c9971-196">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9971-196">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9971-197">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9971-197">See Also</span></span>
