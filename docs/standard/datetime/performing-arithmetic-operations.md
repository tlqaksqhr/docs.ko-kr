---
title: "날짜 및 시간에 대한 산술 연산 수행"
description: "날짜 및 시간에 대한 산술 연산 수행"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b872cc4c2b799ddafc9df263795d860754d1ec17
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="73240-104">날짜 및 시간에 대한 산술 연산 수행</span><span class="sxs-lookup"><span data-stu-id="73240-104">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="73240-105">[System.DateTime](xref:System.DateTime) 및 [System.DateTimeOffset](xref:System.DateTimeOffset) 구조는 모두 해당 값에 산술 연산을 수행하는 구성원을 제공하지만 산술 연산의 결과는 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="73240-105">Although both the [System.DateTime](xref:System.DateTime) and the [System.DateTimeOffset](xref:System.DateTimeOffset) structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="73240-106">이 문서는 이러한 차이점을 검사하고 날짜 및 시간 데이터에서 표준 시간대 인식 수준에 연결하며 날짜 및 시간 데이터를 사용하여 표준 시간대 인식 작업을 완벽하게 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-106">This article examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="73240-107">DateTime 값을 사용한 비교 및 산술 연산</span><span class="sxs-lookup"><span data-stu-id="73240-107">Comparisons and Arithmetic Operations with DateTime Values</span></span>

<span data-ttu-id="73240-108">[System.DateTime](xref:System.DateTime) 값은 제한된 수준의 표준 시간대 인식을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-108">[System.DateTime](xref:System.DateTime) values possess a limited degree of time zone awareness.</span></span> <span data-ttu-id="73240-109">[DateTime.Kind](xref:System.DateTime.Kind) 속성을 사용하면 [System.DateTimeKind](xref:System.DateTimeKind) 값을 현지 시간 또는 UTC(협정 세계시) 또는 지정되지 않은 표준 시간대의 시간을 나타내는지 여부를 나타내는 날짜 및 시간에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-109">The [DateTime.Kind](xref:System.DateTime.Kind) property allows a [System.DateTimeKind](xref:System.DateTimeKind) value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="73240-110">그러나 [DateTime](xref:System.DateTime) 값에 대한 날짜 및 시간 산술 연산을 비교하고 수행할 경우 이 제한된 표준 시간대 정보는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-110">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="73240-111">현재 UTC 시간을 포함한 현재 현지 시간을 비교하는 다음 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73240-111">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

<span data-ttu-id="73240-112">[DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) 메서드는 현지 시간이 UTC 시간보다 빠르거나 느리다고 보고하고, 빼기 연산은 미국에 있는 시스템의 UTC와 현지 시간 간 차이를 나타냅니다. 태평양 표준 시간대는&7;시간입니다.</span><span class="sxs-lookup"><span data-stu-id="73240-112">The [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="73240-113">하지만 이러한 두 개의 값은 시간에서 단일 지점의 다양한 표현을 제공하기 때문에 이 경우에 이 시간 간격이 UTC에서 현지 표준 시간대 오프셋을 발생시키는 것이 명확합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-113">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span> 

<span data-ttu-id="73240-114">보다 일반적으로 해당 결과의 해석에 영향을 줄 수 있지만 [DateTimeKind](xref:System.DateTimeKind) 속성은 [DateTime](xref:System.DateTime) 비교 및 산술 연산 메서드에서 반환되는 결과에 영향을 주지 않습니다(시간에서 두 개의 동일한 지점을 비교하면 알 수 있듯이).</span><span class="sxs-lookup"><span data-stu-id="73240-114">More generally, the [DateTimeKind](xref:System.DateTimeKind) property does not affect the results returned by [DateTime](xref:System.DateTime) comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="73240-115">예:</span><span class="sxs-lookup"><span data-stu-id="73240-115">For example:</span></span>

* <span data-ttu-id="73240-116">[DateTimeKind](xref:System.DateTimeKind) 속성이 둘 다 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)인 두 개의 날짜 및 시간 값에 대해 수행된 모든 산술 연산 작업의 결과는 두 값 사이의 실제 시간 간격을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-116">The result of any arithmetic operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) reflects the actual time interval between the two values.</span></span> <span data-ttu-id="73240-117">마찬가지로 이러한 두 개의 날짜 및 시간 값을 비교하면 시간 간의 관계를 정확하게 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-117">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="73240-118">[DateTimeKind](xref:System.DateTimeKind) 속성이 둘 다 [DateTimeKind.Local](xref:System.DateTimeKind.Local)인 두 개의 날짜 및 시간 값 또는 서로 다른 [DateTimeKind](xref:System.DateTimeKind) 속성 값인 두 개의 날짜 및 시간 값에 대해 수행된 모든 산술 연산 또는 비교 작업은 두 값 사이에 있는 클록 시간의 차이를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-118">The result of any arithmetic or comparison operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Local](xref:System.DateTimeKind.Local) or on two date and time values with different [DateTimeKind](xref:System.DateTimeKind) property values reflects the difference in clock time between the two values.</span></span> 

