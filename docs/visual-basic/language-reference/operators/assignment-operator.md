---
title: = 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603602"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="73c99-102">= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73c99-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="73c99-103">변수 또는 속성에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c99-104">구문</span><span class="sxs-lookup"><span data-stu-id="73c99-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="73c99-105">요소</span><span class="sxs-lookup"><span data-stu-id="73c99-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="73c99-106">모든 쓰기 가능한 변수 또는 모든 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="73c99-107">모든 리터럴, 상수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73c99-108">설명</span><span class="sxs-lookup"><span data-stu-id="73c99-108">Remarks</span></span>  
 <span data-ttu-id="73c99-109">등호 기호 왼쪽에 요소 (`=`)는 단순 스칼라 변수, 속성 또는 배열의 요소 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="73c99-110">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="73c99-111">`=` 연산자의 왼쪽에는 속성 또는 변수는 오른쪽에 값 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73c99-112">`=` 연산자는도 비교 연산자로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="73c99-113">자세한 내용은 참조 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="73c99-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="73c99-114">Overloading</span></span>  
 <span data-ttu-id="73c99-115">`=` 할당 연산자가 아닌 관계 비교 연산자로 연산자를 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="73c99-116">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c99-117">예제</span><span class="sxs-lookup"><span data-stu-id="73c99-117">Example</span></span>  
 <span data-ttu-id="73c99-118">다음 예제에서는 할당 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="73c99-119">오른쪽에 있는 값을 왼쪽에 있는 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c99-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="73c99-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73c99-120">See Also</span></span>  
 [<span data-ttu-id="73c99-121">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="73c99-122">\*= 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="73c99-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="73c99-124">-= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73c99-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="73c99-125">/ = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73c99-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="73c99-126">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="73c99-127">^= 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="73c99-128">문</span><span class="sxs-lookup"><span data-stu-id="73c99-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="73c99-129">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="73c99-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="73c99-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="73c99-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="73c99-131">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="73c99-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
