---
title: "&lt;tokenReplayDetection&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;tokenReplayDetection&gt;
토큰 재생 검색을 사용 하 고 토큰에 대 한 만료 시간을 지정 합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 형식  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|토큰 재생 검색을 사용할지 여부를 지정 하는 값입니다. "true" 토큰을 사용 하도록 설정 하려면 재생 검색 합니다.|  
|expirationPeriod|A <xref:System.TimeSpan> 만료 되 고 캐시에서 제거 항목 간주 됩니다 전에 시간을 최대 크기를 지정 합니다.  지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하십시오. [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안에 대 한 토큰 처리기를 제공합니다.|  
  
## 설명  
 A `<tokenReplayDetection>` 요소를 지정 하는 서비스 수준에서 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서의 `<securityTokenHandlerConfiguration>` 요소.  설정을 토큰 처리기 컬렉션에서 서비스에 지정 된 설정을 무시 합니다.  
  
 토큰 재생 캐시 유형을 지정 되는 [\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 요소.