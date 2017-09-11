---
title: "Nullable 형식 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="28902-102">Nullable 형식 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="28902-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="28902-103">nullable 형식은 기본 형식의 모든 값과 추가 [null](../../../csharp/language-reference/keywords/null.md) 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="28902-104">nullable 형식은 다음과 같은 두 가지 방법 중 하나로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="28902-105">또는</span><span class="sxs-lookup"><span data-stu-id="28902-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="28902-106">`T`는 nullable 형식의 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28902-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="28902-107">`T`는 `struct`를 비롯한 모든 값 형식일 수 있으나, 참조 형식일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="28902-108">nullable 형식을 사용할 수 있는 경우의 예를 들기 위해 일반 부울 변수가 두 가지 값 true와 false를 가질 수 있는 방법을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="28902-109">“정의되지 않음”을 의미하는 값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="28902-110">많은 프로그래밍 응용 프로그램(특히, 데이터베이스 상호 작용)에서 변수는 정의되지 않은 상태로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="28902-111">예를 들어 데이터베이스의 필드는 true 또는 false 값을 포함할 수 있지만, 전혀 값을 포함하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="28902-112">마찬가지로, 초기화되지 않았음을 나타내기 위해 참조 형식을 `null`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="28902-113">이 차이로 인해 상태 정보, 특수 값 사용 등을 저장하는 데 사용되는 추가 변수와 관련한 추가 프로그래밍 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="28902-114">C#에서는 nullable 형식 한정자를 사용하여 정의되지 않은 값을 나타내는 값 형식 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="28902-115">nullable 형식의 예</span><span class="sxs-lookup"><span data-stu-id="28902-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="28902-116">nullable 형식에 대한 기준으로 모든 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="28902-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-117">For example:</span></span>  
  
 <span data-ttu-id="28902-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span></span>  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="28902-119">nullable 형식의 멤버</span><span class="sxs-lookup"><span data-stu-id="28902-119">The Members of Nullable Types</span></span>  
 <span data-ttu-id="28902-120">nullable 형식의 각 인스턴스에는 다음과 같은 두 개의 public 읽기 전용 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-120">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="28902-121">`HasValue`는 `bool` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28902-121">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="28902-122">변수가 null이 아닌 값을 포함한 경우 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-122">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="28902-123">`Value`는 기본 형식과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28902-123">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="28902-124">`HasValue`가 `true`이면 `Value`에는 의미 있는 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-124">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="28902-125">`HasValue`가 `false`이면 `Value`에서는 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-125">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="28902-126">이 예제에서 `HasValue` 멤버는 변수를 표시하려고 하기 전에 변수가 값을 포함하는지를 테스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-126">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 <span data-ttu-id="28902-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span></span>  
  
 <span data-ttu-id="28902-128">값에 대한 테스트는 다음 예제처럼 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-128">Testing for a value can also be done as in the following example:</span></span>  
  
 <span data-ttu-id="28902-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span></span>  
  
## <a name="explicit-conversions"></a><span data-ttu-id="28902-130">명시적 변환</span><span class="sxs-lookup"><span data-stu-id="28902-130">Explicit Conversions</span></span>  
 <span data-ttu-id="28902-131">nullable 형식은 캐스트를 사용하여 명시적으로 또는 `Value` 속성을 사용하여 일반 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-131">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="28902-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-132">For example:</span></span>  
  
 <span data-ttu-id="28902-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span></span>  
  
 <span data-ttu-id="28902-134">두 데이터 형식 간에 사용자 정의 변환이 정의된 경우 이러한 데이터 형식의 nullable 버전에도 같은 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-134">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="28902-135">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="28902-135">Implicit Conversions</span></span>  
 <span data-ttu-id="28902-136">nullable 형식의 변수는 다음 예제와 같이 `null` 키워드를 사용하여 null로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-136">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="28902-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span></span>  
  
 <span data-ttu-id="28902-138">일반 형식에서 nullable 형식으로의 변환은 암시적입니다.</span><span class="sxs-lookup"><span data-stu-id="28902-138">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 <span data-ttu-id="28902-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span></span>  
  
