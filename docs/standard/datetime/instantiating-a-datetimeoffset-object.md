---
title: "DateTimeOffset 개체 인스턴스화"
description: "DateTimeOffset 개체 인스턴스화"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 26be324eb5d58b94a71e89aba213f107cf8dfd1e
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="85259-104">DateTimeOffset 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="85259-104">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="85259-105">[System.DateTimeOffset](xref:System.DateTimeOffset) 구조에서는 다양한 방법으로 새 [DateTimeOffset](xref:System.DateTimeOffset) 값을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-105">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure offers a number of ways to create new [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="85259-106">그 중 대부분은 새로운 [System.DateTime](xref:System.DateTime) 값을 인스턴스화하는 데 사용할 수 있는 메서드에 직접 해당하며 UTC(협정 세계시)의 날짜 및 시간 값의 오프셋을 지정할 수 있도록 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-106">Many of them correspond directly to the methods available for instantiating new [System.DateTime](xref:System.DateTime) values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="85259-107">특히 다음과 같은 방법으로 [DateTimeOffset](xref:System.DateTimeOffset) 값을 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-107">In particular, you can instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value in the following ways:</span></span>

* <span data-ttu-id="85259-108">[DateTimeOffset](xref:System.DateTimeOffset) 생성자 호출</span><span class="sxs-lookup"><span data-stu-id="85259-108">By calling a [DateTimeOffset](xref:System.DateTimeOffset) constructor.</span></span>

