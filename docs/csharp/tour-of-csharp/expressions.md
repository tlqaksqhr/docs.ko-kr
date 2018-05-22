---
title: C# 식 - C# 언어 둘러보기
description: 식, 피연산자 및 연산자는 C# 언어의 기본 구성 요소입니다.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 8fa1c5d0464644b26eb457bca8ecaf007c288f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="expressions"></a><span data-ttu-id="342bd-103">식</span><span class="sxs-lookup"><span data-stu-id="342bd-103">Expressions</span></span>

<span data-ttu-id="342bd-104">*식*은 *피연산자* 및 *연산자*로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="342bd-105">식의 연산자는 피연산자에 적용할 연산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="342bd-106">연산자의 예로 `+`, `-`, `*`, `/` 및 `new`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="342bd-107">피연산자의 예로는 리터럴, 필드, 지역 변수 및 식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="342bd-108">식에 여러 연산자가 포함되어 있으면 연산자의 *우선 순위*에 따라 개별 연산자가 계산되는 순서가 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="342bd-109">예를 들어 `*` 연산자는 `+` 연산자보다 우선 순위가 더 높기 때문에 식 `x + y * z`는 `x + (y * z)`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="342bd-110">피연산자는 동일한 우선 순위를 가진 두 연산자 사이에 나올 경우 연산자의 *결합성*에 따라 연산이 수행되는 순서가 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="342bd-111">대입 연산자를 제외하고 모든 이항 연산자는 *왼쪽 결합성*을 갖습니다. 즉, 연산이 왼쪽에서 오른쪽으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="342bd-112">예를 들어, `x + y + z`는 `(x + y) + z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="342bd-113">대입 연산자 및 조건부 연산자(`?:`)는 *오른쪽 결합성*을 갖습니다. 즉, 연산이 오른쪽에서 왼쪽으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="342bd-114">예를 들어, `x = y = z`는 `x = (y = z)`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="342bd-115">우선 순위 및 결합성은 괄호를 사용하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="342bd-116">예를 들어 `x + y * z`는 먼저 `y`와 `z`를 곱한 다음 그 결과를 `x`와 더하지만 `(x + y) * z`는 먼저 `x`와 `y`를 더한 다음 그 결과에 `z`를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="342bd-117">대부분의 연산자는 *오버로드*할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="342bd-118">연산자 오버로드는 피연산자 중 하나 또는 둘 다가 사용자 정의 클래스 또는 구조체 형식인 연산에 대해 사용자 정의 연산자 구현을 지정할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="342bd-119">다음에서는 C# 연산자를 요약하고 가장 높은 우선 순위부터 연산자 범주를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="342bd-120">동일한 범주의 연산자는 우선 순위가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="342bd-121">각 범주 아래에는 해당 범주의 식 목록과 해당 식 형식에 대한 설명이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="342bd-122">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="342bd-122">Primary</span></span>
    - <span data-ttu-id="342bd-123">`x.m`: 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="342bd-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="342bd-124">`x(...)`: 메서드 및 대리자 호출</span><span class="sxs-lookup"><span data-stu-id="342bd-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="342bd-125">`x[...]`: 배열 및 인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="342bd-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="342bd-126">`x++`: 후위 증가</span><span class="sxs-lookup"><span data-stu-id="342bd-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="342bd-127">`x--`: 후위 감소</span><span class="sxs-lookup"><span data-stu-id="342bd-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="342bd-128">`new T(...)`: 개체 및 대리자 생성</span><span class="sxs-lookup"><span data-stu-id="342bd-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="342bd-129">`new T(...){...}`: 이니셜라이저를 사용한 개체 생성</span><span class="sxs-lookup"><span data-stu-id="342bd-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="342bd-130">`new {...}`: 익명 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="342bd-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="342bd-131">`new T[...]`: 배열 생성</span><span class="sxs-lookup"><span data-stu-id="342bd-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="342bd-132">`typeof(T)`: `T`에 대한 <xref:System.Type> 개체 가져오기</span><span class="sxs-lookup"><span data-stu-id="342bd-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="342bd-133">`checked(x)`: checked 컨텍스트에서 식 계산</span><span class="sxs-lookup"><span data-stu-id="342bd-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="342bd-134">`unchecked(x)`: unchecked 컨텍스트에서 식 계산</span><span class="sxs-lookup"><span data-stu-id="342bd-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="342bd-135">`default(T)`: `T` 형식의 기본값 가져오기</span><span class="sxs-lookup"><span data-stu-id="342bd-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="342bd-136">`delegate {...}`: 익명 함수(무명 메서드)</span><span class="sxs-lookup"><span data-stu-id="342bd-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="342bd-137">단항</span><span class="sxs-lookup"><span data-stu-id="342bd-137">Unary</span></span>
    - <span data-ttu-id="342bd-138">`+x`: ID</span><span class="sxs-lookup"><span data-stu-id="342bd-138">`+x`: Identity</span></span>
    - <span data-ttu-id="342bd-139">`-x`: 부정</span><span class="sxs-lookup"><span data-stu-id="342bd-139">`-x`: Negation</span></span>
    - <span data-ttu-id="342bd-140">`!x`: 논리 부정</span><span class="sxs-lookup"><span data-stu-id="342bd-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="342bd-141">`~x`: 비트 부정 연산</span><span class="sxs-lookup"><span data-stu-id="342bd-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="342bd-142">`++x`: 전위 증가</span><span class="sxs-lookup"><span data-stu-id="342bd-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="342bd-143">`--x`: 전위 감소</span><span class="sxs-lookup"><span data-stu-id="342bd-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="342bd-144">`(T)x`: `x`를 `T` 형식으로 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="342bd-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="342bd-145">`await x`: 비동기적으로 `x` 완료 대기</span><span class="sxs-lookup"><span data-stu-id="342bd-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="342bd-146">곱하기</span><span class="sxs-lookup"><span data-stu-id="342bd-146">Multiplicative</span></span>
    - <span data-ttu-id="342bd-147">`x * y`: 곱하기</span><span class="sxs-lookup"><span data-stu-id="342bd-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="342bd-148">`x / y`: 나누기</span><span class="sxs-lookup"><span data-stu-id="342bd-148">`x / y`: Division</span></span>
    - <span data-ttu-id="342bd-149">`x % y`: 나머지</span><span class="sxs-lookup"><span data-stu-id="342bd-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="342bd-150">더하기</span><span class="sxs-lookup"><span data-stu-id="342bd-150">Additive</span></span>
    - <span data-ttu-id="342bd-151">`x + y`: 더하기, 문자열 연결, 대리자 결합</span><span class="sxs-lookup"><span data-stu-id="342bd-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="342bd-152">`x – y`: 빼기, 대리자 제거</span><span class="sxs-lookup"><span data-stu-id="342bd-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="342bd-153">시프트</span><span class="sxs-lookup"><span data-stu-id="342bd-153">Shift</span></span>
    - <span data-ttu-id="342bd-154">`x << y`: 왼쪽 시프트</span><span class="sxs-lookup"><span data-stu-id="342bd-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="342bd-155">`x >> y`: 오른쪽 시프트</span><span class="sxs-lookup"><span data-stu-id="342bd-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="342bd-156">관계형 및 형식 테스트</span><span class="sxs-lookup"><span data-stu-id="342bd-156">Relational and type testing</span></span>
    - <span data-ttu-id="342bd-157">`x < y`: 보다 작음</span><span class="sxs-lookup"><span data-stu-id="342bd-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="342bd-158">`x > y`: 보다 큼</span><span class="sxs-lookup"><span data-stu-id="342bd-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="342bd-159">`x <= y`: 작거나 같음</span><span class="sxs-lookup"><span data-stu-id="342bd-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="342bd-160">`x >= y`: 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="342bd-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="342bd-161">`x is T`: `x`가 `T`이면 `true` 반환, 그렇지 않으면 `false` 반환</span><span class="sxs-lookup"><span data-stu-id="342bd-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="342bd-162">`x as T`: `T`로 형식이 지정된 `x` 반환, `x`가 `T`가 아닌 경우 `null` 반환</span><span class="sxs-lookup"><span data-stu-id="342bd-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="342bd-163">같음</span><span class="sxs-lookup"><span data-stu-id="342bd-163">Equality</span></span>
    - <span data-ttu-id="342bd-164">`x == y`: 같음</span><span class="sxs-lookup"><span data-stu-id="342bd-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="342bd-165">`x != y`: 같지 않음</span><span class="sxs-lookup"><span data-stu-id="342bd-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="342bd-166">논리적 AND</span><span class="sxs-lookup"><span data-stu-id="342bd-166">Logical AND</span></span>
    - <span data-ttu-id="342bd-167">`x & y`: 정수 비트 AND, 부울 논리곱 AND</span><span class="sxs-lookup"><span data-stu-id="342bd-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="342bd-168">논리 XOR</span><span class="sxs-lookup"><span data-stu-id="342bd-168">Logical XOR</span></span>
    - <span data-ttu-id="342bd-169">`x ^ y`: 정수 비트 XOR, 부울 논리곱 XOR</span><span class="sxs-lookup"><span data-stu-id="342bd-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="342bd-170">논리적 OR</span><span class="sxs-lookup"><span data-stu-id="342bd-170">Logical OR</span></span>
    - <span data-ttu-id="342bd-171">`x | y`: 정수 비트 OR, 부울 논리곱 OR</span><span class="sxs-lookup"><span data-stu-id="342bd-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="342bd-172">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="342bd-172">Conditional AND</span></span>
    - <span data-ttu-id="342bd-173">`x && y`: `x`가 `false`가 아닌 경우에만 `y` 평가</span><span class="sxs-lookup"><span data-stu-id="342bd-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="342bd-174">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="342bd-174">Conditional OR</span></span>
    - <span data-ttu-id="342bd-175">`x || y`: `x`가 `true`가 아닌 경우에만 `y` 평가</span><span class="sxs-lookup"><span data-stu-id="342bd-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="342bd-176">Null 결합</span><span class="sxs-lookup"><span data-stu-id="342bd-176">Null coalescing</span></span>
    - <span data-ttu-id="342bd-177">`x ?? y`: `x`가 null이면 `y`, 그렇지 않으면 `x`로 평가</span><span class="sxs-lookup"><span data-stu-id="342bd-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="342bd-178">조건</span><span class="sxs-lookup"><span data-stu-id="342bd-178">Conditional</span></span>
    - <span data-ttu-id="342bd-179">`x ? y : z`: `x`가 `true`이면 `y`, `x`가 `false`이면 `z`로 평가</span><span class="sxs-lookup"><span data-stu-id="342bd-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="342bd-180">대입 또는 익명 함수</span><span class="sxs-lookup"><span data-stu-id="342bd-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="342bd-181">`x = y`: 대입</span><span class="sxs-lookup"><span data-stu-id="342bd-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="342bd-182">`x op= y`: 복합 대입. 지원되는 연산자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="342bd-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="342bd-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="342bd-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="342bd-184">`(T x) => y`: 익명 함수(람다 식)</span><span class="sxs-lookup"><span data-stu-id="342bd-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="342bd-185">[이전](types-and-variables.md)
[다음](statements.md)</span><span class="sxs-lookup"><span data-stu-id="342bd-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
