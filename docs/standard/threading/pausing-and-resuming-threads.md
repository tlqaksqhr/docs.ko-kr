---
title: "스레드 일시 중지 및 다시 시작"
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
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>스레드 일시 중지 및 다시 시작
스레드 작업을 동기화하는 가장 일반적인 방법은 스레드를 차단 및 해제하거나 개체 또는 코드 영역을 잠그는 것입니다. 이러한 잠금 및 차단 메커니즘에 대한 자세한 내용은 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하세요.  
  
 스레드가 자동으로 중지되도록 할 수도 있습니다. 스레드가 차단 또는 중지된 경우 <xref:System.Threading.ThreadInterruptedException>을 사용하여 대기 상태에서 분리할 수 있습니다.  
  
## <a name="the-threadsleep-method"></a>Thread.Sleep 메서드  
 호출 된 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 메서드 하면 현재 스레드가 즉시 밀리초 또는 메서드에 전달 하는 시간 간격의 수에 대 한 차단 및 다른 스레드에 해당 시간 조각의 나머지를 구합니다. 지정된 시간이 지나면 대기 중인 스레드가 다시 실행되기 시작합니다.  
  
 한 스레드가 다른 스레드에서 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>를 호출할 수는 없습니다.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>현재 스레드 절전 모드를 사용 하면 항상 정적 메서드입니다.  
  
 호출 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 값 <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> 스레드의 호출 하는 다른 스레드에 의해 중단 될 때 까지의 대기는 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 메서드를 호출 하 여 종료 될 때까지 또는 절전 모드 스레드에서 해당 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 메서드.  다음 예제에서는 대기 중인 스레드를 중단하는 두 가지 메서드를 보여 줍니다.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>스레드 중단  
 호출 하 여 대기 중인 스레드를 중단할 수는 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 메서드가 throw 하는 차단 된 스레드에서 <xref:System.Threading.ThreadInterruptedException>, 차단 호출에서 스레드를 중단 하 합니다. 스레드는 <xref:System.Threading.ThreadInterruptedException>을 catch하고 작업을 계속하는 데 필요한 동작을 수행해야 합니다. 스레드가 예외를 무시하는 경우 런타임은 예외를 catch하고 스레드를 중지합니다.  
  
> [!NOTE]
>  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>를 호출할 때 대상 스레드가 차단되지 않는 경우 스레드는 차단될 때까지 중단되지 않습니다. 스레드가 차단되지 않으면 중단 없이 완료될 수 있습니다.  
  
 대기가 관리되는 대기인 경우 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 둘 다 스레드를 즉시 깨웁니다. 관리 되지 않는 대기 되는 경우 (예를 들어 플랫폼 호출 win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) 함수) 되지 않습니다 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 반환 되거나 관리 되는 코드를 호출 될 때까지 스레드를 제어 걸릴 수 있습니다. 관리 코드에서 동작은 다음과 같습니다.  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>는 대기 상태에서 스레드를 깨우고 대상 스레드에서 <xref:System.Threading.ThreadInterruptedException>이 발생하게 합니다.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>에 있을 수 있습니다 하 고 발생 하는 대기 스레드를 다시 시작 되는 <xref:System.Threading.ThreadAbortException> 스레드에서 throw 되 게 합니다. 자세한 내용은 [스레드 제거](../../../docs/standard/threading/destroying-threads.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레드 및 스레딩 사용](../../../docs/standard/threading/using-threads-and-threading.md)  
 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
