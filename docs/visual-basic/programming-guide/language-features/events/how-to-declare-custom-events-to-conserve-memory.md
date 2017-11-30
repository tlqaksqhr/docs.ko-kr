---
title: "방법: 메모리를 절약하는 사용자 지정 이벤트 선언(Visual Basic)"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="4150b-102">방법: 메모리를 절약하는 사용자 지정 이벤트 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4150b-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="4150b-103">이 응용 프로그램 메모리 사용을 낮게 유지 하는 중요 한 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="4150b-104">사용자 지정 이벤트를 처리 하는 이벤트에 대 한 메모리를 사용 하도록 응용 프로그램을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="4150b-105">기본적으로 컴파일러는 클래스에서 이벤트를 선언 이벤트 정보를 저장 하는 필드에 대 한 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="4150b-106">클래스에 사용 하지 않는 이벤트 수, 메모리를 불필요 하 게 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="4150b-107">Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 메모리 사용량을 신중 하 게 관리 하려면 사용자 지정 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4150b-108">예제</span><span class="sxs-lookup"><span data-stu-id="4150b-108">Example</span></span>  
 <span data-ttu-id="4150b-109">이 예에서는 클래스 사용의 한 인스턴스는 <xref:System.ComponentModel.EventHandlerList> 에 저장 된 클래스는 `Events` 필드 사용에는 이벤트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="4150b-110"><xref:System.ComponentModel.EventHandlerList> 클래스가 대리자를 보관 하도록 최적화 목록 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="4150b-111">클래스 사용의 모든 이벤트는 `Events` 각 이벤트를 처리 하는 방법을 추적 하는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="4150b-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4150b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4150b-112">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList>  
 [<span data-ttu-id="4150b-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="4150b-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="4150b-114">방법: 차단을 방지하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="4150b-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
