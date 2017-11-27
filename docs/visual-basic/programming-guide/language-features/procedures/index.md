---
title: "Visual Basic의 프로시저"
ms.custom: 
ms.date: 04/28/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], structured code
- Visual Basic code, procedures
- procedures [Visual Basic], types of
- structured code [Visual Basic], procedures
- procedures
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5487dc7dbe9be50e065610cfd61815242bb74ac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="procedures-in-visual-basic"></a><span data-ttu-id="81119-102">Visual Basic의 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-102">Procedures in Visual Basic</span></span>
<span data-ttu-id="81119-103">*프로시저*란 선언문(`Function`, `Sub`, `Operator`, `Get`, `Set`) 및 일치하는 `End` 문으로 감싼 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문의 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="81119-103">A *procedure* is a block of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements enclosed by a declaration statement (`Function`, `Sub`, `Operator`, `Get`, `Set`) and a matching `End` declaration.</span></span> <span data-ttu-id="81119-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 모든 실행문은 프로시저 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-104">All executable statements in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must be within some procedure.</span></span>  
  
## <a name="calling-a-procedure"></a><span data-ttu-id="81119-105">프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="81119-105">Calling a Procedure</span></span>  
 <span data-ttu-id="81119-106">코드에서 다른 위치에 있는 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-106">You invoke a procedure from some other place in the code.</span></span> <span data-ttu-id="81119-107">이것을 *프로시저 호출*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-107">This is known as a *procedure call*.</span></span> <span data-ttu-id="81119-108">프로시저는 실행이 완료되면 자신을 호출한 코드(*호출 코드*라고 함)로 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-108">When the procedure is finished running, it returns control to the code that invoked it, which is known as the *calling code*.</span></span> <span data-ttu-id="81119-109">호출 코드란 프로시저를 이름으로 지정하고 프로시저에 컨트롤을 전달하는 문 또는 문 내부의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="81119-109">The calling code is a statement, or an expression within a statement, that specifies the procedure by name and transfers control to it.</span></span>  
  
## <a name="returning-from-a-procedure"></a><span data-ttu-id="81119-110">프로시저에서 반환</span><span class="sxs-lookup"><span data-stu-id="81119-110">Returning from a Procedure</span></span>  
 <span data-ttu-id="81119-111">프로시저는 실행이 완료되면 호출 코드로 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-111">A procedure returns control to the calling code when it has finished running.</span></span> <span data-ttu-id="81119-112">이를 위해 [Return 문](../../../../visual-basic/language-reference/statements/return-statement.md), 프로시저에 대한 적절한 [Exit 문](../../../../visual-basic/language-reference/statements/exit-statement.md) 또는 프로시저의 [End \<Keyword> 문](../../../../visual-basic/language-reference/statements/end-keyword-statement.md)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-112">To do this, it can use a [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), the appropriate [Exit Statement](../../../../visual-basic/language-reference/statements/exit-statement.md) statement for the procedure, or the procedure's [End \<keyword> Statement](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) statement.</span></span> <span data-ttu-id="81119-113">그러면 컨트롤이 호출 코드에서 프로시저 호출 지점 이후로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81119-113">Control then passes to the calling code following the point of the procedure call.</span></span>  
  
-   <span data-ttu-id="81119-114">`Return` 문과 함께 컨트롤이 즉시 호출 코드로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="81119-114">With a `Return` statement, control returns immediately to the calling code.</span></span> <span data-ttu-id="81119-115">`Return` 문 이후의 문은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-115">Statements following the `Return` statement do not run.</span></span> <span data-ttu-id="81119-116">동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-116">You can have more than one `Return` statement in the same procedure.</span></span>  
  
-   <span data-ttu-id="81119-117">`Exit Sub` 또는 `Exit Function` 문과 함께 컨트롤이 즉시 호출 코드로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="81119-117">With an `Exit Sub` or `Exit Function` statement, control returns immediately to the calling code.</span></span> <span data-ttu-id="81119-118">`Exit` 문 이후의 문은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-118">Statements following the `Exit` statement do not run.</span></span> <span data-ttu-id="81119-119">동일한 프로시저에 `Exit` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit` 문을 혼합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-119">You can have more than one `Exit` statement in the same procedure, and you can mix `Return` and `Exit` statements in the same procedure.</span></span>  
  
