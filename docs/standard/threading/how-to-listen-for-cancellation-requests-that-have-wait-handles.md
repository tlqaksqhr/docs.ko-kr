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
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="2b700-102">방법: 대기 핸들이 있는 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="2b700-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="2b700-103">메서드는 이벤트 신호를 대기 하는 동안 차단 된 경우 취소 토큰의 값을 확인 및 적절 한 시간 내에 응답 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="2b700-104">첫 번째 예에 사용 하는 이벤트와 같은 때이 문제를 해결 하는 방법을 보여 줍니다 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 고유 하 게 통합 된 취소 프레임 워크를 지원 하지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="2b700-105">두 번째 예제를 사용 하는 더 효율적인된 방법을 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>를 지 원하는 통합 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b700-106">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2b700-107">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-107">This error is benign.</span></span> <span data-ttu-id="2b700-108">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2b700-109">Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b700-110">예제</span><span class="sxs-lookup"><span data-stu-id="2b700-110">Example</span></span>  
 <span data-ttu-id="2b700-111">다음 예제에서는 한 <xref:System.Threading.ManualResetEvent> 통합 된 취소를 지원 하지 않는 대기 핸들의 차단을 해제 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="2b700-112">예제</span><span class="sxs-lookup"><span data-stu-id="2b700-112">Example</span></span>  
 <span data-ttu-id="2b700-113">다음 예제에서는 한 <xref:System.Threading.ManualResetEventSlim> 조정 차단을 해제 하는 방법을 보여 주는 기본 형식을 지원 않는 통합 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="2b700-114">동일한 방법을 사용 하 여 다른 간단한 코디 네이션 기본와 같은 <xref:System.Threading.Semaphore> `Slim` 및 <xref:System.Threading.CountdownEvent>합니다.</span><span class="sxs-lookup"><span data-stu-id="2b700-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2b700-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b700-115">See Also</span></span>  
 [<span data-ttu-id="2b700-116">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="2b700-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
