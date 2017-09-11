---
title: "= 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 46dc9e6018cf2ae71f1fc6dc2b8f19c2f0aadb62
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d6c13-102">= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6c13-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="d6c13-103">변수 또는 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c13-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6c13-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="d6c13-105">요소</span><span class="sxs-lookup"><span data-stu-id="d6c13-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="d6c13-106">모든 쓰기 가능한 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="d6c13-107">모든 리터럴, 상수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6c13-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6c13-108">Remarks</span></span>  
 <span data-ttu-id="d6c13-109">등호의 왼쪽에 요소 (`=`)는 단순 스칼라 변수, 속성 또는 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d6c13-110">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="d6c13-111">`=` 연산자의 왼쪽에는 속성 또는 변수는 오른쪽에 값 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6c13-112">`=` 연산자 비교 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="d6c13-113">자세한 내용은 다음을 참조 하십시오. [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d6c13-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d6c13-114">Overloading</span></span>  
 <span data-ttu-id="d6c13-115">`=` 할당 연산자가 아닌 관계 비교 연산자로 연산자를 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="d6c13-116">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6c13-117">예제</span><span class="sxs-lookup"><span data-stu-id="d6c13-117">Example</span></span>  
 <span data-ttu-id="d6c13-118">다음 예제에서는 할당 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="d6c13-119">오른쪽에 있는 값을 왼쪽에 있는 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6c13-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 <span data-ttu-id="d6c13-120">[!code-vb[VbVbalrOperators #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6c13-120">[!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c13-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6c13-121">See Also</span></span>  
 <span data-ttu-id="d6c13-122">[/ = 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-122">[&= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-123"> [* = 연산자](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-123"> [*= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-124"> [+ = 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-124"> [+= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-125"> [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-125"> [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-126"> [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-126"> [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-127"> [\\= 연산자](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-127"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-128"> [^ = 연산자](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-128"> [^= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span></span>  
<span data-ttu-id="d6c13-129"> [문](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="d6c13-130"> [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-130"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="d6c13-131"> [읽기 전용](../../../visual-basic/language-reference/modifiers/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="d6c13-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span></span>  
<span data-ttu-id="d6c13-132"> [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="d6c13-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

