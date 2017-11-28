---
title: "열거형 형식(C# 프로그래밍 가이드)"
ms.date: 09/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13ec7d5d2a44cddb2b7f440c8d811c2e4060d432
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="49883-102">열거형 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="49883-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="49883-103">열거형 형식(열거형이라고도 함)은 변수에 할당할 수 있는 명명된 정수 계열 상수 집합을 정의하는 효율적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="49883-104">예를 들어 값이 요일을 나타내는 변수를 정의해야 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="49883-105">해당 변수에 저장할 수 있는 의미 있는 값이 7개만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="49883-106">이러한 값을 정의하려면 [enum](../../csharp/language-reference/keywords/enum.md) 키워드를 사용하여 선언되는 열거형 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="49883-107">기본적으로 열거형에서 각 요소의 기본 형식은 [int](../../csharp/language-reference/keywords/int.md)입니다. 이전 예제와 같이 콜론을 사용하여 다른 정수 계열 숫자 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-107">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="49883-108">가능한 형식의 전체 목록은 [enum(C# 참조)](../../csharp/language-reference/keywords/enum.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49883-108">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="49883-109">다음 예제와 같이 기본 형식으로 캐스트하여 기본 숫자 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="49883-110">다음은 숫자 형식 대신 열거형을 사용할 경우의 장점입니다.</span><span class="sxs-lookup"><span data-stu-id="49883-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="49883-111">클라이언트 코드에 대해 변수에 유효한 값을 명확하게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="49883-112">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에서 IntelliSense는 정의된 값 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-112">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>

<span data-ttu-id="49883-113">열거자 목록의 요소에 대해 값을 지정하지 않으면 값이 자동으로 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="49883-114">이전 예제에서 `Day.Sunday`의 값은 0이고, `Day.Monday`의 값은 1이 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49883-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="49883-115">새 `Day` 개체를 만드는 경우 값을 명시적으로 지정하지 않으면 기본값 `Day.Sunday`(0)가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49883-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="49883-116">열거형을 만들 때 가장 논리적인 기본값을 선택하고 0 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="49883-117">그러면 열거형을 만들 때 값을 명시적으로 지정하지 않은 경우 모든 열거형에 해당 기본값이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="49883-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="49883-118">`meetingDay` 변수가 `Day` 형식이면 명시적 캐스트 없이 `Day`에 정의된 값 중 하나만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="49883-119">또한 모임 날짜가 변경될 경우 `Day`에서 `meetingDay` 사이의 새 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="49883-120">임의의 정수 값을 `meetingDay`에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="49883-121">예를 들어 `meetingDay = (Day) 42` 코드 줄은 오류를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="49883-122">그러나 열거형 변수는 enum에 정의된 값 중 하나만 포함한다는 암시적 기대로 인해 이렇게 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49883-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="49883-123">열거형 형식의 변수에 임의의 값을 할당하면 오류가 발생할 위험이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="49883-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="49883-124">열거형 형식의 열거자 목록에 있는 요소에 값을 할당하고 계산된 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="49883-125">비트 플래그로서 열거형 형식</span><span class="sxs-lookup"><span data-stu-id="49883-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="49883-126">열거형 형식을 사용하여 비트 플래그를 정의할 수 있으며, 그러면 열거형 형식의 인스턴스에서 열거자 목록에 정의된 값의 조합을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="49883-127">물론, 일부 조합은 의미가 없거나 프로그램 코드에서 허용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="49883-128">`AND`, `OR`, `NOT` 및 `XOR` 비트 연산을 수행할 수 있도록 <xref:System.FlagsAttribute?displayProperty=nameWithType> 특성을 적용하고 적절히 값을 정의하여 비트 플래그 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49883-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="49883-129">비트 플래그 열거형에서 "플래그가 설정되지 않음"을 의미하는 0 값을 갖는 명명된 상수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="49883-130">0 값이 "플래그가 설정되지 않음"을 의미하지 않는 경우 이 값을 플래그에 지정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="49883-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="49883-131">다음 예제에서는 `Days`라는 다른 버전의 `Day` 열거형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="49883-132">`Days`에는 `Flags` 특성이 있고 각 값에는 다음으로 큰 2의 거듭제곱이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="49883-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="49883-133">따라서 값이 `Days.Tuesday | Days.Thursday` 인 `Days` 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="49883-134">열거형에서 플래그를 설정하려면 다음 예제와 같이 비트 `OR` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="49883-135">특정 플래그가 설정되어 있는지 확인하려면 다음 예제와 같이 비트 `AND` 연산을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49883-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="49883-136"><xref:System.FlagsAttribute?displayProperty=nameWithType> 특성을 사용하여 열거형 형식을 정의할 때 고려할 사항에 대한 자세한 내용은 <xref:System.Enum?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49883-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="49883-137">System.Enum 메서드를 사용하여 열거형 값 검색 및 조작</span><span class="sxs-lookup"><span data-stu-id="49883-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="49883-138">모든 열거형은 <xref:System.Enum?displayProperty=nameWithType> 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="49883-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="49883-139"><xref:System.Enum?displayProperty=nameWithType>에서 새 클래스를 파생시킬 수는 없지만 해당 메서드를 사용하여 열거형 인스턴스에서 값에 대한 정보를 검색하고 값을 조작할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="49883-140">자세한 내용은 <xref:System.Enum?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="49883-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="49883-141">또한 확장 메서드를 사용하여 열거형에 대한 새 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49883-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="49883-142">자세한 내용은 [방법: 새 열거형 메서드 만들기](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49883-142">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49883-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49883-143">See also</span></span>
 <xref:System.Enum?displayProperty=nameWithType>  
 [<span data-ttu-id="49883-144">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="49883-144">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="49883-145">enum</span><span class="sxs-lookup"><span data-stu-id="49883-145">enum</span></span>](../../csharp/language-reference/keywords/enum.md)