-   <span data-ttu-id="81119-120">`Return` 또는 `Exit` 문이 없는 경우 프로시저는 프로시저 본문의 마지막 문 이후에 `End Sub`나 `End Function`, `End Get`, 또는 `End Set` 문으로 마무리됩니다.</span><span class="sxs-lookup"><span data-stu-id="81119-120">If a procedure has no `Return` or `Exit` statements, it concludes with an `End Sub` or `End Function`, `End Get`, or `End Set` statement following the last statement of the procedure body.</span></span> <span data-ttu-id="81119-121">`End` 문은 컨트롤을 호출 코드에 즉시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-121">The `End` statement returns control immediately to the calling code.</span></span> <span data-ttu-id="81119-122">프로시저에 `End` 문을 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-122">You can have only one `End` statement in a procedure.</span></span>  
  
## <a name="parameters-and-arguments"></a><span data-ttu-id="81119-123">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="81119-123">Parameters and Arguments</span></span>  
 <span data-ttu-id="81119-124">대부분의 경우 프로시저는 사용자가 호출할 때마다 다른 데이터에서 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-124">In most cases, a procedure needs to operate on different data each time you call it.</span></span> <span data-ttu-id="81119-125">프로시저 호출의 일부로 이 정보를 프로시저에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-125">You can pass this information to the procedure as part of the procedure call.</span></span> <span data-ttu-id="81119-126">프로시저는 0개 이상의 *매개 변수*를 정의하며, 각 매개 변수는 사용자가 전달할 것으로 예상하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81119-126">The procedure defines zero or more *parameters*, each of which represents a value it expects you to pass to it.</span></span> <span data-ttu-id="81119-127">프로시저 정의의 각 매개 변수에 해당하는 것이 프로시저 호출의 *인수*입니다.</span><span class="sxs-lookup"><span data-stu-id="81119-127">Corresponding to each parameter in the procedure definition is an *argument* in the procedure call.</span></span> <span data-ttu-id="81119-128">인수는 지정된 프로시저 호출에서 해당 매개 변수에 전달하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81119-128">An argument represents the value you pass to the corresponding parameter in a given procedure call.</span></span>  
  
## <a name="types-of-procedures"></a><span data-ttu-id="81119-129">프로시저 유형</span><span class="sxs-lookup"><span data-stu-id="81119-129">Types of Procedures</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="81119-130">은 여러 유형의 프로시저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-130"> uses several types of procedures:</span></span>  
  
-   <span data-ttu-id="81119-131">[Sub 프로시저](./sub-procedures.md)는 작업을 수행하지만 호출 코드에 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-131">[Sub Procedures](./sub-procedures.md) perform actions but do not return a value to the calling code.</span></span>  
  
-   <span data-ttu-id="81119-132">이벤트 처리 프로시저는 사용자 작업에 의해 발생하거나 프로그램에서 발생하는 이벤트에 대한 응답으로 실행되는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="81119-132">Event-handling procedures are `Sub` procedures that execute in response to an event raised by user action or by an occurrence in a program.</span></span>  
  
-   <span data-ttu-id="81119-133">[Function 프로시저](./function-procedures.md)는 호출 코드에 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-133">[Function Procedures](./function-procedures.md) return a value to the calling code.</span></span> <span data-ttu-id="81119-134">반환하기 전에 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-134">They can perform other actions before returning.</span></span>

    <span data-ttu-id="81119-135">C#으로 작성된 일부 함수는 *참조 반환 값*을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-135">Some functions written in C# return a *reference return value*.</span></span> <span data-ttu-id="81119-136">함수 호출자는 반환 값을 수정할 수 있으며, 이 수정은 호출된 개체의 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="81119-136">Function callers can modify the return value, and this modification is reflected in the state of the called object.</span></span> <span data-ttu-id="81119-137">Visual Basic 2017부터 Visual Basic 코드는 참조 반환 값을 사용할 수는 있지만, 값을 참조로 반환할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-137">Starting with Visual Basic 2017, Visual Basic code can consume reference return values, although it cannot return a value by reference.</span></span> <span data-ttu-id="81119-138">자세한 내용은 [참조 반환 값](ref-return-values.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81119-138">For more information, see [Reference return values](ref-return-values.md).</span></span>
  
