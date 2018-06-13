---
title: '&lt;추가&gt; 요소에 대 한 &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743825"
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;추가&gt; 요소에 대 한 &lt;namedCaches&gt;
추가 `namedCache` 항목에는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches >  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>형식  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|-|-|  
|`CacheMemoryLimitMegabytes`|최대 허용 크기를 메가바이트 단위로 지정 하는 정수 값 하의 인스턴스는 <xref:System.Runtime.Caching.MemoryCache> 증가할 수 있습니다. 기본값은 0으로, 즉는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 추론 기본적으로 사용 됩니다.|  
|`Name`|캐시의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 실제로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다. 기본값은 0으로, 즉는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 추론 기본적으로 사용 됩니다.|  
|`PollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 이 값은 "hh: mm:" 형식으로 입력 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `add` 에 항목을 추가 하는 요소는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다. 사용할 수는 [지우기](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) 요소를 사용 하기 전에 `add` 요소를 분명히 다른 수의 명명 된 캐시는 컬렉션입니다. 이 요소는 Web.config 파일 및 machine.config 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본값에 대 한 설정을 정의 하는 방법을 보여 줍니다. `namedCache` 항목을는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [\<namedCaches > 요소 (캐시 설정)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