* <span data-ttu-id="85259-109">암시적으로 값을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환</span><span class="sxs-lookup"><span data-stu-id="85259-109">By implicitly converting a value to [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

* <span data-ttu-id="85259-110">날짜 및 시간의 문자열 표현 구문 분석</span><span class="sxs-lookup"><span data-stu-id="85259-110">By parsing the string representation of a date and time.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="85259-111">날짜 및 시간 리터럴</span><span class="sxs-lookup"><span data-stu-id="85259-111">Date and Time Literals</span></span>

<span data-ttu-id="85259-112">지원하는 언어의 경우 [DateTime](xref:System.DateTime) 값을 인스턴스화하는 가장 일반적인 방법 중 하나는 날짜와 시간을 하드코딩된 리터럴 값으로 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85259-112">For languages that support it, one of the most common ways to instantiate a [DateTime](xref:System.DateTime) value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="85259-113">예를 들어, 다음 Visual Basic 코드는 값이 2008년 1월 1일 오전 10시인 [DateTime](xref:System.DateTime) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85259-113">For example, the following Visual Basic code creates a [DateTime](xref:System.DateTime) object whose value is January 1, 2008, at 10:00 AM.</span></span>

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

<span data-ttu-id="85259-114">[DateTime](xref:System.DateTime) 리터럴을 지원하는 언어를 사용하는 경우 [DateTimeOffset](xref:System.DateTimeOffset) 값은 날짜 및 시간 리터럴을 사용하여 초기화될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-114">[DateTimeOffset](xref:System.DateTimeOffset) values can also be initialized using date and time literals when using languages that support [DateTime](xref:System.DateTime) literals.</span></span> <span data-ttu-id="85259-115">예를 들어, 다음 Visual Basic 코드는 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85259-115">For example, the following Visual Basic code creates a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

<span data-ttu-id="85259-116">콘솔 출력에서 볼 수 있듯이 이러한 방식으로 만들어진 [DateTimeOffset](xref:System.DateTimeOffset) 값을 현지 표준 시간대의 오프셋으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-116">As the console output shows, the [DateTimeOffset](xref:System.DateTimeOffset) value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="85259-117">즉, 서로 다른 컴퓨터에서 코드를 실행하는 경우 리터럴 문자를 사용하여 할당된 [DateTimeOffset](xref:System.DateTimeOffset) 값은 단일 시점을 식별하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-117">This means that a [DateTimeOffset](xref:System.DateTimeOffset) value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="85259-118">DateTimeOffset 생성자</span><span class="sxs-lookup"><span data-stu-id="85259-118">DateTimeOffset Constructors</span></span>

<span data-ttu-id="85259-119">[System.DateTimeOffset](xref:System.DateTimeOffset) 형식은&5;개의 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-119">The [System.DateTimeOffset](xref:System.DateTimeOffset) type defines five constructors.</span></span> <span data-ttu-id="85259-120">이중&3;개의 생성자는 UTC의 날짜 및 시간 오프셋을 정의하는 [System.TimeSpan](xref:System.TimeSpan) 형식의 추가 매개 변수를 사용하는 [DateTime](xref:System.DateTime) 생성자에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-120">Three of them correspond directly to [DateTime](xref:System.DateTime) constructors, with an additional parameter of type [System.TimeSpan](xref:System.TimeSpan) that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="85259-121">개별 날짜 및 시간 구성 요소 값을 기반으로 [DateTimeOffset](xref:System.DateTimeOffset) 값을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-121">These allow you to define a [DateTimeOffset](xref:System.DateTimeOffset) value based on the value of its individual date and time components.</span></span> <span data-ttu-id="85259-122">예를 들어 다음 코드는 이러한 세 가지 생성자를 사용하여 2008년 7월 1일 오전 12시 05분 +01:00과 동일한 값을 가진 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 인스턴트화합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-122">For example, the following code uses these three constructors to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

<span data-ttu-id="85259-123">[PersianCalendar](xref:System.Globalization.PersianCalendar) 개체를 생성자에 인수 중 하나로 사용하여 인스턴스화된 [DateTimeOffset](xref:System.DateTimeOffset) 개체의 값이 콘솔에 표시되면 날짜가 페르시아력의 아니라 그레고리오력으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-123">Note that, when the value of the [DateTimeOffset](xref:System.DateTimeOffset) object instantiated using a [PersianCalendar](xref:System.Globalization.PersianCalendar) object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> 

<span data-ttu-id="85259-124">다른 두 생성자는 DateTime 값에서 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85259-124">The other two constructors create a [DateTimeOffset](xref:System.DateTimeOffset) object from a DateTime value.</span></span> <span data-ttu-id="85259-125">이 중 첫 번째 개체에는 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환할 단일 매개 변수인 [DateTime](xref:System.DateTime) 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-125">The first of these has a single parameter, the [DateTime](xref:System.DateTime) value to convert to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="85259-126">결과인 [DateTimeOffset](xref:System.DateTimeOffset) 값의 오프셋은 생성자의 단일 [DateTime](xref:System.DateTime) 매개 변수 중 [Kind](xref:System.DateTime.Kind) 속성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="85259-126">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the [Kind](xref:System.DateTime.Kind) property of the constructor's single [DateTime](xref:System.DateTime) parameter.</span></span> <span data-ttu-id="85259-127">해당 값이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)인 경우 오프셋은 [TimeSpan.Zero](xref:System.TimeSpan.Zero)와 동일하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-127">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="85259-128">그렇지 않은 경우 해당 오프셋은 현지 표준 시간대의 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-128">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="85259-129">다음 예제에서는 이 생성자를 사용하여 UTC와 현지 표준 시간대를 나타내는 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-129">The following example illustrates the use of this constructor to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects representing UTC and the local time zone:</span></span>

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> <span data-ttu-id="85259-130">단일 [DateTime](xref:System.DateTime) 매개 변수를 가진 [DateTimeOffset](xref:System.DateTimeOffset) 생성자의 오버로드를 호출하는 작업은 [DateTime](xref:System.DateTime) 값을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 암시적으로 변환하는 작업과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-130">Calling the overload of the [DateTimeOffset](xref:System.DateTimeOffset) constructor that has a single [DateTime](xref:System.DateTime) parameter is equivalent to performing an implicit conversion of a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

<span data-ttu-id="85259-131">[DateTime](xref:System.DateTime) 값에서 [DateTimeOffset](xref:System.DateTimeOffset) 개체를 만드는 두 번째 생성자에는 두 개의 매개 변수가 있습니다. 하나는 변환할 [DateTime](xref:System.DateTime) 값이고 다른 하나는 UTC에서 날짜 및 시간의 오프셋을 나타내는 [TimeSpan](xref:System.TimeSpan) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="85259-131">The second constructor that creates a [DateTimeOffset](xref:System.DateTimeOffset) object from a [DateTime](xref:System.DateTime) value has two parameters: the [DateTime](xref:System.DateTime) value to convert, and a [TimeSpan](xref:System.TimeSpan) value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="85259-132">이 오프셋 값은 생성자의 첫 번째 매개 변수 중 [Kind](xref:System.DateTime.Kind) 속성에 해당해야 합니다. 그렇지 않으면 [System.ArgumentException](xref:System.ArgumentException)이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-132">This offset value must correspond to the [Kind](xref:System.DateTime.Kind) property of the constructor's first parameter or an [System.ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="85259-133">첫 번째 매개 변수의 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)인 경우 두 번째 매개 변수 값은 [TimeSpan.Zero](xref:System.TimeSpan.Zero)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-133">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the value of the second parameter must be [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="85259-134">첫 번째 매개 변수의 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Local](xref:System.DateTimeKind.Local)인 경우 두 번째 매개 변수 값은 로컬 시스템 표준 시간대의 오프셋이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-134">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Local](xref:System.DateTimeKind.Local), the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="85259-135">첫 번째 매개 변수의 [Kind](xref:System.DateTime.Kind) 속성이 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)인 경우 오프셋은 모든 유효한 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-135">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset can be any valid value.</span></span> <span data-ttu-id="85259-136">다음 코드에서는 [DateTime](xref:System.DateTime)을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하는 이 생성자에 대한 호출을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-136">The following code illustrates calls to this constructor to convert [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a><span data-ttu-id="85259-137">암시적 형식 변환</span><span class="sxs-lookup"><span data-stu-id="85259-137">Implicit Type Conversion</span></span>
 
<span data-ttu-id="85259-138">[System.DateTimeOffset](xref:System.DateTimeOffset) 형식은 [System.DateTime](xref:System.DateTime) 값에서 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 암시적 형식 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-138">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports one implicit type conversion: from a [System.DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="85259-139">암시적 형식 변환은 명시적 캐스팅(C#의 경우) 또는 변환(Visual Basic의 경우)을 필요로 하지 않고 정보를 손실하지 않는 형식 간의 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="85259-139">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="85259-140">이를 사용하면 다음과 같은 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85259-140">It makes code like the following possible.</span></span>

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

<span data-ttu-id="85259-141">결과인 [DateTimeOffset](xref:System.DateTimeOffset) 값의 오프셋은 [DateTime.Kind](xref:System.DateTime.Kind) 속성 값에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="85259-141">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the DateTime.Kind](xref:System.DateTime.Kind) property value.</span></span> <span data-ttu-id="85259-142">해당 값이 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)인 경우 오프셋은 [TimeSpan.Zero](xref:System.TimeSpan.Zero)와 동일하게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-142">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="85259-143">해당 값이 [DateTimeKind.Local](xref:System.DateTimeKind.Local) 또는 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)인 경우 오프셋은 현지 표준 시간대의 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85259-143">If its value is either [DateTimeKind.Local](xref:System.DateTimeKind.Local) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="85259-144">날짜 및 시간의 문자열 표현 구문 분석</span><span class="sxs-lookup"><span data-stu-id="85259-144">Parsing the String Representation of a Date and Time</span></span>

