---
title: "&lt;defaultFtpCachePolicy&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultFtpCachePolicy> 요소"
  - "defaultFtpCachePolicy 요소"
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;defaultFtpCachePolicy&gt; 요소(네트워크 설정)
FTP 캐싱이 활성화되어 있는지 여부를 나타내고 기본 캐싱 정책을 설명합니다.  
  
## 구문  
  
```  
< defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`policyLevel`|FTP 캐싱 정책을 지정합니다.  기본값은 `Default`입니다.|  
  
## policyLevel 특성  
  
|값|설명|  
|-------|--------|  
|`Default`|리소스가 최신 상태이고, 콘텐츠 길이가 정확하고, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우에 캐시된 리소스를 반환합니다.|  
|`BypassCache`|서버에서 리소스를 반환합니다.|  
|`CacheOnly`|콘텐츠 길이가 있고 엔트리 크기와 일치하는 경우 캐시된 리소스를 반환합니다.|  
|`CacheIfAvailable`|콘텐츠 길이가 제공되었으며 항목 크기와 일치하면 캐시된 리소스를 반환하고, 그렇지 않으면 서버에서 리소스를 다운로드하여 호출자에게 반환합니다.|  
|`Revalidate`|캐시된 리소스의 타임스탬프가 서버에 있는 리소스의 타임스탬프와 동일하면 캐시된 리소스를 반환하고, 그렇지 않으면 서버에서 리소스가 다운로드되어 캐시에 저장된 다음 호출자로 반환됩니다.|  
|`Reload`|서버에서 리소스를 다운로드하여 캐시에 저장한 다음 호출자에 반환합니다.|  
|`NoCacheNoStore`|캐시된 리소스가 있으면 해당 리소스를 삭제합니다.  서버에서 리소스를 다운로드하여 호출자에게 반환합니다.|  
|`Revalidate`|캐시된 리소스 복사본의 타임스탬프가 서버에 있는 리소스의 타임스탬프와 동일하면 캐시된 리소스 복사본을 사용하여 요청을 만족시키고, 그렇지 않으면 서버에서 리소스를 다운로드하여 호출자에게 제공한 다음 캐시에 저장합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.|  
  
## 설명  
  
## 예제  
 다음 코드 예제에서는 FTP 캐싱 정책 `NoCacheNoStore`를 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        Level="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)