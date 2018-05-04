---
title: '&lt;gcConcurrent&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee00c3a307523d2cae831274630ad6828cd9daf6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcConcurrent&gt; 요소
공용 언어 런타임이 별도 스레드에서 가비지 컬렉션을 실행하는지 여부를 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<gcConcurrent >  
  
## <a name="syntax"></a>구문  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 동시에 가비지 수집을 실행하는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|동시에 가비지 컬렉션을 실행하지 않습니다.|  
|`true`|동시에 가비지 컬렉션을 실행합니다. 이 값이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 4 이전에는 워크스테이션 가비지 컬렉션이 별도 스레드에서 백그라운드로 가비지 컬렉션을 수행한 동시 가비지 컬렉션을 지원했습니다. .NET Framework 4에서는 동시 가비지 수집이 역시 별도 스레드에서 백그라운드로 가비지 수집을 수행하는 백그라운드 GC로 대체되었습니다. .NET Framework 4.5부터 백그라운드 수집을 서버 가비지 수집에서 사용할 수 있게 되었습니다. `<gcConcurrent>` 요소는 런타임이 사용 가능한 경우 동시 또는 백그라운드 가비지 수집을 수행하는지 여부 또는 포그라운드에서 가비지 수집을 수행하는지 여부를 제어합니다.  
  
> [!WARNING]
>  .NET Framework 4부터 동시 가비지 컬렉션이 백그라운드 가비지 컬렉션으로 대체되었습니다. 용어 *동시* 및 *배경* .NET Framework 설명서에서 같은 의미로 사용 됩니다. 백그라운드 가비지 수집을 사용하지 않으려면, 이 문서에 설명된 대로 `<gcConcurrent>` 요소를 사용합니다.  
  
 기본적으로 런타임은 대기 시간에 최적화된 동시 또는 백그라운드 가비지 수집을 사용합니다. 사용자 상호 작용이 많이 필요한 응용 프로그램인 경우에는 가비지 수집을 수행할 때 응용 프로그램의 일시 중지를 최소화하도록 동시 가비지 수집 기능을 사용하는 것이 좋습니다. `enabled` 요소의 `<gcConcurrent>` 특성을 `false`에 설정할 경우 런타임은 효율성이 최적화된 비동시성 가비지 수집을 사용합니다. 다음 구성 파일에서는 백그라운드 가비지 수집을 사용하지 않도록 설정합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 컴퓨터 구성 파일에 `<gcConcurrentSetting>` 설정이 있는 경우 모든 .NET Framework 응용 프로그램에 대한 기본값을 정의합니다. 컴퓨터 구성 파일 설정은 응용 프로그램 구성 파일 설정을 재정의합니다.  
  
 자세한 동시에 대 한 정보 및 백그라운드 가비지 수집의 "동시 가비지 수집" 섹션을 참조는 [가비지 수집 기본 사항](../../../../../docs/standard/garbage-collection/fundamentals.md) 항목입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 동시 가비지 컬렉션을 사용하도록 설정합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [가비지 수집 기본 사항](../../../../../docs/standard/garbage-collection/fundamentals.md)
