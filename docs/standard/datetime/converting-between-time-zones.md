---
title: "표준 시간대 간 시간 변환"
description: "표준 시간대 간 시간 변환"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: c2baa48c3b79dfbc5d39652cc57fe015a2313d6e
ms.contentlocale: ko-kr
ms.lasthandoff: 11/16/2016

---

# <a name="converting-times-between-time-zones"></a><span data-ttu-id="1be88-104">표준 시간대 간 시간 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-104">Converting times between time zones</span></span>

<span data-ttu-id="1be88-105">날짜 및 시간을 사용하는 응용 프로그램에서 표준 시간대 간의 차이를 처리하는 것이 더욱 중요해지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-105">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="1be88-106">더 이상 응용 프로그램에서 모든 시간을 [System.DateTime](xref:System.DateTime) 구조체에서 제공되는 현지 시간으로 표시할 수 있다고 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-106">An application can no longer assume that all times can be expressed in the local time, which is the time available from the [System.DateTime](xref:System.DateTime) structure.</span></span> <span data-ttu-id="1be88-107">예를 들어 동아시아 지역 고객에게는 미국 동부 지역의 현재 시간을 표시하는 웹 페이지의 신뢰성이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-107">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="1be88-108">이 항목에서는 한 표준 시간대에서 다른 표준 시간대로 변환하는 방법 및 표준 시간대 인식 수준이 제한된 [System.DateTimeOffset](xref:System.DateTimeOffset) 값을 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-108">This topic explains how to convert times from one time zone to another, as well as how to convert [System.DateTimeOffset](xref:System.DateTimeOffset) values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="1be88-109">UTC로 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-109">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="1be88-110">UTC(협정 세계시)는 고정밀 원자 시간 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-110">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="1be88-111">전세계의 표준 시간대가 UTC의 양 또는 음 오프셋으로 표시됩니다..</span><span class="sxs-lookup"><span data-stu-id="1be88-111">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="1be88-112">따라서 UTC는 어느 정도 표준 시간대에서 자유롭거나 중립적인 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-112">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="1be88-113">컴퓨터 간에 날짜 및 시간의 이식성이 중요한 경우 UTC 시간을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-113">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="1be88-114">개별 표준 시간대를 UTC로 변환하면 시간을 보다 쉽게 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-114">Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="1be88-115">또한 [DateTimeOffset](xref:System.DateTimeOffset) 구조체를 serialize하여 단일 시점을 명확하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-115">You can also serialize a [DateTimeOffset](xref:System.DateTimeOffset) structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="1be88-116">[DateTimeOffset](xref:System.DateTimeOffset) 개체에서는 날짜 및 시간 값과 자체의 UTC 오프셋을 함께 저장하므로 항상 UTC 기준의 특정 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-116">Because [DateTimeOffset](xref:System.DateTimeOffset) objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="1be88-117">시간을 UTC로 변환하는 가장 쉬운 방법으로 `static`(Visual Basic의 경우 `Shared`) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-117">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1be88-118">`TimeZoneInfo.ConvertTimeToUtc(DateTime)` 메서드는 현재 .NET Core에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-118">The `TimeZoneInfo.ConvertTimeToUtc(DateTime)` method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="1be88-119">이 메서드에서 수행되는 정확한 변환은 다음 표에서 보여 주듯이 `DateTime` 매개 변수의 [Kind](xref:System.DateTime.Kind) 속성 값에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-119">The exact conversion performed by the method depends on the value of the `DateTime` parameter's [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="1be88-120">[DateTime.Kind](xref:System.DateTimeKind) 속성</span><span class="sxs-lookup"><span data-stu-id="1be88-120">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="1be88-121">변환</span><span class="sxs-lookup"><span data-stu-id="1be88-121">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="1be88-122">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="1be88-122">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="1be88-123">현지 시간을 UTC로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-123">Converts local time to UTC.</span></span>
[<span data-ttu-id="1be88-124">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="1be88-124">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="1be88-125">`DateTime` 매개 변수가 현지 시간인 것으로 가정하고 현지 시간을 UTC로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-125">Assumes the `DateTime` parameter is local time and converts local time to UTC.</span></span>
[<span data-ttu-id="1be88-126">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="1be88-126">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="1be88-127">변경하지 않은 `DateTime` 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-127">Returns the `DateTime` parameter unchanged.</span></span>

<span data-ttu-id="1be88-128">다음 코드에서는 현재 현지 시간을 UTC로 변환하고 그 결과를 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-128">The following code converts the current local time to UTC and displays the result to the console.</span></span>

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
><span data-ttu-id="1be88-129">[TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 메서드에서 [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) 및 [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) 메서드와 다른 결과를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-129">The [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method does not necessarily produce results that are identical to the [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) and [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) methods.</span></span> <span data-ttu-id="1be88-130">호스트 시스템의 현지 표준 시간대에 여러 조정 규칙이 포함된 경우 [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx)는 특정 날짜 및 시간에 적절한 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-130">If the host system's local time zone includes multiple adjustment rules, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="1be88-131">다른 두 메서드는 항상 최신 조정 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-131">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="1be88-132">날짜 및 시간 값이 현지 시간이나 UTC를 나타내지 않는 경우 [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) 메서드에서 잘못된 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-132">If the date and time value does not represent either the local time or UTC, the [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) method will likely return an erroneous result.</span></span> <span data-ttu-id="1be88-133">그러나 [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 메서드를 사용하면 지정된 표준 시간대의 날짜 및 시간을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-133">However, you can use the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="1be88-134">대상 표준 시간대를 나타내는 TimeZoneInfo 개체 검색에 대한 자세한 내용은 [로컬 시스템에 정의된 표준 시간대 찾기](finding-the-time-zones-on-local-system.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be88-134">(For details on retrieving a TimeZoneInfo object that represents the destination time zone, see [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md).</span></span> <span data-ttu-id="1be88-135">다음 코드에서는 [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 메서드를 사용하여 동부 표준시를 UTC로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-135">The following code uses the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert Eastern Standard Time to UTC.</span></span>

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

<span data-ttu-id="1be88-136">[DateTime](xref:System.DateTime) 개체의 [Kind](xref:System.DateTimeKind) 속성과 표준 시간대가 일치하지 않는 경우 이 메서드에서 [ArgumentException](xref:System.ArgumentException)을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-136">Note that this method throws an [ArgumentException](xref:System.ArgumentException) if the [DateTime](xref:System.DateTime) object's [Kind](xref:System.DateTimeKind) property and the time zone are mismatched.</span></span> <span data-ttu-id="1be88-137">Kind 속성이 [DateTimeKind.Local](xref:System.DateTimeKind.Local)이지만 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체에서 현지 표준 시간대를 나타내지 않는 경우 또는 Kind 속성이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)이지만 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체가 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)와 같지 않은 경우 불일치가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-137">A mismatch occurs if the Kind property is [DateTimeKind.Local](xref:System.DateTimeKind.Local) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not represent the local time zone, or if the Kind property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

<span data-ttu-id="1be88-138">이러한 메서드는 모두 [DateTime](xref:System.DateTime) 값을 매개 변수로 사용하고 [DateTime](xref:System.DateTime) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-138">All of these methods take [DateTime](xref:System.DateTime) values as parameters and return a [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="1be88-139">[DateTimeOffset](xref:System.DateTimeOffset) 값의 경우[DateTimeOffset](xref:System.DateTimeOffset) 구조체에 현재 인스턴스의 날짜 및 시간을 UTC로 변환하는 [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) 인스턴스 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-139">For [DateTimeOffset](xref:System.DateTimeOffset) values, the [DateTimeOffset](xref:System.DateTimeOffset) structure has a [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="1be88-140">다음 예제에서는 [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) 메서드를 호출하여 현지 시간과 여러 다른 시간을 UTC로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-140">The following example calls the [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="1be88-141">UTC를 지정한 표준 시간대로 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-141">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="1be88-142">UTC를 현지 시간으로 변환하려면 다음에 나오는 [UTC를 현지 시간으로 변환](#converting-utc-to-local-time) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be88-142">To convert UTC to local time, see the [Converting UTC to local time](#converting-utc-to-local-time) section that follows.</span></span> 

<span data-ttu-id="1be88-143">UTC를 사용자가 지정하는 표준 시간대 시간으로 변환하려면 [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-143">To convert UTC to the time in any time zone that you designate, call the [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1be88-144">\`TimeZoneInfo.ConvertTimeFromUtc' 메서드는 현재 .NET Core에서 제공되고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-144">The \`TimeZoneInfo.ConvertTimeFromUtc' method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="1be88-145">이 메서드에서 사용하는 두 개의 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-145">The method takes two parameters:</span></span>

* <span data-ttu-id="1be88-146">변환할 UTC.</span><span class="sxs-lookup"><span data-stu-id="1be88-146">The UTC to convert.</span></span> <span data-ttu-id="1be88-147">[Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) 또는 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)로 설정된 [DateTime](xref:System.DateTime) 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-147">This must be a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> 

* <span data-ttu-id="1be88-148">UTC를 변환한 값이 속하게 될 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="1be88-148">The time zone to convert the UTC to.</span></span> 

<span data-ttu-id="1be88-149">다음 코드는 UTC를 중부 표준시로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-149">The following code converts UTC to Central Standard Time.</span></span>

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="1be88-150">UTC를 현지 시간으로 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-150">Converting UTC to local time</span></span>

<span data-ttu-id="1be88-151">UTC를 현지 시간으로 변환하려면 시간을 변환할 [DateTime](xref:System.DateTime) 개체의 [DateTime.ToLocalTime](xref:System.DateTime) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-151">To convert UTC to local time, call the [DateTime.ToLocalTime](xref:System.DateTime) method of the [DateTime](xref:System.DateTime) object whose time you want to convert.</span></span> <span data-ttu-id="1be88-152">이 메서드의 정확한 동작은 다음 표에서 보여 주듯이 개체의 [Kind](xref:System.DateTime.Kind) 속성 값에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-152">The exact behavior of the method depends on the value of the object’s [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="1be88-153">[DateTime.Kind](xref:System.DateTimeKind) 속성</span><span class="sxs-lookup"><span data-stu-id="1be88-153">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="1be88-154">변환</span><span class="sxs-lookup"><span data-stu-id="1be88-154">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="1be88-155">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="1be88-155">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="1be88-156">변경되지 않은 [DateTime](xref:System.DateTime) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-156">Returns the [DateTime](xref:System.DateTime) value unchanged.</span></span>
[<span data-ttu-id="1be88-157">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="1be88-157">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="1be88-158">[DateTime](xref:System.DateTime) 값이 UTC인 것으로 가정하고 UTC를 현지 시간으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-158">Assumes that the [DateTime](xref:System.DateTime) value is UTC and converts the UTC to local time.</span></span>
[<span data-ttu-id="1be88-159">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="1be88-159">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="1be88-160">[DateTime](xref:System.DateTime) 값을 현지 시간으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-160">Converts the [DateTime](xref:System.DateTime) value to local time.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="1be88-161">두 표준 시간대 간 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-161">Converting between any two time zones</span></span>

<span data-ttu-id="1be88-162">[TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))을 사용하면 두 표준 시간대 간에 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-162">You can convert between any two time zones by using the static [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> <span data-ttu-id="1be88-163">이 메서드의 매개 변수는 변환할 [DateTime](xref:System.DateTime) 값, 이 날짜 및 시간 값의 표준 시간대를 나타내는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체, 변환된 날짜 및 시간 값이 속하게 될 표준 시간대를 나타내는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-163">This method's parameters are the [DateTime](xref:System.DateTime) value to convert, a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone of the date and time value, and a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="1be88-164">이 메서드에서는 변환할 날짜 및 시간 값의 [Kind](xref:System.DateTime.Kind) 속성과 표준 시간대를 나타내는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체 또는 표준 시간대 식별자가 서로 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-164">The method requires that the [Kind](xref:System.DateTime.Kind) property of the date and time value to convert and the [TimeZoneInfo](xref:System.TimeZoneInfo) object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="1be88-165">그렇지 않으면 [ArgumentException](xref:System.ArgumentException)이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-165">Otherwise, an [ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="1be88-166">예를 들어 날짜 및 시간 값의 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Local](xref:System.DateTimeKind.Local)이면 메서드에 매개 변수로 전달된 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체가 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local)과 같지 않은 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-166">For example, if the [Kind](xref:System.DateTime.Kind) property of the date and time value is [DateTimeKind.Local](xref:System.DateTimeKind.Local), an exception is thrown if the [TimeZoneInfo](xref:System.TimeZoneInfo) object passed as a parameter to the method is not equal to [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span></span> <span data-ttu-id="1be88-167">또한 메서드에 매개 변수로 전달된 식별자가 [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id)와 같지 않은 경우에도 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-167">An exception is also thrown if the identifier passed as a parameter to the method is not equal to [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span></span>

<span data-ttu-id="1be88-168">다음 예제에서는 [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) 메서드를 사용하여 하와이 표준시를 현지 시간으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-168">The following example uses the [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method to convert from Hawaiian Standard Time to local time.</span></span>

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="1be88-169">DateTimeOffset 값 변환</span><span class="sxs-lookup"><span data-stu-id="1be88-169">Converting DateTimeOffset values</span></span>

<span data-ttu-id="1be88-170">[System.DateTimeOffset](xref:System.DateTimeOffset) 개체는 인스턴스화될 때 표준 시간대에서 분리되므로 이 개체에서 나타낸 날짜 및 시간 값은 표준 시간대를 완전하게 인식하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-170">Date and time values represented by [System.DateTimeOffset](xref:System.DateTimeOffset) objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="1be88-171">그러나 많은 경우에는 응용 프로그램에서 특정 표준 시간대의 시간이 아니라 단순히 서로 다른 UTC 오프셋 두 개를 기준으로 날짜 및 시간을 변환하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-171">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="1be88-172">이러한 변환을 수행하려면 현재 인스턴스의 [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-172">To perform this conversion, you can call the current instance's [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) method.</span></span> <span data-ttu-id="1be88-173">이 메서드의 단일 매개 변수는 메서드에서 반환할 새 날짜 및 시간 값의 오프셋을 나타내는 [TimeSpan](xref:System.TimeSpan)입니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-173">The method's single parameter is [TimeSpan](xref:System.TimeSpan) representing the offset of the new date and time value that the method is to return.</span></span>  

<span data-ttu-id="1be88-174">예를 들어 사용자가 웹 페이지에서 요청한 날짜 및 시간이 알려져 있고 이 값이 MM/dd/yyyy hh:mm:ss zzzz 형식의 문자열로 serialize된 경우 뒤따르는 `ReturnTimeOnServer` 메서드에서 이 날짜 및 시간 값을 웹 서버의 날짜 및 시간 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-174">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

<span data-ttu-id="1be88-175">UTC보다 다섯 시간 빠른 표준 시간대의 날짜 및 시간을 나타내는 "9/1/2007 5:32:07 -05:00" 문자열이 메서드에 전달되는 경우 이 메서드에서는 미국 태평양 표준 시간대에 있는 서버에 대해 9/1/2007 3:32:07 AM -07:00을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-175">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="1be88-176">또한 [TimeZoneInfo](xref:System.TimeZoneInfo) 클래스에는 [System.DateTimeOffset](xref:System.DateTimeOffset) 값으로 표준 시간대 변환을 수행하기 위해 오버로드되는 [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-176">The [TimeZoneInfo](xref:System.TimeZoneInfo) class also includes an overloaded [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method that performs time zone conversions with [System.DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="1be88-177">이 메서드의 매개 변수는 [System.DateTimeOffset](xref:System.DateTimeOffset) 값 및 변환된 시간이 속하는 표준 시간대에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-177">The method's parameters are a [System.DateTimeOffset](xref:System.DateTimeOffset) value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="1be88-178">이 메서드를 호출하면 [System.DateTimeOffset](xref:System.DateTimeOffset) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-178">The method call returns a [System.DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="1be88-179">예를 들어 이전 예제의 `ReturnTimeOnServer` 메서드를 다음과 같이 다시 작성하면 [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be88-179">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a><span data-ttu-id="1be88-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1be88-180">See also</span></span>

[<span data-ttu-id="1be88-181">TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="1be88-181">TimeZoneInfo</span></span>](xref:System.TimeZoneInfo)

[<span data-ttu-id="1be88-182">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="1be88-182">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="1be88-183">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="1be88-183">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)



