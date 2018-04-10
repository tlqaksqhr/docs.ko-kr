---
title: Visual Basic의 연산자 및 식
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dae47988e27ed4b1a714943ce1fbffe3b815066b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="24477-102">Visual Basic의 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="24477-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="24477-103">*연산자*는 값을 가지는 하나 이상의 코드 요소에서 작업을 수행하는 코드 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="24477-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="24477-104">값 요소는 변수, 상수, 리터럴, 속성을 포함하고 `Function` 및 `Operator` 프로시저와 식에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="24477-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="24477-105">*식*은 연산자와 결합된 일련의 값 요소로서, 새 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="24477-106">연산자는 계산, 비교 또는 기타 작업을 수행하여 값 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24477-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="24477-107">연산자 형식</span><span class="sxs-lookup"><span data-stu-id="24477-107">Types of Operators</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="24477-108">에서는 다음과 같은 연산자 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-108"> provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="24477-109">[산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)는 비트 패턴 이동을 포함하여 숫자 값에서 친숙한 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="24477-110">[비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)는 두 개의 식을 비교하고 비교 결과를 나타내는 `Boolean` 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="24477-111">[연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)는 여러 문자열을 단일 문자열로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="24477-112">[Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)는 `Boolean` 또는 숫자 값을 결합하고 값과 같은 데이터 형식의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="24477-113">연산자와 결합된 값 요소를 해당 연산자의 *피연산자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="24477-114">*문*을 구성하는 대입 연산자를 제외하고 값 요소와 결합된 연산자는 식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="24477-115">자세한 내용은 [문](../../../../visual-basic/programming-guide/language-features/statements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24477-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="24477-116">식 평가</span><span class="sxs-lookup"><span data-stu-id="24477-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="24477-117">식의 최종 결과는 값을 나타냅니다. 값은 일반적으로 `Boolean`, `String` 또는 숫자 형식과 같은 친숙한 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="24477-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="24477-118">식의 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24477-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="24477-119">다음 예제와 같은 단일 식 또는 문에서 여러 가지 연산자가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24477-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 <span data-ttu-id="24477-120">이전 예제에서 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]은 대입 연산자(`=`)의 오른쪽에 있는 식에서 작업을 수행하고 나서 결과 값을 왼쪽의 변수 `x`에 대입합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-120">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="24477-121">식에 결합할 수 있는 연산자 수에는 실제로 제한이 없지만 예상하는 결과를 얻으려면 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24477-121">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
 <span data-ttu-id="24477-122">자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)(Visual Basic 2005의 연산자 오버로드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24477-122">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24477-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24477-123">See Also</span></span>  
 [<span data-ttu-id="24477-124">연산자</span><span class="sxs-lookup"><span data-stu-id="24477-124">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)  
 [<span data-ttu-id="24477-125">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="24477-125">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [<span data-ttu-id="24477-126">문</span><span class="sxs-lookup"><span data-stu-id="24477-126">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
