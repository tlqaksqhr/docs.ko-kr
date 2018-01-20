---
title: "신뢰된 외관 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c0d1d0473a821510ee70e386058a2b3249221dd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="trusted-facade-service"></a><span data-ttu-id="81f41-102">신뢰된 외관 서비스</span><span class="sxs-lookup"><span data-stu-id="81f41-102">Trusted Facade Service</span></span>
<span data-ttu-id="81f41-103">이 시나리오 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 보안 인프라를 사용하여 한 서비스에서 다른 서비스로 호출자의 ID 정보를 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-103">This scenario sample demonstrates how to flow caller's identity information from one service to another using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security infrastructure.</span></span>  
  
 <span data-ttu-id="81f41-104">서비스에 의해 제공되는 기능을 외관 서비스를 사용하여 공용 네트워크에 노출하는 것은 일반적인 디자인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-104">It is a common design pattern to expose the functionality provided by a service to the public network using a façade service.</span></span> <span data-ttu-id="81f41-105">일반적으로 외관 서비스는 DMZ, 완충 지역 및 스크린된 서브넷이라고도 하는 경계 네트워크에 상주하며 비즈니스 논리를 구현하고 내부 데이터에 액세스할 수 있는 백 엔드 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-105">The façade service typically resides in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet) and communicates with a backend service that implements the business logic and has access to internal data.</span></span> <span data-ttu-id="81f41-106">외관 서비스와 백 엔드 서비스 간의 통신 채널은 방화벽을 통과하며 일반적으로 단일 용도로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-106">The communication channel between the façade service and the backend service goes through a firewall and is usually limited for a single purpose only.</span></span>  
  
 <span data-ttu-id="81f41-107">이 샘플은 다음 구성 요소로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-107">This sample consists of the following components:</span></span>  
  
-   <span data-ttu-id="81f41-108">계산기 클라이언트</span><span class="sxs-lookup"><span data-stu-id="81f41-108">Calculator client</span></span>  
  
-   <span data-ttu-id="81f41-109">계산기 외관 서비스</span><span class="sxs-lookup"><span data-stu-id="81f41-109">Calculator façade service</span></span>  
  
-   <span data-ttu-id="81f41-110">계산기 백 엔드 서비스</span><span class="sxs-lookup"><span data-stu-id="81f41-110">Calculator backend service</span></span>  
  
 <span data-ttu-id="81f41-111">외관 서비스는 요청의 유효성을 검사하고 호출자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-111">The façade service is responsible for validating the request and authenticating the caller.</span></span> <span data-ttu-id="81f41-112">인증과 유효성 검사에 성공하고 나면 주변 네트워크에서 내부 네트워크로의 제어된 통신 채널을 사용하여 백 엔드 서비스에 요청을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-112">After successful authentication and validation, it forwards the request to the backend service using the controlled communication channel from the perimeter network to the internal network.</span></span> <span data-ttu-id="81f41-113">외관 서비스는 호출자의 ID에 대한 정보를 전달된 요청의 일부로 포함하므로 백 엔드 서비스는 이 정보를 해당 처리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-113">As a part of the forwarded request, the façade service includes information about the caller's identity so that the backend service can use this information in its processing.</span></span> <span data-ttu-id="81f41-114">호출자의 ID는 메시지 `Username` 헤더 내의 `Security` 보안 토큰을 사용하여 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-114">The caller's identity is transmitted using a `Username` security token inside the message `Security` header.</span></span> <span data-ttu-id="81f41-115">이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라를 사용하여 `Security` 헤더에서 이 정보를 전송 및 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-115">The sample uses the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to transmit and extract this information from the `Security` header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81f41-116">백 엔드 서비스는 호출자를 인증하기 위해 외관 서비스를 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-116">The backend service trusts the façade service to authenticate the caller.</span></span> <span data-ttu-id="81f41-117">따라서 백 엔드 서비스는 호출자를 다시 인증하지 않으며 전달된 요청에서 외관 서비스에 의해 제공된 ID 정보를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-117">Because of this, the backend service does not authenticate the caller again; it uses the identity information provided by the façade service in the forwarded request.</span></span> <span data-ttu-id="81f41-118">이 신뢰 관계 때문에 백 엔드 서비스는 전달된 메시지가 신뢰할 수 있는 소스(이 경우에는 외관 서비스)에서 제공되는지 확인하기 위해 외관 서비스를 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-118">Because of this trust relationship, the backend service must authenticate the façade service to ensure that the forwarded message comes from a trusted source - in this case, the façade service.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="81f41-119">구현</span><span class="sxs-lookup"><span data-stu-id="81f41-119">Implementation</span></span>  
 <span data-ttu-id="81f41-120">이 샘플에는 두 개의 통신 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-120">There are two communication paths in this sample.</span></span> <span data-ttu-id="81f41-121">첫 번째는 클라이언트와 외관 서비스 간의 경로이고 두 번째는 외관 서비스와 백 엔드 서비스 간의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-121">First is between the client and the façade service, the second is between the façade service and the backend service.</span></span>  
  
