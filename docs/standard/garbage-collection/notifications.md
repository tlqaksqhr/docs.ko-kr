---
title: "Garbage Collection Notifications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "garbage collection, notifications"
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Garbage Collection Notifications
공용 언어 런타임에서 전체 가비지 수집 \(즉, 2세대 수집\) 을 실행하면 성능이 저하될 수 있는 경우가 있습니다.  특히 많은 요청을 처리하는 서버에서 이러한 경우가 나타날 수 있으며, 가비지 수집이 오래 걸려 요청 시간이 초과될 수 있습니다.  전체 가비지 수집이 임박했다는 알림을 받은 다음 작업 부하를 다른 서버 인스턴스로 리디렉션하면 중요한 작업이 수행되는 동안 전체 수집이 발생하지 않게 할 수 있습니다.  현재 서버 인스턴스에서 요청을 처리할 필요가 없을 때 수집을 직접 실행할 수도 있습니다.  
  
 <xref:System.GC.RegisterForFullGCNotification%2A> 메서드는 전체 가비지 수집이 임박했음을 런타임이 감지할 때 발생하는 알림을 수신 등록합니다.  이 알림에는 전체 가비지 수집이 임박한 시점과 전체 가비지 수집이 완료된 시점이라는 두 부분이 있습니다.  
  
