---
title: "DirectCast 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords: DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="3f0b0-102">DirectCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f0b0-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="3f0b0-103">상속 또는 구현에 따라 형식 변환 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f0b0-104">설명</span><span class="sxs-lookup"><span data-stu-id="3f0b0-104">Remarks</span></span>  
 <span data-ttu-id="3f0b0-105">`DirectCast`변환의 경우 다소을 제공할 수 있도록 런타임에 도우미 루틴 보다 뛰어난 성능을 Visual Basic을 사용 하지 않는 `CType` 데이터 형식에서 변환할 때 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="3f0b0-106">사용 된 `DirectCast` 키워드를 사용 하는 방식과 비슷합니다는 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="3f0b0-107">식을 첫 번째 인수 및 두 번째 인수로 변환 하는 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="3f0b0-108">`DirectCast`두 인수의 데이터 형식 간의 상속 또는 구현 관계를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="3f0b0-109">즉, 한 형식에서 상속 하거나, 다른 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="3f0b0-110">오류 및 실패</span><span class="sxs-lookup"><span data-stu-id="3f0b0-110">Errors and Failures</span></span>  
 <span data-ttu-id="3f0b0-111">`DirectCast`상속 또는 구현 관계 없는 있는지 검색 하는 경우 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="3f0b0-112">하지만 컴파일러 오류가 없다고 성공적인 변환을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="3f0b0-113">원하는 변환이 축소 하는 경우 런타임 시 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="3f0b0-114">이 경우 런타임에서 throw 된 <xref:System.InvalidCastException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="3f0b0-115">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="3f0b0-115">Conversion Keywords</span></span>  
 <span data-ttu-id="3f0b0-116">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="3f0b0-117">키워드</span><span class="sxs-lookup"><span data-stu-id="3f0b0-117">Keyword</span></span>|<span data-ttu-id="3f0b0-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f0b0-118">Data types</span></span>|<span data-ttu-id="3f0b0-119">인수가 관계</span><span class="sxs-lookup"><span data-stu-id="3f0b0-119">Argument relationship</span></span>|<span data-ttu-id="3f0b0-120">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="3f0b0-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="3f0b0-121">CType 함수</span><span class="sxs-lookup"><span data-stu-id="3f0b0-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="3f0b0-122">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f0b0-122">Any data types</span></span>|<span data-ttu-id="3f0b0-123">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="3f0b0-124">Throw<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="3f0b0-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="3f0b0-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f0b0-125">Any data types</span></span>|<span data-ttu-id="3f0b0-126">한 형식에서 상속 하거나 다른 형식을 구현 해야</span><span class="sxs-lookup"><span data-stu-id="3f0b0-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="3f0b0-127">Throw<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="3f0b0-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="3f0b0-128">TryCast 연산자</span><span class="sxs-lookup"><span data-stu-id="3f0b0-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="3f0b0-129">참조 형식에만</span><span class="sxs-lookup"><span data-stu-id="3f0b0-129">Reference types only</span></span>|<span data-ttu-id="3f0b0-130">한 형식에서 상속 하거나 다른 형식을 구현 해야</span><span class="sxs-lookup"><span data-stu-id="3f0b0-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="3f0b0-131">반환 [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="3f0b0-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f0b0-132">예제</span><span class="sxs-lookup"><span data-stu-id="3f0b0-132">Example</span></span>  
 <span data-ttu-id="3f0b0-133">다음 예의 두 가지 용도 `DirectCast`, 성공 하는 런타임과에 하나가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="3f0b0-134">앞의 예제에서의 실행 시간은 입력 `q` 은 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="3f0b0-135">`CType`있기 때문에 성공 `Double` 로 변환할 수 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="3f0b0-136">그러나 첫 번째 `DirectCast` 의 실행 시간을 입력 하기 때문에 런타임에 실패 `Double` 별칭과 없는 상속 관계가 `Integer`한 변환이 존재 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="3f0b0-137">두 번째 `DirectCast` 형식에서 변환 되기 때문에 성공 하면 <xref:System.Windows.Forms.Form> 입력 <xref:System.Windows.Forms.Control>, 올 <xref:System.Windows.Forms.Form> 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0b0-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0b0-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f0b0-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3f0b0-139">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="3f0b0-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="3f0b0-140">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="3f0b0-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
