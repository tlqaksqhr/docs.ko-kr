---
title: '방법: 여러 개의 취소 요청 수신 대기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afa22ed1fe1986712493c2aaa844d7f2c6ffd5bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583132"
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="62a79-102">방법: 여러 개의 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="62a79-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="62a79-103">이 예제에서는 두 개의 취소 토큰 중 하나가 작업을 요청할 경우 작업을 취소할 수 있도록 두 개의 취소 토큰을 동시에 수신 대기하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62a79-104">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="62a79-105">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-105">This error is benign.</span></span> <span data-ttu-id="62a79-106">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="62a79-107">첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62a79-108">예</span><span class="sxs-lookup"><span data-stu-id="62a79-108">Example</span></span>  
 <span data-ttu-id="62a79-109">다음 예제에서 <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> 메서드는 두 개의 토큰을 하나의 토큰으로 결합하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="62a79-110">이렇게 하면 하나의 취소 토큰만 인수로 사용하는 메서드에 토큰을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="62a79-111">이 예제에서는 메서드가 클래스 외부에서 전달되는 토큰과 클래스 내에서 생성되는 토큰을 모두 관찰해야 하는 일반적인 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="62a79-112">연결된 토큰이 <xref:System.OperationCanceledException>을 throw하면 예외에 전달되는 토큰은 선행 작업 토큰이 아닌 연결된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="62a79-113">취소된 토큰을 확인하려면 선행 작업 토큰의 상태를 직접 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="62a79-114">이 예제에서는 <xref:System.AggregateException>이 throw되면 안 되지만 여기에서는 예외를 catch합니다. 실제 시나리오에서는 작업 대리자에서 throw되는 <xref:System.OperationCanceledException> 이외의 다른 예외가 <xref:System.OperationCanceledException>으로 래핑되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="62a79-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a79-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62a79-115">See Also</span></span>  
 [<span data-ttu-id="62a79-116">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="62a79-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
