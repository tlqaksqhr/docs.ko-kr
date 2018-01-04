---
title: "방법: 사용자가 모호한 시간 확인"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d0122ca1469b32692fa9c4ef2bd37cda39622bd7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="3edd5-102">방법: 사용자가 모호한 시간 확인</span><span class="sxs-lookup"><span data-stu-id="3edd5-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="3edd5-103">모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3edd5-104">표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="3edd5-105">모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="3edd5-106">모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="3edd5-107">시간을 UTC로 매핑하는 방법에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="3edd5-108">예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="3edd5-109">이 항목에서는 사용자 모호한 시간을 해결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="3edd5-110">사용자가 모호한 시간을 확인하도록 허용하려면</span><span class="sxs-lookup"><span data-stu-id="3edd5-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="3edd5-111">사용자가 입력한 시간과 날짜를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="3edd5-112">호출의 <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 메서드 시간이 모호한 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="3edd5-113">호출 시간이 모호한 경우는 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 의 배열을 검색 하는 메서드 <xref:System.TimeSpan> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="3edd5-114">배열의 각 요소는 모호한 시간에 매핑할 수 있는 UTC 오프셋을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="3edd5-115">사용자가 원하는 오프셋을 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="3edd5-116">현지 시간에서 사용자가 선택한 오프셋을 빼서 UTC 날짜 및 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="3edd5-117">호출 된 `static` (`Shared` Visual Basic.net에서) <xref:System.DateTime.SpecifyKind%2A> UTC 날짜 및 시간 값의 설정 하는 방법은 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="3edd5-118">예</span><span class="sxs-lookup"><span data-stu-id="3edd5-118">Example</span></span>

<span data-ttu-id="3edd5-119">다음 예제에서는 날짜와 시간을 입력하라는 메시지가 표시되며 모호한 경우 모호한 시간이 매핑하는 UTC 시간을 사용자가 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="3edd5-120">예제 코드의 핵심 배열을 사용 하 여 <xref:System.TimeSpan> 모호한 시간 측정 된 UTC에서의 가능한 오프셋을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="3edd5-121">그러나 이러한 오프셋은 사용자에게 유용하지 않을 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="3edd5-122">오프셋의 의미를 분명히 하기 위해 코드는 오프셋이 현지 표준 시간대의 표준 시간 또는 일광 절약 시간을 나타내는지를 적어둡니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="3edd5-123">코드는 시간이 표준 인지를 확인 하 고 어떤 시간은 일광 오프셋의 값을 비교 하 여는 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="3edd5-124">이 속성은 UTC와 표준 시간대의 표준 시간 사이의 차이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="3edd5-125">이 예제에서는 현지 표준 시간대에 대 한 모든 참조를 통해 이루어집니다는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성; 영역 개체 변수 할당 되지 않으므로 로컬 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="3edd5-126">때문에이 권장된 방법에 대 한 호출에서 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 메서드 현지 표준 시간대에 할당 된 모든 개체가 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="3edd5-127">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3edd5-127">Compiling the code</span></span>

<span data-ttu-id="3edd5-128">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-128">This example requires:</span></span>

* <span data-ttu-id="3edd5-129">System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3edd5-129">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="3edd5-130"><xref:System> 네임 스페이스를 가져올 때는 `using` 문 (C# 코드에 필요).</span><span class="sxs-lookup"><span data-stu-id="3edd5-130">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="3edd5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3edd5-131">See also</span></span>

<span data-ttu-id="3edd5-132">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[하는 방법: 모호한 시간 확인](../../../docs/standard/datetime/resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="3edd5-132">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md)</span></span>