### <a name="communication-path-between-client-and-faade-service"></a><span data-ttu-id="81f41-122">클라이언트와 외관 서비스 간의 통신 경로</span><span class="sxs-lookup"><span data-stu-id="81f41-122">Communication Path between Client and Façade Service</span></span>  
 <span data-ttu-id="81f41-123">클라이언트에서 외관 서비스로의 통신 경로에는 `wsHttpBinding` 클라이언트 자격 증명 유형을 가진 `UserName` 이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-123">The client to the façade service communication path uses `wsHttpBinding` with a `UserName` client credential type.</span></span> <span data-ttu-id="81f41-124">이는 클라이언트가 외관 서비스에 대해 인증하기 위해 사용자 이름과 암호를 사용하고 외관 서비스가 클라이언트에 대해 인증하기 위해 X.509 인증서를 사용한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-124">This means that the client uses username and password to authenticate to the façade service and the façade service uses X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="81f41-125">바인딩 구성은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-125">The binding configuration looks like the following example.</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="81f41-126">외관 서비스는 사용자 지정 `UserNamePasswordValidator` 구현을 사용하여 호출자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-126">The façade service authenticates the caller using custom `UserNamePasswordValidator` implementation.</span></span> <span data-ttu-id="81f41-127">여기서는 데모용이기 때문에 인증은 호출자의 사용자 이름이 제공된 암호와 일치하는지만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-127">For demonstration purposes, the authentication only ensures that the caller's username matches the presented password.</span></span> <span data-ttu-id="81f41-128">실제 상황에서는 Active Directory 또는 사용자 지정 ASP.NET 멤버 자격 공급자를 사용하여 사용자가 인증될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-128">In the real world situation, the user is probably authenticated using Active Directory or custom ASP.NET Membership provider.</span></span> <span data-ttu-id="81f41-129">유효성 검사기 구현은 `FacadeService.cs` 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-129">The validator implementation resides in `FacadeService.cs` file.</span></span>  
  
