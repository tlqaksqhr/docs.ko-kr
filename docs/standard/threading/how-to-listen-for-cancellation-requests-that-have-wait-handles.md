---
title: "방법: 대기 핸들이 있는 취소 요청 수신 대기"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>방법: 대기 핸들이 있는 취소 요청 수신 대기
메서드는 이벤트 신호를 대기 하는 동안 차단 된 경우 취소 토큰의 값을 확인 및 적절 한 시간 내에 응답 없습니다. 첫 번째 예에 사용 하는 이벤트와 같은 때이 문제를 해결 하는 방법을 보여 줍니다 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 고유 하 게 통합 된 취소 프레임 워크를 지원 하지 않는 합니다. 두 번째 예제를 사용 하는 더 효율적인된 방법을 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>를 지 원하는 통합 취소 합니다.  
  
> [!NOTE]
>  “내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다. 이 오류는 심각하지는 않습니다. F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다. Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Threading.ManualResetEvent> 통합 된 취소를 지원 하지 않는 대기 핸들의 차단을 해제 하는 방법을 보여 줍니다.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Threading.ManualResetEventSlim> 조정 차단을 해제 하는 방법을 보여 주는 기본 형식을 지원 않는 통합 취소 합니다. 동일한 방법을 사용 하 여 다른 간단한 코디 네이션 기본와 같은 <xref:System.Threading.Semaphore> `Slim` 및 <xref:System.Threading.CountdownEvent>합니다.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)
