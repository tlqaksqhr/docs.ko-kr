---
title: Visual Basic의 연산자 및 식
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: a0f6d026714f8e933dc75dbb7c3a5e6e8e1bd795
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805450"
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="5723c-102">Visual Basic의 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="5723c-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="5723c-103">*연산자*는 값을 가지는 하나 이상의 코드 요소에서 작업을 수행하는 코드 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="5723c-104">값 요소는 변수, 상수, 리터럴, 속성을 포함하고 `Function` 및 `Operator` 프로시저와 식에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="5723c-105">*식*은 연산자와 결합된 일련의 값 요소로서, 새 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="5723c-106">연산자는 계산, 비교 또는 기타 작업을 수행하여 값 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="5723c-107">연산자 형식</span><span class="sxs-lookup"><span data-stu-id="5723c-107">Types of Operators</span></span>  
 <span data-ttu-id="5723c-108">Visual Basic에는 연산자의 다음과 같은 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-108">Visual Basic provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="5723c-109">[산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)는 비트 패턴 이동을 포함하여 숫자 값에서 친숙한 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="5723c-110">[비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)는 두 개의 식을 비교하고 비교 결과를 나타내는 `Boolean` 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="5723c-111">[연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)는 여러 문자열을 단일 문자열로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="5723c-112">[Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)는 `Boolean` 또는 숫자 값을 결합하고 값과 같은 데이터 형식의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="5723c-113">연산자와 결합된 값 요소를 해당 연산자의 *피연산자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="5723c-114">*문*을 구성하는 대입 연산자를 제외하고 값 요소와 결합된 연산자는 식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="5723c-115">자세한 내용은 [문](../../../../visual-basic/programming-guide/language-features/statements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5723c-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="5723c-116">식 평가</span><span class="sxs-lookup"><span data-stu-id="5723c-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="5723c-117">식의 최종 결과는 값을 나타냅니다. 값은 일반적으로 `Boolean`, `String` 또는 숫자 형식과 같은 친숙한 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="5723c-118">식의 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="5723c-119">다음 예제와 같은 단일 식 또는 문에서 여러 가지 연산자가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 <span data-ttu-id="5723c-120">앞의 예제에서 Visual Basic 할당 연산자의 오른쪽에는 식의 작업을 수행 (`=`), 변수에 결과 값을 할당 한 다음 `x` 왼쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-120">In the preceding example, Visual Basic performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="5723c-121">식에 결합할 수 있는 연산자 수에는 실제로 제한이 없지만 예상하는 결과를 얻으려면 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5723c-121">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
 <span data-ttu-id="5723c-122">자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx)(Visual Basic 2005의 연산자 오버로드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5723c-122">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5723c-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5723c-123">See Also</span></span>  
 [<span data-ttu-id="5723c-124">연산자</span><span class="sxs-lookup"><span data-stu-id="5723c-124">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)  
 [<span data-ttu-id="5723c-125">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="5723c-125">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [<span data-ttu-id="5723c-126">문</span><span class="sxs-lookup"><span data-stu-id="5723c-126">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