<span data-ttu-id="85259-145">[System.DateTimeOffset](xref:System.DateTimeOffset) 형식은 날짜 및 시간 문자열 표현을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환할 수 있게 하는&4;개의 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-145">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports four methods that allow you to convert the string representation of a date and time into a [DateTimeOffset](xref:System.DateTimeOffset) value:</span></span>

* <span data-ttu-id="85259-146">[구문 분석](xref:System.DateTimeOffset.Parse(System.String)), 날짜 및 시간의 문자열 표현을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하려고 시도하고 변환에 실패하는 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="85259-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), 날짜 및 시간의 문자열 표현을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하려고 시도하고 변환이 실패하는 경우 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="85259-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), 지정된 형식인 날짜 및 시간의 문자열 표현을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="85259-149">변환이 실패하면 메서드는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-149">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="85259-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), 지정된 형식인 날짜 및 시간의 문자열 표현을 [DateTimeOffset](xref:System.DateTimeOffset) 값으로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="85259-151">변환에 실패하는 경우 메서드가 `false`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-151">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="85259-152">다음 예제에서는 [DateTimeOffset](xref:System.DateTimeOffset) 값을 인스턴스화하는 이러한&4;개의 문자열 변환 메서드 각각에 대한 호출을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85259-152">The following example illustrates calls to each of these four string conversion methods to instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a><span data-ttu-id="85259-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85259-153">See Also</span></span>

[<span data-ttu-id="85259-154">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="85259-154">Dates, times, and time zones</span></span>](index.md)