## <a name="operators"></a><span data-ttu-id="28902-140">연산자</span><span class="sxs-lookup"><span data-stu-id="28902-140">Operators</span></span>  
 <span data-ttu-id="28902-141">미리 정의된 단항 및 이항 연산자와 값 형식에 대해 존재하는 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-141">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="28902-142">이러한 연산자는 피연산자가 null인 경우 null 값을 생성하고, 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-142">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="28902-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-143">For example:</span></span>  
  
 <span data-ttu-id="28902-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span></span>  
  
 <span data-ttu-id="28902-145">nullable 형식과의 비교를 수행할 때 nullable 형식 중 하나의 값이 null이고 나머지는 null이 아닌 경우 모든 비교는 `!=`(같지 않음)을 제외하고는 `false`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-145">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="28902-146">특정 비교에서는 `false`를 반환하고 그 반대의 경우에는 `true`를 반환한다고 가정하지 않는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-146">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="28902-147">다음 예제에서 10은 null보다 크지 않고, 작지 않고, 같지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-147">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="28902-148">`num1 != num2`만 `true`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-148">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 <span data-ttu-id="28902-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span></span>  
  
 <span data-ttu-id="28902-150">둘 다 null인 두 nullable 형식의 같음 비교는 `true`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-150">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="28902-151">??</span><span class="sxs-lookup"><span data-stu-id="28902-151">The ??</span></span> <span data-ttu-id="28902-152">연산자</span><span class="sxs-lookup"><span data-stu-id="28902-152">Operator</span></span>  
 <span data-ttu-id="28902-153">`??` 연산자는 nullable 형식이 nullable 형식이 아닌 형식에 할당된 경우 반환되는 기본값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-153">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 <span data-ttu-id="28902-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span></span>  
  
 <span data-ttu-id="28902-155">이 연산자는 여러 nullable 형식에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-155">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="28902-156">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-156">For example:</span></span>  
  
 <span data-ttu-id="28902-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="28902-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span></span>  
  
## <a name="the-bool-type"></a><span data-ttu-id="28902-158">bool? 형식</span><span class="sxs-lookup"><span data-stu-id="28902-158">The bool? type</span></span>  
 <span data-ttu-id="28902-159">`bool?` nullable 형식은 세 가지 값 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 및 [null](../../../csharp/language-reference/keywords/null.md)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28902-159">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="28902-160">bool?에서 bool로 캐스팅하는 방법에 대한 자세한 내용은 [방법: bool?에서 bool로 안전하게 캐스팅](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28902-160">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="28902-161">nullable 부울은 SQL에서 사용되는 부울 변수 형식과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="28902-161">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="28902-162">`&` 및 `|` 연산자에 의해 생성된 결과가 SQL의 삼중값 부울 형식과 일치하도록 다음과 같은 미리 정의된 연산자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="28902-162">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="28902-163">다음 표는 이러한 연산자의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28902-163">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="28902-164">X</span><span class="sxs-lookup"><span data-stu-id="28902-164">X</span></span>|<span data-ttu-id="28902-165">y</span><span class="sxs-lookup"><span data-stu-id="28902-165">y</span></span>|<span data-ttu-id="28902-166">x&y</span><span class="sxs-lookup"><span data-stu-id="28902-166">x&y</span></span>|<span data-ttu-id="28902-167">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="28902-167">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="28902-168">true</span><span class="sxs-lookup"><span data-stu-id="28902-168">true</span></span>|<span data-ttu-id="28902-169">true</span><span class="sxs-lookup"><span data-stu-id="28902-169">true</span></span>|<span data-ttu-id="28902-170">true</span><span class="sxs-lookup"><span data-stu-id="28902-170">true</span></span>|<span data-ttu-id="28902-171">true</span><span class="sxs-lookup"><span data-stu-id="28902-171">true</span></span>|  
