---
title: "&lt;sessionSecurityTokenCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;sessionSecurityTokenCache&gt;
세션 토큰 캐시 서비스나 컬렉션 보안 토큰 처리기를 등록합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|형식에서 파생 되는 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 클래스입니다.  사용자 지정 하는 방법에 대 한 자세한 내용은 `type`를 참조 하십시오 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|보안 토큰 처리기 컬렉션 또는 서비스를 사용 하는 캐시를 등록 합니다.|  
  
## 예제  
 다음 XML 구성에 사용자 지정 보안 토큰을 보유 하는 세션에 대 한 캐시를 보여 줍니다 \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  구성을 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.  이 샘플에 대 한 자세한 내용은 [WIF 코드 샘플 인덱스](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>