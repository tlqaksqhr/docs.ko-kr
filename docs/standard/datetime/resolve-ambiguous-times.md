---
title: "방법: 모호한 시간 확인"
description: "모호한 시간을 확인하는 방법"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f4ab3b4bf3487e70be7e885e9b8a2281927eb30e
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="75ecc-104">방법: 모호한 시간 확인</span><span class="sxs-lookup"><span data-stu-id="75ecc-104">How to: resolve ambiguous times</span></span>

<span data-ttu-id="75ecc-105">모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="75ecc-106">표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="75ecc-107">모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="75ecc-108">시간을 UTC로 매핑하는 방법에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-108">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="75ecc-109">예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-109">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="75ecc-110">모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-110">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="75ecc-111">이 문서에서는 모호한 시간이 표준 시간대의 표준 시간을 나타낸다고 가정하여 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-111">This article shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="75ecc-112">모호한 시간을 표준 시간대의 표준 시간으로 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="75ecc-112">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="75ecc-113">[System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) 또는 [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) 메서드를 호출하여 시간이 모호한지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-113">Call the [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="75ecc-114">시간이 모호한 경우 표준 시간대의 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 속성에서 반환된 [TimeSpan](xref:System.TimeSpan) 개체에서 시간을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-114">If the time is ambiguous, subtract the time from the [TimeSpan](xref:System.TimeSpan) object returned by the time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span>

3. <span data-ttu-id="75ecc-115">`static`(Visual basic의 `Shared`) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 메서드를 호출하여 UTC 날짜 및 시간 값의 [Kind](xref:System.DateTime.Kind) 속성을 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-115">Call the `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="75ecc-116">예제</span><span class="sxs-lookup"><span data-stu-id="75ecc-116">Example</span></span>

<span data-ttu-id="75ecc-117">다음 예제에서는 모호한 [DateTime](xref:System.DateTime)이 현지 표준 시간대의 표준 시간을 나타낸다고 가정하여 UTC로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-117">The following example illustrates how to convert an ambiguous [DateTime](xref:System.DateTime) to UTC by assuming that it represents the local time zone's standard time.</span></span> 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

<span data-ttu-id="75ecc-118">예제에서는 전달된 [DateTime](xref:System.DateTime) 값이 모호한지 여부를 결정하는 `ResolveAmbiguousTime`라는 메서드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-118">The example consists of a method named `ResolveAmbiguousTime` that determines whether the [DateTime](xref:System.DateTime) value passed to it is ambiguous.</span></span> <span data-ttu-id="75ecc-119">값이 모호한 경우 메서드는 해당 UTC 시간을 나타내는 [DateTime](xref:System.DateTime) 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-119">If the value is ambiguous, the method returns a [DateTime](xref:System.DateTime) value that represents the corresponding UTC time.</span></span> <span data-ttu-id="75ecc-120">메서드는 현지 시간에서 현지 표준 시간대의 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 속성 값을 빼서 이 변환을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-120">The method handles this conversion by subtracting the value of the local time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property from the local time.</span></span> 

<span data-ttu-id="75ecc-121">일반적으로 모호한 시간에서 가능한 UTC 오프셋을 포함하는 [TimeSpan](xref:System.TimeSpan) 개체의 배열을 검색하는 [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) 메서드를 호출하여 모호한 시간을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-121">Ordinarily, an ambiguous time is handled by calling the [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) method to retrieve an array of [TimeSpan](xref:System.TimeSpan) objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="75ecc-122">그러나 이 예제에서는 모호한 시간이 표준 시간대의 표준 시간으로 항상 매핑되어야 한다고 임의로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-122">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="75ecc-123">[BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 속성은 UTC와 표준 시간대의 표준 시간 간에 오프셋을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="75ecc-123">The [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property returns the offset between UTC and a time zone's standard time.</span></span>

## <a name="see-also"></a><span data-ttu-id="75ecc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75ecc-124">See Also</span></span>

[<span data-ttu-id="75ecc-125">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="75ecc-125">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="75ecc-126">방법: 사용자의 모호한 시간 확인 허용</span><span class="sxs-lookup"><span data-stu-id="75ecc-126">How to: let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)


