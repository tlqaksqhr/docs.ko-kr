---
title: "무시 항목 - C# 가이드 | Microsoft Docs"
description: "할당되지 않은 무시 가능한 변수인 무시 항목에 대한 C#의 지원과 무시 항목을 사용할 수 있는 방법에 관해 설명합니다."
keywords: .NET,.NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 07/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.translationtype: HT
ms.sourcegitcommit: 6170e096e36f8d054fdfe9cbd8311e6492e32a04
ms.openlocfilehash: 3f8804f9b7522e385b145a9643dec942cc1aab9f
ms.contentlocale: ko-kr
ms.lasthandoff: 08/28/2017

---
# <a name="discards---c-guide"></a><span data-ttu-id="717de-104">무시 항목 - C# 가이드</span><span class="sxs-lookup"><span data-stu-id="717de-104">Discards - C# Guide</span></span>

<span data-ttu-id="717de-105">C# 7부터 C#에서는 응용 프로그램 코드에서 의도적으로 사용되지 않는 임시 더미 변수인 무시 항목을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-105">Starting with C# 7, C# supports discards, which are temporary, dummy variables that are intentionally unused in application code.</span></span> <span data-ttu-id="717de-106">무시 항목은 할당되지 않은 변수에 해당하므로 값을 가지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-106">Discards are equivalent to unassigned variables; they do not have a value.</span></span> <span data-ttu-id="717de-107">무시 항목 변수는 하나만 있고 할당된 저장소가 아닐 수도 있으므로 무시 항목은 메모리 할당을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-107">Because there is only a single discard variable, and that variable may not even be allocated storage, discards can reduce memory allocations.</span></span> <span data-ttu-id="717de-108">코드의 의도를 명확하게 만들므로 코드의 가독성과 유지 관리 편의성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-108">Because they make the intent of your code clear, they enhance its readability and maintainability.</span></span>

<span data-ttu-id="717de-109">변수가 무시 항목임을 지정하려면 변수에 밑줄(`_`)을 이름으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-109">You indicate that a variable is a discard by assigning it the underscore (`_`) as its name.</span></span> <span data-ttu-id="717de-110">예를 들어 다음 메서드 호출은 첫 번째와 두 번째 값이 무시 항목인 3 튜플을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-110">For example, the following method call returns a 3-tuple in which the first and second values are discards:</span></span>

```csharp
(var _, _, area) = city.GetCityInformation(cityName);
```

<span data-ttu-id="717de-111">C# 7에서 무시 항목은 다음 컨텍스트의 할당에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="717de-111">In C# 7, discards are supported in assignments in the following contexts:</span></span>

- <span data-ttu-id="717de-112">튜플 및 개체 [분해](deconstruct.md)</span><span class="sxs-lookup"><span data-stu-id="717de-112">Tuple and object [deconstruction](deconstruct.md).</span></span>
- <span data-ttu-id="717de-113">[is](language-reference/keywords/is.md) 및 [switch](language-reference/keywords/switch.md)를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="717de-113">Pattern matching with [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md).</span></span>
- <span data-ttu-id="717de-114">`out` 매개 변수를 사용한 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="717de-114">Calls to methods with `out` parameters.</span></span>
- <span data-ttu-id="717de-115">범위에 `_`이 없는 경우 독립 실행형 `_`</span><span class="sxs-lookup"><span data-stu-id="717de-115">A standalone `_` when no `_` is in scope.</span></span>

<span data-ttu-id="717de-116">`_`이 유효한 무시 항목인 경우, 해당 값을 검색하거나 할당 작업에서 사용하려고 하면 “‘\_’ 이름이 현재 컨텍스트에 없습니다.”라는 컴파일러 오류 CS0301이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="717de-116">When `_` is a valid discard, attempting to retrieve its value or use it in an assignment operation generates compiler error CS0301, "The name '\_' does not exist in the current context".</span></span> <span data-ttu-id="717de-117">이는 `_`에 값이 할당되어 있지 않고 저장소 위치도 할당되어 있지 않을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="717de-117">This is because `_` is not assigned a value, and may not even be assigned a storage location.</span></span> <span data-ttu-id="717de-118">실제 변수인 경우에는 이전 예제에서처럼 2개 이상의 값을 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-118">If it were an actual variable, you could not discard more than one value, as the previous example did.</span></span>

## <a name="tuple-and-object-deconstruction"></a><span data-ttu-id="717de-119">튜플 및 개체 분해</span><span class="sxs-lookup"><span data-stu-id="717de-119">Tuple and object deconstruction</span></span>

