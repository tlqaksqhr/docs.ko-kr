---
title: "&lt;caches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;caches&gt;
세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<sessionSecurityTokenCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|세션 토큰 캐시 서비스나 컬렉션 보안 토큰 처리기를 등록합니다.|  
|[\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|토큰 재생 캐시 서비스나 컬렉션 보안 토큰 처리기를 등록합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## 설명  
 A `<caches>` 요소를 지정 하는 서비스 수준에서 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서 `<securityTokenHandlerConfiguration>` 요소입니다.  설정을 토큰 처리기 컬렉션에서 서비스에 지정 된 설정을 무시 합니다.  
  
 `<caches>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.  구성 된 캐시에서 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스.  
  
## 예제  
 다음 XML 구성에 사용자 지정 보안 토큰을 보유 하는 세션에 대 한 캐시를 보여 줍니다 \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  구성을 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```