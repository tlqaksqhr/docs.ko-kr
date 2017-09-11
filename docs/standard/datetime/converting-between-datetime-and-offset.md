---
title: "DateTime과 DateTimeOffset 간 변환"
description: "DateTime과 DateTimeOffset 간 변환"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fab3af5b-5d0f-4384-a40a-1b5d99b30dd1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2ba70e9ea39148d040bdb46d5e00ea50dcbb8980
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="7e031-104">DateTime과 DateTimeOffset 간 변환</span><span class="sxs-lookup"><span data-stu-id="7e031-104">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="7e031-105">[System.DateTimeOffset](xref:System.DateTimeOffset) 구조체가 [System.DateTime](xref:System.DateTime) 구조체보다 더 높은 표준 시간대 인식 수준을 제공하지만 메서드 호출에서는 [DateTime](xref:System.DateTime) 매개 변수가 더 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-105">Although the [System.DateTimeOffset](xref:System.DateTimeOffset) structure provides a greater degree of time zone awareness than the [System.DateTime](xref:System.DateTime) structure, [DateTime](xref:System.DateTime) parameters are used more commonly in method calls.</span></span> <span data-ttu-id="7e031-106">따라서 [DateTimeOffset](xref:System.DateTimeOffset) 값을 [DateTime](xref:System.DateTime) 값으로 변환하거나 그 반대로 변환하는 기능은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-106">Because of this, the ability to convert [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values and vice versa is particularly important.</span></span> <span data-ttu-id="7e031-107">이 항목에서는 표준 시간대 정보를 최대한 많이 보존하는 방식으로 이러한 변환을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-107">This article shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="7e031-108">[DateTime](xref:System.DateTime) 및 [DateTimeOffset](xref:System.DateTimeOffset) 형식은 둘 다 표준 시간대의 시간을 표시할 때는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-108">Both the [DateTime](xref:System.DateTime) and the [DateTimeOffset](xref:System.DateTimeOffset) types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="7e031-109">[DateTime](xref:System.DateTime) 형식은 [Kind](xref:System.DateTime.Kind) 속성으로 UTC(협정 세계시)와 시스템의 현지 표준 시간대만 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-109">With its [Kind](xref:System.DateTime.Kind) property, [DateTime](xref:System.DateTime) is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="7e031-110">[DateTimeOffset](xref:System.DateTimeOffset) 형식은 UTC 시간 오프셋을 반영하지만 해당 오프셋이 속한 실제 표준 시간대를 반영하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-110">[DateTimeOffset](xref:System.DateTimeOffset) reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="7e031-111">표준 시간대의 시간 값 및 지원에 대한 자세한 내용은 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](choosing-between-datetime.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e031-111">For details about time values and support for time zones, see [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="7e031-112">DateTime에서 DateTimeOffset으로 변환</span><span class="sxs-lookup"><span data-stu-id="7e031-112">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="7e031-113">[DateTimeOffset](xref:System.DateTimeOffset) 구조체는 [DateTime](xref:System.DateTime)에서 [DateTimeOffset](xref:System.DateTimeOffset)으로 변환하는 데 대등하게 사용할 수 있는 두 가지 방법은 다음과 같으며, 대부분의 변환에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-113">The [DateTimeOffset](xref:System.DateTimeOffset) structure provides two equivalent ways to perform [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="7e031-114">[DateTime](xref:System.DateTime) 값 기반의 새 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 만드는 [DateTimeOffset(DateTime)](xref:System.DateTimeOffset) 생성자</span><span class="sxs-lookup"><span data-stu-id="7e031-114">The [DateTimeOffset(DateTime)](xref:System.DateTimeOffset) constructor, which creates a new [DateTimeOffset](xref:System.DateTimeOffset) object based on a [DateTime](xref:System.DateTime) value.</span></span>

* <span data-ttu-id="7e031-115">[DateTimeOffset](xref:System.DateTimeOffset) 개체에 [DateTime](xref:System.DateTime) 값을 할당할 수 있는 암시적 변환 연산자</span><span class="sxs-lookup"><span data-stu-id="7e031-115">The implicit conversion operator, which allows you to assign a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

<span data-ttu-id="7e031-116">UTC 및 현지 [DateTime](xref:System.DateTime) 값의 경우 [DateTimeOffset](xref:System.DateTimeOffset) 결과 값의 [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) 속성이 UTC 또는 현지 표준 시간대 오프셋을 정확하게 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-116">For UTC and local [DateTime](xref:System.DateTime) values, the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="7e031-117">예를 들어 다음 코드에서는 UTC 시간을 대등한 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-117">For example, the following code converts a UTC time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> 

```csharp
DateTime utcTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
utcTime1 = DateTime.SpecifyKind(utcTime1, DateTimeKind.Utc);
DateTimeOffset utcTime2 = utcTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  utcTime1, 
                  utcTime1.Kind.ToString(), 
                  utcTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM +00:00
```

```vb
Dim utcTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, _
                                        DateTimeKind.Utc)
Dim utcTime2 As DateTimeOffset = utcTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  utcTime1, _
                  utcTime1.Kind.ToString(), _
                  utcTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM  +00:00
```

<span data-ttu-id="7e031-118">이 경우 `utcTime2` 변수의 오프셋은 00:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-118">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="7e031-119">마찬가지로 다음 코드에서는 현지 시간을 대등한 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-119">Similarly, the following code converts a local time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTime localTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
localTime1 = DateTime.SpecifyKind(localTime1, DateTimeKind.Local);
DateTimeOffset localTime2 = localTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  localTime1, 
                  localTime1.Kind.ToString(), 
                  localTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim localTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, DateTimeKind.Local)
Dim localTime2 As DateTimeOffset = localTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  localTime1, _
                  localTime1.Kind.ToString(), _
                  localTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="7e031-120">하지만 해당 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)인 [DateTime](xref:System.DateTime) 값의 경우 이러한 두 변환 메서드에서는 오프셋이 현지 표준 시간대의 오프셋인 [DateTimeOffset](xref:System.DateTimeOffset) 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-120">However, for [DateTime](xref:System.DateTime) values whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), these two conversion methods produce a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset is that of the local time zone.</span></span> <span data-ttu-id="7e031-121">미국 태평양 표준시에서 실행되는 다음 예제에서 이러한 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-121">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);  // Kind is DateTimeKind.Unspecified
