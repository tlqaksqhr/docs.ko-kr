---
title: ^= 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5f640-102">^= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f640-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="5f640-103">변수 또는 식의 제곱으로 속성의 값 및 변수 또는 속성에 다시 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f640-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f640-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5f640-105">요소</span><span class="sxs-lookup"><span data-stu-id="5f640-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5f640-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5f640-106">Required.</span></span> <span data-ttu-id="5f640-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5f640-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5f640-108">Required.</span></span> <span data-ttu-id="5f640-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f640-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f640-110">Remarks</span></span>  
 <span data-ttu-id="5f640-111">왼쪽에 요소는 `^=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5f640-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5f640-113">`^=` 연산자 (연산자의 오른쪽)에 식의 값의 거듭제곱으로 변수 또는 연산자의 왼쪽) (에 속성의 값을 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="5f640-114">연산자는 다음 다시 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="5f640-115">Visual Basic의 지 수를 항상 수행는 [Double 데이터 형식의](../../../visual-basic/language-reference/data-types/double-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="5f640-116">다른 형식의 피연산자 변환할 `Double`, 결과 항상 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="5f640-117">값 `expression` 소수인 수 음수, 또는 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5f640-118">오버로딩</span><span class="sxs-lookup"><span data-stu-id="5f640-118">Overloading</span></span>  
 <span data-ttu-id="5f640-119">[^ 연산자](../../../visual-basic/language-reference/operators/exponentiation-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5f640-120">오버 로드는 `^` 연산자의 동작에 영향을 줍니다는 `^=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="5f640-121">코드에서 `^=` 클래스 또는 구조체에 오버 로드에서 `^`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5f640-122">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f640-123">예제</span><span class="sxs-lookup"><span data-stu-id="5f640-123">Example</span></span>  
 <span data-ttu-id="5f640-124">다음 예제에서는 `^=` 연산자를 하나의 값 `Integer` 변수의 두 번째 변수 및 결과 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f640-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5f640-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f640-125">See Also</span></span>  
 [<span data-ttu-id="5f640-126">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="5f640-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="5f640-127">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="5f640-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="5f640-128">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="5f640-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5f640-129">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="5f640-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5f640-130">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="5f640-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5f640-131">문</span><span class="sxs-lookup"><span data-stu-id="5f640-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
