---
title: "-= 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: 694033ec89e32b5fdba4092bd60292af536f58dd
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="e73b2-102">-= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e73b2-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="e73b2-103">변수 또는 속성의 값에서 식의 값을 빼고 변수 또는 속성에 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="e73b2-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="e73b2-105">요소</span><span class="sxs-lookup"><span data-stu-id="e73b2-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e73b2-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e73b2-106">Required.</span></span> <span data-ttu-id="e73b2-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="e73b2-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e73b2-108">Required.</span></span> <span data-ttu-id="e73b2-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e73b2-110">주의</span><span class="sxs-lookup"><span data-stu-id="e73b2-110">Remarks</span></span>  
 <span data-ttu-id="e73b2-111">왼쪽에는 요소는 `-=` 연산자는 단순 스칼라 변수, 속성 또는 배열의 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e73b2-112">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="e73b2-113">`-=` 연산자는 변수 또는 연산자의 왼쪽) (에 대 한 속성의 값에서 먼저 (연산자의 오른쪽)에 대 한 식의 값을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="e73b2-114">연산자는 다음 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e73b2-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="e73b2-115">Overloading</span></span>  
 <span data-ttu-id="e73b2-116">[-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e73b2-117">오버 로드는 `-` 연산자의 동작에 영향을 줍니다는 `-=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="e73b2-118">코드를 사용 하는 경우 `-=` 클래스 또는 구조체에 오버 로드에서 `-`, 다시 정의 된 동작을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e73b2-119">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e73b2-120">예제</span><span class="sxs-lookup"><span data-stu-id="e73b2-120">Example</span></span>  
 <span data-ttu-id="e73b2-121">다음 예제에서는 `-=` 연산자를 빼면 `Integer` 에서 다른 변수 및 결과를 두 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e73b2-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 <span data-ttu-id="e73b2-122">[!code-vb[VbVbalrOperators #&11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e73b2-122">[!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73b2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e73b2-123">See Also</span></span>  
 <span data-ttu-id="e73b2-124">[-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span><span class="sxs-lookup"><span data-stu-id="e73b2-124">[- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span></span>  
<span data-ttu-id="e73b2-125"> [대입 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="e73b2-125"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="e73b2-126"> [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="e73b2-126"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="e73b2-127"> [Visual Basic의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="e73b2-127"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="e73b2-128"> [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="e73b2-128"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="e73b2-129"> [문](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="e73b2-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