<span data-ttu-id="717de-120">무시 항목은 튜플을 작업할 때 응용 프로그램 코드에 튜플 요소 중 일부만 사용하고 일부는 무시하는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-120">Discards are particularly useful in working with tuples when your application code uses some tuple elements but ignores others.</span></span> <span data-ttu-id="717de-121">예를 들어, 다음 `QueryCityDataForYears` 메서드는 도시의 이름, 도시의 면적, 연도, 해당 연도의 도시 인구, 두 번째 연도, 해당 두 번째 연도의 도구 인구를 포함하는 6 튜플을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-121">For example, the following `QueryCityDataForYears` method returns a 6-tuple with the name of a city, its area, a year, the city's population for that year, a second year, and the city's population for that second year.</span></span> <span data-ttu-id="717de-122">이 예제는 이러한 두 연도 사이의 인구 변화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="717de-122">The example shows the change in population between those two years.</span></span> <span data-ttu-id="717de-123">튜플에서 사용 가능한 데이터 중 도시 면적에는 관심이 없고 디자인 타임에 도시 이름과 두 날짜를 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-123">Of the data available from the tuple, we're unconcerned with the city area, and we know the city name and the two dates at design-time.</span></span> <span data-ttu-id="717de-124">따라서 튜플에 저장된 두 가지 인구 값에만 관심이 있고 나머지 값은 무시 항목으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-124">As a result, we're only interested in the two population values stored in the tuple, and can handle its remaining values as discards.</span></span>  

<span data-ttu-id="717de-125">[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span><span class="sxs-lookup"><span data-stu-id="717de-125">[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]</span></span>

<span data-ttu-id="717de-126">무시 항목을 사용한 튜플 분해에 대한 자세한 내용은 [튜플 및 기타 형식 분해](deconstruct.md#deconstructing-tuple-elements-with-discards)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="717de-126">For more information on deconstructing tuples with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-tuple-elements-with-discards).</span></span>

<span data-ttu-id="717de-127">클래스, 구조체 또는 인터페이스의 `Deconstruct` 메서드로도 개체에서 특정 데이터 집합을 검색 및 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-127">The `Deconstruct` method of a class, structure, or interface also allows you to retrieve and deconstruct a specific set of data from an object.</span></span> <span data-ttu-id="717de-128">분해된 값의 하위 집합만으로 작업하려는 경우 무시 항목을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-128">You can use discards when you are interested in working with only a subset of the deconstructed values.</span></span> <span data-ttu-id="717de-129">다음 예제에서는 `Person` 개체를 4개의 문자열(이름, 성, 도시 및 주)로 분해하지만 성과 주는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-129">Ihe following example deconstructs a `Person` object into four strings (the first and last names, the city, and the state), but discards the last name and the state.</span></span>

<span data-ttu-id="717de-130">[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]</span><span class="sxs-lookup"><span data-stu-id="717de-130">[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]</span></span>

<span data-ttu-id="717de-131">무시 항목을 사용한 사용자 정의 형식 분해에 대한 자세한 내용은 [튜플 및 기타 형식 분해](deconstruct.md#deconstructing-a-user-defined-type-with-discards)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="717de-131">For more information on deconstructing user-defined types with discards, see [Deconstructing tuples and other types](deconstruct.md#deconstructing-a-user-defined-type-with-discards).</span></span>

## <a name="pattern-matching-with-switch-and-is"></a><span data-ttu-id="717de-132">`switch` 및 `is`를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="717de-132">Pattern matching with `switch` and `is`</span></span>

<span data-ttu-id="717de-133">*무시 패턴*은 [is](language-reference/keywords/is.md) 및 [switch](language-reference/keywords/switch.md) 키워드를 사용한 패턴 일치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-133">The *discard pattern* can be used in pattern matching with the [is](language-reference/keywords/is.md) and [switch](language-reference/keywords/switch.md) keywords.</span></span> <span data-ttu-id="717de-134">모든 식은 무시 패턴과 항상 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="717de-134">Every expression always matches the discard pattern.</span></span>

<span data-ttu-id="717de-135">다음 예제에서는 [is](language-reference/keywords/is.md) 문을 사용하여 개체가 <xref:System.IFormatProvider> 구현을 제공하고 개체가 `null`인지 테스트하는지를 결정하는 `ProvidesFormatInfo` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-135">The following example defines a `ProvidesFormatInfo` method that uses [is](language-reference/keywords/is.md) statements to determine whether an object provides an <xref:System.IFormatProvider> implementation and tests whether the object is `null`.</span></span> <span data-ttu-id="717de-136">또한 무시 패턴을 사용하여 다른 형식의 null이 아닌 개체도 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-136">It also uses the discard pattern to handle non-null objects of any other type.</span></span>

<span data-ttu-id="717de-137">[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]</span><span class="sxs-lookup"><span data-stu-id="717de-137">[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]</span></span>

## <a name="calls-to-methods-with-out-parameters"></a><span data-ttu-id="717de-138">out 매개 변수를 사용한 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="717de-138">Calls to methods with out parameters</span></span>

<span data-ttu-id="717de-139">`Deconstruct` 메서드를 호출하여 사용자 정의 형식(클래스, 구조체 또는 인터페이스의 인스턴스)를 분해할 때 개별 `out` 인수의 값을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-139">When calling the `Deconstruct` method to deconstruct a user-defined type (an instance of a class, structure, or interface), you can discard the values of individual `out` arguments.</span></span> <span data-ttu-id="717de-140">하지만 어느 메서드든 out 매개 변수를 사용하여 호출할 때 `out` 인수의 값을 무시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-140">But you can also discard the value of `out` arguments when calling any method with an out parameter.</span></span> 

<span data-ttu-id="717de-141">다음 예제에서는 [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) 메서드를 호출하여 날짜의 문자열 표현이 현재 문화권에 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-141">The following example calls the [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) method to determine whether the string representation of a date is valid in the current culture.</span></span> <span data-ttu-id="717de-142">이 예제에서는 날짜 문자열의 유효성 검사에만 관심이 있고 이 문자열의 구문 검사를 통한 날짜 추출에는 관심이 없으므로 메서드의 `out` 인수는 무시 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="717de-142">Because the example is concerned only with validating the date string and not with parsing it to extract the date, the `out` argument to the method is a discard.</span></span>

<span data-ttu-id="717de-143">[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]</span><span class="sxs-lookup"><span data-stu-id="717de-143">[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]</span></span>

## <a name="a-standalone-discard"></a><span data-ttu-id="717de-144">독립 실행형 무시 항목</span><span class="sxs-lookup"><span data-stu-id="717de-144">A standalone discard</span></span>

<span data-ttu-id="717de-145">독립 실행형 무시 항목을 사용하여 무시할 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-145">You can use a standalone discard to indicate any variable that you choose to ignore.</span></span> <span data-ttu-id="717de-146">다음 예제에서는 독립 실행형 무시 항목을 사용하여 비동기 작업에서 반환되는 <xref:System.Threading.Tasks.Task>개체를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-146">The following example uses a standalone discard to ignore the <xref:System.Threading.Tasks.Task> object returned by an asynchronous operation.</span></span> <span data-ttu-id="717de-147">따라서 작업이 완료되려고 할 때 throw되는 예외가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-147">This has the effect of suppressing the exception that the operation throws as it is about to complete.</span></span>

<span data-ttu-id="717de-148">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]</span><span class="sxs-lookup"><span data-stu-id="717de-148">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]</span></span>

<span data-ttu-id="717de-149">`_`은 유효한 식별자이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="717de-149">Note that `_` is also a valid identifier.</span></span> <span data-ttu-id="717de-150">지원되는 컨텍스트 외부에서 사용하면 `_`은 무시 항목이 아니라 유효한 변수로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="717de-150">When used outside of a supported context, `_` is treated not as a discard but as a valid variable.</span></span> <span data-ttu-id="717de-151">`_`이라는 식별자가 이미 범위 내에 있는 경우 `_`을 독립 실행형 무시 항목으로 사용하면 다음과 같은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="717de-151">If an identifier named `_` is already in scope, the use of `_` as a standalone discard can result in:</span></span>

- <span data-ttu-id="717de-152">범위 내 `_` 변수 값을 실수로 수정하여 의도한 무시 항목의 값 할당.</span><span class="sxs-lookup"><span data-stu-id="717de-152">Accidental modification of the value of the in-scope `_` variable by assigning it the value of the intended discard.</span></span> <span data-ttu-id="717de-153">예:</span><span class="sxs-lookup"><span data-stu-id="717de-153">For example:</span></span>

   <span data-ttu-id="717de-154">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="717de-154">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]</span></span>
 
