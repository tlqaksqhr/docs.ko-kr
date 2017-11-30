---
title: "반복기(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="652a1-102">반복기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="652a1-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="652a1-103">지정 하는 함수 또는 `Get` 접근자가 반복기입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="652a1-104">설명</span><span class="sxs-lookup"><span data-stu-id="652a1-104">Remarks</span></span>  
 <span data-ttu-id="652a1-105">*반복기* 컬렉션 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="652a1-106">반복기를 사용 하 여는 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 하나씩 컬렉션의 각 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="652a1-107">경우는 `Yield` 문에 도달 하면, 코드에서 현재 위치는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="652a1-108">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="652a1-109">반복기 또는 함수로 구현할 수 있습니다는 `Get` 속성 정의의 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="652a1-110">`Iterator` 반복기 함수의 선언에 한정자 표시 또는 `Get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="652a1-111">사용 하 여 클라이언트 코드에서 반복기를 호출는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="652a1-112">반복기 함수의 반환 형식 또는 `Get` 접근자 수 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="652a1-113">반복기를 사용할 수 없습니다 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="652a1-114">반복기는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="652a1-115">반복기는 익명 함수 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="652a1-116">자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="652a1-116">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="652a1-117">반복기에 대한 자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="652a1-117">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="652a1-118">용도</span><span class="sxs-lookup"><span data-stu-id="652a1-118">Usage</span></span>  
 <span data-ttu-id="652a1-119">`Iterator` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="652a1-120">Function 문</span><span class="sxs-lookup"><span data-stu-id="652a1-120">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="652a1-121">Property 문</span><span class="sxs-lookup"><span data-stu-id="652a1-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="652a1-122">예제</span><span class="sxs-lookup"><span data-stu-id="652a1-122">Example</span></span>  
 <span data-ttu-id="652a1-123">다음 예제에서는 반복기 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="652a1-124">반복기 함수에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-124">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="652a1-125">각 반복에서 [각각에 대해](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문 본문에서 `Main` 에 대 한 호출을 만듭니다는 `Power` 반복기 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-125">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="652a1-126">반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="652a1-127">예제</span><span class="sxs-lookup"><span data-stu-id="652a1-127">Example</span></span>  
 <span data-ttu-id="652a1-128">다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="652a1-129">`Iterator` 한정자는 속성 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="652a1-130">추가 예제를 참조 하십시오. [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="652a1-130">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652a1-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="652a1-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="652a1-132">반복기</span><span class="sxs-lookup"><span data-stu-id="652a1-132">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="652a1-133">Yield 문</span><span class="sxs-lookup"><span data-stu-id="652a1-133">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
