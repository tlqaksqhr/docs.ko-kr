---
title: "DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택"
description: "DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: aeb1928be32584ee4b6acf7c9a4f4330daedc590
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a><span data-ttu-id="fca9b-104">DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택</span><span class="sxs-lookup"><span data-stu-id="fca9b-104">Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>

<span data-ttu-id="fca9b-105">날짜 및 시간 정보를 사용하는 .NET 응용 프로그램은 매우 다양하며 해당 정보를 여러 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-105">.NET applications that use date and time information are very diverse and can use that information in several ways.</span></span> <span data-ttu-id="fca9b-106">날짜 및 시간 정보를 사용하는 보다 일반적인 방법에는 다음 중 하나 이상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-106">The more common uses of date and time information include one or more of the following:</span></span>

* <span data-ttu-id="fca9b-107">시간 정보가 중요하지 않도록 날짜만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-107">To reflect a date only, so that time information is not important.</span></span>

* <span data-ttu-id="fca9b-108">날짜 정보가 중요하지 않도록 시간만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-108">To reflect a time only, so that date information is not important.</span></span>

* <span data-ttu-id="fca9b-109">특정 시간과 장소에 연결되지 않은 추상 날짜와 시간을 반영합니다(예: 국제 체인의 상점은 대부분 평일 오전 9:00에 열림).</span><span class="sxs-lookup"><span data-stu-id="fca9b-109">To reflect an abstract date and time that is not tied to a specific time and place (for example, most stores in an international chain open on weekdays at 9:00 A.M.).</span></span>

* <span data-ttu-id="fca9b-110">일반적으로 날짜 및 시간 정보가 단순 데이터 형식으로 저장되는 .NET 응용 프로그램 외부의 소스에서 날짜 및 시간 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-110">To retrieve date and time information from sources outside of the .NET application, typically where date and time information is stored in a simple data type.</span></span>

* <span data-ttu-id="fca9b-111">단일 시점을 고유하고 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-111">To uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="fca9b-112">호스트 시스템에서만 날짜와 시간이 명확하면 되는 응용 프로그램도 있고, 시스템 간에 명확해야 하는 응용 프로그램도 있습니다(즉, 한 시스템에서 직렬화된 날짜를 다른 시스템에서 의미 있게 역직렬화하고 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="fca9b-112">Some applications require that a date and time be unambiguous only on the host system; others require that it be unambiguous across systems (that is, a date serialized on one system can be meaningfully deserialized and used on another system anywhere in the world).</span></span> 

* <span data-ttu-id="fca9b-113">여러 개의 관련 시간(예: 요청자의 현지 시간 및 서버의 웹 요청 수신 시간)을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-113">To preserve multiple related times (such as the requestor's local time and the server's time of receipt for a Web request).</span></span>

