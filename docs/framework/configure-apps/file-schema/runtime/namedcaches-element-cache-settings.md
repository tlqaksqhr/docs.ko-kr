---
title: "&lt;namedCaches&gt; 요소(캐시 설정) | Microsoft Docs"
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
  - "<namedCaches> 요소"
  - "캐시[.NET Framework], 구성"
  - "namedCaches 요소"
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;namedCaches&gt; 요소(캐시 설정)
명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스의 구성 설정 컬렉션을 지정합니다.  <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 속성은 구성 파일의 하나 이상의 `namedCaches` 요소에서 구성 설정의 컬렉션을 참조합니다.  
  
## 구문  
  
```  
<namedCaches>  
  <add name="default"   
</namedCaches>  
```  
  
## 형식  
 `None`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`CacheMemoryLimitMegabytes`|<xref:System.Runtime.Caching.MemoryCache>의 인스턴스가 커질 수 있는 최대 허용 가능한 크기\(메가바이트 단위\)를 지정하는 정수 값입니다.  기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 경험적 접근을 기본적으로 사용함을 의미합니다.|  
|`Name`|캐시의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에 의해 사용될 수 있는 실제로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다.  기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 경험적 접근을 기본적으로 사용함을 의미합니다.|  
|`PollingInterval`|캐시 구현이 캐시 인스턴스에 설정된 메모리 제한\(절대값 및 백분율\)을 기준으로 현재 메모리 로드를 비교하는 시간 간격을 나타내는 값입니다.  "HH:MM:SS" 형식으로 이 값을 입력합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<추가\>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|메모리 캐시를 위해 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|메모리 캐시에 대한 `namedCaches` 컬렉션을 지웁니다.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|메모리 캐시를 위해 `namedCaches` 컬렉션에서 명명된 캐시 항목을 제거합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<xref:System.Runtime.Caching.MemoryCache> 클래스를 기준으로 하는 캐시를 구성하는 데 사용되는 요소를 정의합니다.|  
  
## 설명  
 Web.config 파일의 메모리 캐시 구성 섹션은 `namedCaches` 컬렉션에 대한 `add`, `remove` 및 `clear` 특성을 포함할 수 있습니다.  각 `namedCaches` 항목은 `name` 특성에 의해 고유하게 식별됩니다.  
  
 응용 프로그램 구성 파일의 정보를 참조하여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다.  기본적으로 기본 캐시 인스턴스에만 구성 파일에 항목이 있습니다.  기본 캐시 인스턴스는 <xref:System.Runtime.Caching.MemoryCache.Default%2A> 속성에서 반환된 인스턴스입니다.  
  
 이름 특성을 "기본값"으로 설정하는 경우 요소는 기본 메모리 캐시 인스턴스를 사용합니다.  
  
## 예제  
 다음 예제에서는 `name` 특성을 "기본값"으로 설정하여 캐시의 이름을 기본 캐시 항목 이름으로 설정하는 방법을 보여줍니다.  
  
 `cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.  이 특성을 0으로 설정하면 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 경험적 접근을 사용하는 것을 의미합니다.  캐시 구현은 현재 메모리 로드를 절대 및 백분율 기반 메모리 제한과 2분마다 비교합니다.  
  
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
 [\<memoryCache\> 요소\(캐시 설정\)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)