DateTimeOffset time2 = time1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  time1, 
                  time1.Kind.ToString(), 
                  time2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Dim time2 As DateTimeOffset = time1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  time1, _
                  time1.Kind.ToString(), _
                  time2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="7e031-122">[DateTime](xref:System.DateTime) 값에서 현지 표준 시간대 또는 UTC와 다른 날짜 및 시간을 반영하는 경우 이 값을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하고 오버로드된 [DateTimeOffset (DateTime, TimeSpan)](xref:System.DateTimeOffset) 생성자를 호출하여 해당 표준 시간대 정보를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-122">If the [DateTime](xref:System.DateTime) value reflects the date and time in something other than the local time zone or UTC, you can convert it to a [DateTimeOffset](xref:System.DateTimeOffset) value and preserve its time zone information by calling the overloaded [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset) constructor.</span></span> <span data-ttu-id="7e031-123">예를 들어 다음 예제에서는 중부 표준시를 반영하는 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-123">For example, the following example instantiates a [DateTimeOffset](xref:System.DateTimeOffset) object that reflects Central Standard Time.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);     // Kind is DateTimeKind.Unspecified
try
{
   DateTimeOffset time2 = new DateTimeOffset(time1, 
                  TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)); 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", 
                     time1, 
                     time1.Kind.ToString(), 
                     time2);
}
// Handle exception if time zone is not defined in registry
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to identify target time zone for conversion.");
}
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Try
   Dim time2 As New DateTimeOffset(time1, _
                    TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)) 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", _
                     time1, _
                     time1.Kind.ToString(), _
                     time2)
' Handle exception if time zone is not defined in registry
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to identify target time zone for conversion.")
End Try
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

