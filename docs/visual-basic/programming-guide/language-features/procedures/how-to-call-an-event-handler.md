---
title: "방법: Visual Basic에서 이벤트 처리기를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dc0174d50c7b5f5cda9d057bce39960b3e563f4e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="9f2d1-102">방법: Visual Basic에서 이벤트 처리기 호출</span><span class="sxs-lookup"><span data-stu-id="9f2d1-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="9f2d1-103">*이벤트* 작업 또는 항목은 — 들면 마우스 클릭 이나 신용 한도 초과-응답 하 고 코드를 작성할 수 있는 일부 프로그램 구성 요소에 의해 인식 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="9f2d1-104">*이벤트 처리기* 이벤트에 응답 하기 위해 작성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="9f2d1-105">이벤트 처리기가 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-105">An event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is a `Sub` procedure.</span></span> <span data-ttu-id="9f2d1-106">그러나 호출 하지 않으면 일반적으로 동일한 다른 방식으로 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="9f2d1-107">대신, 이벤트에 대 한 처리기로 프로시저를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="9f2d1-108">이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="9f2d1-109">사용 하는 `Handles` 절에서 이벤트 처리기를 선언 하는 기본 방법은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-109">Using a `Handles` clause is the default way to declare an event handler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="9f2d1-110">이 방법은 통합된 개발 환경 (IDE)에서 프로그래밍할 때 이벤트 처리기는 디자이너에 의해 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="9f2d1-111">`AddHandler` 문에 런타임에 동적으로 이벤트를 발생 시키기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="9f2d1-112">이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 이벤트 처리기 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-112">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the event handler procedure.</span></span> <span data-ttu-id="9f2d1-113">이벤트에 대 한 액세스 권한이 있는 모든 코드를 사용 하면 실행 하 여 발생 하는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="9f2d1-114">동일한 이벤트와 둘 이상의 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="9f2d1-115">일부 경우에는 이벤트 처리기를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="9f2d1-116">자세한 내용은 참조 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="9f2d1-117">핸들 및 WithEvents를 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="9f2d1-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="9f2d1-118">이벤트 선언 되었는지 확인 되는 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="9f2d1-119">모듈 또는 클래스에서 개체 변수를 사용 하 여 수준 선언 된 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="9f2d1-120">`As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="9f2d1-121">이벤트 처리의 선언에 `Sub` 프로시저를 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 지정 하는 `WithEvents` 변수 및 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="9f2d1-122">이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 호출 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-122">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="9f2d1-123">코드에서 사용할 수는 `RaiseEvent` 이벤트를 발생 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="9f2d1-124">다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="9f2d1-125">이벤트 처리 `Sub` 프로시저는 한 `Handles` 절을 지정 하는 클래스와 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     <span data-ttu-id="9f2d1-126">[!code-vb[VbVbcnProcedures #&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9f2d1-126">[!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]</span></span>  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="9f2d1-127">AddHandler를 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="9f2d1-127">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="9f2d1-128">이벤트 선언 되었는지 확인 되는 `Event` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-128">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="9f2d1-129">실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트와 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-129">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="9f2d1-130">이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 호출 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-130">When the event occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="9f2d1-131">코드에서 사용할 수는 `RaiseEvent` 이벤트를 발생 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-131">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="9f2d1-132">다음 예제에서는 정의 `Sub` 를 처리 하는 절차는 <xref:System.Windows.Forms.Form.Closing>폼의 이벤트.</xref:System.Windows.Forms.Form.Closing></span><span class="sxs-lookup"><span data-stu-id="9f2d1-132">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="9f2d1-133">다음 사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing> 에 대 한 이벤트 처리기와 프로시저</span><span class="sxs-lookup"><span data-stu-id="9f2d1-133">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     <span data-ttu-id="9f2d1-134">[!code-vb[VbVbcnProcedures #&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9f2d1-134">[!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]</span></span>  
  
     <span data-ttu-id="9f2d1-135">실행 하 여 이벤트에서 이벤트 처리기를 분리할 수는 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f2d1-135">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2d1-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f2d1-136">See Also</span></span>  
 <span data-ttu-id="9f2d1-137">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d1-137">[Procedures](./index.md) </span></span>  
<span data-ttu-id="9f2d1-138"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d1-138"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="9f2d1-139"> [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d1-139"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="9f2d1-140"> [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d1-140"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="9f2d1-141"> [방법: 프로시저 만들기](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d1-141"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="9f2d1-142"> [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="9f2d1-142"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