-   <span data-ttu-id="81119-139">[Property 프로시저](./property-procedures.md)는 개체 및 모듈에 대한 속성 값을 반환하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-139">[Property Procedures](./property-procedures.md) return and assign values of properties on objects or modules.</span></span>  
  
-   <span data-ttu-id="81119-140">[Operator 프로시저](./operator-procedures.md)는 피연산자 중 하나 또는 둘 모두가 새로 정의된 클래스 또는 구조일 때 표준 연산자의 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-140">[Operator Procedures](./operator-procedures.md) define the behavior of a standard operator when one or both of the operands is a newly-defined class or structure.</span></span>  
  
-   <span data-ttu-id="81119-141">호출 코드가 호출할 때마다 특정 데이터 유형을 전달할 수 있도록, [Visual Basic의 제네릭 프로시저](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)는 일반 매개 변수 외에도 하나 이상의 *형식 매개 변수*를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-141">[Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) define one or more *type parameters* in addition to their normal parameters, so the calling code can pass specific data types each time it makes a call.</span></span>  
  
## <a name="procedures-and-structured-code"></a><span data-ttu-id="81119-142">프로시저 및 구조적 코드</span><span class="sxs-lookup"><span data-stu-id="81119-142">Procedures and Structured Code</span></span>  
 <span data-ttu-id="81119-143">응용 프로그램의 각 실행 코드 줄은 `Main`, `calculate` 또는 `Button1_Click` 등의 프로시저 내부에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-143">Every line of executable code in your application must be inside some procedure, such as `Main`, `calculate`, or `Button1_Click`.</span></span> <span data-ttu-id="81119-144">큰 프로시저를 더 작은 프로시저로 세분화하면 응용 프로그램을 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-144">If you subdivide large procedures into smaller ones, your application is more readable.</span></span>  
  
 <span data-ttu-id="81119-145">프로시저는 자주 사용되는 계산, 텍스트와 컨트롤 조작, 데이터베이스 작업 등의 반복 또는 공유 작업을 수행하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-145">Procedures are useful for performing repeated or shared tasks, such as frequently used calculations, text and control manipulation, and database operations.</span></span> <span data-ttu-id="81119-146">코드의 여러 위치에서 프로시저를 호출할 수 있으므로 프로시저를 응용 프로그램의 빌딩 블록으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-146">You can call a procedure from many different places in your code, so you can use procedures as building blocks for your application.</span></span>  
  
 <span data-ttu-id="81119-147">프로시저로 코드의 구조를 만들면 다음과 같은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-147">Structuring your code with procedures gives you the following benefits:</span></span>  
  
-   <span data-ttu-id="81119-148">프로시저를 사용하여 프로그램을 개별 논리 단위로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-148">Procedures allow you to break your programs into discrete logical units.</span></span> <span data-ttu-id="81119-149">프로시저 없이 전체 프로그램을 디버그하는 것보다는 개별 단위를 디버그하는 것이 더 수월합니다.</span><span class="sxs-lookup"><span data-stu-id="81119-149">You can debug separate units more easily than you can debug an entire program without procedures.</span></span>  
  
-   <span data-ttu-id="81119-150">한 프로그램에서 사용하기 위해 프로시저를 개발한 후, 거의 또는 전혀 수정하지 않고 종종 다른 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-150">After you develop procedures for use in one program, you can use them in other programs, often with little or no modification.</span></span> <span data-ttu-id="81119-151">이를 통해 코드 중복을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81119-151">This helps you avoid code duplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81119-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81119-152">See Also</span></span>  
 [<span data-ttu-id="81119-153">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="81119-153">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="81119-154">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-154">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="81119-155">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-155">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="81119-156">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-156">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="81119-157">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-157">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="81119-158">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="81119-158">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="81119-159">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-159">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="81119-160">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="81119-160">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="81119-161">Visual Basic의 제네릭 프로시저</span><span class="sxs-lookup"><span data-stu-id="81119-161">Generic Procedures in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="81119-162">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="81119-162">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
