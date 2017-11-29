---
title: "Yield 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99f5129d5cb43cddfb17731f337a72fae22d3626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="3292f-102">Yield 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3292f-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="3292f-103">컬렉션의 다음 요소로 보냅니다는 `For Each...Next` 문.</span><span class="sxs-lookup"><span data-stu-id="3292f-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3292f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3292f-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3292f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3292f-105">Parameters</span></span>  
  
|<span data-ttu-id="3292f-106">용어</span><span class="sxs-lookup"><span data-stu-id="3292f-106">Term</span></span>|<span data-ttu-id="3292f-107">정의</span><span class="sxs-lookup"><span data-stu-id="3292f-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="3292f-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3292f-108">Required.</span></span> <span data-ttu-id="3292f-109">반복기 함수 형식으로 암시적으로 변환 될 수 있는 식 또는 `Get` 접근자를 포함 하는 `Yield` 문.</span><span class="sxs-lookup"><span data-stu-id="3292f-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3292f-110">설명</span><span class="sxs-lookup"><span data-stu-id="3292f-110">Remarks</span></span>  
 <span data-ttu-id="3292f-111">`Yield` 문을 한 번에 컬렉션의 요소를 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="3292f-112">`Yield` 문이 반복기 함수에 포함 되는지 또는 `Get` 컬렉션에 대해 사용자 지정 반복을 수행 하는 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="3292f-113">반복기 함수를 사용 하 여 소비는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 또는 LINQ 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="3292f-114">각 반복에서 `For Each` 루프 반복기 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="3292f-115">경우는 `Yield` 문이 반복기 함수에 도달 하면 `expression` 반환 되 고 코드에서 현재 위치는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="3292f-116">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="3292f-117">형식에서 암시적 변환이 있어야 합니다. `expression` 에 `Yield` 문을 반복기의 반환 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="3292f-118">사용할 수는 `Exit Function` 또는 `Return` 문을 반복을 끝내 세요.</span><span class="sxs-lookup"><span data-stu-id="3292f-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="3292f-119">"생성"는 예약어 아니며에 사용 되는 경우에 특별 한 의미가 있는 `Iterator` 함수 또는 `Get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="3292f-120">반복기 함수에 대 한 자세한 내용은 및 `Get` 접근자 참조 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="3292f-121">반복기 함수 및 Get 접근자</span><span class="sxs-lookup"><span data-stu-id="3292f-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="3292f-122">반복기 함수 선언 또는 `Get` 접근자에는 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="3292f-123">여기에 포함 해야 합니다는 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="3292f-124">반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="3292f-125">포함할 수 없다는 것 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="3292f-126">반복기 함수는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="3292f-127">반복기 함수는 익명 함수를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="3292f-128">자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3292f-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="3292f-129">예외 처리</span><span class="sxs-lookup"><span data-stu-id="3292f-129">Exception Handling</span></span>  
 <span data-ttu-id="3292f-130">A `Yield` 문 내에 있을 수는 `Try` 블록는 [시도 중... Catch 하는 중... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="3292f-131">A `Try` 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="3292f-132">A `Yield` 문 내에 있을 수 없습니다는 `Catch` 블록 또는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="3292f-133">경우는 `For Each` 본문 (반복기 함수) 외부 예외를 throw 하지는 `Catch` 블록에 반복기 함수가 실행 되지 않으며 하지만 `Finally` 반복기 함수에는 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="3292f-134">A `Catch` 반복기 함수 내의 블록 반복기 함수 내에서 발생 하는 예외만을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="3292f-135">기술 구현</span><span class="sxs-lookup"><span data-stu-id="3292f-135">Technical Implementation</span></span>  
 <span data-ttu-id="3292f-136">다음에는 반환 코드는 `IEnumerable (Of String)` 반복기 함수에서 다음의 요소 반복는 `IEnumerable (Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="3292f-137">에 대 한 호출 `MyIteratorFunction` 함수 본문을 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="3292f-138">대신에 `IEnumerable(Of String)` 변수에 `elements`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="3292f-139">`For Each` 루프 반복에서 <xref:System.Collections.IEnumerator.MoveNext%2A>에 대한 `elements` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="3292f-140">이 호출은 다음 `MyIteratorFunction` 문에 도달할 때까지 `Yield` 본문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="3292f-141">`Yield` 뿐만 아니라의 값을 결정 하는 식을 반환 하는 명령문은 `element` 루프 본문에서 소비 하기 위한 변수 뿐만 아니라는 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 요소, 즉는 `IEnumerable (Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="3292f-142">이후에 `For Each` 루프가 반복될 때마다 중지되었던 위치에서 반복기 본문 실행이 계속되고 `Yield` 문에 도달하면 다시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="3292f-143">`For Each` 루프를 완료 하는 경우 반복기 함수의 끝 또는 `Return` 또는 `Exit Function` 문에 도달 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3292f-144">예제</span><span class="sxs-lookup"><span data-stu-id="3292f-144">Example</span></span>  
 <span data-ttu-id="3292f-145">다음 예제에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="3292f-146">각 반복에서 [각각에 대해](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문 본문에서 `Main` 에 대 한 호출을 만듭니다는 `Power` 반복기 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="3292f-147">반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="3292f-148">반복기 메서드의 반환 형식이 <xref:System.Collections.Generic.IEnumerable%601>, 반복기 인터페이스 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="3292f-149">반복기 메서드가 호출되면 숫자의 거듭제곱이 들어 있는 열거형 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3292f-150">예제</span><span class="sxs-lookup"><span data-stu-id="3292f-150">Example</span></span>  
 <span data-ttu-id="3292f-151">다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="3292f-152">속성 선언에 포함 되어는 `Iterator` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="3292f-153">추가 예제를 참조 하십시오. [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="3292f-153">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3292f-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3292f-154">See Also</span></span>  
 [<span data-ttu-id="3292f-155">반복기</span><span class="sxs-lookup"><span data-stu-id="3292f-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="3292f-156">문</span><span class="sxs-lookup"><span data-stu-id="3292f-156">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
