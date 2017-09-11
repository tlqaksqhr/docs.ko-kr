---
title: "방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 대한 액세스"
description: "미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스하는 방법"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: fcc48e40cdad25c6142dbc3a86513b816378fa4b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="8df3a-104">방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 대한 액세스</span><span class="sxs-lookup"><span data-stu-id="8df3a-104">How to: access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="8df3a-105">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스에는 두 가지 속성, `Utc` 및 `Local`이 있는데 미리 정의된 표준 시간대 개체에 대한 액세스 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class provides two properties, `Utc` and `Local`, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="8df3a-106">이 항목에서는 이러한 속성들이 반환하는 `TimeZoneInfo` 개체에 액세스하는 방법에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-106">This topic discusses how to access the `TimeZoneInfo` objects returned by those properties.</span></span>

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="8df3a-107">UTC TimeZoneInfo 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="8df3a-107">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="8df3a-108">**static**(Visual Basic의 경우는 **Shared**) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 속성을 사용하여 UTC(협정 세계시)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-108">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="8df3a-109">속성에서 반환하는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 개체 변수에 할당하는 대신 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 속성을 통해 UTC에 계속 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-109">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property.</span></span>


## <a name="to-access-the-local-time-zone"></a><span data-ttu-id="8df3a-110">현지 표준 시간대 TimeZoneInfo 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="8df3a-110">To access the local time zone</span></span>

1. <span data-ttu-id="8df3a-111">**static**(Visual Basic의 경우 **Shared**) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 속성을 사용하여 로컬 시스템 표준 시간대에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-111">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property to access the local system time zone.</span></span>

2. <span data-ttu-id="8df3a-112">속성에서 반환하는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 개체 변수에 할당하는 대신 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 속성을 통해 표준 시간대에 계속 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-112">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property.</span></span>

## <a name="example"></a><span data-ttu-id="8df3a-113">예제</span><span class="sxs-lookup"><span data-stu-id="8df3a-113">Example</span></span>

<span data-ttu-id="8df3a-114">다음 코드에서는 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 및 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 속성을 사용하여 시간을 미국 및 캐나다 동부 표준시에서 변환하고 해당 표준시 이름을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-114">The following code uses the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) and [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

<span data-ttu-id="8df3a-115">현지 표준 시간대를 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체 변수에 할당하는 대신 항상 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 속성을 통해 현지 표준 시간대에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-115">You should always access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property rather than assigning the local time zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="8df3a-116">마찬가지로 UTC 시간대를 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체 변수에 할당하는 대신 항상 [TimeZoneInfo.LocalTimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 속성을 통해 UTC에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-116">Similarly, you should always access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property rather than assigning the UTC zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="8df3a-117">이렇게 하면 외부 메서드에서 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체 변수를 무효화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8df3a-117">This prevents the [TimeZoneInfo](xref:System.TimeZoneInfo) object variable from being invalidated by an external method.</span></span>


## <a name="see-also"></a><span data-ttu-id="8df3a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8df3a-118">See Also</span></span>

[<span data-ttu-id="8df3a-119">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="8df3a-119">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="8df3a-120">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="8df3a-120">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)

