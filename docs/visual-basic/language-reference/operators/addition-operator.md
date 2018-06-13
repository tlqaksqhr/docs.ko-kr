---
title: + 연산자 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ccf79c700cf852c0febb9c3f3464cbacdd39296e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605227"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="852e3-102">+ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="852e3-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="852e3-103">두 개의 숫자를 추가 하거나 숫자 식의 양수 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="852e3-104">두 문자열 식을 연결할 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="852e3-105">구문</span><span class="sxs-lookup"><span data-stu-id="852e3-105">Syntax</span></span>  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="852e3-106">요소</span><span class="sxs-lookup"><span data-stu-id="852e3-106">Parts</span></span>  
  
|<span data-ttu-id="852e3-107">용어</span><span class="sxs-lookup"><span data-stu-id="852e3-107">Term</span></span>|<span data-ttu-id="852e3-108">정의</span><span class="sxs-lookup"><span data-stu-id="852e3-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="852e3-109">필수.</span><span class="sxs-lookup"><span data-stu-id="852e3-109">Required.</span></span> <span data-ttu-id="852e3-110">모든 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="852e3-111">필수 하지 않는 경우는 `+` 연산자가 음수 값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="852e3-112">모든 숫자 또는 문자열 식입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="852e3-113">결과</span><span class="sxs-lookup"><span data-stu-id="852e3-113">Result</span></span>  
 <span data-ttu-id="852e3-114">경우 `expression1` 및 `expression2` 가 모두 숫자인 경우 결과 산술 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="852e3-115">경우 `expression2` 없어진 경우는 `+` 연산자는는 *단항* 식의 변경 되지 않은 값에 대 한 같음 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="852e3-116">이러한 관점에서 작업의 부호를 포함 시킬 이루어져 `expression1`이므로 결과 음수 경우 `expression1` 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="852e3-117">경우 `expression1` 및 `expression2` 은 모두 문자열 결과 해당 값의 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="852e3-118">경우 `expression1` 및 `expression2` 는 혼합된 형식 중 해당 형식, 내용 및의 설정에 따라 다른 동작이 수행 된 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="852e3-119">자세한 내용은 "주의"에서 테이블을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="852e3-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="852e3-120">지원 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-120">Supported Types</span></span>  
 <span data-ttu-id="852e3-121">부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`, 및 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="852e3-122">설명</span><span class="sxs-lookup"><span data-stu-id="852e3-122">Remarks</span></span>  
 <span data-ttu-id="852e3-123">일반적으로 `+` 산술 더하기를 수행 하 고 모두 두 식이 문자열인 경우에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="852e3-124">두 식 모두 하는 경우는 `Object`, Visual Basic은 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="852e3-125">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-125">Data types of expressions</span></span>|<span data-ttu-id="852e3-126">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="852e3-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="852e3-127">두 식이 모두 숫자 데이터 형식 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, 또는 `Double`)</span><span class="sxs-lookup"><span data-stu-id="852e3-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="852e3-128">추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-128">Add.</span></span> <span data-ttu-id="852e3-129">결과 데이터 형식이 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="852e3-130">"정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="852e3-131">형식의 두 식이 모두 `String`</span><span class="sxs-lookup"><span data-stu-id="852e3-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="852e3-132">연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-132">Concatenate.</span></span>|  
|<span data-ttu-id="852e3-133">한 식이 숫자 데이터 형식이 며 다른 하나는 문자열</span><span class="sxs-lookup"><span data-stu-id="852e3-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="852e3-134">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="852e3-135">경우 `Option Strict` 은 `Off`, 암시적으로 변환의 `String` 를 `Double` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="852e3-136">경우는 `String` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="852e3-137">한 식이 숫자 데이터 형식이 며 다른 하나는 [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="852e3-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="852e3-138">에 추가 된 `Nothing` 값은 0으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="852e3-139">한 식은 문자열을 하 고 다른 하나는 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="852e3-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="852e3-140">와 concatenate `Nothing` 값으로 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="852e3-141">하나의 식이 `Object` Visual Basic 식에서 다음 동작을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="852e3-142">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-142">Data types of expressions</span></span>|<span data-ttu-id="852e3-143">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="852e3-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="852e3-144">`Object` 식이 숫자 값이 고 다른 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="852e3-145">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="852e3-146">경우 `Option Strict` 은 `Off`를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="852e3-147">`Object` 식이 숫자 값이 고 다른 형식의 `String`</span><span class="sxs-lookup"><span data-stu-id="852e3-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="852e3-148">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="852e3-149">경우 `Option Strict` 은 `Off`, 암시적으로 변환의 `String` 를 `Double` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="852e3-150">경우는 `String` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="852e3-151">`Object` 식이 문자열 고 다른 하나는 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="852e3-152">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="852e3-153">경우 `Option Strict` 은 `Off`, 다음 문자열을 암시적으로 변환 `Object` 를 `Double` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="852e3-154">경우 문자열 `Object` 변환할 수 없습니다 `Double`, 다음 throw는 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="852e3-155">`Object` 식이 문자열 하 고 다른 하나는 형식 `String`</span><span class="sxs-lookup"><span data-stu-id="852e3-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="852e3-156">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="852e3-157">경우 `Option Strict` 은 `Off`, 암시적으로 변환할 `Object` 를 `String` 을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="852e3-158">두 식이 모두 `Object` 식, Visual Basic은 다음 작업을 수행 (`Option Strict Off` 만).</span><span class="sxs-lookup"><span data-stu-id="852e3-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="852e3-159">식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="852e3-159">Data types of expressions</span></span>|<span data-ttu-id="852e3-160">컴파일러 작업</span><span class="sxs-lookup"><span data-stu-id="852e3-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="852e3-161">둘 다 `Object` 숫자 값을 사용 하는 식</span><span class="sxs-lookup"><span data-stu-id="852e3-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="852e3-162">추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-162">Add.</span></span>|  
|<span data-ttu-id="852e3-163">둘 다 `Object` 식이란 형식의 `String`</span><span class="sxs-lookup"><span data-stu-id="852e3-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="852e3-164">연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-164">Concatenate.</span></span>|  
|<span data-ttu-id="852e3-165">하나의 `Object` 식이 숫자 값 및 다른 식이 문자열</span><span class="sxs-lookup"><span data-stu-id="852e3-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="852e3-166">문자열을 암시적으로 변환할 `Object` 를 `Double` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="852e3-167">경우 문자열 `Object` throw 한 다음 숫자 값을 변환할 수 없습니다는 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="852e3-168">경우 `Object` 식이 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 <xref:System.DBNull>, `+` 연산자도 처리 한 `String` 값이 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="852e3-169">사용 하는 경우는 `+` 연산자, 더하기 또는 문자열 연결 발생 여부를 확인할 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="852e3-170">사용 된 `&` 연결에 대 한 연산자 모호성을 제거 하 고 자동 문서화 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="852e3-171">오버로딩</span><span class="sxs-lookup"><span data-stu-id="852e3-171">Overloading</span></span>  
 <span data-ttu-id="852e3-172">`+` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="852e3-173">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="852e3-174">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="852e3-175">예제</span><span class="sxs-lookup"><span data-stu-id="852e3-175">Example</span></span>  
 <span data-ttu-id="852e3-176">다음 예제에서는 `+` 덧셈 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="852e3-177">피연산자가 모두 숫자, Visual Basic 산술 결과 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="852e3-178">산술 연산 결과 두 개의 피연산자의 합계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 <span data-ttu-id="852e3-179">사용할 수도 있습니다는 `+` 문자열을 연결 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="852e3-180">피연산자가 모두 문자열, Visual Basic로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="852e3-181">연결 결과 두 피연산자의 내용을 다른 구성 된 단일 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="852e3-182">결과의 설정에 따라 피연산자가 혼합 된 형식의 경우는 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="852e3-183">다음 예제에서는 결과 때 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 <span data-ttu-id="852e3-184">다음 예제에서는 결과 때 `Option Strict` 은 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 <span data-ttu-id="852e3-185">혼동을 피하려면 사용할지는 `&` 연산자 대신 `+` 을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="852e3-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852e3-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="852e3-186">See Also</span></span>  
 [<span data-ttu-id="852e3-187">& 연산자</span><span class="sxs-lookup"><span data-stu-id="852e3-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="852e3-188">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="852e3-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="852e3-189">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="852e3-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="852e3-190">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="852e3-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="852e3-191">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="852e3-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="852e3-192">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="852e3-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="852e3-193">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="852e3-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