* <span data-ttu-id="fca9b-114">날짜 및 시간 산술 연산을 수행합니다(단일 시점을 고유하고 명확하게 식별하는 결과를 제공할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="fca9b-114">To perform date and time arithmetic, possibly with a result that uniquely and unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="fca9b-115">.NET에는 [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), 및 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 형식이 포함되어 있습니다. 이러한 형식은 모두 날짜와 시간을 사용하는 응용 프로그램을 빌드하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-115">.NET includes the [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), and [System.TimeZoneInfo](xref:System.TimeZoneInfo) types, all of which can be used to build applications that work with dates and times.</span></span> 

> [!NOTE]
> <span data-ttu-id="fca9b-116">이 항목에서는 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스에 거의 완전히 통합되었기 때문에 오래된 `TimeZone` 형식에 대해서는 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-116">This topic does not discuss the older `TimeZone` type, because its functionality is almost entirely incorporated in the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class.</span></span> <span data-ttu-id="fca9b-117">개발자는 가능한 경우 `TimeZone` 클래스 대신 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스를 항상 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-117">Whenever possible, developers should use the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class instead of the `TimeZone` class.</span></span>


## <a name="the-datetime-structure"></a><span data-ttu-id="fca9b-118">DateTime 구조체</span><span class="sxs-lookup"><span data-stu-id="fca9b-118">The DateTime structure</span></span>

<span data-ttu-id="fca9b-119">[System.DateTime](xref:System.DateTime) 값은 특정 날짜 및 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-119">A [System.DateTime](xref:System.DateTime) value defines a particular date and time.</span></span> <span data-ttu-id="fca9b-120">이 값에는 해당 날짜와 시간이 속한 표준 시간대 관련의 제한된 정보를 제공하는 [Kind](xref:System.DateTime.Kind) 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-120">It includes a [Kind](xref:System.DateTime.Kind) property that provides limited information about the time zone to which that date and time belongs.</span></span> <span data-ttu-id="fca9b-121">[Kind](xref:System.DateTime.Kind) 속성에서 반환하는 [DateTimeKind](xref:System.DateTimeKind) 값은 현지 시간([DateTimeKind.Local](xref:System.DateTimeKind.Local)), UTC(협정 세계시)[DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) 또는 지정되지 않은 시간([DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)) 중 어느 것에 속하는 [DateTime](xref:System.DateTime) 값인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-121">The [DateTimeKind](xref:System.DateTimeKind) value returned by the [Kind](xref:System.DateTime.Kind) property indicates whether the [DateTime](xref:System.DateTime) value represents the local time [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), or an unspecified time [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span>

<span data-ttu-id="fca9b-122">[DateTime](xref:System.DateTime) 구조체는 다음을 수행하는 응용 프로그램에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-122">The [DateTime](xref:System.DateTime) structure is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="fca9b-123">날짜만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-123">Work with dates only.</span></span>

* <span data-ttu-id="fca9b-124">시간만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-124">Work with times only.</span></span>

* <span data-ttu-id="fca9b-125">추상 날짜와 시간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-125">Work with abstract dates and times.</span></span>

* <span data-ttu-id="fca9b-126">표준 시간대 정보가 없는 날짜 및 시간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-126">Work with dates and times for which time zone information is missing.</span></span> 

* <span data-ttu-id="fca9b-127">UTC 날짜 및 시간만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-127">Work with UTC dates and times only.</span></span> 

* <span data-ttu-id="fca9b-128">SQL 데이터베이스와 같이 .NET Framework 외부의 소스에서 날짜 및 시간 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-128">Retrieve date and time information from sources outside the .NET Framework, such as SQL databases.</span></span> <span data-ttu-id="fca9b-129">일반적으로 이러한 소스에는 [DateTime](xref:System.DateTime) 구조체와 호환되는 간단한 형식의 날짜 및 시간 정보가 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-129">Typically, these sources store date and time information in a simple format that is compatible with the [DateTime](xref:System.DateTime) structure.</span></span>

* <span data-ttu-id="fca9b-130">날짜 및 시간 산술 연산을 수행하지만 일반적인 결과와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-130">Perform date and time arithmetic, but are concerned with general results.</span></span> <span data-ttu-id="fca9b-131">예를 들어 특정 날짜와 시간에&6;개월을 더하는 더하기 연산에서 일광 절약 시간제에 맞게 결과를 조정하는지 여부는 대체로 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-131">For example, in an addition operation that adds six months to a particular date and time, it is often not important whether the result is adjusted for daylight saving time.</span></span>

<span data-ttu-id="fca9b-132">특정 [DateTime](xref:System.DateTime) 값이 UTC를 나타내지 않는 경우 해당 날짜 및 시간 값은 대체로 모호하거나 이식성이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-132">Unless a particular [DateTime](xref:System.DateTime) value represents UTC, that date and time value is often ambiguous or limited in its portability.</span></span> <span data-ttu-id="fca9b-133">예를 들어 현지 시간을 나타내는 [DateTime](xref:System.DateTime) 값은 해당 현지 표준 시간대에 이식할 수 있습니다. 즉 다른 시스템에서 동일한 표준 시간대의 값을 역직렬화하는 경우에도 해당 값에서 계속 단일 시점을 명확히 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-133">For example, if a [DateTime](xref:System.DateTime) value represents the local time, it is portable within that local time zone (that is, if the value is deserialized on another system in the same time zone, that value still unambiguously identifies a single point in time).</span></span> <span data-ttu-id="fca9b-134">현지 표준 시간대 외부에서는 해당 [DateTime](xref:System.DateTime) 값이 여러 가지로 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-134">Outside the local time zone, that [DateTime](xref:System.DateTime) value can have multiple interpretations.</span></span> <span data-ttu-id="fca9b-135">값의 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)이면 이식하기가 더 어려워집니다. 이제는 동일한 표준 시간대뿐만 아니라 처음 직렬화된 시스템에서도 모호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-135">If the value's [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), it is even less portable: it is now ambiguous within the same time zone and possibly even on the same system on which it was first serialized.</span></span> <span data-ttu-id="fca9b-136">[DateTime](xref:System.DateTime) 값이 UTC를 나타내는 경우에만 값이 사용되는 시스템이나 표준 시간대에 관계없이 시간의 단일 시점을 명확히 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-136">Only if a [DateTime](xref:System.DateTime) value represents UTC does that value unambiguously identify a single point in time regardless of the system or time zone in which the value is used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fca9b-137">[DateTime](xref:System.DateTime) 데이터를 저장하거나 공유하는 경우 UTC를 사용해야 하며 [DateTime](xref:System.DateTime) 값의 [Kind](xref:System.DateTime.Kind) 속성을 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-137">When saving or sharing [DateTime](xref:System.DateTime) data, UTC should be used and the [DateTime](xref:System.DateTime) value's [Kind](xref:System.DateTime.Kind) property should be set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="the-datetimeoffset-structure"></a><span data-ttu-id="fca9b-138">DateTimeOffset 구조체</span><span class="sxs-lookup"><span data-stu-id="fca9b-138">The DateTimeOffset structure</span></span>

<span data-ttu-id="fca9b-139">[System.DateTimeOffset](xref:System.DateTimeOffset) 구조체는 날짜 및 시간 값, 그리고 해당 값이 UTC와 다른 정도를 나타내는 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-139">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure represents a date and time value, together with an offset that indicates how much that value differs from UTC.</span></span> <span data-ttu-id="fca9b-140">따라서 값이 항상 단일 시점을 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-140">Thus, the value always unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="fca9b-141">[DateTimeOffset](xref:System.DateTimeOffset) 형식에는 [DateTime](xref:System.DateTime) 형식의 모든 기능과 표준 시간대 인식 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-141">The [DateTimeOffset](xref:System.DateTimeOffset) type includes all of the functionality of the [DateTime](xref:System.DateTime) type along with time zone awareness.</span></span> <span data-ttu-id="fca9b-142">이렇게 하면 다음을 수행하는 응용 프로그램에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-142">This makes it is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="fca9b-143">단일 시점을 고유하고 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-143">Uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="fca9b-144">[DateTimeOffset](xref:System.DateTimeOffset) 형식을 사용하면 "now"의 의미를 명확히 정의하고, 트랜잭션 시간을 기록하며, 시스템 또는 응용 프로그램 이벤트의 시간을 기록하고, 파일을 만든 시간과 수정 시간을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-144">The [DateTimeOffset](xref:System.DateTimeOffset) type can be used to unambiguously define the meaning of "now", to log transaction times, to log the times of system or application events, and to record file creation and modification times.</span></span> 

* <span data-ttu-id="fca9b-145">일반적인 날짜 및 시간 산술 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-145">Perform general date and time arithmetic.</span></span>

* <span data-ttu-id="fca9b-146">시간이 두 개의 개별 값으로 저장되거나 한 구조체의 두 멤버로 저장된 경우 관련된 여러 시간을 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-146">Preserve multiple related times, as long as those times are stored as two separate values or as two members of a structure.</span></span>

> [!NOTE]
> <span data-ttu-id="fca9b-147">[DateTimeOffset](xref:System.DateTimeOffset) 값은 [DateTime](xref:System.DateTime) 값보다 훨씬 더 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-147">These uses for [DateTimeOffset](xref:System.DateTimeOffset) values are much more common than those for [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="fca9b-148">따라서 [DateTimeOffset](xref:System.DateTimeOffset)을 응용 프로그램 개발의 기본 날짜 및 시간 형식으로 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-148">As a result, [DateTimeOffset](xref:System.DateTimeOffset) should be considered the default date and time type for application development.</span></span>

<span data-ttu-id="fca9b-149">[DateTimeOffset](xref:System.DateTimeOffset) 값은 특정 표준 시간대에만 한정되지 않고 다양한 표준 시간대에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-149">A [DateTimeOffset](xref:System.DateTimeOffset) value is not tied to a particular time zone, but can originate from any of a variety of time zones.</span></span> <span data-ttu-id="fca9b-150">이를 설명하기 위해 다음 예제에서는 다양한 [DateTimeOffset](xref:System.DateTimeOffset) 값(현지 태평양 표준시 포함)이 속할 수 있는 표준 시간대를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-150">To illustrate this, the following example lists the time zones to which a number of [DateTimeOffset](xref:System.DateTimeOffset) values (including a local Pacific Standard Time) can belong.</span></span>

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

<span data-ttu-id="fca9b-151">출력은 이 예제의 각 날짜 및 시간 값이 세 개 이상의 표준 시간대에 속할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-151">The output shows that each date and time value in this example can belong to at least three different time zones.</span></span> <span data-ttu-id="fca9b-152">2007년 6월 10일의 [DateTimeOffset](xref:System.DateTimeOffset) 값에서는 날짜 및 시간 값이 일광 절약 시간제를 나타내는 경우 UTC 오프셋이 원래 표준 시간대의 기본 UTC 오프셋이나 표시 이름에 있는 UTC 오프셋과 일치하지 않을 수도 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-152">The [DateTimeOffset](xref:System.DateTimeOffset) value of 6/10/2007 shows that if a date and time value represents a daylight saving time, its offset from UTC does not even necessarily correspond to the originating time zone's base UTC offset or to the offset from UTC found in its display name.</span></span> <span data-ttu-id="fca9b-153">즉 [DateTimeOffset](xref:System.DateTimeOffset) 값 하나만 해당 표준 시간대와 긴밀히 연결되지는 않기 때문에 표준 시간대의 일광 절약 시간제 전환을 반영할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-153">This means that, because a single [DateTimeOffset](xref:System.DateTimeOffset)  value is not tightly coupled with its time zone, it cannot reflect a time zone's transition to and from daylight saving time.</span></span> <span data-ttu-id="fca9b-154">이는 날짜 및 시간 산술 연산을 사용하여 [DateTimeOffset](xref:System.DateTimeOffset) 값을 조작하는 경우에만 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-154">This can be particularly problematic when date and time arithmetic is used to manipulate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="fca9b-155">표준 시간대의 조정 규칙을 고려하는 방식으로 날짜 및 시간 산술 연산을 수행하는 방법에 대한 자세한 내용은 [날짜 및 시간으로 산술 연산 수행](performing-arithmetic-operations.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fca9b-155">For a discussion of how to perform date and time arithmetic in a way that takes account of a time zone's adjustment rules, see [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md).</span></span>

## <a name="the-timespan-structure"></a><span data-ttu-id="fca9b-156">TimeSpan 구조체</span><span class="sxs-lookup"><span data-stu-id="fca9b-156">The TimeSpan structure</span></span>

<span data-ttu-id="fca9b-157">[System.TimeSpan](xref:System.TimeSpan) 구조체는 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-157">The [System.TimeSpan](xref:System.TimeSpan) structure represents a time interval.</span></span> <span data-ttu-id="fca9b-158">일반적으로 다음 두 가지 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-158">Its two typical uses are:</span></span> 

* <span data-ttu-id="fca9b-159">두 개의 날짜 및 시간 값의 시간 간격을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-159">Reflecting the time interval between two date and time values.</span></span> <span data-ttu-id="fca9b-160">예를 들어 다른 값에서 [DateTime](xref:System.DateTime) 값 하나를 빼면 [TimeSpan](xref:System.TimeSpan) 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-160">For example, subtracting one [DateTime](xref:System.DateTime) value from another returns a [TimeSpan](xref:System.TimeSpan) value.</span></span> 

* <span data-ttu-id="fca9b-161">경과 시간을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-161">Measuring elapsed time.</span></span> <span data-ttu-id="fca9b-162">예를 들어 [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) 속성은 경과 시간 측정을 시작하는 [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) 메서드 중 하나를 호출한 후에 경과된 시간 간격을 반영하는 [TimeSpan](xref:System.TimeSpan) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-162">For example, the [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) property returns a [TimeSpan](xref:System.TimeSpan) value that reflects the time interval that has elapsed since the call to one of the [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) methods that begins to measure elapsed time.</span></span>

<span data-ttu-id="fca9b-163">값이 하루 중 특정 시간을 참조하지 않고 시간을 반영하는 경우 [DateTime](xref:System.DateTime) 값을 대신하여 [TimeSpan](xref:System.TimeSpan) 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-163">A [TimeSpan](xref:System.TimeSpan) value can also be used as a replacement for a [DateTime](xref:System.DateTime) value when that value reflects a time without reference to a particular time of day.</span></span> <span data-ttu-id="fca9b-164">이렇게 사용하면 날짜를 참조하지 않고 시간을 나타내는 [TimeSpan](xref:System.TimeSpan) 값을 반환하는 [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) 및 [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) 속성과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-164">This usage is similar to the [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) and [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) properties, which return a [TimeSpan](xref:System.TimeSpan) value that represents the time without reference to a date.</span></span> <span data-ttu-id="fca9b-165">예를 들어 [TimeSpan](xref:System.TimeSpan) 구조체를 사용하여 매일 상점을 여는 시간 또는 닫는 시간을 반영하거나 정기 이벤트가 발생하는 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-165">For example, the [TimeSpan](xref:System.TimeSpan) structure can be used to reflect a store's daily opening or closing time, or it can be used to represent the time at which any regular event occurs.</span></span>

<span data-ttu-id="fca9b-166">다음 예제에서는 상점을 여는 시간과 닫는 시간에 사용되는 [TimeSpan](xref:System.TimeSpan) 개체와 상점의 표준 시간대를 나타내는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체가 포함된 `StoreInfo` 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-166">The following example defines a `StoreInfo` structure that includes [TimeSpan](xref:System.TimeSpan) objects for store opening and closing times, as well as a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the store's time zone.</span></span> <span data-ttu-id="fca9b-167">구조체에는 현지 표준 시간대에 있는 것으로 가정되는 사용자가 지정한 시간에 상점이 열려 있는지 여부를 나타내는 `IsOpenNow` 및 `IsOpenAt`의 두 메서드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-167">The structure also includes two methods, `IsOpenNow` and `IsOpenAt`, that indicates whether the store is open at a time specified by the user, who is assumed to be in the local time zone.</span></span>  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

<span data-ttu-id="fca9b-168">`StoreInfo` 구조체는 클라이언트 코드에서 다음과 같이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-168">The `StoreInfo` structure can then be used by client code like the following.</span></span> 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a><span data-ttu-id="fca9b-169">TimeZoneInfo 클래스</span><span class="sxs-lookup"><span data-stu-id="fca9b-169">The TimeZoneInfo class</span></span>

<span data-ttu-id="fca9b-170">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스는 지구상의 특정 표준 시간대를 나타내며, 한 표준 시간대의 날짜 및 시간을 다른 표준 시간대의 해당 항목으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-170">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class represents any of the earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone.</span></span> <span data-ttu-id="fca9b-171">[TimeZoneInfo](xref:System.TimeZoneInfo) 클래스를 사용하면 모든 날짜 및 시간 값에서 명확하게 단일 시점을 식별하도록 날짜 및 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-171">The [TimeZoneInfo](xref:System.TimeZoneInfo) class makes it possible to work with dates and times so that any date and time value unambiguously identifies a single point in time.</span></span>

<span data-ttu-id="fca9b-172">어떤 경우에는 [TimeZoneInfo](xref:System.TimeZoneInfo) 클래스를 완전히 활용하기 위해 추가적으로 개발할 필요도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-172">In some cases, taking full advantage of the [TimeZoneInfo](xref:System.TimeZoneInfo) class may require further development work.</span></span> <span data-ttu-id="fca9b-173">날짜 및 시간 값은 속해 있는 표준 시간대와 긴밀히 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-173">Date and time values are not tightly coupled with the time zones to which they belong.</span></span> <span data-ttu-id="fca9b-174">따라서 응용 프로그램이 날짜 및 시간을 관련 표준 시간대에 연결하는 메커니즘을 제공하지 않을 경우 특정 날짜 및 시간 값과 표준 시간대의 연결이 쉽게 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-174">As a result, unless your application provides some mechanism for linking a date and time with its associated time zone, it is easy for a particular date and time value to become disassociated from its time zone.</span></span> <span data-ttu-id="fca9b-175">이 정보를 연결하는 한 가지 방법으로 날짜 및 시간 값, 그리고 연결되는 표준 시간대 개체를 둘 다 포함하는 클래스나 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-175">One method of linking this information is to define a class or structure that contains both the date and time value and its associated time zone object.</span></span>

<span data-ttu-id="fca9b-176">날짜 및 시간 개체를 인스턴스화할 때 날짜 및 시간 값이 속하는 표준 시간대가 알려진 경우에만 .NET의 표준 시간대 지원을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-176">Taking advantage of time zone support in .NET is possible only if the time zone to which a date and time value belongs is known when that date and time object is instantiated.</span></span> <span data-ttu-id="fca9b-177">웹 또는 네트워크 응용 프로그램에서는 특히 알 수 없는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9b-177">This is often not the case, particularly in Web or network applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="fca9b-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fca9b-178">See Also</span></span>

[<span data-ttu-id="fca9b-179">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="fca9b-179">Dates, times, and time zones</span></span>](index.md)
