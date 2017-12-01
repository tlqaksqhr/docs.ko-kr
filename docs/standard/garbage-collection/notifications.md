---
title: "가비지 컬렉션 알림"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>가비지 컬렉션 알림
공용 언어 런타임에서 전체 가비지 컬렉션(즉, 2세대 컬렉션)을 실행하면 성능이 저하될 수 있는 경우가 있습니다. 이 많은 양의; 요청을 처리 하는 서버에 특히 문제가 될 수 있습니다. 이 경우 긴 가비지 수집에는 요청 시간 제한이 발생할 수 있습니다. 전체 수집이 중요 한 기간 동안 발생을 방지 하려면 알림을 받을 수 있습니다 전체 가비지 컬렉션이 임박 하 고 작업 부하를 다른 서버 인스턴스로 리디렉션하는 조치를 취할 합니다. 실행할 수도 있습니다 컬렉션, 직접는 현재 서버 인스턴스가 요청을 처리 하지 않아도 됩니다.  
  
 <xref:System.GC.RegisterForFullGCNotification%2A> 런타임이 전체 가비지 컬렉션이 임박 감지할 때 발생 하는 알림을 수신 메서드를 등록 합니다. 두 가지 방법으로이 알림에: 전체 가비지 컬렉션이 임박 때 및 전체 가비지 수집이 완료 되 면 합니다.  
  
