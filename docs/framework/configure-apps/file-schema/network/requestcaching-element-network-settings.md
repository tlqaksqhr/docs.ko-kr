---
title: "&lt;requestCaching&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requestCaching> 요소"
  - "requestCaching 요소"
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;requestCaching&gt; 요소(네트워크 설정)
네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.  
  
## 구문  
  
```  
  
      <requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss""  
  <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
  <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`isPrivateCache`|캐시에서 사용별로 정보를 격리하는지 여부를 지정합니다.  기본값은 `true`입니다.  중간 계층 응용 프로그램에 대해서는 이 값이 `false`여야 합니다.|  
|`disableAllCaching`|모든 웹 응답에 대해 캐싱을 사용할 수 없도록 지정하며, 프로그래밍 방식으로 재정의될 수 없습니다.|  
|`defaultPolicyLevel`|<xref:System.Net.Cache.RequestCacheLevel> 열거형의 값 중 하나입니다.  기본값은 `BypassCache`입니다.|  
|`unspecifiedMaximumAge`|콘텐츠 만료 기준이 되는 기본 시간을 지정합니다.|  
  
## policyLevel 특성  
  
|값|설명|  
|-------|--------|  
|`Default`|리소스가 최신 상태이고, 콘텐츠 길이가 정확하고, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우에 캐시된 리소스를 반환합니다.|  
|`BypassCache`|서버에서 리소스를 반환합니다.|  
|`CacheOnly`|콘텐츠 길이가 있고 엔트리 크기와 일치하는 경우 캐시된 리소스를 반환합니다.|  
|`CacheIfAvailable`|콘텐츠 길이가 제공되었으며 항목 크기와 일치하면 캐시된 리소스를 반환하고, 그렇지 않으면 서버에서 리소스를 다운로드하여 호출자에게 반환합니다.|  
|`Revalidate`|캐시된 리소스의 타임스탬프가 서버에 있는 리소스의 타임스탬프와 같은 경우 캐시된 리소스를 반환하고, 그렇지 않으면 리소스가 서버에서 다운로드되어 캐시에 저장된 다음 호출자에 반환됩니다.|  
|`Reload`|서버에서 리소스를 다운로드하여 캐시에 저장한 다음 호출자에 반환합니다.|  
|`NoCacheNoStore`|캐시된 리소스가 있으면 해당 리소스를 삭제합니다.  서버에서 리소스를 다운로드하여 호출자에게 반환합니다.|  
|`Revalidate`|타임스탬프가 서버에 있는 리소스의 타임스탬프와 같은 경우 리소스의 캐시된 복사본을 사용하여 요청을 충족시키고, 그렇지 않을 경우 서버에서 리소스를 다운로드하여 호출자에 제공하고 캐시에 저장합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|선택적 요소입니다.<br /><br /> HTTP 캐싱이 활성화되어 있는지 여부를 나타내고 기본 캐싱 정책을 설명합니다.|  
|[\<defaultFtpCachePolicy\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|선택적 요소입니다.<br /><br /> FTP 캐싱이 활성화되어 있는지 여부를 나타내고 기본 캐싱 정책을 설명합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## 예제  
 다음 코드 예제에서는 모든 캐싱을 사용할 수 없도록 하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Cache?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)