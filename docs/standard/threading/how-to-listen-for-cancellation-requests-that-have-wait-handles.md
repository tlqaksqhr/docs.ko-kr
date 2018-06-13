---
title: '방법: 대기 핸들이 있는 취소 요청 수신 대기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6543c2e5ea953887e699ee6f9ca3b70e08e5ae85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583918"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="333cf-102">방법: 대기 핸들이 있는 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="333cf-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="333cf-103">이벤트의 신호를 받을 때까지 대기하는 동안 메서드가 차단된 경우 취소 토큰의 값을 확인하고 적시에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="333cf-104">첫 번째 예제는 기본적으로 통합 취소 프레임워크를 지원하지 않는 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>와 같은 이벤트에 대해 작업할 때 이 문제점을 해결하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="333cf-105">두 번째 예제는 통합 취소를 지원하는 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>을 사용하는 보다 간소화된 접근 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="333cf-106">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="333cf-107">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-107">This error is benign.</span></span> <span data-ttu-id="333cf-108">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="333cf-109">첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="333cf-110">예</span><span class="sxs-lookup"><span data-stu-id="333cf-110">Example</span></span>  
 <span data-ttu-id="333cf-111">다음 예제는 <xref:System.Threading.ManualResetEvent>를 사용하여 통합 취소를 지원하지 않는 대기 핸들을 차단 해제하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="333cf-112">예</span><span class="sxs-lookup"><span data-stu-id="333cf-112">Example</span></span>  
 <span data-ttu-id="333cf-113">다음 예제는 <xref:System.Threading.ManualResetEventSlim>를 사용하여 통합 취소를 지원하는 조정의 기본 형식을 차단 해제하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="333cf-114">동일한 접근 방식을 <xref:System.Threading.Semaphore> `Slim` 및 <xref:System.Threading.CountdownEvent>과 같은 다른 간단한 조정의 기본 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="333cf-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="333cf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="333cf-115">See Also</span></span>  
 [<span data-ttu-id="333cf-116">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="333cf-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
