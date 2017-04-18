---
title: "&lt;namedCaches&gt;에 대한 &lt;add&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<namedCaches>에 대한 <add> 요소"
  - "<namedCaches>에 대한 add 요소"
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;namedCaches&gt;에 대한 &lt;add&gt; 요소
메모리 캐시를 위해 `namedCache` 항목을 `namedCaches` 컬렉션에 추가합니다.  
  
## 구문  
  
```  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## 형식  
 `None`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|||  
|-|-|  
|특성|설명|  
|`CacheMemoryLimitMegabytes`|<xref:System.Runtime.Caching.MemoryCache>의 인스턴스가 커질 수 있는 최대 허용되는 크기\(메가바이트 단위\)를 지정하는 정수 값입니다.  기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 경험적 접근을 기본적으로 사용함을 의미합니다.|  
|`Name`|캐시의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에 의해 사용될 수 있는 실제로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다.  기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 경험적 접근을 기본적으로 사용함을 의미합니다.|  
|`PollingInterval`|캐시 구현이 캐시 인스턴스에 설정된 메모리 제한\(절대값 및 백분율\)을 기준으로 현재 메모리 로드를 비교하는 시간 간격을 나타내는 값입니다.  "HH:MM:SS" 형식으로 이 값을 입력합니다.|  
  
### 자식 요소  
 `None`  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스의 구성 설정 컬렉션을 포함합니다.|  
  
## 설명  
 `add` 요소는 메모리 캐시에 대한 `namedCaches` 컬렉션에 항목을 추가합니다.  `add` 요소를 사용하기 전에 [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) 요소를 사용하여 컬렉션에 다른 명명된 캐시가 없는지 확인할 수 있습니다.  이 요소는 machine.config 파일과 Web.config 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 메모리 캐시의 `namedCaches`  컬렉션에 대해 기본 `namedCache` 항목의 설정을 정의하는 방법을 보여줍니다.  
  
```  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## 참고 항목  
 [\<namedCaches\> 요소\(캐시 설정\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)