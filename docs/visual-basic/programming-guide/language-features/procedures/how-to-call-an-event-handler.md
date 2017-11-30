---
title: "방법: Visual Basic에서 이벤트 처리기 호출"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52b4b6ca8b03d8301535d6aeedc3bd0190d8527f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="2b6f8-102">방법: Visual Basic에서 이벤트 처리기 호출</span><span class="sxs-lookup"><span data-stu-id="2b6f8-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="2b6f8-103">*이벤트* 작업이 나 항목은-들면 마우스 클릭 또는 신용 한도 초과-응답 하도록 코드를 작성할 수에 대 한 일부 프로그램 구성 요소가 인식 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="2b6f8-104">*이벤트 처리기* 이벤트에 응답 하기 위해 작성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="2b6f8-105">이벤트 처리기가 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-105">An event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="2b6f8-106">그러나 호출 하지 않으면 일반적으로 동일한 다른 방식으로 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="2b6f8-107">대신, 이벤트에 대 한 처리기로 프로시저를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="2b6f8-108">이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="2b6f8-109">사용 하는 `Handles` 절에서 이벤트 처리기를 선언 하는 기본 방법은 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="2b6f8-110">이 방법은 보고서 통합된 개발 환경 (IDE)에서 프로그래밍할 때 디자이너에서 이벤트 처리기를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="2b6f8-111">`AddHandler` 문에 런타임 시 동적으로 이벤트를 발생 시키기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="2b6f8-112">이벤트가 발생할 때 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 자동으로 이벤트 처리기 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-112">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="2b6f8-113">이벤트에 대 한 액세스 권한이 있는 모든 코드를 실행 하 여 발생 하 게 할 수는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="2b6f8-114">둘 이상의 이벤트 처리기를 동일한 이벤트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="2b6f8-115">경우에 따라 이벤트에서 처리기를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="2b6f8-116">자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="2b6f8-117">WithEvents와 핸들을 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2b6f8-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="2b6f8-118">이벤트와 선언 되어 있는지 확인 한 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="2b6f8-119">모듈 또는 클래스 개체 변수를 사용 하 여 수준 선언 된 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="2b6f8-120">`As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="2b6f8-121">이벤트 처리의 선언에 `Sub` 프로시저 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 지정 하는 `WithEvents` 변수 및 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="2b6f8-122">이벤트가 발생할 때 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 자동으로 호출 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-122">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="2b6f8-123">코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="2b6f8-124">다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="2b6f8-125">이벤트 처리 `Sub` 프로시저는 한 `Handles` 절 클래스와를 처리 하는 이벤트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="2b6f8-126">AddHandler를 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2b6f8-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="2b6f8-127">이벤트와 선언 되어 있는지 확인 한 `Event` 문.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="2b6f8-128">실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트와 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="2b6f8-129">이벤트가 발생할 때 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 자동으로 호출 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-129">When the event occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="2b6f8-130">코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="2b6f8-131">다음 예제에서는 정의 `Sub` 처리 하는 프로시저는 <xref:System.Windows.Forms.Form.Closing> 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="2b6f8-132">다음 사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` 에 대 한 이벤트 처리기로 프로시저 <xref:System.Windows.Forms.Form.Closing>합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="2b6f8-133">실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다는 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6f8-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6f8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b6f8-134">See Also</span></span>  
 [<span data-ttu-id="2b6f8-135">절차</span><span class="sxs-lookup"><span data-stu-id="2b6f8-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="2b6f8-136">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="2b6f8-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="2b6f8-137">Sub 문</span><span class="sxs-lookup"><span data-stu-id="2b6f8-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="2b6f8-138">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="2b6f8-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="2b6f8-139">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="2b6f8-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="2b6f8-140">방법: 값을 반환하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="2b6f8-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
