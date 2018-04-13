---
title: '방법: 폴링을 통해 취소 요청 수신 대기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 56a927e10cb026814302728a72acb2f32223b29b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="8e587-102">방법: 폴링을 통해 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="8e587-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="8e587-103">다음 예제는 사용자 코드가 정기적으로 취소 토큰을 폴링하여 호출 스레드에서 취소가 요청되었는지 여부를 확인하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="8e587-104">이 예제에서는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 유형을 사용하지만, 동일한 패턴이 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 유형 또는 <xref:System.Threading.Thread?displayProperty=nameWithType> 유형으로 직접 생성된 비동기 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e587-105">예</span><span class="sxs-lookup"><span data-stu-id="8e587-105">Example</span></span>  
 <span data-ttu-id="8e587-106">폴링에는 부울 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성의 값을 정기적으로 읽을 수 있는 특정한 종류의 루프 또는 순환 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="8e587-107"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 유형을 사용 중이고 작업이 호출 스레드에서 완료될 때까지 대기 중인 경우 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드를 사용하여 속성을 확인하고 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="8e587-108">이 메서드를 사용하여 요청에 대한 응답으로 올바른 예외가 throw되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="8e587-109"><xref:System.Threading.Tasks.Task>를 사용하는 경우 이 메서드를 호출하는 것이 <xref:System.OperationCanceledException>를 수동으로 throw하는 것보다 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="8e587-110">예외를 throw할 필요가 없는 경우 속성을 확인하고 속성이 `true`인 경우 메서드에서 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="8e587-111"><xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 호출은 매우 빠르며 루프에서 오버헤드를 그다지 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="8e587-112"><xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>를 호출하는 경우 예외를 throw하는 것 외에 취소에 대한 응답으로 수행해야 할 다른 작업이 있는 경우에만 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 명시적으로 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="8e587-113">이 예제에서는 코드가 실제로 속성에 두 번 액세스하는 것을 볼 수 있습니다. 명시적으로 한 번 액세스하고 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드에서 다시 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="8e587-114">그러나 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 읽는 작업에는 액세스당 하나의 volatile 읽기 명령만 포함되므로 성능상의 관점에서는 두 번의 액세스가 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="8e587-115"><xref:System.OperationCanceledException>을 수동으로 throw하는 것보다 메서드를 호출하는 것이 여전히 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8e587-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e587-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e587-116">See Also</span></span>  
 [<span data-ttu-id="8e587-117">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="8e587-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
