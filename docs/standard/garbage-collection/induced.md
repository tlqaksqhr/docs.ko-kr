---
title: "인덱싱된 컬렉션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92918e347b10dfcf3a0d6e2c08cec8c7a6963f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="induced-collections"></a>인덱싱된 컬렉션
대부분의 경우 가비지 수집기가 수집을 수행할 적절한 시기를 결정할 수 있으며 가비지 수집기가 독립적으로 실행되는 것이 좋습니다. 강제된 컬렉션이 응용 프로그램의 성능을 향상시키는 드문 경우도 있습니다. 이러한 경우에 사용 하 여 가비지 수집을 실행할 수 있습니다는 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 메서드를 가비지 수집을 실행 합니다.  
  
 사용 된 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 응용 프로그램의 코드의 특정 지점에서 사용 되는 메모리 양을 크게 절감 하는 경우 방법입니다. 응용 프로그램에 여러 컨트롤이 있는 복잡 한 대화 상자를 사용 하는 경우 호출 하는 예를 들어 <xref:System.GC.Collect%2A> 대화 상자를 닫을 때 즉시 대화 상자에서 사용 되는 메모리를 확보 하 여 성능을 개선할 수 있습니다. 가비지 수집기가 최적이 아닌 시간에 개체를 회수하려고 하는 경우 성능이 저하될 수 있기 때문에 응용 프로그램이 너무 자주 가비지 수집을 발생시키지 않도록 합니다. 제공할 수 있습니다는 <xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType> 열거형 값의 <xref:System.GC.Collect%2A> 메서드를 다음 섹션에서 설명한 대로 컬렉션 생산성을 높일 수는 경우에 수집 합니다.  
  
## <a name="gc-collection-mode"></a>GC 컬렉션 모드  
 하나를 사용할 수는 <xref:System.GC.Collect%2A?displayProperty=nameWithType> 메서드 오버 로드를 포함 하는 <xref:System.GCCollectionMode> 강제 컬렉션에 대 한 동작을 다음과 같이 지정 하는 값입니다.  
  
|`GCCollectionMode` 값|설명|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|실행 중인 버전의.NET에 대 한 기본 가비지 수집 설정을 사용합니다.|  
|<xref:System.GCCollectionMode.Forced>|가비지 수집이 즉시 실행되도록 강제합니다. 이 호출에 해당 하는 <xref:System.GC.Collect?displayProperty=nameWithType> 오버 로드 합니다. 모든 세대의 전체 차단 컬렉션에서 발생합니다.<br /><br /> 설정 하 여 큰 개체 힙 또한 압축할 수 있습니다는 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType> 즉시 전체 차단 가비지 수집을 강제로 적용 하기 전에.|  
|<xref:System.GCCollectionMode.Optimized>|가비지 수집기는 현재 시간이 개체를 회수하기 위한 최적 시간인지 확인할 수 있습니다.<br /><br /> 가비지 수집기는 컬렉션이 정당화될 만큼 생산적이지 않다는 것을 결정할 수 있습니다. 이 경우에 개체를 회수하지 않고 반환합니다.|  
  
## <a name="background-or-blocking-collections"></a>배경 또는 차단 컬렉션  
 호출할 수 있습니다는 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType> 메서드 오버 로드를 발생 시킨된 컬렉션 차단 여부를 지정 합니다. 메서드의 조합의에 수행 되는 컬렉션 형식에 따라 달라 집니다 `mode` 및 `blocking` 매개 변수입니다. `mode`구성원은 <xref:System.GCCollectionMode> 열거형 및 `blocking` 는 <xref:System.Boolean> 값입니다. 다음 표에서 요약의 상호 작용은 `mode` 및 `blocking` 인수입니다.  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> 또는 <xref:System.GCCollectionMode.Default>|차단 컬렉션은 가능한 한 빨리 수행됩니다. 백그라운드 컬렉션 진행 중 이므로 0 또는 1 세대는 경우는 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 즉시 차단 컬렉션을 트리거하여 메서드와 완료 되는 컬렉션을 반환 합니다. 백그라운드 컬렉션 진행 중인 경우와 `generation` 매개 변수는 2, 백그라운드 컬렉션이 완료 되 고 차단 2 세대 컬렉션을 트리거하여 다음 반환 될 때까지 메서드 대기 합니다.|컬렉션은 가능한 한 빨리 수행됩니다. <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 메서드 요청 백그라운드 컬렉션 있지만 보장 되지 않습니다; 상황에 따라 차단 컬렉션 계속 수행 될 수 있습니다. 백그라운드 컬렉션이 이미 진행 중인 경우 메서드가 즉시 반환됩니다.|  
|<xref:System.GCCollectionMode.Optimized>|가비지 수집기의 상태에 따라 차단 컬렉션에 수행, 될 수 있습니다 및 `generation` 매개 변수입니다. 가비지 수집기는 최적의 성능을 제공하려고 합니다.|가비지 수집기의 상태에 따라 컬렉션이 수행될 수 있습니다. <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 메서드 요청 백그라운드 컬렉션 있지만 보장 되지 않습니다; 상황에 따라 차단 컬렉션 계속 수행 될 수 있습니다. 가비지 수집기는 최적의 성능을 제공하려고 합니다. 백그라운드 컬렉션이 이미 진행 중인 경우 메서드가 즉시 반환됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [대기 시간 모드](../../../docs/standard/garbage-collection/latency.md)  
 [가비지 수집](../../../docs/standard/garbage-collection/index.md)
