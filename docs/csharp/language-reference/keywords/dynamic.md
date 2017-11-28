---
title: "dynamic(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: "25"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e3bf51ab62e195f7a5d1f0641f62380977c731ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="dynamic-c-reference"></a><span data-ttu-id="a69a1-102">dynamic(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a69a1-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="a69a1-103">`dynamic` 형식을 통해 컴파일 시간 형식 검사를 우회하는 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="a69a1-104">대신, 이러한 작업은 런타임에 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="a69a1-105">`dynamic` 형식은 Office Automation API 등의 COM API, IronPython 라이브러리 등의 동적 API 및 HTML DOM(문서 개체 모델)에 대한 액세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="a69a1-106">`dynamic` 형식은 대부분의 상황에서 `object` 형식처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="a69a1-107">그러나 `dynamic` 형식의 식을 포함하는 작업은 컴파일러에서 확인되거나 형식이 검사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="a69a1-108">컴파일러는 작업에 대한 정보를 패키지하며, 나중에 해당 정보는 런타임에 작업을 평가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="a69a1-109">이 과정에서 `dynamic` 형식의 변수는 `object` 형식의 변수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="a69a1-110">따라서 `dynamic` 형식은 컴파일 시간에만 존재하고 런타임에는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="a69a1-111">다음 예제에서는 `dynamic` 형식의 변수와 `object` 형식의 변수를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="a69a1-112">컴파일 시간에 각 변수의 형식을 확인하려면 `WriteLine` 문의 `dyn` 또는 `obj` 위에 마우스 포인터를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="a69a1-113">IntelliSense는 `dyn`에 대해 **dynamic**을 표시하고 `obj`에 대해 **object**를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 <span data-ttu-id="a69a1-114">`WriteLine` 문은 `dyn` 및 `obj`의 런타임 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-114">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="a69a1-115">이 시점에는 둘 다 동일한 형식인 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-115">At that point, both have the same type, integer.</span></span> <span data-ttu-id="a69a1-116">다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-116">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="a69a1-117">컴파일 시간에 `dyn` 및 `obj` 간의 차이를 보려면 앞의 예제에서 선언과 `WriteLine` 문 사이에 다음 두 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-117">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="a69a1-118">`obj + 3` 식에 정수와 개체를 추가하려는 시도와 관련해서 컴파일러 오류가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-118">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="a69a1-119">하지만 `dyn + 3`에 대한 오류는 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-119">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="a69a1-120">`dyn`의 형식이 `dynamic`이기 때문에 `dyn`을 포함하는 식은 컴파일 시간에 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-120">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="a69a1-121">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="a69a1-121">Context</span></span>  
 <span data-ttu-id="a69a1-122">`dynamic` 키워드는 직접 또는 다음과 같은 경우에 생성된 형식의 구성 요소로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-122">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="a69a1-123">선언에서 속성, 필드, 인덱서, 매개 변수, 반환 값, 지역 변수 또는 형식 제약 조건으로.</span><span class="sxs-lookup"><span data-stu-id="a69a1-123">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="a69a1-124">다음 클래스 정의는 여러 선언에 `dynamic`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-124">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   <span data-ttu-id="a69a1-125">명시적 형식 변환에서 변환의 대상 형식으로.</span><span class="sxs-lookup"><span data-stu-id="a69a1-125">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   <span data-ttu-id="a69a1-126">`is` 연산자 또는 `as` 연산자의 오른쪽, 생성된 형식의 일부로 포함된 `typeof` 인수 등 형식이 값으로 사용되는 모든 컨텍스트에서.</span><span class="sxs-lookup"><span data-stu-id="a69a1-126">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="a69a1-127">예를 들어 다음 식에서 `dynamic`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-127">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     [!code-csharp[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="a69a1-128">예제</span><span class="sxs-lookup"><span data-stu-id="a69a1-128">Example</span></span>  
 <span data-ttu-id="a69a1-129">다음 예제에서는 여러 선언에 `dynamic`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-129">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="a69a1-130">또한 `Main` 메서드는 컴파일 시간 형식 검사를 런타임 형식 검사와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a69a1-130">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 <span data-ttu-id="a69a1-131">자세한 내용 및 예제는 [dynamic 형식 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a69a1-131">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69a1-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a69a1-132">See Also</span></span>  
 <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
 <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
 [<span data-ttu-id="a69a1-133">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="a69a1-133">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="a69a1-134">object</span><span class="sxs-lookup"><span data-stu-id="a69a1-134">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
 [<span data-ttu-id="a69a1-135">is</span><span class="sxs-lookup"><span data-stu-id="a69a1-135">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="a69a1-136">as</span><span class="sxs-lookup"><span data-stu-id="a69a1-136">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
 [<span data-ttu-id="a69a1-137">typeof</span><span class="sxs-lookup"><span data-stu-id="a69a1-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
 [<span data-ttu-id="a69a1-138">방법: as 및 is 연산자를 사용한 안전한 캐스팅</span><span class="sxs-lookup"><span data-stu-id="a69a1-138">How to: Safely Cast by Using as and is Operators</span></span>](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
 [<span data-ttu-id="a69a1-139">연습: 동적 개체 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="a69a1-139">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
