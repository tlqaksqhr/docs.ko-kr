---
title: '- 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 4df8eb3844ed20fd24ca375f77cea46b9c6cee37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604317"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="0c211-102">- 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c211-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="0c211-103">두 숫자 식 또는 숫자 식의 음수 값의 차이 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c211-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c211-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="0c211-105">요소</span><span class="sxs-lookup"><span data-stu-id="0c211-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="0c211-106">필수.</span><span class="sxs-lookup"><span data-stu-id="0c211-106">Required.</span></span> <span data-ttu-id="0c211-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="0c211-108">필수 하지 않는 경우는 `–` 연산자가 음수 값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="0c211-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="0c211-110">결과</span><span class="sxs-lookup"><span data-stu-id="0c211-110">Result</span></span>  
 <span data-ttu-id="0c211-111">결과 차이 `expression1` 및 `expression2`, 또는의 부정된 값 `expression1`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="0c211-112">결과 데이터 형식이 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="0c211-113">"정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="0c211-114">지원 형식</span><span class="sxs-lookup"><span data-stu-id="0c211-114">Supported Types</span></span>  
 <span data-ttu-id="0c211-115">모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-115">All numeric types.</span></span> <span data-ttu-id="0c211-116">여기에 서명 되지 않은 부동 소수점 형식과 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c211-117">설명</span><span class="sxs-lookup"><span data-stu-id="0c211-117">Remarks</span></span>  
 <span data-ttu-id="0c211-118">이전에 나와 있는 구문에서 표시 된 첫 번째 사용에는 `–` 연산자는는 *이진* 두 숫자 식의 차이점에 대해 빼기 산술 연산자.</span><span class="sxs-lookup"><span data-stu-id="0c211-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="0c211-119">이전에 나와 있는 구문에 표시 된 두 번째 사용에서는 `–` 연산자는는 *단항* 부정 연산자는 식의 음수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="0c211-120">이러한 관점에서 부정은의 부호를 반대로 `expression1` 결과 양수 경우 `expression1` 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="0c211-121">두 식 중 하나가 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), `–` 연산자 0으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c211-122">`–` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0c211-123">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="0c211-124">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c211-125">예제</span><span class="sxs-lookup"><span data-stu-id="0c211-125">Example</span></span>  
 <span data-ttu-id="0c211-126">다음 예제에서는 `–` 계산 하 고 두 숫자 간의 차이 반환 하는 연산자 및 숫자를 부정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="0c211-127">이러한 문 실행 한 후 다음 `binaryResult` 124.45 포함 및 `unaryResult` –334.90을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c211-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c211-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c211-128">See Also</span></span>  
 <span data-ttu-id="0c211-129">[-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="0c211-129">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span></span>  
 [<span data-ttu-id="0c211-130">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0c211-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="0c211-131">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="0c211-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="0c211-132">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="0c211-132">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
