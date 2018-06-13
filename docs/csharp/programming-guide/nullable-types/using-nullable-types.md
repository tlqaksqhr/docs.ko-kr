---
title: Nullable 형식 사용(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336923"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="f5c21-102">Nullable 형식 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f5c21-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="f5c21-103">nullable 형식은 기본 형식의 모든 값과 추가 [null](../../../csharp/language-reference/keywords/null.md) 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="f5c21-104">nullable 형식은 다음과 같은 두 가지 방법 중 하나로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="f5c21-105">또는</span><span class="sxs-lookup"><span data-stu-id="f5c21-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="f5c21-106">`T`는 nullable 형식의 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="f5c21-107">`T`는 `struct`를 비롯한 모든 값 형식일 수 있으나, 참조 형식일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="f5c21-108">nullable 형식을 사용할 수 있는 경우의 예를 들기 위해 일반 부울 변수가 두 가지 값 true와 false를 가질 수 있는 방법을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="f5c21-109">“정의되지 않음”을 의미하는 값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="f5c21-110">많은 프로그래밍 응용 프로그램(특히, 데이터베이스 상호 작용)에서 변수는 정의되지 않은 상태로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="f5c21-111">예를 들어 데이터베이스의 필드는 true 또는 false 값을 포함할 수 있지만, 전혀 값을 포함하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="f5c21-112">마찬가지로, 초기화되지 않았음을 나타내기 위해 참조 형식을 `null`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="f5c21-113">이 차이로 인해 상태 정보, 특수 값 사용 등을 저장하는 데 사용되는 추가 변수와 관련한 추가 프로그래밍 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="f5c21-114">C#에서는 nullable 형식 한정자를 사용하여 정의되지 않은 값을 나타내는 값 형식 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="f5c21-115">nullable 형식의 예</span><span class="sxs-lookup"><span data-stu-id="f5c21-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="f5c21-116">nullable 형식에 대한 기준으로 모든 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="f5c21-117">예:</span><span class="sxs-lookup"><span data-stu-id="f5c21-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="f5c21-118">nullable 형식의 멤버</span><span class="sxs-lookup"><span data-stu-id="f5c21-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="f5c21-119">nullable 형식의 각 인스턴스에는 다음과 같은 두 개의 public 읽기 전용 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="f5c21-120">`HasValue`는 `bool` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="f5c21-121">변수가 null이 아닌 값을 포함한 경우 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="f5c21-122">`Value`는 기본 형식과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="f5c21-123">`HasValue`가 `true`이면 `Value`에는 의미 있는 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="f5c21-124">`HasValue`가 `false`이면 `Value`에서는 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="f5c21-125">이 예제에서 `HasValue` 멤버는 변수를 표시하려고 하기 전에 변수가 값을 포함하는지를 테스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="f5c21-126">값에 대한 테스트는 다음 예제처럼 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="f5c21-127">명시적 변환</span><span class="sxs-lookup"><span data-stu-id="f5c21-127">Explicit Conversions</span></span>  
 <span data-ttu-id="f5c21-128">nullable 형식은 캐스트를 사용하여 명시적으로 또는 `Value` 속성을 사용하여 일반 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="f5c21-129">예:</span><span class="sxs-lookup"><span data-stu-id="f5c21-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="f5c21-130">두 데이터 형식 간에 사용자 정의 변환이 정의된 경우 이러한 데이터 형식의 nullable 버전에도 같은 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="f5c21-131">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="f5c21-131">Implicit Conversions</span></span>  
 <span data-ttu-id="f5c21-132">nullable 형식의 변수는 다음 예제와 같이 `null` 키워드를 사용하여 null로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="f5c21-133">일반 형식에서 nullable 형식으로의 변환은 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="f5c21-134">연산자</span><span class="sxs-lookup"><span data-stu-id="f5c21-134">Operators</span></span>  
 <span data-ttu-id="f5c21-135">미리 정의된 단항 및 이항 연산자와 값 형식에 대해 존재하는 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="f5c21-136">이러한 연산자는 피연산자가 null인 경우 null 값을 생성하고, 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="f5c21-137">예:</span><span class="sxs-lookup"><span data-stu-id="f5c21-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="f5c21-138">nullable 형식과의 비교를 수행할 때 nullable 형식 중 하나의 값이 null이고 나머지는 null이 아닌 경우 모든 비교는 `!=`(같지 않음)을 제외하고는 `false`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="f5c21-139">특정 비교에서는 `false`를 반환하고 그 반대의 경우에는 `true`를 반환한다고 가정하지 않는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="f5c21-140">다음 예제에서 10은 null보다 크지 않고, 작지 않고, 같지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="f5c21-141">`num1 != num2`만 `true`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="f5c21-142">둘 다 null인 두 nullable 형식의 같음 비교는 `true`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="f5c21-143">??</span><span class="sxs-lookup"><span data-stu-id="f5c21-143">The ??</span></span> <span data-ttu-id="f5c21-144">연산자</span><span class="sxs-lookup"><span data-stu-id="f5c21-144">Operator</span></span>  
 <span data-ttu-id="f5c21-145">`??` 연산자는 nullable 형식이 nullable 형식이 아닌 형식에 할당된 경우 반환되는 기본값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="f5c21-146">이 연산자는 여러 nullable 형식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="f5c21-147">예:</span><span class="sxs-lookup"><span data-stu-id="f5c21-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="f5c21-148">bool? 형식</span><span class="sxs-lookup"><span data-stu-id="f5c21-148">The bool? type</span></span>  
 <span data-ttu-id="f5c21-149">`bool?` nullable 형식은 세 가지 값 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 및 [null](../../../csharp/language-reference/keywords/null.md)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="f5c21-150">bool?에서 bool로 캐스팅하는 방법에 대한 자세한 내용은 [방법: bool?에서 bool로 안전하게 캐스팅](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5c21-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="f5c21-151">nullable 부울은 SQL에서 사용되는 부울 변수 형식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="f5c21-152">`&` 및 `|` 연산자에 의해 생성된 결과가 SQL의 삼중값 부울 형식과 일치하도록 다음과 같은 미리 정의된 연산자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="f5c21-153">다음 표는 이러한 연산자의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5c21-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="f5c21-154">X</span><span class="sxs-lookup"><span data-stu-id="f5c21-154">X</span></span>|<span data-ttu-id="f5c21-155">y</span><span class="sxs-lookup"><span data-stu-id="f5c21-155">y</span></span>|<span data-ttu-id="f5c21-156">x&y</span><span class="sxs-lookup"><span data-stu-id="f5c21-156">x&y</span></span>|<span data-ttu-id="f5c21-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="f5c21-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="f5c21-158">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-158">true</span></span>|<span data-ttu-id="f5c21-159">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-159">true</span></span>|<span data-ttu-id="f5c21-160">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-160">true</span></span>|<span data-ttu-id="f5c21-161">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-161">true</span></span>|  
|<span data-ttu-id="f5c21-162">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-162">true</span></span>|<span data-ttu-id="f5c21-163">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-163">false</span></span>|<span data-ttu-id="f5c21-164">false</span><span class="sxs-lookup"><span data-stu-id="f5c21-164">false</span></span>|<span data-ttu-id="f5c21-165">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-165">true</span></span>|  
|<span data-ttu-id="f5c21-166">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-166">true</span></span>|<span data-ttu-id="f5c21-167">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-167">null</span></span>|<span data-ttu-id="f5c21-168">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-168">null</span></span>|<span data-ttu-id="f5c21-169">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-169">true</span></span>|  
|<span data-ttu-id="f5c21-170">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-170">false</span></span>|<span data-ttu-id="f5c21-171">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-171">true</span></span>|<span data-ttu-id="f5c21-172">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-172">false</span></span>|<span data-ttu-id="f5c21-173">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-173">true</span></span>|  
|<span data-ttu-id="f5c21-174">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-174">false</span></span>|<span data-ttu-id="f5c21-175">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-175">false</span></span>|<span data-ttu-id="f5c21-176">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-176">false</span></span>|<span data-ttu-id="f5c21-177">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-177">false</span></span>|  
|<span data-ttu-id="f5c21-178">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-178">false</span></span>|<span data-ttu-id="f5c21-179">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-179">null</span></span>|<span data-ttu-id="f5c21-180">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-180">false</span></span>|<span data-ttu-id="f5c21-181">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-181">null</span></span>|  
|<span data-ttu-id="f5c21-182">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-182">null</span></span>|<span data-ttu-id="f5c21-183">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-183">true</span></span>|<span data-ttu-id="f5c21-184">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-184">null</span></span>|<span data-ttu-id="f5c21-185">true</span><span class="sxs-lookup"><span data-stu-id="f5c21-185">true</span></span>|  
|<span data-ttu-id="f5c21-186">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-186">null</span></span>|<span data-ttu-id="f5c21-187">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-187">false</span></span>|<span data-ttu-id="f5c21-188">False</span><span class="sxs-lookup"><span data-stu-id="f5c21-188">false</span></span>|<span data-ttu-id="f5c21-189">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-189">null</span></span>|  
|<span data-ttu-id="f5c21-190">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-190">null</span></span>|<span data-ttu-id="f5c21-191">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-191">null</span></span>|<span data-ttu-id="f5c21-192">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-192">null</span></span>|<span data-ttu-id="f5c21-193">null</span><span class="sxs-lookup"><span data-stu-id="f5c21-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5c21-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5c21-194">See Also</span></span>  
 [<span data-ttu-id="f5c21-195">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f5c21-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f5c21-196">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="f5c21-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="f5c21-197">Nullable 형식 boxing</span><span class="sxs-lookup"><span data-stu-id="f5c21-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="f5c21-198">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="f5c21-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
