---
title: C# 연산자
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
caps.latest.revision: 40
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c62a168c845575e4fd3df212db379548926d2fab
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="c-operators"></a><span data-ttu-id="dbba7-102">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-102">C# Operators</span></span>
<span data-ttu-id="dbba7-103">C#에서는 많은 연산자를 제공하며, 이러한 연산자는 식에서 수행할 연산(수학, 인덱싱, 함수 호출 등)을 지정하는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="dbba7-104">많은 연산자를 [오버로드](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)하여 사용자 정의 형식에 적용되는 경우의 의미를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-104">You can [overload](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>  
  
 <span data-ttu-id="dbba7-105">정수 계열 형식에 대한 연산(예: `==`, `!=`, `<`, `>`, `&`, `|`)은 일반적으로 열거형(`enum`에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>  
  
 <span data-ttu-id="dbba7-106">아래 섹션에서는 우선 순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="dbba7-107">각 섹션 내의 연산자는 동일한 우선 순위 수준을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-107">The operators within each section share the same precedence level.</span></span>  
 
## <a name="primary-operators"></a><span data-ttu-id="dbba7-108">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-108">Primary Operators</span></span>  
 <span data-ttu-id="dbba7-109">우선 순위가 가장 높은 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-109">These are the highest precedence operators.</span></span>
  
 <span data-ttu-id="dbba7-110">[x.y](../../../csharp/language-reference/operators/member-access-operator.md) – 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="dbba7-110">[x.y](../../../csharp/language-reference/operators/member-access-operator.md) – member access.</span></span>  
  
 <span data-ttu-id="dbba7-111">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – null 조건부 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="dbba7-111">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="dbba7-112">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>  
 
 <span data-ttu-id="dbba7-113">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) - null 조건부 인덱스 액세스</span><span class="sxs-lookup"><span data-stu-id="dbba7-113">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="dbba7-114">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>
 
 <span data-ttu-id="dbba7-115">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – 함수 호출</span><span class="sxs-lookup"><span data-stu-id="dbba7-115">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – function invocation.</span></span>  
  
 <span data-ttu-id="dbba7-116">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – 집계 개체 인덱싱</span><span class="sxs-lookup"><span data-stu-id="dbba7-116">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – aggregate object indexing.</span></span>  
   
 <span data-ttu-id="dbba7-117">[x++](../../../csharp/language-reference/operators/increment-operator.md) – 후위 증가.</span><span class="sxs-lookup"><span data-stu-id="dbba7-117">[x++](../../../csharp/language-reference/operators/increment-operator.md) – postfix increment.</span></span> <span data-ttu-id="dbba7-118">x의 값을 반환하고 1 더 큰 x 값(일반적으로 정수 1을 더함)으로 저장소 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="dbba7-119">[x--](../../../csharp/language-reference/operators/decrement-operator.md) –  후위 감소.</span><span class="sxs-lookup"><span data-stu-id="dbba7-119">[x--](../../../csharp/language-reference/operators/decrement-operator.md) –  postfix decrement.</span></span> <span data-ttu-id="dbba7-120">x의 값을 반환하고 1 더 작은 x 값(일반적으로 정수 1을 뺌)으로 저장소 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="dbba7-121">[new](../../../csharp/language-reference/keywords/new-operator.md) – 형식 인스턴스화.</span><span class="sxs-lookup"><span data-stu-id="dbba7-121">[new](../../../csharp/language-reference/keywords/new-operator.md) – type instantiation.</span></span>  
  
 <span data-ttu-id="dbba7-122">[typeof](../../../csharp/language-reference/keywords/typeof.md) – 피연산자를 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-122">[typeof](../../../csharp/language-reference/keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>  
  
 <span data-ttu-id="dbba7-123">[checked](../../../csharp/language-reference/keywords/checked.md) – 정수 연산에 오버플로 검사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-123">[checked](../../../csharp/language-reference/keywords/checked.md) – enables overflow checking for integer operations.</span></span>  
  
 <span data-ttu-id="dbba7-124">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) – 정수 연산에 오버플로 검사를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-124">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="dbba7-125">이것은 기본 컴파일러 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-125">This is the default compiler behavior.</span></span>  
  
 <span data-ttu-id="dbba7-126">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) – T 형식의 기본값을 반환합니다. 참조 형식의 경우 `null`, 숫자 형식의 경우 0, 구조체 형식의 경우 멤버에 입력된 0/`null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-126">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) – returns the default value of type T: `null` for reference types, zero for numeric types, and zero/`null` filled in members for struct types.</span></span>  
  
 <span data-ttu-id="dbba7-127">[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – 대리자 인스턴스를 선언하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-127">[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>  
  
 <span data-ttu-id="dbba7-128">[sizeof](../../../csharp/language-reference/keywords/sizeof.md) – 형식 피연산자의 크기(바이트)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-128">[sizeof](../../../csharp/language-reference/keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>  
  
 <span data-ttu-id="dbba7-129">[->](../../../csharp/language-reference/operators/dereference-operator.md) – 멤버 액세스와 결합된 포인터 역참조입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-129">[->](../../../csharp/language-reference/operators/dereference-operator.md) – pointer dereferencing combined with member access.</span></span>  
  
## <a name="unary-operators"></a><span data-ttu-id="dbba7-130">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-130">Unary Operators</span></span>  
 <span data-ttu-id="dbba7-131">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-132">[+x](../../../csharp/language-reference/operators/addition-operator.md) – x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-132">[+x](../../../csharp/language-reference/operators/addition-operator.md) – returns the value of x.</span></span>  
  
 <span data-ttu-id="dbba7-133">[-x](../../../csharp/language-reference/operators/subtraction-operator.md) – 숫자 부정</span><span class="sxs-lookup"><span data-stu-id="dbba7-133">[-x](../../../csharp/language-reference/operators/subtraction-operator.md) – numeric negation.</span></span>  
  
 <span data-ttu-id="dbba7-134">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – 논리 부정</span><span class="sxs-lookup"><span data-stu-id="dbba7-134">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – logical negation.</span></span>  
  
 <span data-ttu-id="dbba7-135">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – 비트 보수</span><span class="sxs-lookup"><span data-stu-id="dbba7-135">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – bitwise complement.</span></span>  
  
 <span data-ttu-id="dbba7-136">[++x](../../../csharp/language-reference/operators/increment-operator.md) – 전위 증가</span><span class="sxs-lookup"><span data-stu-id="dbba7-136">[++x](../../../csharp/language-reference/operators/increment-operator.md) – prefix increment.</span></span> <span data-ttu-id="dbba7-137">1 더 큰 x 값(일반적으로 정수 1을 더함)으로 저장소 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="dbba7-138">[--x](../../../csharp/language-reference/operators/decrement-operator.md) – 전위 감소</span><span class="sxs-lookup"><span data-stu-id="dbba7-138">[--x](../../../csharp/language-reference/operators/decrement-operator.md) – prefix decrement.</span></span> <span data-ttu-id="dbba7-139">1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 저장소 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="dbba7-140">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="dbba7-140">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – type casting.</span></span>  
  
 <span data-ttu-id="dbba7-141">[await](../../../csharp/language-reference/keywords/await.md) – `Task`를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-141">[await](../../../csharp/language-reference/keywords/await.md) – awaits a `Task`.</span></span>  
  
 <span data-ttu-id="dbba7-142">[&x](../../../csharp/language-reference/operators/and-operator.md) – 주소</span><span class="sxs-lookup"><span data-stu-id="dbba7-142">[&x](../../../csharp/language-reference/operators/and-operator.md) – address of.</span></span>  
  
 <span data-ttu-id="dbba7-143">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md) – 역참조</span><span class="sxs-lookup"><span data-stu-id="dbba7-143">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md) – dereferencing.</span></span>  
  
## <a name="multiplicative-operators"></a><span data-ttu-id="dbba7-144">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-144">Multiplicative Operators</span></span>  
 <span data-ttu-id="dbba7-145">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-146">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md) – 곱하기</span><span class="sxs-lookup"><span data-stu-id="dbba7-146">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md) – multiplication.</span></span>  
  
 <span data-ttu-id="dbba7-147">[x / y](../../../csharp/language-reference/operators/division-operator.md) – 나누기</span><span class="sxs-lookup"><span data-stu-id="dbba7-147">[x / y](../../../csharp/language-reference/operators/division-operator.md) – division.</span></span> <span data-ttu-id="dbba7-148">피연산자가 정수인 경우 결과는 0으로 잘린 정수입니다(예: `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="dbba7-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>  
  
 <span data-ttu-id="dbba7-149">[x % y](../../../csharp/language-reference/operators/remainder-operator.md) - 나머지.</span><span class="sxs-lookup"><span data-stu-id="dbba7-149">[x % y](../../../csharp/language-reference/operators/remainder-operator.md) – remainder.</span></span> <span data-ttu-id="dbba7-150">피연산자가 정수인 경우 x를 y로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="dbba7-151">`q = x / y`이고 `r = x % y`인 경우 `x = q * y + r`입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>  
  