```  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="81f41-130">사용자 지정 유효성 검사기는 외관 서비스 구성 파일에서 `serviceCredentials` 동작 안에 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-130">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span> <span data-ttu-id="81f41-131">이 동작은 또한 서비스의 X.509 인증서를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-131">This behavior is also used to configure the service's X.509 certificate.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate   
               findValue="localhost"   
               storeLocation="LocalMachine"   
               storeName="My"   
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a><span data-ttu-id="81f41-132">외관 서비스와 백 엔드 서비스 간의 통신 경로</span><span class="sxs-lookup"><span data-stu-id="81f41-132">Communication Path between Façade Service and Backend Service</span></span>  
 <span data-ttu-id="81f41-133">외관 서비스에서 백 엔드 서비스로의 통신 경로는 여러 바인딩 요소로 구성된 `customBinding` 을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-133">The façade service to the backend service communication path uses a `customBinding` that consists of several binding elements.</span></span> <span data-ttu-id="81f41-134">이 바인딩은 두 가지 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-134">This binding accomplishes two things.</span></span> <span data-ttu-id="81f41-135">이 바인딩은 통신이 보안되었는지, 그리고 신뢰할 수 있는 소스에서 제공되는지 확인하기 위해 외관 서비스와 백 엔드 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-135">It authenticates the façade service and backend service to ensure that the communication is secure and is coming from a trusted source.</span></span> <span data-ttu-id="81f41-136">또한 `Username` 보안 토큰 내에서 초기 호출자의 ID를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-136">Additionally, it also transmits the initial caller's identity inside the `Username` security token.</span></span> <span data-ttu-id="81f41-137">이 경우 초기 호출자의 사용자 이름만 백 엔드 서비스에 전송되고 암호는 메시지에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-137">In this case, only the initial caller's username is transmitted to the backend service, the password is not included in the message.</span></span> <span data-ttu-id="81f41-138">이는 백 엔드 서비스가 요청을 전달하기 전에 호출자를 인증하기 위해 외관 서비스를 신뢰하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-138">This is because the backend service trusts the façade service to authenticate the caller before forwarding the request to it.</span></span> <span data-ttu-id="81f41-139">외관 서비스가 백 엔드 서비스에 대해 자체 인증하므로 백 엔드 서비스는 전달된 요청에 포함된 정보를 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-139">Because the façade service authenticates itself to the backend service, the backend service can trust the information contained in the forwarded request.</span></span>  
  
 <span data-ttu-id="81f41-140">이 통신 경로에 대한 바인딩 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-140">The following is the binding configuration for this communication path.</span></span>  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="81f41-141">[ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 바인딩 요소는 초기 호출자의 사용자 이름 전송과 추출을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-141">The [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) binding element takes care of the initial caller's username transmission and extraction.</span></span> <span data-ttu-id="81f41-142">[ \<windowsStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md) 및 [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 외관 및 백 엔드 서비스 인증을 처리 하 고 메시지 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-142">The [\<windowsStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md) and [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) take care of authenticating façade and backend services and message protection.</span></span>  
  
 <span data-ttu-id="81f41-143">요청을 전달하기 위해 외관 서비스 구현은 초기 호출자의 사용자 이름을 제공해야 하므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라에서 이 정보를 전달된 메시지에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-143">To forward the request, the façade service implementation must provide the initial caller's username so that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure can place this into the forwarded message.</span></span> <span data-ttu-id="81f41-144">외관 서비스가 백 엔드 서비스와 통신하기 위해 사용하는 클라이언트 프록시 인스턴스의 `ClientCredentials` 속성에서 초기 호출자의 사용자 이름을 설정함으로써 외관 서비스 구현에서 해당 사용자 이름이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-144">The initial caller's username is provided in the façade service implementation by setting it in the `ClientCredentials` property on the client proxy instance that façade service uses to communicate with the backend service.</span></span>  
  
 <span data-ttu-id="81f41-145">다음 코드에서는 `GetCallerIdentity` 메서드가 외관 서비스에서 구현되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-145">The following code shows how `GetCallerIdentity` method is implemented on the façade service.</span></span> <span data-ttu-id="81f41-146">다른 메서드에도 동일한 패턴이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-146">Other methods use the same pattern.</span></span>  
  
```  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 <span data-ttu-id="81f41-147">위 코드에서 볼 수 있듯이 `ClientCredentials` 속성에서는 암호가 설정되지 않고 사용자 이름만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-147">As shown in the previous code, the password is not set on the `ClientCredentials` property, only the username is set.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="81f41-148"> 보안 인프라는 암호 없이 사용자 이름 보안 토큰을 만드는 데 이 시나리오에서는 이와 같은 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-148"> security infrastructure creates a username security token without a password in this case, which is exactly what is required in this scenario.</span></span>  
  
 <span data-ttu-id="81f41-149">백 엔드 서비스에서는 사용자 이름 보안 토큰에 포함된 정보가 인증되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-149">On the backend service, the information contained in the username security token must be authenticated.</span></span> <span data-ttu-id="81f41-150">기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안에서는 제공된 암호를 사용하여 Windows 계정에 사용자를 매핑하는 것을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-150">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security attempts to map the user to a Windows account using the provided password.</span></span> <span data-ttu-id="81f41-151">이 경우에는 제공된 암호가 없으며 외관 서비스에 의해 인증이 이미 수행되었으므로 백 엔드 서비스는 사용자 이름을 인증할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-151">In this case, there is no password provided and the backend service is not required to authenticate the username because the authentication was already performed by the façade service.</span></span> <span data-ttu-id="81f41-152">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이 기능을 구현하기 위해 토큰에 사용자 이름을 지정하는 것만 강제하고 어떠한 추가 인증도 수행하지 않는 사용자 지정 `UserNamePasswordValidator` 가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-152">To implement this functionality in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], a custom `UserNamePasswordValidator` is provided that only enforces that a username is specified in the token and does not perform any additional authentication.</span></span>  
  
