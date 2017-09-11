---
title: "Yield 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="a5999-102">Yield 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5999-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="a5999-103">전송 하는 컬렉션의 다음 요소는 `For Each...Next` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5999-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5999-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5999-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5999-105">Parameters</span></span>  
  
|<span data-ttu-id="a5999-106">용어</span><span class="sxs-lookup"><span data-stu-id="a5999-106">Term</span></span>|<span data-ttu-id="a5999-107">정의</span><span class="sxs-lookup"><span data-stu-id="a5999-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="a5999-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a5999-108">Required.</span></span> <span data-ttu-id="a5999-109">반복기 함수의 형식으로 암시적으로 변환 될 수 있는 식 또는 `Get` 접근자를 포함 하는 `Yield` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5999-110">주의</span><span class="sxs-lookup"><span data-stu-id="a5999-110">Remarks</span></span>  
 <span data-ttu-id="a5999-111">`Yield` 문을 한 번에 컬렉션의 요소를 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="a5999-112">`Yield` 문이 반복기 함수에 포함 되는지 또는 `Get` 컬렉션에 대해 사용자 지정 반복을 수행 하는 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="a5999-113">반복기 함수를 사용 하 여 소비는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 또는 LINQ 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="a5999-114">각 반복에서 `For Each` 루프 반복기 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="a5999-115">때는 `Yield` 문이 반복기 함수에 도달 하면 `expression` 반환 되 고 코드에서 현재 위치는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="a5999-116">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="a5999-117">형식에서 암시적 변환이 있어야 `expression` 에 `Yield` 문을 반복기의 반환 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="a5999-118">사용할 수는 `Exit Function` 또는 `Return` 문을 반복을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="a5999-119">"생성" 예약어 아니며에 사용 될 때만 특별 한 의미가 있는 `Iterator` 함수 또는 `Get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="a5999-120">반복기 함수에 대 한 자세한 내용은 및 `Get` 접근자 참조 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="a5999-121">반복기 함수 및 Get 접근자</span><span class="sxs-lookup"><span data-stu-id="a5999-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="a5999-122">반복기 함수 선언 또는 `Get` 접근자에는 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="a5999-123">포함 해야는 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="a5999-124">반환 형식이 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="a5999-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="a5999-125">이 사용할 수 없습니다 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="a5999-126">반복기 함수는 이벤트, 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="a5999-127">반복기 함수에는 익명 함수 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="a5999-128">자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5999-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="a5999-129">예외 처리</span><span class="sxs-lookup"><span data-stu-id="a5999-129">Exception Handling</span></span>  
 <span data-ttu-id="a5999-130">A `Yield` 내부 문을 수는 `Try` 블록는 [시도... Catch... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="a5999-131">A `Try` 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="a5999-132">A `Yield` 문 내 야는 `Catch` 블록 또는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="a5999-133">하는 경우는 `For Each` 예외를 throw 하는 본문 (반복기 함수) 외부는 `Catch` 블록 반복기 함수에이 실행 되지 않으면 되지만 `Finally` 반복기 함수 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="a5999-134">A `Catch` 반복기 함수 내의 블록 반복기 함수 내 발생 하는 예외에만 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="a5999-135">기술 구현</span><span class="sxs-lookup"><span data-stu-id="a5999-135">Technical Implementation</span></span>  
 <span data-ttu-id="a5999-136">다음에는 반환 코드는 `IEnumerable (Of String)` 반복기 함수를 다음의 요소를 반복 하 고는 `IEnumerable (Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="a5999-137">에 대 한 호출 `MyIteratorFunction` 함수 본문을 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="a5999-138">대신에 `IEnumerable(Of String)` 변수에 `elements`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="a5999-139">반복에서는 `For Each` 루프는 <xref:System.Collections.IEnumerator.MoveNext%2A>에 대 한 메서드는 `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A></span><span class="sxs-lookup"><span data-stu-id="a5999-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="a5999-140">이 호출은 다음 `MyIteratorFunction` 문에 도달할 때까지 `Yield` 본문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="a5999-141">`Yield` 뿐만 아니라 값을 결정 하는 식을 반환 하는 명령문의 `element` 루프 본문에서 소비에 대 한 변수 뿐만 아니라는 <xref:System.Collections.Generic.IEnumerator%601.Current%2A>요소의 속성은 `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A></span><span class="sxs-lookup"><span data-stu-id="a5999-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="a5999-142">이후에 `For Each` 루프가 반복될 때마다 중지되었던 위치에서 반복기 본문 실행이 계속되고 `Yield` 문에 도달하면 다시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="a5999-143">`For Each` 루프 완료 될 때 반복기 함수의 끝 또는 `Return` 또는 `Exit Function` 문이 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5999-144">예제</span><span class="sxs-lookup"><span data-stu-id="a5999-144">Example</span></span>  
 <span data-ttu-id="a5999-145">다음 예제에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="a5999-146">각 반복은 [각각에 대해](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문 본문에서 `Main` 호출 하는 `Power` 반복기 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="a5999-147">반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="a5999-148">반복기 메서드의 반환 형식은 <xref:System.Collections.Generic.IEnumerable%601>, 반복기 인터페이스 형식인.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5999-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="a5999-149">반복기 메서드가 호출되면 숫자의 거듭제곱이 들어 있는 열거형 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="a5999-150">[!code-vb[VbVbalrStatements #&98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5999-150">[!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5999-151">예제</span><span class="sxs-lookup"><span data-stu-id="a5999-151">Example</span></span>  
 <span data-ttu-id="a5999-152">다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-152">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="a5999-153">속성 선언에 포함 되어 있는 `Iterator` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-153">The property declaration includes an `Iterator` modifier.</span></span>  
  
 <span data-ttu-id="a5999-154">[!code-vb[VbVbalrStatements #&99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a5999-154">[!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="a5999-155">추가 예제를 보려면 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5999-155">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5999-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5999-156">Requirements</span></span>  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5999-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5999-157">See Also</span></span>  
 <span data-ttu-id="a5999-158">[반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span><span class="sxs-lookup"><span data-stu-id="a5999-158">[Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span></span>  
<span data-ttu-id="a5999-159"> [문](../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="a5999-159"> [Statements](../../../visual-basic/language-reference/statements/index.md)</span></span>
