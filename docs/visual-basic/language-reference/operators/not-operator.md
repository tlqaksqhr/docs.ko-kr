---
title: Not 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="a20b4-102">Not 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a20b4-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="a20b4-103">논리 부정을 수행는 `Boolean` 식 또는 숫자 식에 비트 부정을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a20b4-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a20b4-105">요소</span><span class="sxs-lookup"><span data-stu-id="a20b4-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a20b4-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a20b4-106">Required.</span></span> <span data-ttu-id="a20b4-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="a20b4-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a20b4-108">Required.</span></span> <span data-ttu-id="a20b4-109">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a20b4-110">설명</span><span class="sxs-lookup"><span data-stu-id="a20b4-110">Remarks</span></span>  
 <span data-ttu-id="a20b4-111">에 대 한 `Boolean` 식, 다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a20b4-112">경우 `expression` 은</span><span class="sxs-lookup"><span data-stu-id="a20b4-112">If `expression` is</span></span>|<span data-ttu-id="a20b4-113">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="a20b4-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="a20b4-114">숫자 식에 대 한는 `Not` 임의의 숫자 식의 비트 값을 반전 하 고의 해당 비트를 설정 하는 연산자 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="a20b4-115">경우에 비트 `expression` 은</span><span class="sxs-lookup"><span data-stu-id="a20b4-115">If bit in `expression` is</span></span>|<span data-ttu-id="a20b4-116">에 있는 비트 `result` 은</span><span class="sxs-lookup"><span data-stu-id="a20b4-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="a20b4-117">1</span><span class="sxs-lookup"><span data-stu-id="a20b4-117">1</span></span>|<span data-ttu-id="a20b4-118">0</span><span class="sxs-lookup"><span data-stu-id="a20b4-118">0</span></span>|  
|<span data-ttu-id="a20b4-119">0</span><span class="sxs-lookup"><span data-stu-id="a20b4-119">0</span></span>|<span data-ttu-id="a20b4-120">1</span><span class="sxs-lookup"><span data-stu-id="a20b4-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a20b4-121">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a20b4-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a20b4-122">Data Types</span></span>  
 <span data-ttu-id="a20b4-123">부울 부정에 대 한 데이터의 결과 형식이 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="a20b4-124">비트 부정에 대 한 결과 데이터 형식이 구문과 같습니다 `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="a20b4-125">그러나 식이 `Decimal`, 결과 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a20b4-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a20b4-126">Overloading</span></span>  
 <span data-ttu-id="a20b4-127">`Not` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="a20b4-128">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a20b4-129">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20b4-130">예제</span><span class="sxs-lookup"><span data-stu-id="a20b4-130">Example</span></span>  
 <span data-ttu-id="a20b4-131">다음 예제에서는 `Not` 에 논리 부정을 수행 하는 연산자는 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="a20b4-132">결과는 `Boolean` 식의 값의 역순을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="a20b4-133">앞 예제의 결과는 `False` 및 `True`각각.</span><span class="sxs-lookup"><span data-stu-id="a20b4-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20b4-134">예제</span><span class="sxs-lookup"><span data-stu-id="a20b4-134">Example</span></span>  
 <span data-ttu-id="a20b4-135">다음 예제에서는 `Not` 숫자 식의 개별 비트의 논리 부정을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="a20b4-136">결과 패턴의 비트는 부호 비트를 포함 하 여 피연산자 패턴에 해당 비트의 역순으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="a20b4-137">앞의 예제는 각각 – 11, – 9,-7의 결과 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a20b4-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20b4-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a20b4-138">See Also</span></span>  
 [<span data-ttu-id="a20b4-139">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a20b4-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="a20b4-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a20b4-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a20b4-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a20b4-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a20b4-142">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="a20b4-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