- <span data-ttu-id="717de-155">형식 안전성 위반으로 인한 컴파일러 오류.</span><span class="sxs-lookup"><span data-stu-id="717de-155">A compiler error for violating type safety.</span></span> <span data-ttu-id="717de-156">예:</span><span class="sxs-lookup"><span data-stu-id="717de-156">For example:</span></span>

   <span data-ttu-id="717de-157">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="717de-157">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]</span></span>
 
- <span data-ttu-id="717de-158">컴파일러 오류 CS0136, “이름이 ‘_’인 지역 또는 매개 변수는 이 범위에서 선언될 수 없습니다. 해당 이름이 지역 또는 매개 변수를 정의하기 위해 바깥쪽 지역 범위에서 사용되었습니다.”</span><span class="sxs-lookup"><span data-stu-id="717de-158">Compiler error CS0136, "A local or parameter named '_' cannot be declared in this scope because that name is used in an enclosing local scope to define a local or parameter."</span></span> <span data-ttu-id="717de-159">예:</span><span class="sxs-lookup"><span data-stu-id="717de-159">For example:</span></span>

   <span data-ttu-id="717de-160">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="717de-160">[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]</span></span>

## <a name="see-also"></a><span data-ttu-id="717de-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="717de-161">See also</span></span>
<span data-ttu-id="717de-162">[튜플 및 기타 형식 분해](deconstruct.md) </span><span class="sxs-lookup"><span data-stu-id="717de-162">[Deconstructing tuples and other types](deconstruct.md) </span></span>  
<span data-ttu-id="717de-163">[`is` 키워드](language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="717de-163">[`is` keyword](language-reference/keywords/is.md) </span></span>  
[<span data-ttu-id="717de-164">`switch` 키워드</span><span class="sxs-lookup"><span data-stu-id="717de-164">`switch` keyword</span></span>](language-reference/keywords/switch.md)   

