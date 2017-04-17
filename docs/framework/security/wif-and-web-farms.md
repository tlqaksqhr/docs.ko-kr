---
title: "WIF 및 웹 팜 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WIF 및 웹 팜
Windows Identity 파운데이션 \(싸 우 자\)를 사용 하는 웹 팜에 배포 되는 신뢰 당사자 \(RP\) 응용 프로그램의 리소스를 보호 하는 경우 싸 우 자 토큰 인스턴스로부터 팜에 다른 컴퓨터에서 실행 중인 RP 응용 프로그램을 처리할 수 있도록 하는 특정 단계를 수행 해야 합니다.  암호화 세션 토큰 서명 확인이 처리를 포함 한 세션 토큰을 해독, 세션 토큰을 캐싱 및 검색 보안 토큰을 재생 합니다.  
  
 RP\-웹 팜 또는 단일 컴퓨터에서 실행 되는지 여부 싸 우 자 – RP 응용 프로그램의 리소스 보호를 사용할 때 일반적인 경우에는 클라이언트가 보안 토큰 서비스 \(STS\)에서 얻은 보안 토큰 기반 세션 설정 됩니다.  클라이언트가 STS 싸 우 자 사용 하 여 보호 되는 모든 응용 프로그램 리소스에 대해 인증 하는 데 피할 것입니다.  싸 우 자 세션을 처리 하는 방법에 대 한 자세한 내용은 [WIF 세션 관리](../../../docs/framework/security/wif-session-management.md).  
  
 싸 우 자 기본 설정을 사용 하는 경우 다음을 수행 합니다.  
  
-   인스턴스를 사용 하는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스는 세션 토큰을 읽고 \(의 인스턴스는 <xref:System.IdentityModel.Tokens.SessionSecurityToken> 클래스\) 클레임 및 인증에 사용 된 보안 토큰에 대 한 다른 정보 뿐만 아니라 해당 세션에 대 한 정보 전달.  세션 토큰 패키징되며 세션 쿠키에 저장 합니다.  기본적으로 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 를 사용 하는 <xref:System.IdentityModel.ProtectedDataCookieTransform> 클래스는 DPAPI \(데이터 보호 API\)를 사용 하 여 세션 토큰을 보호 합니다.  DPAPI는 사용자 또는 컴퓨터 자격 증명을 사용 하 여 보호 기능을 제공 및 키 데이터를 사용자 프로필에 저장 합니다.  
  
-   기본적으로 메모리의 구현을 사용 하는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 저장 하 고 세션 토큰을 처리 하는 클래스입니다.  
  
 단일 컴퓨터에서 RP 응용 프로그램 배포 시나리오에서 이러한 기본 설정을 작동 합니다. 그러나의 웹 팜에 배포 되 면 각 HTTP 요청 수 수 주고 RP 응용 프로그램이 다른 컴퓨터에서 실행 중인 다른 인스턴스를 처리 합니다.  토큰 보호 및 토큰 캐싱을 특정 컴퓨터에 종속 되어 있기 때문에이 시나리오에서 위에서 설명한 기본 싸 우 자 설정을 작동 하지 않습니다.  
  
 웹 팜의 RP 응용 프로그램을 배포 하려면 처리 세션 토큰 \(물론 재생된 토큰\)는 특정 컴퓨터에서 실행 되는 응용 프로그램에 종속 되지 않았는지 확인 해야 합니다.  이렇게 하는 한 가지 방법은 ASP가 제공 하는 기능을 사용 하 여 RP 응용 프로그램을 구현 하는 것.NET `<machineKey>` 구성 요소 및 세션 토큰을 처리 하는 분산 캐싱을 제공 하 고 토큰을 재생 합니다.  `<machineKey>` 요소 유효성 검사, 암호화 및 토큰 웹 팜의 여러 컴퓨터에서 동일한 키를 지정할 수 있게 하는 구성 파일의 암호를 해독 하는 데 필요한 키를 지정할 수 있습니다.  싸 우 자는 전문된 세션 토큰 처리기를 제공 합니다.는 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>는 보호 토큰에 지정 된 키를 사용 하 여 해당 `<machineKey>` 요소.  이 전략을 구현 하려면 다음이 지침을 따르십시오.  
  
