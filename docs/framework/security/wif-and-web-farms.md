---
title: "WIF 및 웹 팜"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 93c3e4251943afa383002043d9259184be82d929
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wif-and-web-farms"></a><span data-ttu-id="c0df4-102">WIF 및 웹 팜</span><span class="sxs-lookup"><span data-stu-id="c0df4-102">WIF and Web Farms</span></span>
<span data-ttu-id="c0df4-103">WIF(Windows Identity Foundation)를 사용하여 웹 팜에 배포된 RP(신뢰 당사자) 응용 프로그램의 리소스를 보호하는 경우 특정 단계를 수행하여 WIF가 팜의 여러 컴퓨터에서 실행되는 RP 응용 프로그램 인스턴스의 토큰을 처리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-103">When you use Windows Identity Foundation (WIF) to secure the resources of a relying party (RP) application that is deployed in a web farm, you must take specific steps to ensure that WIF can process tokens from instances of the RP application running on different computers in the farm.</span></span> <span data-ttu-id="c0df4-104">이 처리에는 세션 토큰 시그니처의 유효성 검사, 세션 토큰 암호화 및 암호 해독, 세션 토큰 캐싱 및 재생된 보안 토큰 검색이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-104">This processing includes validating session token signatures, encrypting and decrypting session tokens, caching session tokens, and detecting replayed security tokens.</span></span>  
  
 <span data-ttu-id="c0df4-105">일반적인 경우 WIF가 RP 응용 프로그램의 리소스를 보호하는 데 사용되는 경우 RP가 단일 컴퓨터 또는 웹 팜에서 실행되는지에 관계없이 STS(보안 토큰 서비스)에서 가져온 보안 토큰에 따라 클라이언트와 세션이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-105">In the typical case, when WIF is used to secure resources of an RP application – whether the RP is running on a single computer or in a web farm -- a session is established with the client based on the security token that was obtained from the security token service (STS).</span></span> <span data-ttu-id="c0df4-106">이렇게 하면 클라이언트가 WIF를 사용하여 보호되는 모든 응용 프로그램 리소스에 대해 STS에서 인증하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-106">This is to avoid forcing the client to have to authenticate at the STS for every application resource that is secured using WIF.</span></span> <span data-ttu-id="c0df4-107">WIF의 세션 처리 방법에 대한 자세한 내용은 [WIF 세션 관리](../../../docs/framework/security/wif-session-management.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0df4-107">For more information about how WIF handles sessions, see [WIF Session Management](../../../docs/framework/security/wif-session-management.md).</span></span>  
  
 <span data-ttu-id="c0df4-108">기본 설정이 사용되는 경우 WIF는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-108">When default settings are used, WIF does the following:</span></span>  
  
-   <span data-ttu-id="c0df4-109"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스 인스턴스를 사용하여 인증에 사용된 보안 토큰에 대한 클레임 및 기타 정보와 세션 자체에 대한 정보를 전달하는 세션 토큰(<xref:System.IdentityModel.Tokens.SessionSecurityToken> 클래스 인스턴스)을 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-109">It uses an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class to read and write a session token (an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityToken> class) that carries the claims and other information about the security token that was used for authentication as well as information about the session itself.</span></span> <span data-ttu-id="c0df4-110">세션 토큰은 세션 쿠키에 패키징되어 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-110">The session token is packaged and stored in a session cookie.</span></span> <span data-ttu-id="c0df4-111"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>에서는 기본적으로 DPAPI(데이터 보호 API)를 사용하는 <xref:System.IdentityModel.ProtectedDataCookieTransform> 클래스를 통해 세션 토큰을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-111">By default, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> uses the <xref:System.IdentityModel.ProtectedDataCookieTransform> class, which uses the Data Protection API (DPAPI), to protect the session token.</span></span> <span data-ttu-id="c0df4-112">DPAPI는 사용자 또는 컴퓨터 자격 증명을 사용하여 보호를 제공하고 사용자 프로필에 키 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-112">The DPAPI provides protection by using the user or machine credentials and stores the key data in the user profile.</span></span>  
  
-   <span data-ttu-id="c0df4-113"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스의 메모리 내 기본 구현을 사용하여 세션 토큰을 저장하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-113">It uses a default, in-memory implementation of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class to store and process the session token.</span></span>  
  
 <span data-ttu-id="c0df4-114">RP 응용 프로그램이 단일 컴퓨터에 배포되는 시나리오에서는 이러한 기본 설정이 작동하지만 웹 팜에 배포된 경우 각 HTTP 요청이 컴퓨터마다 실행되는 다른 RP 응용 프로그램 인스턴스에 전송되고 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-114">These default settings work in scenarios in which the RP application is deployed on a single computer; however, when deployed in a web farm, each HTTP request may be sent to and processed by a different instance of the RP application running on a different computer.</span></span> <span data-ttu-id="c0df4-115">이 시나리오에서 위에 설명한 기본 WIF 설정은 토큰 보호 및 토큰 캐싱이 둘 다 특정 컴퓨터에 종속되어 있으므로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-115">In this scenario, the default WIF settings described above will not work because both token protection and token caching are dependent on a specific computer.</span></span>  
  
 <span data-ttu-id="c0df4-116">웹 팜에 RP 응용 프로그램을 배포하려면 세션 토큰(및 재생된 토큰)의 처리가 특정 컴퓨터에서 실행되는 응용 프로그램에 종속되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-116">To deploy an RP application in a web farm, you must ensure that the processing of session tokens (as well as of replayed tokens) is not dependent on the application running on a specific computer.</span></span> <span data-ttu-id="c0df4-117">이 작업을 수행하는 한 가지 방법은 ASP.NET `<machineKey>` 구성 요소에서 제공하는 기능을 사용하고 세션 토큰 및 재생된 토큰 처리를 위한 분산 캐싱을 제공하도록 RP 응용 프로그램을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-117">One way to do this is to implement your RP application so that it uses the functionality provided by the ASP.NET `<machineKey>` configuration element and provides distributed caching for processing session tokens and replayed tokens.</span></span> <span data-ttu-id="c0df4-118">`<machineKey>` 요소를 사용하면 구성 파일에 토큰의 유효성 검사, 암호화, 암호 해독에 필요한 키를 지정할 수 있습니다. 웹 팜에 있는 여러 다른 컴퓨터에 동일한 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-118">The `<machineKey>` element allows you to specify the keys needed to validate, encrypt, and decrypt tokens in a configuration file, which enables you to specify the same keys on different computers in the web farm.</span></span> <span data-ttu-id="c0df4-119">WIF는 `<machineKey>` 요소에 지정된 키를 사용하여 토큰을 보호하는 특수 세션 토큰 처리기 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-119">WIF provides a specialized session token handler, the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, that protects tokens by using the keys specified in the `<machineKey>` element.</span></span> <span data-ttu-id="c0df4-120">이 전략을 구현하려면 다음 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c0df4-120">To implement this strategy, you can follow these guidelines:</span></span>  
  
-   <span data-ttu-id="c0df4-121">ASP.NET `<machineKey>` 요소를 구성에 사용하여 팜의 전체 컴퓨터에서 사용할 수 있는 서명 및 암호화 키를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-121">Use the ASP.NET `<machineKey>` element in configuration to explicitly specify signing and encryption keys that can be used across computers in the farm.</span></span> <span data-ttu-id="c0df4-122">다음 XML은 구성 파일의 `<system.web>` 요소 아래에 있는 `<machineKey>` 요소의 사양을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-122">The following XML shows the specification of the `<machineKey>` element under the `<system.web>` element in a configuration file.</span></span>  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   <span data-ttu-id="c0df4-123">토큰 처리기 컬렉션에 추가하여 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>를 사용하도록 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-123">Configure the application to use the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> by adding it to the token handler collection.</span></span> <span data-ttu-id="c0df4-124"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>(또는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스에서 파생된 임의 처리기)가 있는 경우 먼저 토큰 처리기 컬렉션에서 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-124">You must first remove the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (or any handler derived from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class) from the token handler collection if such a handler is present.</span></span> <span data-ttu-id="c0df4-125"><xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>는 `<machineKey>` 요소에 지정된 암호화 자료를 사용하여 세션 쿠키 데이터를 보호하는 <xref:System.IdentityModel.Services.MachineKeyTransform> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-125">The <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> uses the <xref:System.IdentityModel.Services.MachineKeyTransform> class, which protects the session cookie data by using the cryptographic material specified in the `<machineKey>` element.</span></span> <span data-ttu-id="c0df4-126">다음 XML에서는 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>를 토큰 처리기 컬렉션에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-126">The following XML shows how to add the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> to a token handler collection.</span></span>  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   <span data-ttu-id="c0df4-127"><xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>에서 파생하고 분산 캐싱, 즉 RP를 실행할 수 있는 팜의 모든 컴퓨터에서 액세스할 수 있는 캐시를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-127">Derive from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and implement distributed caching, that is, a cache that is accessible from all computers in the farm on which the RP might run.</span></span> <span data-ttu-id="c0df4-128">구성 파일에 [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 요소를 지정하여 분산 캐시를 사용하도록 RP를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-128">Configure the RP to use your distributed cache by specifying the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element in the configuration file.</span></span> <span data-ttu-id="c0df4-129">파생 클래스의 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> 메서드를 재정의하여 필요한 경우 `<sessionSecurityTokenCache>` 요소의 자식 요소를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-129">You can override the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> method in your derived class to implement child elements of the `<sessionSecurityTokenCache>` element if they are required.</span></span>  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     <span data-ttu-id="c0df4-130">분산 캐싱을 구현하는 한 가지 방법은 사용자 지정 캐시에 대한 WCF 프런트 엔드를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-130">One way to implement distributed caching is to provide a WCF front end for your custom cache.</span></span> <span data-ttu-id="c0df4-131">WCF 캐싱 서비스를 구현하는 방법에 대한 자세한 내용은 [WCF 캐싱 서비스](#BKMK_TheWCFCachingService)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0df4-131">For more information about implementing a WCF caching service, see [The WCF Caching Service](#BKMK_TheWCFCachingService).</span></span> <span data-ttu-id="c0df4-132">RP 응용 프로그램이 캐싱 서비스 호출에 사용할 수 있는 WCF 클라이언트를 구현하는 방법에 대한 자세한 내용은 [WCF 캐싱 클라이언트](#BKMK_TheWCFClient)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0df4-132">For more information about implementing a WCF client that the RP application can use to call the caching service, see [The WCF Caching Client](#BKMK_TheWCFClient).</span></span>  
  
-   <span data-ttu-id="c0df4-133">응용 프로그램이 재생된 토큰을 검색하는 경우 <xref:System.IdentityModel.Tokens.TokenReplayCache>에서 파생하고 [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 구성 요소의 토큰 재생 캐싱 서비스를 가리켜 토큰 재생 캐시에 대한 유사한 분산 캐싱 전략을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-133">If your application detects replayed tokens you must follow a similar distributed caching strategy for the token replay cache by deriving from <xref:System.IdentityModel.Tokens.TokenReplayCache> and pointing to your token replay caching service in the [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) configuration element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0df4-134">이 항목의 모든 예제 XML 및 코드는 [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408)(http://go.microsoft.com/fwlink/?LinkID=248408) 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-134">All of the example XML and code in this topic is taken from the [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) (http://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0df4-135">이 항목의 예제는 현재 상태대로 제공되며 수정 없이 프로덕션 코드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-135">The examples in this topic are provided as-is and are not intended to be used in production code without modification.</span></span>  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a><span data-ttu-id="c0df4-136">WCF 캐싱 서비스</span><span class="sxs-lookup"><span data-stu-id="c0df4-136">The WCF Caching Service</span></span>  
 <span data-ttu-id="c0df4-137">다음 인터페이스는 WCF 캐싱 서비스와 신뢰 당사자 응용 프로그램이 통신에 사용하는 WCF 클라이언트 간의 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-137">The following interface defines the contract between the WCF caching service and the WCF client used by the relying party application to communicate with it.</span></span> <span data-ttu-id="c0df4-138">기본적으로 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스의 메서드를 서비스 작업으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-138">It essentially exposes the methods of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class as service operations.</span></span>  
  
```  
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 <span data-ttu-id="c0df4-139">다음 코드에서는 WCF 캐싱 서비스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-139">The following code shows the implementation of the WCF caching service.</span></span> <span data-ttu-id="c0df4-140">이 예제에서는 WIF에 의해 구현되는 메모리 내 기본 세션 토큰 캐시가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-140">In this example, the default, in-memory session token cache implemented by WIF is used.</span></span> <span data-ttu-id="c0df4-141">또는 데이터베이스에서 지원하는 영구 캐시를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-141">Alternatively, you could implement a durable cache backed by a database.</span></span> <span data-ttu-id="c0df4-142">`ISessionSecurityTokenCacheService`에서는 위에 표시된 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-142">`ISessionSecurityTokenCacheService` defines the interface shown above.</span></span> <span data-ttu-id="c0df4-143">이 예제에서 인터페이스를 구현하는 데 필요한 일부 메서드는 간단한 설명을 위해 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-143">In this example, not all of the methods required to implement the interface are shown for brevity.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## <a name="the-wcf-caching-client"></a><span data-ttu-id="c0df4-144">WCF 캐싱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0df4-144">The WCF Caching Client</span></span>  
 <span data-ttu-id="c0df4-145">이 섹션에서는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>에서 파생되는 클래스의 구현과 캐싱 서비스에 대한 대리자 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-145">This section shows the implementation of a class that derives from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and that delegates calls to the caching service.</span></span> <span data-ttu-id="c0df4-146">다음 XML과 같이 [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 요소를 통해 이 클래스를 사용하도록 RP 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-146">You configure the RP application to use this class through the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element as in the following XML</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 <span data-ttu-id="c0df4-147">이 클래스는 `<sessionSecurityTokenCache>` 요소의 사용자 지정 `<cacheServiceAddress>` 자식 요소에서 서비스 끝점을 가져오도록 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-147">The class overrides the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> method to get the service endpoint from the custom `<cacheServiceAddress>` child element of the `<sessionSecurityTokenCache>` element.</span></span> <span data-ttu-id="c0df4-148">이 끝점을 사용하여 서비스와 통신할 수 있는 `ISessionSecurityTokenCacheService` 채널을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-148">It uses this endpoint to initialize an `ISessionSecurityTokenCacheService` channel over which it can communicate with the service.</span></span>  <span data-ttu-id="c0df4-149">이 예제에서 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스를 구현하는 데 필요한 일부 메서드는 간단한 설명을 위해 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0df4-149">In this example, not all of the methods required to implement the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class are shown for brevity.</span></span>  
  
```  
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0df4-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0df4-150">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>  
 [<span data-ttu-id="c0df4-151">WIF 세션 관리</span><span class="sxs-lookup"><span data-stu-id="c0df4-151">WIF Session Management</span></span>](../../../docs/framework/security/wif-session-management.md)