<span data-ttu-id="7e031-124">이 생성자 오버로드에 대한 두 번째 매개 변수로서 UTC 시간 오프셋을 나타내는 [System.TimeSpan](xref:System.TimeSpan) 개체는 해당 시간이 속한 표준 시간대의 [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) 메서드를 호출하여 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-124">The second parameter to this constructor overload, a [System.TimeSpan](xref:System.TimeSpan) object that represents the time's offset from UTC, should be retrieved by calling the [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) method of the time's corresponding time zone.</span></span> <span data-ttu-id="7e031-125">이 메서드의 단일 매개 변수는 변환할 날짜와 시간을 나타내는 [DateTime](xref:System.DateTime) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-125">The method's single parameter is the [DateTime](xref:System.DateTime) value that represents the date and time to be converted.</span></span> <span data-ttu-id="7e031-126">표준 시간대에서 일광 절약 시간제를 지원하는 경우 이 매개 변수를 사용하면 특정 날짜와 시간에 적절한 오프셋을 해당 메서드에서 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-126">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="7e031-127">DateTimeOffset에서 DateTime으로 변환</span><span class="sxs-lookup"><span data-stu-id="7e031-127">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="7e031-128">[DateTime](xref:System.DateTime) 속성은[DateTimeOffset](xref:System.DateTimeOffset)을 [DateTime](xref:System.DateTime)으로 변환하는 데 가장 일반적으로 사용되지만,</span><span class="sxs-lookup"><span data-stu-id="7e031-128">The [DateTime](xref:System.DateTime) property is most commonly used to perform [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversion.</span></span> <span data-ttu-id="7e031-129">다음 예제와 같이 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) [Kind](xref:System.DateTime.Kind) 속성이 있는 [DateTime](xref:System.DateTime) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-129">However, it returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), as the following example illustrates.</span></span> 

```csharp
DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset sourceTime;
DateTime targetTime;

// Convert UTC to DateTime value
sourceTime = new DateTimeOffset(baseTime, TimeSpan.Zero);
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert local time to DateTime value
sourceTime = new DateTimeOffset(baseTime, 
                                TimeZoneInfo.Local.GetUtcOffset(baseTime));
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert Central Standard Time to a DateTime value
try
{
   TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime);
   sourceTime = new DateTimeOffset(baseTime, offset);
   targetTime = sourceTime.DateTime;
   Console.WriteLine("{0} converts to {1} {2}", 
                     sourceTime, 
                     targetTime, 
                     targetTime.Kind.ToString());
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.");
} 
// This example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

```vb
Const baseTime As Date = #06/19/2008 7:00AM#
Dim sourceTime As DateTimeOffset
Dim targetTime As Date

' Convert UTC to DateTime value
sourceTime = New DateTimeOffset(baseTime, TimeSpan.Zero)
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert local time to DateTime value
sourceTime = New DateTimeOffset(baseTime, _
                                TimeZoneInfo.Local.GetUtcOffset(baseTime))
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert Central Standard Time to a DateTime value
Try
   Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime)
   sourceTime = New DateTimeOffset(baseTime, offset)
   targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.")
End Try 
' This example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

<span data-ttu-id="7e031-130">즉 [DateTime](xref:System.DateTime) 속성이 사용될 때 변환을 수행하면 UTC와 [DateTimeOffset](xref:System.DateTimeOffset) 값의 관계에 대한 모든 정보가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-130">This means that any information about the [DateTimeOffset](xref:System.DateTimeOffset) value's relationship to UTC is lost by the conversion when the [DateTime](xref:System.DateTime) property is used.</span></span> <span data-ttu-id="7e031-131">이 경우 [DateTime](xref:System.DateTime) 구조체에서 자체의 [Kind](xref:System.DateTime.Kind) 속성에 있는 두 개의 표준 시간대만 반영하므로 UTC 시간이나 시스템의 현지 시간에 해당하는 [DateTimeOffset](xref:System.DateTimeOffset) 값에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-131">This affects [DateTimeOffset](xref:System.DateTimeOffset) values that correspond to UTC time or to the system's local time because the [DateTime](xref:System.DateTime) structure reflects only those two time zones in its [Kind](xref:System.DateTime.Kind) property.</span></span>

<span data-ttu-id="7e031-132">[DateTimeOffset](xref:System.DateTimeOffset) 값을 [DateTime](xref:System.DateTime) 값으로 변환할 때 표준 시간대 정보를 최대한 많이 보존하려면 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 및 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-132">To preserve as much time zone information as possible when converting a [DateTimeOffset](xref:System.DateTimeOffset) to a [DateTime](xref:System.DateTime) value, you can use the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) and [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) properties.</span></span> 

## <a name="converting-a-utc-time"></a><span data-ttu-id="7e031-133">UTC 시간 변환</span><span class="sxs-lookup"><span data-stu-id="7e031-133">Converting a UTC Time</span></span>

