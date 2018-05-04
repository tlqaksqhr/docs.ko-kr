---
title: '&lt;UseSmallInternalThreadStacks&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a11b9a008878e716e9b3d8cd54abe5eb4169672a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt; 요소
요청을 공용 언어 런타임 (CLR) 메모리를 줄이지 이러한 스레드에 대 한 기본 스택 크기를 사용 하는 대신 내부적으로 사용 하는 특정 스레드를 만들 때에 명시적 스택 크기를 지정 하 여 사용 합니다.  
  
 \<구성 > 요소  
\<런타임 > 요소  
\<UseSmallInternalThreadStacks > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|필수 특성입니다.<br /><br /> 지정 하는 요청 기본 스택 크기 대신 CLR 사용 하 여 명시적 스택 크기 내부적으로 사용 하 여 특정 스레드를 만들 때 합니다. 명시적 스택 크기는 1MB의 기본 스택 크기 보다 작습니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|true|명시적 스택 크기를 요청 합니다.|  
|False|기본 스택 크기를 사용 합니다. 에 대 한 기본값은 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 기본 크기 보다 작으므로 요청 인식 되 면 CLR에 대 한 해당 내부 스레드를 사용 하는 명시적 스레드 크기 때문에 프로세스에서 사용 하 여 감소 된 가상 메모리를 요청 하려면이 구성 요소 사용 됩니다.  
  
> [!IMPORTANT]
>  이 구성 요소에는 절대적인 요구 사항이 보다는 CLR에 대 한 요청입니다. 에 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], x86에 대해서만 요청이 수행 됩니다 아키텍처. 이 요소는 CLR의 이후 버전에서는 완전히 무시 또는 항상 선택한 내부 스레드 사용 되는 명시적 스택 크기도 대체 될 수 있습니다.  
  
 이 구성 요소 거래 작은 가상 메모리 사용에 대 한 안정성 CLR 요청을 인식 하는 경우 스택 크기가 작은 스택 만들 수 있으므로 지정 오버플로가 발생할 가능성이 더 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 CLR 사용 하 여 명시적 스택 크기가 특정 내부적으로 사용 하는 스레드를 요청 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
