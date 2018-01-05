---
title: "DateTime과 DateTimeOffset 간 변환"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2055df26618664ee130be417599f4ec46e439444
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="709e1-102">DateTime과 DateTimeOffset 간 변환</span><span class="sxs-lookup"><span data-stu-id="709e1-102">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="709e1-103">하지만 <xref:System.DateTimeOffset> 구조는 더 높은 수준의 보다 시간대 인식 제공는 <xref:System.DateTime> 구조, <xref:System.DateTime> 메서드 호출에 매개 변수가 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-103">Although the <xref:System.DateTimeOffset> structure provides a greater degree of time zone awareness than the <xref:System.DateTime> structure, <xref:System.DateTime> parameters are used more commonly in method calls.</span></span> <span data-ttu-id="709e1-104">따라서 변환 기능을 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값 및 반대의 작업은 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-104">Because of this, the ability to convert <xref:System.DateTimeOffset> values to <xref:System.DateTime> values and vice versa is particularly important.</span></span> <span data-ttu-id="709e1-105">이 항목에는 최대한 많은 표준 시간대 정보를 유지 하는 방식으로 이러한 변환을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-105">This topic shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="709e1-106">둘 다는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 형식 시간대의 시간을 나타낼 때 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-106">Both the <xref:System.DateTime> and the <xref:System.DateTimeOffset> types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="709e1-107">와 해당 <xref:System.DateTime.Kind%2A> 속성 <xref:System.DateTime> utc (협정 세계시) 및 시스템의 현지 표준 시간대를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-107">With its <xref:System.DateTime.Kind%2A> property, <xref:System.DateTime> is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="709e1-108"><xref:System.DateTimeOffset>한 번 UTC에서 오프셋 되지만 실제 표준 시간대 오프셋이 있는 속한 반영 되지 않습니다 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-108"><xref:System.DateTimeOffset> reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="709e1-109">시간 값 및 표준 시간대에 대 한 지원에 대 한 세부 정보를 참조 하십시오. [Choosing Between DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-109">For details about time values and support for time zones, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="709e1-110">DateTime에서 DateTimeOffset으로 변환</span><span class="sxs-lookup"><span data-stu-id="709e1-110">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="709e1-111"><xref:System.DateTimeOffset> 구조에 해당 하는 두 가지 방법으로 수행할 수는 제공 <xref:System.DateTime> 를 <xref:System.DateTimeOffset> 대부분 변환에 적합 한 변환:</span><span class="sxs-lookup"><span data-stu-id="709e1-111">The <xref:System.DateTimeOffset> structure provides two equivalent ways to perform <xref:System.DateTime> to <xref:System.DateTimeOffset> conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="709e1-112"><xref:System.DateTimeOffset.%23ctor%2A> 새 생성자 <xref:System.DateTimeOffset> 기반 개체는 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-112">The <xref:System.DateTimeOffset.%23ctor%2A> constructor, which creates a new <xref:System.DateTimeOffset> object based on a <xref:System.DateTime> value.</span></span>

* <span data-ttu-id="709e1-113">할당할 수 있도록 하는 암시적 변환 연산자에는 <xref:System.DateTime> 값을 한 <xref:System.DateTimeOffset> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-113">The implicit conversion operator, which allows you to assign a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> object.</span></span>

<span data-ttu-id="709e1-114">UTC 및 현지 <xref:System.DateTime> 값의 <xref:System.DateTimeOffset.Offset%2A> 결과 속성 <xref:System.DateTimeOffset> 값은 표준 시간대 오프셋을 UTC 또는 현지 시간을 정확 하 게 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-114">For UTC and local <xref:System.DateTime> values, the <xref:System.DateTimeOffset.Offset%2A> property of the resulting <xref:System.DateTimeOffset> value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="709e1-115">다음 코드는 해당 하는 UTC 시간을 변환 하는 예를 들어 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-115">For example, the following code converts a UTC time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

<span data-ttu-id="709e1-116">이 경우 `utcTime2` 변수의 오프셋은 00:00입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-116">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="709e1-117">다음 코드는 해당 하는 현지 시간을 변환 하는 마찬가지로, <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-117">Similarly, the following code converts a local time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

<span data-ttu-id="709e1-118">그러나 <xref:System.DateTime> 값을 갖는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 이러한 두 변환 메서드를 생성 한 <xref:System.DateTimeOffset> 현지 표준 시간대의 오프셋이 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-118">However, for <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, these two conversion methods produce a <xref:System.DateTimeOffset> value whose offset is that of the local time zone.</span></span> <span data-ttu-id="709e1-119">미국 태평양 표준시에서 실행되는 다음 예제에서 이러한 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-119">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

<span data-ttu-id="709e1-120">경우는 <xref:System.DateTime> 를 변환할 수 있습니다, 날짜 및 시간을 현지 표준 시간대 또는 utc 형식이 아닌 다른 값은 반영는 <xref:System.DateTimeOffset> 값 및 오버 로드 된 호출 하 여 해당 표준 시간대 정보를 보존 <xref:System.DateTimeOffset.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-120">If the <xref:System.DateTime> value reflects the date and time in something other than the local time zone or UTC, you can convert it to a <xref:System.DateTimeOffset> value and preserve its time zone information by calling the overloaded <xref:System.DateTimeOffset.%23ctor%2A> constructor.</span></span> <span data-ttu-id="709e1-121">예를 들어 다음 예제에서는 인스턴스화하는 <xref:System.DateTimeOffset> 중부 표준시 반영 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-121">For example, the following example instantiates a <xref:System.DateTimeOffset> object that reflects Central Standard Time.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

<span data-ttu-id="709e1-122">이 생성자 오버 로드에 두 번째 매개 변수는 <xref:System.TimeSpan> UTC에서의 시간 오프셋을 나타내는 개체를 호출 하 여 검색할는 <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> 시간에서 해당 표준 시간대의 메서드.</span><span class="sxs-lookup"><span data-stu-id="709e1-122">The second parameter to this constructor overload, a <xref:System.TimeSpan> object that represents the time's offset from UTC, should be retrieved by calling the <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> method of the time's corresponding time zone.</span></span> <span data-ttu-id="709e1-123">메서드의 단일 매개 변수는 <xref:System.DateTime> 변환할 날짜 및 시간을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-123">The method's single parameter is the <xref:System.DateTime> value that represents the date and time to be converted.</span></span> <span data-ttu-id="709e1-124">표준 시간대에서 일광 절약 시간제를 지원하는 경우 이 매개 변수를 사용하면 특정 날짜와 시간에 적절한 오프셋을 해당 메서드에서 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-124">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="709e1-125">DateTimeOffset에서 DateTime으로 변환</span><span class="sxs-lookup"><span data-stu-id="709e1-125">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="709e1-126"><xref:System.DateTimeOffset.DateTime%2A> 속성은 가장 일반적으로 수행 하는 데 사용 됩니다 <xref:System.DateTimeOffset> 를 <xref:System.DateTime> 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-126">The <xref:System.DateTimeOffset.DateTime%2A> property is most commonly used to perform <xref:System.DateTimeOffset> to <xref:System.DateTime> conversion.</span></span> <span data-ttu-id="709e1-127">그러나 반환 된 <xref:System.DateTime> 값 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified>다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-127">However, it returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified>, as the following example illustrates.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

<span data-ttu-id="709e1-128">즉, 모든 정보에 대 한는 <xref:System.DateTimeOffset> 변환에 의해 손실 되는 값의 관계 UTC로 때는 <xref:System.DateTimeOffset.DateTime%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-128">This means that any information about the <xref:System.DateTimeOffset> value's relationship to UTC is lost by the conversion when the <xref:System.DateTimeOffset.DateTime%2A> property is used.</span></span> <span data-ttu-id="709e1-129">이 영향을 줍니다 <xref:System.DateTimeOffset> 있기 때문에 시스템의 현지 시간 또는 UTC 시간에 일치 하는 값은 <xref:System.DateTimeOffset.DateTime%2A> 구조에만 이러한 두 표준 시간대에 반영 해당 <xref:System.DateTime.Kind%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-129">This affects <xref:System.DateTimeOffset> values that correspond to UTC time or to the system's local time because the <xref:System.DateTimeOffset.DateTime%2A> structure reflects only those two time zones in its <xref:System.DateTime.Kind%2A> property.</span></span>

<span data-ttu-id="709e1-130">변환 하는 경우 최대한 많은 표준 시간대 정보를 유지 하기 위해는 <xref:System.DateTimeOffset> 에 <xref:System.DateTime> 사용할 수 값을는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 및 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-130">To preserve as much time zone information as possible when converting a <xref:System.DateTimeOffset> to a <xref:System.DateTime> value, you can use the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> properties.</span></span>

### <a name="converting-a-utc-time"></a><span data-ttu-id="709e1-131">UTC 시간으로 변환</span><span class="sxs-lookup"><span data-stu-id="709e1-131">Converting a UTC time</span></span>

<span data-ttu-id="709e1-132">나타내기 위해 변환 된 <xref:System.DateTimeOffset.DateTime%2A> 값은 UTC 시간, 값을 검색할 수 있습니다는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-132">To indicate that a converted <xref:System.DateTimeOffset.DateTime%2A> value is the UTC time, you can retrieve the value of the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="709e1-133">다른는 <xref:System.DateTimeOffset.DateTime%2A> 두 가지 방법으로 속성:</span><span class="sxs-lookup"><span data-stu-id="709e1-133">It differs from the <xref:System.DateTimeOffset.DateTime%2A> property in two ways:</span></span>

* <span data-ttu-id="709e1-134">반환 된 <xref:System.DateTime> 값 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Utc>합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-134">It returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span>

* <span data-ttu-id="709e1-135">경우는 <xref:System.DateTimeOffset.Offset%2A> 속성 값이 다르면 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, 시간을 UTC로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-135">If the <xref:System.DateTimeOffset.Offset%2A> property value does not equal <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="709e1-136">응용 프로그램에 필요한 변환 하는 경우 <xref:System.DateTime> 값에에서 단일 시점을 명확 하 게 식별, 사용을 고려해 야는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성을 모두 처리 <xref:System.DateTimeOffset> 를 <xref:System.DateTime> 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-136">If your application requires that converted <xref:System.DateTime> values unambiguously identify a single point in time, you should consider using the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property to handle all <xref:System.DateTimeOffset> to <xref:System.DateTime> conversions.</span></span>

<span data-ttu-id="709e1-137">다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 변환 하는 속성을 <xref:System.DateTimeOffset> 오프셋 인 값 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> 에 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-137">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to convert a <xref:System.DateTimeOffset> value whose offset equals <xref:System.TimeSpan.Zero?displayProperty=nameWithType> to a <xref:System.DateTime> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

<span data-ttu-id="709e1-138">다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성에서 표준 시간대 변환 및 형식 변환을 모두 수행 하는 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-138">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to perform both a time zone conversion and a type conversion on a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a><span data-ttu-id="709e1-139">현지 시간 변환</span><span class="sxs-lookup"><span data-stu-id="709e1-139">Converting a local time</span></span>

<span data-ttu-id="709e1-140">나타내기 위해는 <xref:System.DateTimeOffset> 값 현지 시간을 나타내는 전달할 수 있습니다는 <xref:System.DateTime> 에서 반환 된 값은 <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> 속성을는 `static` (`Shared` Visual Basic의) <xref:System.DateTime.SpecifyKind%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="709e1-140">To indicate that a <xref:System.DateTimeOffset> value represents the local time, you can pass the <xref:System.DateTime> value returned by the <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> property to the `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> method.</span></span> <span data-ttu-id="709e1-141">메서드가 첫 번째 매개 변수로 전달 된 시간과 날짜를 반환 하지만 설정는 <xref:System.DateTime.Kind%2A> 속성을 두 번째 매개 변수에 의해 지정 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-141">The method returns the date and time passed to it as its first parameter, but sets the <xref:System.DateTime.Kind%2A> property to the value specified by its second parameter.</span></span> <span data-ttu-id="709e1-142">다음 코드에서는 <xref:System.DateTime.SpecifyKind%2A> 변환 하는 경우 메서드는 <xref:System.DateTimeOffset> 해당 오프셋이 현지 표준 시간대에 해당 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-142">The following code uses the <xref:System.DateTime.SpecifyKind%2A> method when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

<span data-ttu-id="709e1-143">사용할 수도 있습니다는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 변환 하는 속성을 <xref:System.DateTimeOffset> 값을 현지 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-143">You can also use the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to convert a <xref:System.DateTimeOffset> value to a local <xref:System.DateTime> value.</span></span> <span data-ttu-id="709e1-144"><xref:System.DateTime.Kind%2A> 반환 된 속성 <xref:System.DateTime> 값은 <xref:System.DateTimeKind.Local>합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-144">The <xref:System.DateTime.Kind%2A> property of the returned <xref:System.DateTime> value is <xref:System.DateTimeKind.Local>.</span></span> <span data-ttu-id="709e1-145">다음 코드에서는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성 변환 하는 경우는 <xref:System.DateTimeOffset> 해당 오프셋이 현지 표준 시간대의 해당 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-145">The following code uses the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span> 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

<span data-ttu-id="709e1-146">검색할 때는 <xref:System.DateTime> 를 사용 하 여 값의 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성, 속성의 `get` 접근자 먼저 변환는 <xref:System.DateTimeOffset> 값 UTC로 다음 변환 현지 시간으로 호출 하 여는 <xref:System.DateTimeOffset.ToLocalTime%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="709e1-146">When you retrieve a <xref:System.DateTime> value using the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property, the property's `get` accessor first converts the <xref:System.DateTimeOffset> value to UTC, then converts it to local time by calling the <xref:System.DateTimeOffset.ToLocalTime%2A> method.</span></span> <span data-ttu-id="709e1-147">즉,의 값을 검색할 수는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 형식 변환을 수행 하는 동시에 표준 시간대 변환을 수행 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-147">This means that you can retrieve a value from the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="709e1-148">또한 변환을 수행할 때 현지 표준 시간대의 조정 규칙도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-148">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="709e1-149">다음 코드에서는 사용 된 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 형식과 시간대 변환을 모두 수행 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-149">The following code illustrates the use of the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform both a type and a time zone conversion.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="709e1-150">범용 변환 메서드</span><span class="sxs-lookup"><span data-stu-id="709e1-150">A general-purpose conversion method</span></span>

<span data-ttu-id="709e1-151">라는 메서드를 정의 하는 다음 예제에서는 `ConvertFromDateTimeOffset` 변환 하 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-151">The following example defines a method named `ConvertFromDateTimeOffset` that converts <xref:System.DateTimeOffset> values to <xref:System.DateTime> values.</span></span> <span data-ttu-id="709e1-152">오프셋에 따라, 결정 여부는 <xref:System.DateTimeOffset> 값은 UTC 시간, 현지 시간 또는 다른 시간에 및 반환 된 날짜 및 시간 값의 정의 <xref:System.DateTime.Kind%2A> 속성 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-152">Based on its offset, it determines whether the <xref:System.DateTimeOffset> value is a UTC time, a local time, or some other time, and defines the returned date and time value's <xref:System.DateTime.Kind%2A> property accordingly.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

<span data-ttu-id="709e1-153">다음 예제에서는 `ConvertFromDateTimeOffset` 메서드 <xref:System.DateTimeOffset> UTC 시간, 현지 시간 및 미국에는 한 번 표시 하는 값 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-153">The follow example calls the `ConvertFromDateTimeOffset` method to convert <xref:System.DateTimeOffset> values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

<span data-ttu-id="709e1-154">이 코드에서는 다음 두 가지를 가정합니다. 이러한 가정은 응용 프로그램과 응용 프로그램에서 사용하는 날짜 및 시간 값의 소스에 따라 맞지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-154">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="709e1-155">날짜 및 시간 값 해당 오프셋이 가정 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> UTC를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-155">It assumes that a date and time value whose offset is <xref:System.TimeSpan.Zero?displayProperty=nameWithType> represents UTC.</span></span> <span data-ttu-id="709e1-156">실제로 UTC는 특정 표준 시간대의 시간이 아니라 표준화된 전세계 표준 시간대의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-156">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="709e1-157">표준 시간대 오프셋을 가질 수도 있습니다 <xref:System.TimeSpan.Zero>합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-157">Time zones can also have an offset of <xref:System.TimeSpan.Zero>.</span></span>

* <span data-ttu-id="709e1-158">현지 표준 시간대 오프셋과 동일한 오프셋의 날짜와 시간이 현지 표준 시간대를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-158">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="709e1-159">그러나 날짜 및 시간 값이 원래 표준 시간대와 관련이 없기 때문에 이와 다른 경우가 있을 수 있습니다. 날짜와 시간은 동일한 오프셋을 사용하는 다른 표준 시간대에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709e1-159">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="709e1-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="709e1-160">See also</span></span>

[<span data-ttu-id="709e1-161">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="709e1-161">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
