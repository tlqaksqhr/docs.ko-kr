---
title: "방법: 숫자 값 계산 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe781cca8f716c792d3af153b2004c716bc87f90
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="5b40b-102">방법: 숫자 값 계산(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b40b-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="5b40b-103">숫자 식 사용 하 여 숫자 값을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="5b40b-104">A *숫자 식* 리터럴, 상수 및 숫자 값을 나타내는 변수를 포함 하는 식을 이며 해당 값에 대해 작동 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="5b40b-105">숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="5b40b-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="5b40b-106">숫자 값을 계산 하려면</span><span class="sxs-lookup"><span data-stu-id="5b40b-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="5b40b-107">숫자 식으로 하나 이상의 숫자 리터럴, 상수 및 변수를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="5b40b-108">다음 예제에는 유효한 숫자 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="5b40b-109">처음 세 줄은 리터럴, 상수 및 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="5b40b-110">각 자체적으로 유효한 숫자 식을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="5b40b-111">마지막 줄의 두 가지 리터럴 사용 하 여 변수 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="5b40b-112">참고 숫자 식 전체 형성 하지 않습니다 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자체적으로 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statement by itself.</span></span> <span data-ttu-id="5b40b-113">전체 문의 일부로 식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="5b40b-114">숫자 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="5b40b-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="5b40b-115">다음 예제 에서처럼 변수에 숫자 식을 사용 하 여 표시 되는 값을 할당 하는 대입문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     <span data-ttu-id="5b40b-116">[!code-vb[VbVbalrOperators #&82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b40b-116">[!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span></span>  
  
     <span data-ttu-id="5b40b-117">위의 예제에서는 같음 연산자의 오른쪽에 있는 식의 값 (`=`) 변수에 할당 `j` 연산자의 왼쪽에 있으므로 `j` 276으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="5b40b-118">자세한 내용은 참조 [문을](../../../../visual-basic/language-reference/statements/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-118">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="5b40b-119">여러 명의 연산자</span><span class="sxs-lookup"><span data-stu-id="5b40b-119">Multiple Operators</span></span>  
 <span data-ttu-id="5b40b-120">숫자 식에 하나 이상의 연산자, 평가 되는 순서는 연산자 우선 순위 규칙에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="5b40b-121">식 위의 예와 괄호로 묶어 있습니다의 연산자 우선 순위 규칙을 재정의 하려면 괄호 안의 식이 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="5b40b-122">일반 연산자 우선 순위를 재정의 하려면</span><span class="sxs-lookup"><span data-stu-id="5b40b-122">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="5b40b-123">괄호를 사용 하 여 먼저 수행 하려는 작업을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="5b40b-124">다음 예제에서는 동일한 연산자와 피연산자와 두 개의 서로 다른 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     <span data-ttu-id="5b40b-125">[!code-vb[VbVbalrOperators #&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b40b-125">[!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span></span>  
  
     <span data-ttu-id="5b40b-126">앞의 예제에 대 한 계산에서 `j` 더하기 연산자를 수행 (`+`) 첫 번째 때문에 괄호로 `(67 + i)` 일반 우선 순위에 할당 된 값을 재정의 `j` 은 276 (4 회 69).</span><span class="sxs-lookup"><span data-stu-id="5b40b-126">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="5b40b-127">에 대 한 계산 `k` 일반 우선 순위에 연산자를 수행 하므로 (`*` 하기 전에 `+`), 및에 할당 된 값 `k` 은 270 (268 + 2).</span><span class="sxs-lookup"><span data-stu-id="5b40b-127">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="5b40b-128">자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b40b-128">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b40b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b40b-129">See Also</span></span>  
 <span data-ttu-id="5b40b-130">[연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="5b40b-130">[Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="5b40b-131"> [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="5b40b-131"> [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="5b40b-132"> [문](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="5b40b-132"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="5b40b-133"> [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="5b40b-133"> [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="5b40b-134"> [산술 연산자](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="5b40b-134"> [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="5b40b-135"> [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="5b40b-135"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
