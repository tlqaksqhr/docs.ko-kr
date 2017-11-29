---
title: "\\=연산자"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ba74f7a433687b306e8b4273f3a2a6d60583396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator"></a><span data-ttu-id="38e2d-102">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="38e2d-102">\\= Operator</span></span>
<span data-ttu-id="38e2d-103">변수 또는 속성의 값 식의 값으로 나누고 정수 결과 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="38e2d-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="38e2d-105">요소</span><span class="sxs-lookup"><span data-stu-id="38e2d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="38e2d-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="38e2d-106">Required.</span></span> <span data-ttu-id="38e2d-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="38e2d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="38e2d-108">Required.</span></span> <span data-ttu-id="38e2d-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38e2d-110">설명</span><span class="sxs-lookup"><span data-stu-id="38e2d-110">Remarks</span></span>  
 <span data-ttu-id="38e2d-111">왼쪽에 요소는 `\=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="38e2d-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="38e2d-113">`\=` 연산자의 오른쪽에 있는 값으로 변수 또는 왼쪽 속성의 값을 나누고 정수 결과 변수 또는 속성의 왼쪽에 할당</span><span class="sxs-lookup"><span data-stu-id="38e2d-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="38e2d-114">정수 나누기의 보다 자세한 정보를 참조 하십시오. [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="38e2d-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="38e2d-115">Overloading</span></span>  
 <span data-ttu-id="38e2d-116">`\` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="38e2d-117">오버 로드는 `\` 연산자의 동작에 영향을 줍니다는 `\=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="38e2d-118">코드에서 `\=` 클래스 또는 구조체에 오버 로드에서 `\`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="38e2d-119">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38e2d-120">예제</span><span class="sxs-lookup"><span data-stu-id="38e2d-120">Example</span></span>  
 <span data-ttu-id="38e2d-121">다음 예제에서는 `\=` 연산자 하나를 `Integer` 변수를 두 번째 및 정수 결과 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="38e2d-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="38e2d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38e2d-122">See Also</span></span>  
 [<span data-ttu-id="38e2d-123">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38e2d-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="38e2d-124">/ = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38e2d-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="38e2d-125">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="38e2d-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="38e2d-126">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="38e2d-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="38e2d-127">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="38e2d-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="38e2d-128">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="38e2d-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="38e2d-129">문</span><span class="sxs-lookup"><span data-stu-id="38e2d-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
