---
title: Mod 연산자(Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5120823f4e001fc3aff71f267176311e2465597a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604852"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="9fa8e-102">Mod 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fa8e-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="9fa8e-103">두 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa8e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fa8e-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="9fa8e-105">요소</span><span class="sxs-lookup"><span data-stu-id="9fa8e-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="9fa8e-106">필수.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-106">Required.</span></span> <span data-ttu-id="9fa8e-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="9fa8e-108">필수.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-108">Required.</span></span> <span data-ttu-id="9fa8e-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="9fa8e-110">지원 되는 형식</span><span class="sxs-lookup"><span data-stu-id="9fa8e-110">Supported types</span></span>  
 <span data-ttu-id="9fa8e-111">모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-111">All numeric types.</span></span> <span data-ttu-id="9fa8e-112">여기에 서명 되지 않은 부동 소수점 형식과 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="9fa8e-113">결과</span><span class="sxs-lookup"><span data-stu-id="9fa8e-113">Result</span></span>

<span data-ttu-id="9fa8e-114">결과 나머지 `number1` 나눈 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="9fa8e-115">예를 들어 식 `14 Mod 4` 계산 결과 2입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="9fa8e-116">간의 차이가 *나머지* 및 *모듈러스* 수학 여 음수에 대 한 다양 한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="9fa8e-117">`Mod` Visual Basic의 경우.NET Framework에서는 연산자 `op_Modulus` 연산자 및 기본 [rem]<xref:System.Reflection.Emit.OpCodes.Rem> IL 명령의 모든 나머지 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem]<xref:System.Reflection.Emit.OpCodes.Rem> IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="9fa8e-118">결과 `Mod` 는 피제수의 부호를 유지 하는 작업 `number1`, 등과 양수 또는 음수가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="9fa8e-119">결과 항상 범위에서 (-`number2`, `number2`)을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="9fa8e-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9fa8e-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="9fa8e-121">설명</span><span class="sxs-lookup"><span data-stu-id="9fa8e-121">Remarks</span></span>  
 <span data-ttu-id="9fa8e-122">어느 경우 `number1` 또는 `number2` 는 부동 소수점 값, 부동 소수점 나누기의 나머지가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="9fa8e-123">결과의 데이터 형식이 데이터 형식으로 나눈 결과인 가능한 모든 값을 보유할 수 있는 가장 작은 데이터 형식 `number1` 및 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="9fa8e-124">경우 `number1` 또는 `number2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="9fa8e-125">관련 된 연산자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="9fa8e-126">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나누기의 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="9fa8e-127">예를 들어 식 `14 \ 4` 3으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="9fa8e-128">[/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 부동 소수점 숫자로 나머지를 포함 하 여 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="9fa8e-129">예를 들어 식 `14 / 4` 3.5로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="9fa8e-130">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="9fa8e-130">Attempted division by zero</span></span>  
 <span data-ttu-id="9fa8e-131">경우 `number2` 의 동작을 0으로 계산 되는 `Mod` 연산자는 피연산자의 데이터 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="9fa8e-132">이 정수 나누기를 throw 한 <xref:System.DivideByZeroException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="9fa8e-133">부동 소수점 나누기 반환 <xref:System.Double.NaN>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="9fa8e-134">해당 하는 수식</span><span class="sxs-lookup"><span data-stu-id="9fa8e-134">Equivalent formula</span></span>  
 <span data-ttu-id="9fa8e-135">식 `a Mod b` 다음 수식을 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="9fa8e-136">부동 소수점 연산이</span><span class="sxs-lookup"><span data-stu-id="9fa8e-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="9fa8e-137">부동 소수점 숫자를 작업할 때는 항상 없는 정확한 10 진수 표현을 메모리에서 기억 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="9fa8e-138">값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다 및 `Mod` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="9fa8e-139">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9fa8e-140">오버로딩</span><span class="sxs-lookup"><span data-stu-id="9fa8e-140">Overloading</span></span>  
 <span data-ttu-id="9fa8e-141">`Mod` 연산자 *오버 로드 된*, 클래스 또는 구조체의 동작 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="9fa8e-142">코드에 적용 되는 경우 `Mod` 클래스 또는 이러한 오버 로드를 포함 하는 구조체의 인스턴스로 사용할 다시 정의 된 동작을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9fa8e-143">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa8e-144">예제</span><span class="sxs-lookup"><span data-stu-id="9fa8e-144">Example</span></span>  
 <span data-ttu-id="9fa8e-145">다음 예제에서는 `Mod` 연산자를 두 개의 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="9fa8e-146">중 하나가 숫자가 부동 소수점 숫자 이면의 결과 나머지를 나타내는 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="9fa8e-147">예제</span><span class="sxs-lookup"><span data-stu-id="9fa8e-147">Example</span></span>  
 <span data-ttu-id="9fa8e-148">다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="9fa8e-149">피연산자는 첫 번째 문에서 `Double`, 0.2는 저장 된 값이 0.20000000000000001 인 무한 반복 이진 소수 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="9fa8e-150">두 번째 문을 리터럴 형식 문자 `D` 두 피연산자 모두 강제로 `Decimal`, 0.2에 정확한 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa8e-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9fa8e-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fa8e-151">See also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="9fa8e-152">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="9fa8e-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="9fa8e-153">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="9fa8e-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="9fa8e-154">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="9fa8e-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="9fa8e-155">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9fa8e-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="9fa8e-156">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="9fa8e-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="9fa8e-157">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fa8e-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
