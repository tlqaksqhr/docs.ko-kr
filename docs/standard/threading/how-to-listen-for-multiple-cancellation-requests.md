---
title: "방법: 여러 개의 취소 요청 수신 대기"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="78479-102">방법: 여러 개의 취소 요청 수신 대기</span><span class="sxs-lookup"><span data-stu-id="78479-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="78479-103">이 예제에서는 두 토큰의 요청이 있을 경우 작업을 취소할 수 있도록 두 개의 취소 토큰을 동시에 수신 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78479-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78479-104">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="78479-105">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78479-105">This error is benign.</span></span> <span data-ttu-id="78479-106">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78479-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="78479-107">Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78479-108">예제</span><span class="sxs-lookup"><span data-stu-id="78479-108">Example</span></span>  
 <span data-ttu-id="78479-109">다음 예제에서는 <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> 하나의 토큰으로 두 개의 토큰을 연결할 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="78479-110">이 통해 토큰을 하나만 취소 토큰을 인수로 사용 하는 메서드로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="78479-111">이 예제에서는 메서드를 모두 토큰에서 전달 된 외부의 클래스 및 클래스 내부에서 생성 한 토큰을 준수 해야 하는 일반적인 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78479-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="78479-112">연결 된 토큰 throw 하는 경우는 <xref:System.OperationCanceledException>, 예외에 전달 되는 토큰은 연결 된 토큰 선행 토큰 중 하나가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="78479-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="78479-113">토큰을 취소를 확인 하려면 직접 입력 하는 선행 토큰의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="78479-114">이 예제에서는 <xref:System.AggregateException> 발생 하지 않아야 아니라 때문에 여기 걸러은 실제 시나리오에서 외에도 다른 모든 예외가 <xref:System.OperationCanceledException> 작업 대리자에서 throw 된에 래핑됩니다.이 <xref:System.OperationCanceledException>합니다.</span><span class="sxs-lookup"><span data-stu-id="78479-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78479-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78479-115">See Also</span></span>  
 [<span data-ttu-id="78479-116">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="78479-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