> [!WARNING]
>  차단 가비지 컬렉션만 알림을 발생시킵니다. 경우는 [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 구성 요소를 사용 하면 백그라운드 가비지 컬렉션 알림이 발생 하지 것입니다.  
  
 사용 하 여 알림을 발생 시기를 확인 하려면는 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드. 이러한 메서드를 사용 하는 일반적으로 `while` 을 계속 가져옵니다 루프는 <xref:System.GCNotificationStatus> 알림의 상태를 표시 하는 열거형입니다. 해당 값이 <xref:System.GCNotificationStatus.Succeeded>, 다음을 수행할 수 있습니다.  
  
-   가져온 알림에 대 한 응답에서 <xref:System.GC.WaitForFullGCApproach%2A> 메서드를 리디렉션할 작업 하 고 가능한 컬렉션을 직접 실행할 수 있습니다.  
  
-   가져온 알림에 대 한 응답에서 <xref:System.GC.WaitForFullGCComplete%2A> 메서드를 다시 요청을 처리할 수 있도록 현재 서버 인스턴스를 만들 수 있습니다. 정보를 수집할 수도 있습니다. 예를 들어, 사용할 수는 <xref:System.GC.CollectionCount%2A> 메서드 컬렉션의 수를 기록 합니다.  
  
 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 방법은 함께 작동 하도록 설계 되었습니다. 서로 사용 하 여 확인할 수 없는 결과가 발생할 수 있습니다.  
  
## <a name="full-garbage-collection"></a>전체 가비지 수집  
 다음 시나리오 중 하나가 충족 되 면 런타임에서 전체 가비지 수집:  
  
-   메모리가 부족 하 여 다음 2 세대 수집을 유발 하는 2 세대로 승격 된 경우  
  
-   다음 2 세대 수집을 큰 개체 힙에 메모리가 부족 하 여 승격 된 합니다.  
  
-   1 세대의 컬렉션을 다른 원인으로 인해 2 세대 컬렉션 에스컬레이션 됩니다.  
  
 지정 하는 임계값은 <xref:System.GC.RegisterForFullGCNotification%2A> 메서드는 처음 두 시나리오에 적용 합니다. 그러나 첫 번째 시나리오에서 하지 항상 알림이 두 가지 이유로 지정 된 임계값 값에 비례 시간에:  
  
-   런타임은 각 소형 개체 할당 (성능상의 이유로) 확인 하지 않습니다.  
  
-   생성 1 컬렉션 승격할 메모리에 2 세대입니다.  
  
 세 번째 시나리오 알림을 받는 시점을 명확 하지 않게에도 적용 됩니다. 보장 하지 않더라도이 시간 동안 요청을 리디렉션하거나 더 잘 수용 될 때 컬렉션 직접 실행 하 여 부적절 한 전체 가비지 수집의 영향을 완화 하는 유용한 방법은 되도록 증명지 않습니다.  
  
## <a name="notification-threshold-parameters"></a>알림 임계값 매개 변수  
 <xref:System.GC.RegisterForFullGCNotification%2A> 메서드에 두 개의 매개 변수가 2 세대 개체 및 큰 개체 힙의 임계값을 지정할 수 있습니다. 이러한 값에 도달 하는 경우 가비지 컬렉션 알림이 발생 하도록 합니다. 다음 표에서 이러한 매개 변수에 대해 설명 합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`maxGenerationThreshold`|2 세대로 승격 된 개체에 따라 알림을 발생 시킬 시점을 지정 하는 1에서 99 사이의 숫자입니다.|  
|`largeObjectHeapThreshold`|대형 개체 힙에 할당 된 개체에 따라 알림을 발생 시킬 시점을 지정 하는 1과 99 사이의 숫자.|  
  
 너무 큰 값을 지정 하는 경우 알림을 받게 됩니다 이지만 런타임에서 수집 전까지 대기 하는 기간을 너무 오래 수도 확률이 높은 차이가 있습니다. 컬렉션, 직접 실행할 경우에 런타임에서 수집 하는 경우 회수 되는 것 보다 많은 개체를 회수할 수 있습니다.  
  
 이 너무 낮은 값을 지정 하는 경우에 런타임에 알림을 받을 수 있는 충분 한 시간이 전에 컬렉션에 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 서버 그룹을 들어오는 웹 요청을 처리 합니다. 요청 처리의 작업을 시뮬레이트하기 위해 바이트 배열에 추가 되는 <xref:System.Collections.Generic.List%601> 컬렉션입니다. 가비지 컬렉션 알림의 등록 하 고 다음에서 스레드를 시작 하는 각 서버는 `WaitForFullGCProc` 지속적으로 모니터링 하려면 사용자는 <xref:System.GCNotificationStatus> 열거형에서 반환 되는 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드.  
  
 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드 알림이 발생 하는 경우 해당 이벤트 처리 사용자 메서드를 호출 합니다.  
  
-   `OnFullGCApproachNotify`  
  
     이 메서드를 호출는 `RedirectRequests` 사용자 메서드를 보내는 일시 중단 요청 대기 서버를 지정 하는 서버에 요청 합니다. 클래스 수준 변수를 설정 하 여이 동작을 시뮬레이션 `bAllocate` 를 `false` 더 이상 개체가 할당 됩니다.  
  
     다음으로 `FinishExistingRequests` 사용자 메서드가 보류 중인 서버 요청을 처리 합니다. 선택을 취소 하 여이 동작을 시뮬레이션 된 <xref:System.Collections.Generic.List%601> 컬렉션입니다.  
  
     마지막으로, 가비지 수집 했으므로 부하가 합니다.  
  
-   `OnFullGCCompleteNotify`  
  
     이 메서드는 사용자 지정 메서드를 호출 `AcceptRequests` 서버를 전체 가비지 수집에 취약 더 이상 요청 수신을 다시 시작 합니다. 이 동작을 설정 하 여 시뮬레이션는 `bAllocate` 변수를 `true` 개체에 추가 되 고 다시 시작할 수 있도록는 <xref:System.Collections.Generic.List%601> 컬렉션입니다.  
  
 다음 코드를 포함 하는 `Main` 예제의 메서드.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 다음 코드를 포함 하는 `WaitForFullGCProc` 연속 while 루프 가비지 컬렉션 알림 확인을 포함 하는 사용자 메서드.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 다음 코드를 포함 하는 `OnFullGCApproachNotify` 메서드에서 호출 메서드는  
  
 `WaitForFullGCProc` 메서드를 호출하여 생성됩니다.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 다음 코드를 포함 하는 `OnFullGCApproachComplete` 메서드에서 호출 메서드는  
  
 `WaitForFullGCProc` 메서드를 호출하여 생성됩니다.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 다음 코드에서 호출 하는 사용자 메서드가 포함 된 `OnFullGCApproachNotify` 및 `OnFullGCCompleteNotify` 메서드. 사용자 메서드 요청 리디렉션, 기존 요청을 완료 및 다음 전체 가비지 컬렉션이 발생 한 후 요청을 다시 시작 합니다.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 전체 코드 샘플은 다음과 같습니다.  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [가비지 수집](../../../docs/standard/garbage-collection/index.md)