> [!WARNING]
>  차단 가비지 수집은 알림을 발생시킵니다.  [\<\>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 구성 요소가 사용 될 수 있을 때, 백그라운 가비지 수집 알림은 발생 하지 않습니다.  
  
 알림이 발생한 시점을 확인하려면 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드를 사용합니다.  일반적으로 `while` 루프에서 이러한 메서드를 사용하여 알림의 상태를 보여 주는 <xref:System.GCNotificationStatus> 열거형을 계속 가져옵니다.  이 값이 <xref:System.GCNotificationStatus>이면 다음을 수행할 수 있습니다.  
  
-   <xref:System.GC.WaitForFullGCApproach%2A> 메서드로 가져온 알림에 대한 응답으로 작업 부하를 리디렉션하고 수집을 직접 실행할 수 있습니다.  
  
-   <xref:System.GC.WaitForFullGCComplete%2A> 메서드로 가져온 알림에 대한 응답으로 현재 서버 인스턴스에서 요청을 처리하도록 다시 허용할 수 있습니다.  정보를 수집할 수도 있습니다.  예를 들어, <xref:System.GC.CollectionCount%2A> 메서드를 사용하여 수집 횟수를 기록할 수 있습니다.  
  
 <xref:System.GC.WaitForFullGCApproach%2A>와 <xref:System.GC.WaitForFullGCComplete%2A> 메서드는 함께 작동하도록 설계되었습니다.  둘 중 하나만 사용하면 명확하지 않은 결과가 나타날 수 있습니다.  
  
## 전체 가비지 수집  
 다음 시나리오에 하나라도 해당하면 런타임에서 전체 가비지 수집을 실행합니다.  
  
-   다음 2세대 수집을 유발하기에 충분한 메모리가 2세대로 승격된 경우  
  
-   다음 2세대 수집을 유발하기에 충분한 메모리가 대형 개체 힙으로 승격된 경우  
  
-   1세대 수집이 기타 요소로 인해 2세대 수집으로 에스컬레이션된 경우  
  
 <xref:System.GC.RegisterForFullGCNotification%2A> 메서드에 지정하는 임계값은 처음 두 시나리오에 적용됩니다.  그러나 첫 번째 시나리오에서는 다음 두 가지 이유로 인해 임계값에 해당하는 시점에 알림을 받지 못할 수도 있습니다.  
  
-   런타임은 성능상의 이유로 모든 소형 개체 할당을 검사하지 않습니다.  
  
-   1세대 수집만 메모리를 2세대로 승격합니다.  
  
 세 번째 시나리오도 알림을 받는 시점을 명확하지 않게 합니다.  항상 그러한 것은 아니지만, 해당 시간 동안 요청을 리디렉션하거나 보다 여유가 있는 적절한 시점에 수집을 직접 실행하면 부적절한 전체 가비지 수집의 영향을 줄일 수 있습니다.  
  
## 알림 임계값 매개 변수  
 <xref:System.GC.RegisterForFullGCNotification%2A> 메서드에는 2세대 개체와 대형 개체 힙의 임계값을 지정하는 두 매개 변수가 있습니다.  이러한 값에 도달하면 가비지 수집 알림이 발생합니다.  다음 표에서는 이러한 매개 변수를 보여 줍니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`maxGenerationThreshold`|2세대로 승격된 개체에 따라 알림을 발생시킬 시점을 지정하는 1에서 99 사이의 숫자입니다.|  
|`largeObjectHeapThreshold`|대형 개체 힙에 할당된 개체에 따라 알림을 발생시킬 시점을 지정하는 1에서 99 사이의 숫자입니다.|  
  
 너무 높은 값을 지정하면 알림을 받을 확률은 높아지지만 런타임에서 수집을 실행할 때까지 너무 오래 기다려야 할 수 있습니다.  수집을 직접 실행하는 경우에는 런타임에서 수집을 실행할 때보다 많은 개체를 회수해야 할 수 있습니다.  
  
 너무 낮은 값을 지정하면 사용자가 알림을 받기 전에 런타임에서 수집을 실행할 수도 있습니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 들어오는 웹 요청을 서버 그룹에서 처리합니다.  요청을 처리하는 작업 부하를 시뮬레이션하기 위해 <xref:System.Collections.Generic.List%601> 컬렉션에 바이트 배열이 추가되었습니다.  각 서버는 가비지 수집 알림을 수신 등록한 다음 `WaitForFullGCProc` 사용자 메서드에서 스레드를 시작하여 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드에서 반환하는 <xref:System.GCNotificationStatus> 열거형을 계속 모니터링합니다.  
  
 알림이 발생하면 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드는 해당 이벤트 처리 사용자 메서드를 호출합니다.  
  
-   `OnFullGCApproachNotify`  
  
     이 메서드는 해당 서버에 대한 요청 전송을 일시 중단하도록 요청 대기 서버에 지시하는 `RedirectRequests` 사용자 메서드를 호출합니다.  개체가 더 이상 할당되지 않도록 클래스 수준 변수인 `bAllocate`를 `false`로 설정하여 이 동작을 시뮬레이션합니다.  
  
     다음으로 `FinishExistingRequests` 사용자 메서드를 호출하여 대기 중인 서버 요청의 처리를 마칩니다.  <xref:System.Collections.Generic.List%601> 컬렉션의 내용을 지워 이 동작을 시뮬레이션합니다.  
  
     마지막으로 작업 부하가 감소했으므로 가비지 수집을 실행합니다.  
  
-   `OnFullGCCompleteNotify`  
  
     서버에서 전체 가비지 수집이 더 이상 실행되지 않으므로 이 메서드는 사용자 메서드인 `AcceptRequests`를 호출하여 요청 수신을 다시 시작합니다.  <xref:System.Collections.Generic.List%601> 컬렉션에 개체가 다시 추가되도록 `bAllocate` 변수를 `true`로 설정하여 이 동작을 시뮬레이션합니다.  
  
 다음 코드에는 예제의 `Main` 메서드가 들어 있습니다.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 다음 코드에는 `WaitForFullGCProc` 사용자 메서드가 들어 있으며, 여기에는 가비지 수집 알림을 확인하는 연속적인 while 루프가 포함되어 있습니다.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 다음 코드에는 아래 메서드에서 호출하는 `OnFullGCApproachNotify` 메서드가 들어 있습니다.  
  
 `WaitForFullGCProc` 메서드  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 다음 코드에는 아래 메서드에서 호출하는 `OnFullGCApproachComplete` 메서드가 들어 있습니다.  
  
 `WaitForFullGCProc` 메서드  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 다음 코드에는 `OnFullGCApproachNotify` 및 `OnFullGCCompleteNotify` 메서드에서 호출하는 사용자 메서드가 들어 있습니다.  이 사용자 메서드는 요청을 리디렉션하고 기존 요청을 완료한 다음 전체 가비지 수집이 수행된 후 요청을 다시 시작합니다.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 전체 코드 샘플은 다음과 같습니다.  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## 참고 항목  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)