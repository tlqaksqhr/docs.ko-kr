---
title: "&lt;NetFx40_PInvokeStackResilience&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b17816ee6134dc6b3074256093c0cba07419baf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a>&lt;NetFx40_PInvokeStackResilience&gt; 요소
런타임이 잘못된 플랫폼 호출 선언을 실행 시간에 자동으로 수정할지를 지정합니다. 자동 수정을 수행하는 경우 관리 코드와 비관리 코드 간 전환 속도가 느려집니다.  
  
 \<configuration>  
\<런타임 >  
< NetFx40_PInvokeStackResilience >  
  
## <a name="syntax"></a>구문  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 잘못 된 플랫폼 감지 하는지 여부를 지정 합니다. 호출 선언 및 32 비트 플랫폼에서 런타임 시 스택의 자동으로 해결 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`0`|런타임에서 사용 하는 빠른 interop 마샬링에 도입 된 아키텍처는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 감지 하지 못한 및 수정 프로그램 잘못 된 플랫폼 호출 선언 합니다. 이 값이 기본값입니다.|  
|`1`|검색 하 여 잘못 된 플랫폼을 수정 하는 런타임 사용 하 여 느린 전환 호출 선언 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 사용 하면 빠른 interop 마샬링을 실행 시 복원 기능 잘못 된 플랫폼 호출 선언에 대 한 수 있습니다.  
  
 부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 합리적인된 interop 마샬링 아키텍처는 관리 코드에서 비관리 코드로 전환에 대 한 성능이 크게 향상을 제공 합니다. .NET Framework의 이전 버전에서 마샬링 계층 검색 잘못 된 플랫폼 32 비트 플랫폼에서 선언 호출과 스택을 자동으로 해결 합니다. 마샬링 새로운 아키텍처는이 단계를 제거 합니다. 결과적으로, 전이 매우 빠르게 있지만 잘못 된 플랫폼 호출 선언 프로그램 오류를 발생 시킬 수 있습니다.  
  
 쉽게 개발 하는 동안 잘못 된 선언 검색 Visual Studio 디버깅 환경을 향상 되었습니다. [및](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) 관리 디버깅 도우미 (MDA) 디버거가 연결 된 응용 프로그램을 실행 하는 경우 하면 잘못 된 플랫폼 호출 선언에 알립니다.  
  
 응용 프로그램 구성 요소를 다시 컴파일할 수 및 사용할 수 있는 잘못 된 플랫폼 호출 선언를 사용 하는 경우 주소 시나리오에는 `NetFx40_PInvokeStackResilience` 요소입니다. 이 요소와 응용 프로그램 구성 파일에 추가 `enabled="1"` 이전 버전의.NET Framework 느린 전환 비용의 동작과 호환 모드로 opts 합니다. 이전 버전의.NET Framework에 대해 컴파일된 어셈블리는 자동으로이 호환성 모드를 선택 하며 및이 요소가 필요 하지 않습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 잘못 된 복원 기능 향상된을 선택 하도록 플랫폼 호출 사이의 느린 전환 비용 응용 프로그램에 대 한 선언 관리 및 비관리 코드 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