* <span data-ttu-id="73240-119">로컬 날짜 및 시간 값에 대한 산술 또는 비교 작업은 특정 값이 모호하거나 잘못되었는지 여부를 고려하지 않거나 현지 표준 시간대 전환 또는 일광 절약 시간에서 발생하는 모든 조정 규칙의 효과를 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-119">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="73240-120">UTC와 현지 시간 사이의 차이를 비교하거나 계산하는 작업에는 결과에 있는 UTC에서 현지 표준 시간대 오프셋과 동일한 시간 간격이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-120">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span> 

* <span data-ttu-id="73240-121">지정되지 않은 시간과 UTC 또는 현지 시간 사이의 차이를 비교하거나 계산하는 작업은 간단한 클록 시간을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-121">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="73240-122">표준 시간대 차이를 고려하지 않으면 결과가 표준 시간대 조정 규칙의 응용 프로그램을 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-122">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span> 

* <span data-ttu-id="73240-123">두 개의 지정되지 않은 시간 사이의 차이를 비교하거나 계산하는 작업에는 두 개의 다른 시간대의 시간 사이의 차이를 반영하는 알 수 없는 간격이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-123">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="73240-124">다양한 시나리오에서 표준 시간대 차이가 날짜 및 시간 계산에 영향을 주지 않거나 날짜 및 시간 데이터의 컨텍스트가 비교 또는 산술 연산 작업의 의미를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-124">There are many scenarios in which time zone differences do not affect date and time calculations or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span> <span data-ttu-id="73240-125">이 중 일부에 대한 설명은 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](choosing-between-datetime.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73240-125">For a discussion of some of these, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="73240-126">DateTimeOffset 값을 사용한 비교 및 산술 연산</span><span class="sxs-lookup"><span data-stu-id="73240-126">Comparisons and Arithmetic Operations with DateTimeOffset Values</span></span>

<span data-ttu-id="73240-127">[System.DateTimeOffset](xref:System.DateTimeOffset) 값은 UTC에 상대적인 해당 날짜 및 시간을 명확하게 정의하는 오프셋뿐만 아니라 날짜 및 시간을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-127">A [System.DateTimeOffset](xref:System.DateTimeOffset) value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="73240-128">이렇게 하면 [System.DateTime](xref:System.DateTime) 값의 경우와 다르게 같음을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-128">This makes it possible to define equality somewhat differently than for [System.DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="73240-129">동일한 날짜 및 시간 값을 갖는 경우 [DateTime](xref:System.DateTime) 값이 같은 반면 두 값이 시간에서 동일한 지점을 의미하는 경우 [DateTimeOffset](xref:System.DateTimeOffset) 값이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-129">Whereas [DateTime](xref:System.DateTime) values are equal if they have the same date and time value, [DateTimeOffset](xref:System.DateTimeOffset) values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="73240-130">이렇게 하면 두 날짜 및 시간 사이의 간격을 결정하는 비교 및 대부분의 산술 연산에서 사용되는 경우 [DateTimeOffset](xref:System.DateTimeOffset) 값은 더 정확해지고 해석의 필요가 적어집니다.</span><span class="sxs-lookup"><span data-stu-id="73240-130">This makes a [DateTimeOffset](xref:System.DateTimeOffset) value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="73240-131">로컬과 UTC DateTime 값을 비교하는 이전 예제와 같은 [DateTimeOffset](xref:System.DateTimeOffset)에 대한 다음 예제에서는 해당 동작의 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73240-131">The following example, which is the [DateTimeOffset](xref:System.DateTimeOffset) equivalent to the previous example that compared local and UTC DateTime values, illustrates this difference in behavior.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

<span data-ttu-id="73240-132">이 예제에서 [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) 메서드는 현재 현지 시간과 현재 UTC 시간이 동일함을 나타내며 [DateTimeOffset](xref:System.DateTimeOffset) 값의 빼기는 두 시간 사이의 차이가 [TimeSpan.Zero](xref:System.TimeSpan.Zero)임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73240-132">In this example, the [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) method indicates that the current local time and the current UTC time are equal, and subtraction of [DateTimeOffset](xref:System.DateTimeOffset) values indicates that the difference between the two times is [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> 

<span data-ttu-id="73240-133">날짜 및 시간 산술 연산에서 [DateTimeOffset](xref:System.DateTimeOffset) 값 을 사용하는 주요 제한 사항은 [DateTimeOffset](xref:System.DateTimeOffset) 값에 표준 시간대 인식이 포함됨에도 불구하고 완전한 표준 시간대 인식이 아니라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="73240-133">The chief limitation of using [DateTimeOffset](xref:System.DateTimeOffset) values in date and time arithmetic is that although [DateTimeOffset](xref:System.DateTimeOffset) values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="73240-134">[DateTimeOffset](xref:System.DateTimeOffset) 값의 오프셋이 UTC의 표준 시간대 오프셋을 반영하지만 [DateTimeOffset](xref:System.DateTimeOffset) 변수에 값이 먼저 할당된 경우 이후의 표준 시간과 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-134">Although the [DateTimeOffset](xref:System.DateTimeOffset) value's offset reflects a time zone's offset from UTC when a [DateTimeOffset](xref:System.DateTimeOffset) variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="73240-135">더 이상 식별 가능한 시간과 직접 연결되어 있기 때문에 날짜 및 시간 간격의 더하기 및 빼기는 표준 시간대의 조정 규칙을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-135">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span> 

<span data-ttu-id="73240-136">예를 들어 미국 중부 표준시에서는 2008년 3월 9일 오전 2시에 표준 시간대가</span><span class="sxs-lookup"><span data-stu-id="73240-136">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="73240-137">일광 절약 시간제로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-137">on March 9, 2008.</span></span> <span data-ttu-id="73240-138">즉, 중부 표준시 2008년 3월 9일 오전 1시 30분에</span><span class="sxs-lookup"><span data-stu-id="73240-138">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="73240-139">2시간 30분의 간격을 더하면 날짜와 시간은</span><span class="sxs-lookup"><span data-stu-id="73240-139">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="73240-140">2008년 3월 9일 오전 5시가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-140">on March 9, 2008.</span></span> <span data-ttu-id="73240-141">그러나 다음 예제와 같이 이 더하기 연산의 결과는</span><span class="sxs-lookup"><span data-stu-id="73240-141">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="73240-142">2008년 3월 9일 오전 4시가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73240-142">on March 9, 2008.</span></span> <span data-ttu-id="73240-143">관심 있는 표준 시간대의 시간이 아니지만(즉, 예상된 표준 시간대 오프셋이 아님) 이 작업의 결과는 올바른 특정 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73240-143">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="73240-144">표준 시간대의 시간을 사용한 산술 연산</span><span class="sxs-lookup"><span data-stu-id="73240-144">Arithmetic Operations with Times in Time Zones</span></span>

<span data-ttu-id="73240-145">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스는 날짜 및 시간 산술 연산을 수행할 때 자동으로 조정 규칙을 적용하는 메서드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73240-145">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="73240-146">그러나 이렇게 하려면 표준 시간대의 시간을 UTC로 변환하고 산술 연산을 수행하며 UTC에서 표준 시간대의 시간으로 다시 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-146">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="73240-147">자세한 내용은 [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](use-time-zones-in-arithmetic.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73240-147">For details, see [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="73240-148">예를 들어 다음 코드는 2008년 3월 9일 오전 2시에 2시간 30분을 더한</span><span class="sxs-lookup"><span data-stu-id="73240-148">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="73240-149">이전 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-149">on March 9, 2008.</span></span> <span data-ttu-id="73240-150">그러나 날짜 및 시간 산술 연산을 수행하기 전에 중부 표준시를 UTC로 변환한 다음 UTC의 결과를 중부 표준시로 다시 변환하기 때문에 결과 시간은 일광 절약 시간제로 전환된 중앙 표준 시간대를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73240-150">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a><span data-ttu-id="73240-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73240-151">See Also</span></span>

[<span data-ttu-id="73240-152">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="73240-152">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="73240-153">방법: 날짜 및 시간 산술 연산의 표준 시간대 사용</span><span class="sxs-lookup"><span data-stu-id="73240-153">How to: use time zones in date and time arithmetic</span></span>](use-time-zones-in-arithmetic.md)



