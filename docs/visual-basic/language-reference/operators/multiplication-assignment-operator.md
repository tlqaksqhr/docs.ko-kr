---
title: '*= 연산자(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 3863e6c7416057507e8ae569804ed4a1be6a5b50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604161"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a151c-102">\*= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a151c-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="a151c-103">변수 또는 속성의 값 식의 값으로 곱하고 결과 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a151c-104">구문</span><span class="sxs-lookup"><span data-stu-id="a151c-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a151c-105">요소</span><span class="sxs-lookup"><span data-stu-id="a151c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a151c-106">필수.</span><span class="sxs-lookup"><span data-stu-id="a151c-106">Required.</span></span> <span data-ttu-id="a151c-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a151c-108">필수.</span><span class="sxs-lookup"><span data-stu-id="a151c-108">Required.</span></span> <span data-ttu-id="a151c-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a151c-110">설명</span><span class="sxs-lookup"><span data-stu-id="a151c-110">Remarks</span></span>  
 <span data-ttu-id="a151c-111">왼쪽에 요소는 `*=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a151c-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a151c-113">`*=` 연산자 변수 또는 연산자의 왼쪽) (에 속성의 값에 의해 먼저 (연산자의 오른쪽)에 식의 값을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="a151c-114">다음 연산자는 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a151c-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a151c-115">Overloading</span></span>  
 <span data-ttu-id="a151c-116">[\* 연산자](../../../visual-basic/language-reference/operators/multiplication-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a151c-117">오버 로드는 `*` 연산자의 동작에 영향을 줍니다는 `*=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="a151c-118">코드에서 `*=` 클래스 또는 구조체에 오버 로드에서 `*`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a151c-119">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a151c-120">예제</span><span class="sxs-lookup"><span data-stu-id="a151c-120">Example</span></span>  
 <span data-ttu-id="a151c-121">다음 예제에서는 `*=` 연산자를 곱하는 하나 `Integer` 변수를 두 번째 및 결과 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a151c-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a151c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a151c-122">See Also</span></span>  
 [<span data-ttu-id="a151c-123">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="a151c-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [<span data-ttu-id="a151c-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="a151c-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="a151c-125">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a151c-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="a151c-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a151c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a151c-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a151c-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a151c-128">문</span><span class="sxs-lookup"><span data-stu-id="a151c-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
