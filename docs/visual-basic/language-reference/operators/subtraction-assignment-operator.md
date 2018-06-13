---
title: -= 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 598fd9db4262d0a33bf0408ebe9455760d5e4506
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603875"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="b3353-102">-= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3353-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="b3353-103">변수 또는 속성의 값에서 식의 값을 빼고 변수 또는 속성에 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3353-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3353-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b3353-105">요소</span><span class="sxs-lookup"><span data-stu-id="b3353-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b3353-106">필수.</span><span class="sxs-lookup"><span data-stu-id="b3353-106">Required.</span></span> <span data-ttu-id="b3353-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b3353-108">필수.</span><span class="sxs-lookup"><span data-stu-id="b3353-108">Required.</span></span> <span data-ttu-id="b3353-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3353-110">설명</span><span class="sxs-lookup"><span data-stu-id="b3353-110">Remarks</span></span>  
 <span data-ttu-id="b3353-111">왼쪽에 요소는 `-=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b3353-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b3353-113">`-=` 연산자는 변수 또는 연산자의 왼쪽) (에 속성의 값에서 먼저 (연산자의 오른쪽)에 식의 값을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="b3353-114">다음 연산자는 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b3353-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="b3353-115">Overloading</span></span>  
 <span data-ttu-id="b3353-116">[-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b3353-117">오버 로드는 `-` 연산자의 동작에 영향을 줍니다는 `-=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="b3353-118">코드에서 `-=` 클래스 또는 구조체에 오버 로드에서 `-`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b3353-119">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3353-120">예제</span><span class="sxs-lookup"><span data-stu-id="b3353-120">Example</span></span>  
 <span data-ttu-id="b3353-121">다음 예제에서는 `-=` 연산자 1을 뺍니다를 `Integer` 에서 다른 변수 및 결과를 두 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3353-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b3353-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3353-122">See Also</span></span>  
 [<span data-ttu-id="b3353-123">-연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3353-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)  
 [<span data-ttu-id="b3353-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="b3353-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="b3353-125">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="b3353-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="b3353-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="b3353-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b3353-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="b3353-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b3353-128">문</span><span class="sxs-lookup"><span data-stu-id="b3353-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
