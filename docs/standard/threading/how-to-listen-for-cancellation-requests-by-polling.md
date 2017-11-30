---
title: "방법: 폴링을 통해 취소 요청 수신 대기"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="832e8-102">방법: 폴링을 통해 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="832e8-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="832e8-103">다음 예제에서는 사용자 코드가 호출 스레드에서 취소를 요청 되었는지 여부를 확인 하려면 정기적으로 취소 토큰을 폴링할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="832e8-104">사용 하 여이 예제는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 형식이 아니라 동일한 패턴에서 직접 만든 비동기 작업에 적용 되는 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 형식 또는 <xref:System.Threading.Thread?displayProperty=nameWithType> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="832e8-105">예제</span><span class="sxs-lookup"><span data-stu-id="832e8-105">Example</span></span>  
 <span data-ttu-id="832e8-106">폴링 부울 값을 주기적으로 읽을 수 있는 루프 또는 재귀 코드 필요 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="832e8-107">사용 하는 경우는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 유형인 작업이 호출 스레드에 대 완료 되기를 기다리는, 사용할 수 있습니다는 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드 하는 속성을 확인 하 고 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="832e8-108">이 메서드를 사용 하 여 올바른 예외가 요청에 대 한 응답에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="832e8-109">사용 하는 경우는 <xref:System.Threading.Tasks.Task>,이 메서드를 호출 하는 것은 수동으로 throw 하는 보다는 <xref:System.OperationCanceledException>합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="832e8-110">예외를 throw 하지 않은 경우 방금 속성을 확인 하 고 속성이 이면이 메서드에서 반환할 수 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="832e8-111">호출 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 매우 신속 하 고 루프에 상당한 오버 헤드가 제공 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="832e8-112">호출 하는 경우 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>를 명시적으로 확인 해야는 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 다른 작업을 취소 된 예외를 throw 하는 외에 대 한 응답으로 수행 해야 하는 경우 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="832e8-113">이 예에서 볼 수 있습니다는 코드가 실제로 액세스 속성이 두 번: 한 번 명시적 액세스 및 다시는 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="832e8-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="832e8-114">하지만 없기 때문에 읽는 동작에는 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성 하나만 volatile 읽기 액세스 당 명령만 포함, 이중 액세스는 성능 측면에서 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="832e8-115">좋습니다 수동으로 throw 하는 대신 메서드를 호출 하 여 <xref:System.OperationCanceledException>합니다.</span><span class="sxs-lookup"><span data-stu-id="832e8-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832e8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832e8-116">See Also</span></span>  
 [<span data-ttu-id="832e8-117">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="832e8-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
