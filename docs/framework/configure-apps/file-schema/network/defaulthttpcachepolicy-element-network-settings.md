---
title: "&lt;defaultHttpCachePolicy&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultHttpCachePolicy> 요소"
  - "defaultHttpCachePolicy 요소"
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;defaultHttpCachePolicy&gt; 요소(네트워크 설정)
HTTP 캐싱이 활성화되어 있는지 여부를 나타내고 기본 캐싱 정책을 설명합니다.  
  
## 구문  
  
```  
< defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss"|"minValue"  
  maximumAge  ="d.hh:mm:ss"|"maxValue"  
  maximumStale="d.hh:mm:ss"|"maxValue"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`maximumAge`|캐시된 개체가 만료된 것으로 표시되기 전까지 허용되는 최대 시간을 지정합니다.|  
|`maximumStale`|계산된 새로 고침 시간 이후 캐시된 개체가 만료된 것으로 표시되기 전까지 허용되는 최대 시간을 지정합니다.|  
|`minimumFresh`|캐시된 개체가 최신 개체로 간주되는 최소 시간을 지정합니다.|  
|`policyLevel`|캐싱 정책이 자동인지 여부 또는 캐시가 무시될지 여부를 지정합니다.  기본값은 `BypassCache`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.|  
  
## 설명  
 `policyLevel` 특성 값은 `BypassCache` 또는 `Default`입니다.  
  
 `maximumAge`, `maximumStale`, 및 `minimumFresh` 요소의 값은 경우에 따라 *d*.*hh*.*mm*:*ss*\(일, 시, 분, 및 초\) 형식의 명시적 시간 간격이거나 상수 `minValue` 또는 `maxValue` 입니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 6시간의 최소 새로 고침 시간, 2일의 최대 사용 기간 및 4시간의 최대 비사용 시간을 지정하는 방법을 설명합니다.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy>  
        <set minimumFresh="0.06:00:00" />  
        <set maximumAge  ="2.00:00:00" />  
        <set maximumStale="0.04:00:00" />  
      </defaultHttpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)