```  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,   
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the   
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new   
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="81f41-153">사용자 지정 유효성 검사기는 외관 서비스 구성 파일에서 `serviceCredentials` 동작 안에 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-153">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,   
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="81f41-154">신뢰할 수 있는 외관 서비스 계정에 대한 사용자 이름과 정보를 추출하기 위해 백 엔드 서비스 구현에서는 `ServiceSecurityContext` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-154">To extract the username information and information about the trusted façade service account, the backend service implementation uses the `ServiceSecurityContext` class.</span></span> <span data-ttu-id="81f41-155">다음 코드에서는 `GetCallerIdentity` 메서드를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-155">The following code shows how the `GetCallerIdentity` method is implemented.</span></span>  
  
```  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =   
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on   
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in   
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets   
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in   
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&   
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject   
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 <span data-ttu-id="81f41-156">외관 서비스 계정 정보는 `ServiceSecurityContext.Current.WindowsIdentity` 속성을 사용하여 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-156">The façade service account information is extracted using the `ServiceSecurityContext.Current.WindowsIdentity` property.</span></span> <span data-ttu-id="81f41-157">초기 호출자에 대한 정보에 액세스하기 위해 백 엔드 서비스는 `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-157">To access the information about the initial caller the backend service uses the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` property.</span></span> <span data-ttu-id="81f41-158">이 속성은 `Identity` 형식을 가진 `Name`클레임을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-158">It looks for an `Identity` claim with a type `Name`.</span></span> <span data-ttu-id="81f41-159">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 인프라는 `Username` 보안 토큰에 포함된 정보에서 이 클레임을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-159">This claim is automatically generated by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure from the information contained in the `Username` security token.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="81f41-160">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="81f41-160">Running the sample</span></span>  
 <span data-ttu-id="81f41-161">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="81f41-162">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-162">Press ENTER in the client window to shut down the client.</span></span> <span data-ttu-id="81f41-163">외관 및 백 엔드 서비스 콘솔 창에서 Enter 키를 눌러 서비스를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-163">You can press ENTER in the façade and backend service console windows to shut down the services.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="81f41-164">신뢰할 수 있는 외관 시나리오 샘플에 포함된 Setup.bat 배치 파일을 사용하면 클라이언트에 자체 인증하는 데 인증서 기반 보안이 필요한 외관 서비스를 실행하기 위해 관련 인증서로 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-164">The Setup.bat batch file included with the Trusted Facade scenario sample enables you to configure the server with a relevant certificate to run the façade service that requires certificate-based security to authenticate itself to the client.</span></span> <span data-ttu-id="81f41-165">자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f41-165">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="81f41-166">다음은 배치 파일의 여러 다른 섹션에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-166">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
-   <span data-ttu-id="81f41-167">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="81f41-167">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="81f41-168">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-168">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="81f41-169">`%SERVER_NAME%` 변수는 서버 이름을 지정합니다. 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-169">The `%SERVER_NAME%` variable specifies the server name - the default value is localhost.</span></span> <span data-ttu-id="81f41-170">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-170">The certificate is stored in the LocalMachine store.</span></span>  
  
-   <span data-ttu-id="81f41-171">클라이언트의 신뢰할 수 있는 인증서 저장소에 외관 서비스의 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="81f41-171">Installing the façade service's certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="81f41-172">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 외관 서비스의 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-172">The following line copies the façade service's certificate into the client trusted people store.</span></span> <span data-ttu-id="81f41-173">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-173">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="81f41-174">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-174">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="81f41-175">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="81f41-175">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="81f41-176">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-176">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="81f41-177">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-177">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="81f41-178">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="81f41-178">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="81f41-179">Makecert.exe가 있는 폴더가 경로에 포함되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-179">Ensure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2.  <span data-ttu-id="81f41-180">샘플 설치 폴더에서 Setup.bat를 실행하여</span><span class="sxs-lookup"><span data-stu-id="81f41-180">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="81f41-181">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-181">This installs all the certificates required for running the sample.</span></span>  
  
3.  <span data-ttu-id="81f41-182">\BackendService\bin 디렉터리에서 BackendService.exe를 별도의 콘솔 창에 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-182">Launch the BackendService.exe from \BackendService\bin directory in a separate console window</span></span>  
  
4.  <span data-ttu-id="81f41-183">\FacadeService\bin 디렉터리에서 FacadeService.exe를 별도의 콘솔 창에 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-183">Launch the FacadeService.exe from \FacadeService\bin directory in a separate console window</span></span>  
  
5.  <span data-ttu-id="81f41-184">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-184">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="81f41-185">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-185">Client activity is displayed on the client console application.</span></span>  
  
6.  <span data-ttu-id="81f41-186">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-186">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="81f41-187">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="81f41-187">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="81f41-188">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-188">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81f41-189">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-189">The samples may already be installed on your machine.</span></span> <span data-ttu-id="81f41-190">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="81f41-190">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="81f41-191">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="81f41-191">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="81f41-192">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f41-192">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`  
  
## <a name="see-also"></a><span data-ttu-id="81f41-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81f41-193">See Also</span></span>