|<span data-ttu-id="28902-172">true</span><span class="sxs-lookup"><span data-stu-id="28902-172">true</span></span>|<span data-ttu-id="28902-173">false</span><span class="sxs-lookup"><span data-stu-id="28902-173">false</span></span>|<span data-ttu-id="28902-174">false</span><span class="sxs-lookup"><span data-stu-id="28902-174">false</span></span>|<span data-ttu-id="28902-175">true</span><span class="sxs-lookup"><span data-stu-id="28902-175">true</span></span>|  
|<span data-ttu-id="28902-176">true</span><span class="sxs-lookup"><span data-stu-id="28902-176">true</span></span>|<span data-ttu-id="28902-177">null</span><span class="sxs-lookup"><span data-stu-id="28902-177">null</span></span>|<span data-ttu-id="28902-178">null</span><span class="sxs-lookup"><span data-stu-id="28902-178">null</span></span>|<span data-ttu-id="28902-179">true</span><span class="sxs-lookup"><span data-stu-id="28902-179">true</span></span>|  
|<span data-ttu-id="28902-180">false</span><span class="sxs-lookup"><span data-stu-id="28902-180">false</span></span>|<span data-ttu-id="28902-181">true</span><span class="sxs-lookup"><span data-stu-id="28902-181">true</span></span>|<span data-ttu-id="28902-182">false</span><span class="sxs-lookup"><span data-stu-id="28902-182">false</span></span>|<span data-ttu-id="28902-183">true</span><span class="sxs-lookup"><span data-stu-id="28902-183">true</span></span>|  
|<span data-ttu-id="28902-184">false</span><span class="sxs-lookup"><span data-stu-id="28902-184">false</span></span>|<span data-ttu-id="28902-185">false</span><span class="sxs-lookup"><span data-stu-id="28902-185">false</span></span>|<span data-ttu-id="28902-186">false</span><span class="sxs-lookup"><span data-stu-id="28902-186">false</span></span>|<span data-ttu-id="28902-187">false</span><span class="sxs-lookup"><span data-stu-id="28902-187">false</span></span>|  
|<span data-ttu-id="28902-188">false</span><span class="sxs-lookup"><span data-stu-id="28902-188">false</span></span>|<span data-ttu-id="28902-189">null</span><span class="sxs-lookup"><span data-stu-id="28902-189">null</span></span>|<span data-ttu-id="28902-190">false</span><span class="sxs-lookup"><span data-stu-id="28902-190">false</span></span>|<span data-ttu-id="28902-191">null</span><span class="sxs-lookup"><span data-stu-id="28902-191">null</span></span>|  
|<span data-ttu-id="28902-192">null</span><span class="sxs-lookup"><span data-stu-id="28902-192">null</span></span>|<span data-ttu-id="28902-193">true</span><span class="sxs-lookup"><span data-stu-id="28902-193">true</span></span>|<span data-ttu-id="28902-194">null</span><span class="sxs-lookup"><span data-stu-id="28902-194">null</span></span>|<span data-ttu-id="28902-195">true</span><span class="sxs-lookup"><span data-stu-id="28902-195">true</span></span>|  
|<span data-ttu-id="28902-196">null</span><span class="sxs-lookup"><span data-stu-id="28902-196">null</span></span>|<span data-ttu-id="28902-197">false</span><span class="sxs-lookup"><span data-stu-id="28902-197">false</span></span>|<span data-ttu-id="28902-198">false</span><span class="sxs-lookup"><span data-stu-id="28902-198">false</span></span>|<span data-ttu-id="28902-199">null</span><span class="sxs-lookup"><span data-stu-id="28902-199">null</span></span>|  
|<span data-ttu-id="28902-200">null</span><span class="sxs-lookup"><span data-stu-id="28902-200">null</span></span>|<span data-ttu-id="28902-201">null</span><span class="sxs-lookup"><span data-stu-id="28902-201">null</span></span>|<span data-ttu-id="28902-202">null</span><span class="sxs-lookup"><span data-stu-id="28902-202">null</span></span>|<span data-ttu-id="28902-203">null</span><span class="sxs-lookup"><span data-stu-id="28902-203">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28902-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28902-204">See Also</span></span>  
 <span data-ttu-id="28902-205">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="28902-205">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="28902-206">[Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="28902-206">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="28902-207">[Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="28902-207">[Boxing Nullable Types](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span></span>  
 [<span data-ttu-id="28902-208">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="28902-208">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