-   ASP를 사용 하십시오.NET `<machineKey>` 팜의 컴퓨터에서 사용할 수 있는 서명 및 암호화 키를 명시적으로 지정 하는 구성에서 요소입니다.  다음 XML 사양을 보여 줍니다.의 `<machineKey>` 요소는 `<system.web>` 구성 파일 요소를에서.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   사용 하는 응용 프로그램 구성의 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> 토큰 처리기 컬렉션에 추가 하 여.  먼저 제거 해야는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> \(또는 파생 된 모든 처리기는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스\) 처리기가 없으면 토큰 처리기 컬렉션에서.  <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> 를 사용 하는 <xref:System.IdentityModel.Services.MachineKeyTransform> 암호화 지정 된 재료를 사용 하 여 세션 쿠키 데이터를 보호 하는 클래스는 `<machineKey>` 요소.  다음 XML을 추가 하는 방법을 보여 줍니다 있는 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> 토큰 처리기 컬렉션입니다.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   파생 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 및 구현 분산 캐시 RP 있습니다 실행 팜의 모든 컴퓨터에서 액세스할 수 있는, 즉, 캐싱.  RP를 지정 하 여 분산된 캐시를 사용 하도록 구성의 [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 구성 파일의 요소입니다.  재정의할 수는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=fullName> 의 자식 요소를 구현 하 여 파생된 클래스의 메서드는 `<sessionSecurityTokenCache>` 필요한 경우 요소.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     분산 캐싱을 구현 하는 한 가지 방법은 캐시에 대 한 사용자 지정 WCF 프런트 엔드를 제공 하는 것입니다.  캐싱 서비스는 WCF 구현에 대 한 자세한 내용은 참조 하십시오. [캐싱은 WCF 서비스](#BKMK_TheWCFCachingService).  RP 응용 프로그램 캐싱 서비스를 호출 하는 데 사용할 수 있는 WCF 클라이언트를 구현 하는 방법에 대 한 자세한 내용은 [WCF 클라이언트의 캐싱](#BKMK_TheWCFClient).  
  
-   응용 프로그램이 재생 된 토큰을 발견 하면 이와 비슷한 분산 재생을 토큰 캐시에 대 한 전략에서 파생 하 여 캐싱을 수행 해야 <xref:System.IdentityModel.Tokens.TokenReplayCache> 및 재생에서 캐싱 서비스 사용자의 토큰을 가리키는 있는 [\<tokenReplayCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 구성 요소.  
  
> [!IMPORTANT]
>  모든 XML 예제와이 항목의 코드에서 결정 됩니다 있는 [ClaimsAwareWebFarm](란?LinkID%20=%20248408) \(란?LinkID \= 248408\) 샘플.  
  
> [!IMPORTANT]
>  이 항목의 예제로 제공 됩니다\-이며 프로덕션 코드를 수정 하지 않고 사용할 수는 없습니다.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## 캐싱은 WCF 서비스  
 다음 인터페이스 간의 캐싱 WCF 서비스와 WCF 클라이언트 신뢰 타사 응용 프로그램에 의해 사용 되는 통신을 계약을 정의 합니다.  기본적으로 메서드를 노출의 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스로 서비스 작업입니다.  
  
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
  
 다음 코드 캐싱 서비스의 WCF 구현을 보여 줍니다.  이 예제에서는 기본 구현 싸 우 자 여 메모리에 세션 토큰 캐시가 사용 됩니다.  또는, 영속적으로 데이터베이스 백업 캐시를 구현할 수 있습니다.  `ISessionSecurityTokenCacheService`위에 표시 되는 인터페이스를 정의 합니다.  이 예제에서는 인터페이스를 구현 하는 데 필요한 방법 중 일부만 잠시 표시 됩니다.  
  
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
## WCF 클라이언트의 캐싱  
 이 섹션에서 파생 되는 클래스의 구현을 보여 줍니다. <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 및 캐싱 서비스에는 대리자를 호출 합니다.  이 클래스를 사용 하 여 RP 응용 프로그램 구성의 [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 다음 XML와 같이 요소  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 클래스 재정의 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> 서비스 끝점에서 사용자 지정 메서드 `<cacheServiceAddress>` 의 자식 요소는 `<sessionSecurityTokenCache>` 요소입니다.  이 끝점을 사용 하 여 초기화 하는 `ISessionSecurityTokenCacheService` life 있습니다 통신 서비스와 채널.  이 예제에서는 모든 메서드 필요한 구현 하는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스를 간단히 표시 됩니다.  
  
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
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>   
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>   
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>   
 [WIF 세션 관리](../../../docs/framework/security/wif-session-management.md)