<span data-ttu-id="7e031-134">변환된 [DateTime](xref:System.DateTime) 값이 UTC 시간임을 나타내려면 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 속성 값을 검색하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-134">To indicate that a converted [DateTime](xref:System.DateTime) value is the UTC time, you can retrieve the value of the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property.</span></span> <span data-ttu-id="7e031-135">이 속성은 다음 두 가지 방식에서 [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) 속성과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-135">It differs from the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property in two ways:</span></span>

* <span data-ttu-id="7e031-136">[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) [Kind](xref:System.DateTime.Kind) 속성이 있는 [DateTime](xref:System.DateTime) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-136">It returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

* <span data-ttu-id="7e031-137">[DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) 속성 값이 [TimeSpan.Zero](xref:System.TimeSpan.Zero)가 아닐 경우 시간을 UTC로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-137">If the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property value does not equal [TimeSpan.Zero](xref:System.TimeSpan.Zero), it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="7e031-138">응용 프로그램에서 변환된 [DateTime](xref:System.DateTime) 값이 특정 시점을 명확하게 식별해야 하는 경우 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 속성을 사용하여 모든 [DateTimeOffset](xref:System.DateTimeOffset)을 [DateTime](xref:System.DateTime) 값으로 변환하도록 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-138">If your application requires that converted [DateTime](xref:System.DateTime) values unambiguously identify a single point in time, you should consider using the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to handle all [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversions.</span></span>

<span data-ttu-id="7e031-139">다음 코드에서는 [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 속성을 사용하여 [TimeSpan.Zero](xref:System.TimeSpan.Zero) 오프셋의 [DateTimeOffset](xref:System.DateTimeOffset) 값을 [DateTime](xref:System.DateTime) 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-139">The following code uses the [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset equals [TimeSpan.Zero](xref:System.TimeSpan.Zero) to a [DateTime](xref:System.DateTime) value.</span></span>

```csharp
DateTimeOffset utcTime1 = new DateTimeOffset(2008, 6, 19, 7, 0, 0, TimeSpan.Zero);
DateTime utcTime2 = utcTime1.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

```vb
Dim utcTime1 As New DateTimeOffset(#06/19/2008 7:00AM#, TimeSpan.Zero)
Dim utcTime2 As Date = utcTime1.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

<span data-ttu-id="7e031-140">다음 코드에서는 UtcDateTime 속성을 사용하여 [DateTimeOffset](xref:System.DateTimeOffset) 값에 대한 표준 시간대 및 형식 변환을 모두 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-140">The following code uses the UtcDateTime property to perform both a time zone conversion and a type conversion on a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTimeOffset originalTime = new DateTimeOffset(2008, 6, 19, 7, 0, 0, new TimeSpan(5, 0, 0));
DateTime utcTime = originalTime.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalTime, 
                  utcTime, 
                  utcTime.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

```vb
Dim originalTime As New DateTimeOffset(#6/19/2008 7:00AM#, _
                                       New TimeSpan(5, 0, 0))
Dim utcTime As Date = originalTime.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _ 
                  originalTime, _
                  utcTime, _
                  utcTime.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

## <a name="converting-a-local-time"></a><span data-ttu-id="7e031-141">현지 시간 변환</span><span class="sxs-lookup"><span data-stu-id="7e031-141">Converting a Local Time</span></span>

<span data-ttu-id="7e031-142">[DateTimeOffset](xref:System.DateTimeOffset) 값이 현지 시간임을 나타내려면 [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) 속성에서 반환한 [DateTime](xref:System.DateTime) 값을 static [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 메서드에 전달하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-142">To indicate that a [DateTimeOffset](xref:System.DateTimeOffset) value represents the local time, you can pass the [DateTime](xref:System.DateTime) value returned by the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property to the static [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method.</span></span> <span data-ttu-id="7e031-143">이 메서드는 전달받은 날짜와 시간을 첫 번째 매개 변수로 반환하지만 [Kind](xref:System.DateTime.Kind) 속성을 두 번째 매개 변수에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-143">The method returns the date and time passed to it as its first parameter, but sets the [Kind](xref:System.DateTime.Kind) property to the value specified by its second parameter.</span></span> <span data-ttu-id="7e031-144">다음 코드에서는 현지 표준 시간대 오프셋과 동일한 오프셋의 [DateTimeOffset](xref:System.DateTimeOffset) 값을 변환할 때 [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-144">The following code uses the [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset utcTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime utcTime2 = utcTime1.DateTime;
if (utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime))) 
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local);

Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim utcTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim utcTime2 As Date = utcTime1.DateTime
If utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime)) Then
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local)
End If   
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

<span data-ttu-id="7e031-145">또한 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성을 사용하여 [DateTimeOffset](xref:System.DateTimeOffset) 값을 현지 [DateTime](xref:System.DateTime) 값으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-145">You can also use the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value to a local [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="7e031-146">반환되는 [DateTime](xref:System.DateTime) 값의 [Kind](xref:System.DateTime.Kind) 속성은 [DateTimeKind.Local](xref:System.DateTimeKind.Local)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-146">The [Kind](xref:System.DateTime.Kind) property of the returned [DateTime](xref:System.DateTime) value is [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span></span> <span data-ttu-id="7e031-147">다음 코드에서는 현지 표준 시간대 오프셋과 동일한 오프셋의 [DateTimeOffset](xref:System.DateTimeOffset) 값을 변환할 때 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-147">The following code uses the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset localTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime localTime2 = localTime1.LocalDateTime;

Console.WriteLine("{0} converted to {1} {2}", 
                  localTime1, 
                  localTime2, 
                  localTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim localTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim localTime2 As Date = localTime1.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime1, _
                  localTime2, _
                  localTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local 
```

<span data-ttu-id="7e031-148">[DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성을 사용하여 [DateTime](xref:System.DateTime) 값을 검색하면 먼저 해당 속성의 `get` 접근자에서 [DateTimeOffset](xref:System.DateTimeOffset) 값을 UTC로 변환한 다음 [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) 메서드를 호출하여 이 UTC를 현지 시간으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-148">When you retrieve a [DateTime](xref:System.DateTime) value using the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property, the property's `get` accessor first converts the [DateTimeOffset](xref:System.DateTimeOffset) value to UTC, then converts it to local time by calling the [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) method.</span></span> <span data-ttu-id="7e031-149">즉 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성 값을 검색하여 형식 변환과 표준 시간대 변환을 동시에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-149">This means that you can retrieve a value from the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="7e031-150">또한 변환을 수행할 때 현지 표준 시간대의 조정 규칙도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-150">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="7e031-151">다음 코드에서는 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 속성을 사용하여 형식 변환과 표준 시간대의 변환을 동시에 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-151">The following code illustrates the use of the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform both a type and a time zone conversion.</span></span>

```csharp
DateTimeOffset originalDate;
DateTime localDate;

// Convert time originating in a different time zone
originalDate = new DateTimeOffset(2008, 6, 18, 7, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// Convert time originating in a different time zone 
// so local time zone's adjustment rules are applied
originalDate = new DateTimeOffset(2007, 11, 4, 4, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
//       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

```vb
Dim originalDate As DateTimeOffset
Dim localDate As Date

' Convert time originating in a different time zone
originalDate = New DateTimeOffset(#06/19/2008 7:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' Convert time originating in a different time zone 
' so local time zone's adjustment rules are applied
originalDate = New DateTimeOffset(#11/04/2007 4:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
'       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

## <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="7e031-152">범용 변환 메서드</span><span class="sxs-lookup"><span data-stu-id="7e031-152">A General-Purpose Conversion Method</span></span>

<span data-ttu-id="7e031-153">다음 예제에서는 [DateTimeOffset](xref:System.DateTimeOffset) 값을 [DateTime](xref:System.DateTime) 값으로 변환하는 `ConvertFromDateTimeOffset`이라는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-153">The following example defines a method named `ConvertFromDateTimeOffset` that converts [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="7e031-154">이 메서드는 자체의 오프셋에 기반하여 [DateTimeOffset](xref:System.DateTimeOffset) 값이 UTC 시간, 현지 시간 또는 다른 시간대 중 어느 것인지 결정하고 이에 따라 반환된 날짜 및 시간 값의 [Kind](xref:System.DateTime.Kind) 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-154">Based on its offset, it determines whether the [DateTimeOffset](xref:System.DateTimeOffset) value is a UTC time, a local time, or some other time, and defines the returned date and time value's [Kind](xref:System.DateTime.Kind) property accordingly.</span></span> 

```csharp
static DateTime ConvertFromDateTimeOffset(DateTimeOffset dateTime)
{
   if (dateTime.Offset.Equals(TimeSpan.Zero))
      return dateTime.UtcDateTime;
   else if (dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime)))
      return DateTime.SpecifyKind(dateTime.DateTime, DateTimeKind.Local);
   else
      return dateTime.DateTime;   
}
```

```vb
Function ConvertFromDateTimeOffset(dateTime As DateTimeOffset) As Date
   If dateTime.Offset.Equals(TimeSpan.Zero) Then
      Return dateTime.UtcDateTime
   ElseIf dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime))
      Return Date.SpecifyKind(dateTime.DateTime, DateTimeKind.Local)
   Else
      Return dateTime.DateTime   
   End If
```

<span data-ttu-id="7e031-155">다음 예제에서는 `ConvertFromDateTimeOffset` 메서드를 호출하여 UTC 시간, 현지 시간 및 미국 중부 표준시 시간을 나타내는 [DateTimeOffset](xref:System.DateTimeOffset) 값을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-155">The follow example calls the `ConvertFromDateTimeOffset` method to convert [DateTimeOffset](xref:System.DateTimeOffset) values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

```csharp
DateTime timeComponent = new DateTime(2008, 6, 19, 7, 0, 0);
DateTime returnedDate; 

// Convert UTC time
DateTimeOffset utcTime = new DateTimeOffset(timeComponent, TimeSpan.Zero);
returnedDate = ConvertFromDateTimeOffset(utcTime); 
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert local time
DateTimeOffset localTime = new DateTimeOffset(timeComponent, 
                           TimeZoneInfo.Local.GetUtcOffset(timeComponent)); 
returnedDate = ConvertFromDateTimeOffset(localTime);                                          
Console.WriteLine("{0} converted to {1} {2}", 
                  localTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert Central Standard Time
DateTimeOffset cstTime = new DateTimeOffset(timeComponent, 
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent));
returnedDate = ConvertFromDateTimeOffset(cstTime);
Console.WriteLine("{0} converted to {1} {2}", 
                  cstTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());
// The example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
//    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
//    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

```vb
Dim timeComponent As Date = #06/19/2008 7:00AM#
Dim returnedDate As Date 

' Convert UTC time
Dim utcTime As New DateTimeOffset(timeComponent, TimeSpan.Zero)
returnedDate = ConvertFromDateTimeOffset(utcTime) 
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert local time
Dim localTime As New DateTimeOffset(timeComponent, _
                                    TimeZoneInfo.Local.GetUtcOffset(timeComponent)) 
returnedDate = ConvertFromDateTimeOffset(localTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert Central Standard Time
Dim cstTime As New DateTimeOffset(timeComponent, _
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent))
returnedDate = ConvertFromDateTimeOffset(cstTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  cstTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())
' The example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
'    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
'    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

<span data-ttu-id="7e031-156">이 코드에서는 다음 두 가지를 가정합니다. 이러한 가정은 응용 프로그램과 응용 프로그램에서 사용하는 날짜 및 시간 값의 소스에 따라 맞지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-156">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="7e031-157">[TimeSpan.Zero](xref:System.TimeSpan.Zero) 오프셋의 날짜 및 시간 값이 UTC를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-157">It assumes that a date and time value whose offset is [TimeSpan.Zero](xref:System.TimeSpan.Zero) represents UTC.</span></span> <span data-ttu-id="7e031-158">실제로 UTC는 특정 표준 시간대의 시간이 아니라 표준화된 전세계 표준 시간대의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-158">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="7e031-159">표준 시간대에 [Zero](xref:System.TimeSpan.Zero) 오프셋이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-159">Time zones can also have an offset of [Zero](xref:System.TimeSpan.Zero).</span></span>

* <span data-ttu-id="7e031-160">현지 표준 시간대 오프셋과 동일한 오프셋의 날짜와 시간이 현지 표준 시간대를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-160">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="7e031-161">그러나 날짜 및 시간 값이 원래 표준 시간대와 관련이 없기 때문에 이와 다른 경우가 있을 수 있습니다. 날짜와 시간은 동일한 오프셋을 사용하는 다른 표준 시간대에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e031-161">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e031-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e031-162">See Also</span></span>

[<span data-ttu-id="7e031-163">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="7e031-163">Dates, times, and time zones</span></span>](index.md)





