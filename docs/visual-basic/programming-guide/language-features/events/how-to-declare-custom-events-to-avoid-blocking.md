---
title: "방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a36c855efb67752674615a61f2fa701974ce5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="9a5a2-102">방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a5a2-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="9a5a2-103">이 하나의 이벤트 처리기는 후속 이벤트 처리기를 차단 하지 중요 한 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="9a5a2-104">사용자 지정 이벤트의 이벤트 처리기를 비동기적으로 호출 하려면 이벤트를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="9a5a2-105">기본적으로는 이벤트 선언에 대 한 지원 저장소 필드는 멀티 캐스트 대리자 모든 이벤트 처리기를 순차적입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="9a5a2-106">이 하나의 처리기는 완료 하는 데 시간이 오래 걸리면, 차단할 다른 처리기 완료 될 때까지 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="9a5a2-107">(때 이벤트 처리기 긴 또는 잠재적인 차단 작업이 수행 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="9a5a2-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="9a5a2-108">Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 이벤트 처리기를 비동기적으로 실행 하는 사용자 지정 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a5a2-109">예제</span><span class="sxs-lookup"><span data-stu-id="9a5a2-109">Example</span></span>  
 <span data-ttu-id="9a5a2-110">이 예제는 `AddHandler` 의 각 처리기에 대 한 대리자를 추가 하는 접근자는 `Click` 이벤트를는 <xref:System.Collections.ArrayList> 에 저장 된는 `EventHandlerList` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="9a5a2-111">발생 시키는 경우 코드는 `Click` 이벤트는 `RaiseEvent` 비동기적으로 사용 하 여 모든 이벤트 처리기 대리자를 호출 하는 접근자는 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="9a5a2-112">해당 메서드는 작업자 스레드에서 각 처리기를 호출 하 고 즉시 반환 하므로 처리기 서로 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9a5a2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a5a2-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="9a5a2-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="9a5a2-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="9a5a2-115">방법: 메모리를 절약하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="9a5a2-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
