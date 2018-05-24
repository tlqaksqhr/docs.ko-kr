---
title: nullable 형식(C# 프로그래밍 가이드)
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: fcff492f420a60a41b373bf9042ed0c2d66d0446
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="61a64-102">nullable 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="61a64-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="61a64-103">Nullable 형식은 <xref:System.Nullable%601?displayProperty=nameWithType> 구조체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="61a64-104">Null 허용 형식은 해당 내부 형식의 올바른 값 범위와 추가 `null` 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="61a64-105">예를 들어 "Nullable of Int32"로도 나타내는 `Nullable<Int32>`에는 -2147483648에서 2147483647까지 값이 할당되거나 `null` 값이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="61a64-106">`Nullable<bool>`에는 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 또는 [null](../../../csharp/language-reference/keywords/null.md) 값이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="61a64-107">숫자 및 부울 형식에 `null`을 할당하는 기능은 값을 할당할 수 없는 요소를 포함하는 데이터베이스 및 기타 데이터 형식을 처리할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="61a64-108">예를 들어 데이터베이스의 부울 필드는 값 `true` 또는 `false`를 저장하거나 정의되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="61a64-109">추가 예제를 보려면 [Null 허용 형식 사용](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61a64-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="61a64-110">null 허용 형식 개요</span><span class="sxs-lookup"><span data-stu-id="61a64-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="61a64-111">null 허용 형식은 다음 특성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="61a64-112">null 허용 형식은 `null` 값이 할당될 수 있는 값-형식 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="61a64-113">참조 형식에 따라 null 허용 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="61a64-114">(참조 형식은 `null` 값을 이미 지원합니다.)</span><span class="sxs-lookup"><span data-stu-id="61a64-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="61a64-115">구문 `T?`는 <xref:System.Nullable%601>의 축약형입니다. 여기서 `T`는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="61a64-116">두 가지 형태는 동일하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="61a64-117">일반 값 형식의 경우처럼 null 허용 형식에 값을 할당합니다(예: `int? x = 10;` 또는 `double? d = 4.108`).</span><span class="sxs-lookup"><span data-stu-id="61a64-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="61a64-118">null 허용 형식에 값 `null`을 할당할 수도 있습니다. `int? x = null.`</span><span class="sxs-lookup"><span data-stu-id="61a64-118">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="61a64-119"><xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> 메서드를 사용하여 할당된 값 또는 내부 형식의 기본값(값이 `null`인 경우)을 반환합니다(예: `int j = x.GetValueOrDefault();`).</span><span class="sxs-lookup"><span data-stu-id="61a64-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="61a64-120">다음 예제와 같이 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 읽기 전용 속성을 사용하여 null인지 테스트하고 값을 검색합니다. `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="61a64-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="61a64-121">`HasValue` 속성은 변수에 값이 있으면 `true`를, `null`이면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="61a64-122">`Value` 속성은 할당된 값이 있으면 해당 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="61a64-123">그렇지 않으면 <xref:System.InvalidOperationException?displayProperty=nameWithType>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="61a64-124">`HasValue`의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="61a64-125">`Value` 속성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="61a64-126">다음 예제와 같이 null 허용 형식에 `==` 및 `!=` 연산자를 사용할 수도 있습니다. `if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="61a64-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="61a64-127">`??` 연산자를 사용하여 현재 값이 `null`인 null 허용 형식이 null을 허용하지 않는 형식에 할당되면 적용될 기본값을 할당합니다(예: `int? x = null; int y = x ?? -1;`).</span><span class="sxs-lookup"><span data-stu-id="61a64-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="61a64-128">중첩된 null 허용 형식은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a64-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="61a64-129">다음 줄은 컴파일되지 않습니다. `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="61a64-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61a64-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="61a64-130">Related Sections</span></span>  
 <span data-ttu-id="61a64-131">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61a64-131">For more information:</span></span>  
  
-   [<span data-ttu-id="61a64-132">Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="61a64-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="61a64-133">Nullable 형식 boxing</span><span class="sxs-lookup"><span data-stu-id="61a64-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="61a64-134">?? 연산자</span><span class="sxs-lookup"><span data-stu-id="61a64-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="61a64-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="61a64-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61a64-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61a64-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="61a64-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="61a64-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="61a64-138">C#</span><span class="sxs-lookup"><span data-stu-id="61a64-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="61a64-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="61a64-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="61a64-140">'리프트'란 정확히 어떤 의미입니까?</span><span class="sxs-lookup"><span data-stu-id="61a64-140">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
