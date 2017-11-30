---
title: "방법: 취소 요청에 대한 콜백 등록"
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
helpviewer_keywords: cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85b15ed610d80958ac9d7e3762ac8ea7b781b8d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="c1766-102">방법: 취소 요청에 대한 콜백 등록</span><span class="sxs-lookup"><span data-stu-id="c1766-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="c1766-103">다음 예제에서는 될 대리자를 등록 하는 방법을 보여 줍니다 될 때 호출 되는 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성이 호출으로 인해 true가 <xref:System.Threading.CancellationTokenSource.Cancel%2A> 토큰을 만든 개체에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="c1766-104">이 기술은 통합된 취소 프레임워크를 기본적으로 지원하지 않는 비동기 작업을 취소하고 비동기 작업이 완료되기를 기다릴 수 있는 메서드의 차단을 해제하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1766-105">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="c1766-106">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-106">This error is benign.</span></span> <span data-ttu-id="c1766-107">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="c1766-108">Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1766-109">예제</span><span class="sxs-lookup"><span data-stu-id="c1766-109">Example</span></span>  
 <span data-ttu-id="c1766-110">다음 예제에서 <xref:System.Net.WebClient.CancelAsync%2A> 메서드는 취소 토큰을 통해 취소가 요청될 때 호출할 메서드로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="c1766-111">콜백을 등록할 때 이미 취소가 요청된 경우에도 콜백 호출이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="c1766-112">이 특별한 경우에서는 진행 중인 비동기 작업이 없는 경우 <xref:System.Net.WebClient.CancelAsync%2A> 메서드가 아무 작업도 하지 않으므로 항상 안전하게 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1766-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1766-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1766-113">See Also</span></span>  
 [<span data-ttu-id="c1766-114">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="c1766-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
