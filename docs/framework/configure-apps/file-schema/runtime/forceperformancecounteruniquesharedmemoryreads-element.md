---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 602359b713adfd4adf90d3e18f5f434d50c92ef4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a>&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소
PerfCounter.dll이 .NET Framework 버전 1.1 응용 프로그램에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.  
  
 \<configuration>  
\<런타임 >  
\<forcePerformanceCounterUniqueSharedMemoryReads >  
  
## <a name="syntax"></a>구문  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 범주별 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할 것인지 결정 PerfCounter.dll CategoryOptions 레지스트리 설정을 사용 하는지 여부를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|PerfCounter.dll는 CategoryOptions 사용 하지 않는 레지스트리가 설정 값이 기본값입니다.|  
|`true`|PerfCounter.dll는 CategoryOptions 레지스트리 설정을 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이전의.NET Framework의 버전에는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], PerfCounter.dll 로드 된 버전의 프로세스에서 로드 된 런타임에 상응 합니다. 컴퓨터의.NET Framework 버전 1.1 갖는 경우 및 [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] 설치 된.NET Framework 1.1 응용 프로그램 로드 PerfCounter.dll의.NET Framework 1.1 버전입니다. 부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], PerfCounter.dll의 설치 된 최신 버전을 로드 합니다. 즉,.NET Framework 1.1 응용 프로그램 로드 됩니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 버전 PerfCounter.dll의 경우는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 컴퓨터에 설치 합니다.  
  
 부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 성능 카운터를 사용 하 고 PerfCounter.dll 범주별 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 확인 하려면 각 공급자에 대 한 CategoryOptions 레지스트리 항목을 확인 합니다. 공유 메모리 범주별; 인식 하지 않으므로.NET Framework 1.1 PerfCounter.dll 해당 레지스트리 항목을 읽지 않습니다. 항상 전역 공유 메모리에서 읽습니다.  
  
 이전 버전과 호환성을 위해는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll.NET Framework 1.1 응용 프로그램에서 실행 될 때 CategoryOptions 레지스트리 항목을 확인 하지 않습니다. 단순히.NET Framework 1.1 PerfCounter.dll 마찬가지로 전역 공유 메모리를 사용 합니다. 지시할 수 있습니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll 레지스트리 설정을 사용 하 여 확인 하는 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소입니다.  
  
> [!NOTE]
>  사용 하도록 설정 된 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소 범주별 공유 메모리 사용 됨을 보장 하지 않습니다. 사용 하는 설정과 `true` CategoryOptions 레지스트리 설정을 참조 하는 PerfCounter.dll만 발생 합니다. CategoryOptions에 대 한 기본 설정은 범주별 공유 메모리를 사용 하는 그러나 전역 공유 메모리를 사용 해야 함을 나타내기 위해 CategoryOptions 변경할 수 있습니다.  
  
 CategoryOptions 설정을 포함 하는 레지스트리 키가 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance 합니다. 기본적으로 CategoryOptions은 3으로 설정, PerfCounter.dll 게 지시 범주별 공유 메모리를 사용 하도록 합니다. CategoryOptions을 0으로 설정 하는 경우 PerfCounter.dll 전역 공유 메모리를 사용 합니다. 만들 인스턴스의 이름을 다시 사용 되 고 인스턴스와 다를 경우에 인스턴스 데이터를 다시 사용 됩니다. 모든 버전의 범주에 쓸 수 됩니다. CategoryOptions가 1로 설정 하는 경우 전역 공유 메모리 사용 되지만 범주 이름을 다시 사용 하는 범주와 길이가 같은 경우에 인스턴스 데이터를 다시 사용할 수 있습니다.  
  
 메모리 누수 및 성능 카운터 메모리의 채우기를 0과 1 설정 될 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 지정 PerfCounter.dll 범주별 공유 메모리를 사용 해야 하는지 여부를 확인 하려면 CategoryOptions 레지스트리 항목을 참조 해야 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
