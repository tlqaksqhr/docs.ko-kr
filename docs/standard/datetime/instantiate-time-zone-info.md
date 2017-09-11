---
title: "방법: TimeZoneInfo 개체 인스턴스화"
description: "방법: TimeZoneInfo 개체 인스턴스화"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f2584d446c92d2df2f6d74533ef07fe96888d36a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="d6ec8-104">방법: TimeZoneInfo 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="d6ec8-104">How to: instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="d6ec8-105">[TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 인스턴스화하는 가장 일반적인 방법은 운영 체제에서 해당 정보를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-105">The most common way to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object is to retrieve information about it from the operating system.</span></span> <span data-ttu-id="d6ec8-106">이 항목에서는 로컬 시스템에서 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-106">This topic discusses how to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object from the local system.</span></span>

## <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="d6ec8-107">TimeZoneInfo 개체를 인스턴스화하려면</span><span class="sxs-lookup"><span data-stu-id="d6ec8-107">To instantiate a TimeZoneInfo Object</span></span>

1. <span data-ttu-id="d6ec8-108">[TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-108">Declare a [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span>

2. <span data-ttu-id="d6ec8-109">`static`(Visual Basic의 `Shared`) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-109">Call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method.</span></span>

3. <span data-ttu-id="d6ec8-110">메서드에서 throw한 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-110">Handle any exceptions thrown by the method.</span></span>

## <a name="example"></a><span data-ttu-id="d6ec8-111">예제</span><span class="sxs-lookup"><span data-stu-id="d6ec8-111">Example</span></span>

<span data-ttu-id="d6ec8-112">다음 코드는 동부 표준시 표준 시간대를 나타내고 현지 시간에 해당하는 동부 표준시를 표시하는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-112">The following code retrieves a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

<span data-ttu-id="d6ec8-113">[TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) 메서드의 단일 매개 변수는 개체의 [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) 속성에 해당하는, 검색할 표준 시간대의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-113">The [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) property.</span></span> <span data-ttu-id="d6ec8-114">표준 시간대 식별자는 표준 시간대를 고유하게 식별하는 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-114">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="d6ec8-115">대부분 키는 비교적 짧지만 표준 시간대 식별자는 비교적 깁니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-115">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="d6ec8-116">대부분의 경우 해당 값은 표준 시간대의 표준 시간 이름을 제공하는 데 사용되는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체의 [StandardName](xref:System.TimeZoneInfo.StandardName) 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-116">In most cases, its value corresponds to the [StandardName](xref:System.TimeZoneInfo.StandardName) property of a [TimeZoneInfo](xref:System.TimeZoneInfo) object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="d6ec8-117">그러나 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-117">However, there are exceptions.</span></span> <span data-ttu-id="d6ec8-118">유효한 식별자를 제공하는지 확인하는 가장 좋은 방법은 시스템에서 사용 가능한 표준 시간대를 열거하고 표시된 표준 시간대의 식별자를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-118">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="d6ec8-119">설명은 [방법: 컴퓨터에 있는 표준 시간대 열거](enumerate-time-zones.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-119">For an illustration, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span> <span data-ttu-id="d6ec8-120">[로컬 시스템에 정의된 표준 시간대 찾기](finding-the-time-zones-on-local-system.md) 항목은 선택한 표준 시간대 식별자의 목록도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-120">The [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="d6ec8-121">표준 시간대가 있는 경우 메서드는 해당 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-121">If the time zone is found, the method returns its [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="d6ec8-122">표준 시간대가 있지만 해당 데이터가 손상되었거나 불완전한 경우 메서드에서는 [InvalidTimeZoneException](xref:System.InvalidTimeZoneException)을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ec8-122">If the time zone is found but its data is corrupted or incomplete, the method throws an [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span></span> 

## <a name="see-also"></a><span data-ttu-id="d6ec8-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6ec8-123">See Also</span></span>

[<span data-ttu-id="d6ec8-124">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="d6ec8-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="d6ec8-125">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="d6ec8-125">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