## <a name="additive-operators"></a><span data-ttu-id="dbba7-152">더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-152">Additive Operators</span></span>  
 <span data-ttu-id="dbba7-153">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-154">[x + y](../../../csharp/language-reference/operators/addition-operator.md) – 더하기</span><span class="sxs-lookup"><span data-stu-id="dbba7-154">[x + y](../../../csharp/language-reference/operators/addition-operator.md) – addition.</span></span>  
  
 <span data-ttu-id="dbba7-155">[x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – 빼기</span><span class="sxs-lookup"><span data-stu-id="dbba7-155">[x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – subtraction.</span></span>  
  
## <a name="shift-operators"></a><span data-ttu-id="dbba7-156">시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-156">Shift Operators</span></span>  
 <span data-ttu-id="dbba7-157">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-158">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – 왼쪽 비트를 시프트하고 오른쪽을 0으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-158">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>  
  
 <span data-ttu-id="dbba7-159">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – 오른쪽 비트를 시프트합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-159">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="dbba7-160">왼쪽 피연산자가 `int` 또는 `long`이면 왼쪽 비트는 부호 비트로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="dbba7-161">왼쪽 피연산자가 `uint` 또는 `ulong`이면 왼쪽 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>  
  
## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="dbba7-162">관계형 및 형식 테스트 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-162">Relational and Type-testing Operators</span></span>  
 <span data-ttu-id="dbba7-163">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-164">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md) –보다 작음(x가 y보다 작은 경우 true)</span><span class="sxs-lookup"><span data-stu-id="dbba7-164">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md) – less than (true if x is less than y).</span></span>  
  
 <span data-ttu-id="dbba7-165">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – 보다 큼(x가 y보다 큰 경우 true)</span><span class="sxs-lookup"><span data-stu-id="dbba7-165">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – greater than (true if x is greater than y).</span></span>  
  
 <span data-ttu-id="dbba7-166">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="dbba7-166">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – less than or equal to.</span></span>  
  
 <span data-ttu-id="dbba7-167">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – 보다 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="dbba7-167">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – greater than or equal to.</span></span>  
  
 <span data-ttu-id="dbba7-168">[is](../../../csharp/language-reference/keywords/is.md) – 형식 호환성.</span><span class="sxs-lookup"><span data-stu-id="dbba7-168">[is](../../../csharp/language-reference/keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="dbba7-169">계산된 왼쪽 피연산자를 오른쪽 피연산자에 지정된 형식(정적 형식)으로 캐스팅할 수 있는 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>  
  
 <span data-ttu-id="dbba7-170">[as](../../../csharp/language-reference/keywords/as.md) – 형식 변환.</span><span class="sxs-lookup"><span data-stu-id="dbba7-170">[as](../../../csharp/language-reference/keywords/as.md) – type conversion.</span></span> <span data-ttu-id="dbba7-171">오른쪽 피연산자에 지정된 형식(정적 유형)으로 캐스팅된 왼쪽 피연산자를 반환하지만 `(T)x`가 예외를 throw하는 경우 `as`는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="dbba7-172">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-172">Equality Operators</span></span>  
 <span data-ttu-id="dbba7-173">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-174">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – 같음.</span><span class="sxs-lookup"><span data-stu-id="dbba7-174">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – equality.</span></span> <span data-ttu-id="dbba7-175">기본적으로 `string`이 아닌 참조 형식에 대해 참조 같음(ID 테스트)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="dbba7-176">그러나 형식이 `==`를 오버로드할 수 있으므로 ID를 테스트하려는 경우에는 `object`에서 `ReferenceEquals` 메서드를 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>  
  
 <span data-ttu-id="dbba7-177">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – 같지 않음.</span><span class="sxs-lookup"><span data-stu-id="dbba7-177">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – not equal.</span></span> <span data-ttu-id="dbba7-178">`==`에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbba7-178">See comment for `==`.</span></span> <span data-ttu-id="dbba7-179">형식이 `==`를 오버로드하는 경우 `!=`를 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-179">If a type overloads `==`, then it must overload `!=`.</span></span>  
  
## <a name="logical-and-operator"></a><span data-ttu-id="dbba7-180">논리적 AND 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-180">Logical AND Operator</span></span>  
 <span data-ttu-id="dbba7-181">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-182">[x & y](../../../csharp/language-reference/operators/and-operator.md) – 논리적 또는 비트 AND.</span><span class="sxs-lookup"><span data-stu-id="dbba7-182">[x & y](../../../csharp/language-reference/operators/and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="dbba7-183">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-183">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="logical-xor-operator"></a><span data-ttu-id="dbba7-184">논리적 XOR 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-184">Logical XOR Operator</span></span>  
 <span data-ttu-id="dbba7-185">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-186">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – 논리적 또는 비트 XOR.</span><span class="sxs-lookup"><span data-stu-id="dbba7-186">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="dbba7-187">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-187">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="logical-or-operator"></a><span data-ttu-id="dbba7-188">논리적 OR 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-188">Logical OR Operator</span></span>  
 <span data-ttu-id="dbba7-189">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-190">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – 논리적 또는 비트 OR.</span><span class="sxs-lookup"><span data-stu-id="dbba7-190">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="dbba7-191">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-191">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="conditional-and-operator"></a><span data-ttu-id="dbba7-192">조건부 AND 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-192">Conditional AND Operator</span></span>  
 <span data-ttu-id="dbba7-193">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-194">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – 논리적 AND.</span><span class="sxs-lookup"><span data-stu-id="dbba7-194">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="dbba7-195">첫 번째 피연산자가 false로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>  
  
## <a name="conditional-or-operator"></a><span data-ttu-id="dbba7-196">조건부 OR 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-196">Conditional OR Operator</span></span>  
 <span data-ttu-id="dbba7-197">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-198">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – 논리적 OR.</span><span class="sxs-lookup"><span data-stu-id="dbba7-198">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="dbba7-199">첫 번째 피연산자가 true로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>  
  
## <a name="null-coalescing-operator"></a><span data-ttu-id="dbba7-200">Null 병합 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-200">Null-coalescing Operator</span></span>  
 <span data-ttu-id="dbba7-201">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-202">[x ?? y](../../../csharp/language-reference/operators/null-conditional-operator.md) – `null`이 아닌 경우 `x`를 반환하고, 그렇지 않은 경우 `y`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-202">[x ?? y](../../../csharp/language-reference/operators/null-conditional-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>  
  
## <a name="conditional-operator"></a><span data-ttu-id="dbba7-203">조건 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-203">Conditional Operator</span></span>  
 <span data-ttu-id="dbba7-204">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-205">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) - 테스트 `t`가 true로 확인되면 `x`를 계산하여 반환하고, 그렇지 않은 경우 `y`를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-205">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>  
  
## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="dbba7-206">할당 및 람다 연산자</span><span class="sxs-lookup"><span data-stu-id="dbba7-206">Assignment and Lambda Operators</span></span>  
 <span data-ttu-id="dbba7-207">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="dbba7-208">[x = y](../../../csharp/language-reference/operators/assignment-operator.md) – 할당</span><span class="sxs-lookup"><span data-stu-id="dbba7-208">[x = y](../../../csharp/language-reference/operators/assignment-operator.md) – assignment.</span></span>  
  
 <span data-ttu-id="dbba7-209">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – 증가.</span><span class="sxs-lookup"><span data-stu-id="dbba7-209">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="dbba7-210">`y`의 값을 `x` 값에 더하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="dbba7-211">`x`가 `event`를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 추가하는 적절한 함수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>  
  
 <span data-ttu-id="dbba7-212">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – 감소.</span><span class="sxs-lookup"><span data-stu-id="dbba7-212">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="dbba7-213">`x`의 값에서 `y`의 값을 빼고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="dbba7-214">`x`가 `event`를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 제거하는 적절한 함수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>  
  
 <span data-ttu-id="dbba7-215">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – 곱하기 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-215">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="dbba7-216">`y`의 값을 `x`의 값에 곱하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-217">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – 나누기 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-217">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – division assignment.</span></span> <span data-ttu-id="dbba7-218">`x`의 값을 `y`의 값으로 나누고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-219">[x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) – 나머지 할당.</span><span class="sxs-lookup"><span data-stu-id="dbba7-219">[x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) – remainder assignment.</span></span> <span data-ttu-id="dbba7-220">`x`의 값을 `y`의 값으로 나누고 나머지를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-221">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-221">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="dbba7-222">`y`의 값을 `x`의 값과 AND하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-223">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-223">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="dbba7-224">`y`의 값을 `x`의 값과 OR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-225">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-225">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="dbba7-226">`y`의 값을 `x`의 값과 XOR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-227">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – 왼쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-227">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="dbba7-228">`x`의 값을 왼쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-229">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – 오른쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="dbba7-229">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="dbba7-230">`x`의 값을 오른쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="dbba7-231">[=>](../../../csharp/language-reference/operators/lambda-operator.md) – 람다 선언.</span><span class="sxs-lookup"><span data-stu-id="dbba7-231">[=>](../../../csharp/language-reference/operators/lambda-operator.md) – lambda declaration.</span></span>  
  
## <a name="arithmetic-overflow"></a><span data-ttu-id="dbba7-232">산술 연산 오버플로</span><span class="sxs-lookup"><span data-stu-id="dbba7-232">Arithmetic Overflow</span></span>  
 <span data-ttu-id="dbba7-233">산술 연산자([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md))는 관련된 숫자 형식에 가능한 값의 범위를 벗어나는 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-233">The arithmetic operators ([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md)) can produce results that are outside the range of possible values for the numeric type involved.</span></span> <span data-ttu-id="dbba7-234">자세한 내용은 특정 연산자에 대한 섹션을 참조해야 하지만 일반적으로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-234">You should refer to the section on a particular operator for details, but in general:</span></span>  
  
- <span data-ttu-id="dbba7-235">정수 산술 연산 오버플로는 <xref:System.OverflowException>을 throw하거나 결과의 가장 중요한 비트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-235">Integer arithmetic overflow either throws an <xref:System.OverflowException> or discards the most significant bits of the result.</span></span> <span data-ttu-id="dbba7-236">정수를 0으로 나누면 항상 <xref:System.DivideByZeroException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-236">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  

   <span data-ttu-id="dbba7-237">정수 오버플로가 발생할 경우 수행되는 작업은 실행 컨텍스트에 따라 달라지며, 컨텍스트는 [checked 또는 unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-237">When integer overflow occurs, what happens depends on the execution context, which can be [checked or unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="dbba7-238">checked 컨텍스트에서는 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-238">In a checked context, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="dbba7-239">unchecked 컨텍스트에서는 결과의 가장 중요한 비트가 무시되고 실행이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-239">In an unchecked context, the most significant bits of the result are discarded and execution continues.</span></span> <span data-ttu-id="dbba7-240">따라서 C#에서는 오버플로 처리 또는 무시를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-240">Thus, C# gives you the choice of handling or ignoring overflow.</span></span> <span data-ttu-id="dbba7-241">기본적으로 산술 연산은 *unchecked* 컨텍스트에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-241">By default, arithmetic operations occur in an *unchecked* context.</span></span> 

   <span data-ttu-id="dbba7-242">산술 연산자 외에도 정수 계열 형식 간 캐스팅(예: [long](../../../csharp/language-reference/keywords/long.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 캐스팅)은 오버플로를 발생시키고 checked 또는 unchecked 실행이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-242">In addition to the arithmetic operations, integral-type to integral-type casts can cause overflow (such as when you cast a [long](../../../csharp/language-reference/keywords/long.md) to an [int](../../../csharp/language-reference/keywords/int.md)), and are subject to checked or unchecked execution.</span></span> <span data-ttu-id="dbba7-243">그러나 비트 연산자와 시프트 연산자는 오버플로를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-243">However, bitwise operators and shift operators never cause overflow.</span></span>  
   
-   <span data-ttu-id="dbba7-244">부동 소수점 산술 연산 오버플로 또는 0으로 나누기에서 예외를 throw하지 않습니다. 부동 소수점 형식은 IEEE 754를 기반으로 하여 무한대 및 NaN(숫자가 아님)를 나타내려면 프로비전이 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-244">Floating-point arithmetic overflow or division by zero never throws an exception, because floating-point types are based on IEEE 754 and so have provisions for representing infinity and NaN (Not a Number).</span></span>  
  
-   <span data-ttu-id="dbba7-245">[10진수<xref:System.OverflowException> 산술 연산 오버플로는 항상 ](../../../csharp/language-reference/keywords/decimal.md)을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-245">[Decimal](../../../csharp/language-reference/keywords/decimal.md) arithmetic overflow always throws an <xref:System.OverflowException>.</span></span> <span data-ttu-id="dbba7-246">10진수를 0으로 나누면 항상 <xref:System.DivideByZeroException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbba7-246">Decimal division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="dbba7-247">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbba7-247">See Also</span></span>  
 [<span data-ttu-id="dbba7-248">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dbba7-248">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dbba7-249">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dbba7-249">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="dbba7-250">[C#](../../../csharp/index.md) [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)</span><span class="sxs-lookup"><span data-stu-id="dbba7-250">[C#](../../../csharp/index.md) [Overloadable Operators](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)</span></span>  
 [<span data-ttu-id="dbba7-251">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="dbba7-251">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
