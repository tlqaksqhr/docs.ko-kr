---
title: "방법: 모호한 시간 확인"
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
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3706747848dbcd29d4ed2e81d5b7447a127a653
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="90982-102">방법: 모호한 시간 확인</span><span class="sxs-lookup"><span data-stu-id="90982-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="90982-103">모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="90982-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="90982-104">표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="90982-105">모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90982-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="90982-106">시간을 UTC로 매핑하는 방법에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="90982-107">예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90982-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="90982-108">모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90982-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="90982-109">이 항목에서는 표준 시간대의 표준 시간을 나타내는 것으로 가정 하 여 모호한 시간을 해결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90982-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="90982-110">모호한 시간을 표준 시간대의 표준 시간으로 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="90982-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="90982-111">호출의 <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 메서드 시간이 모호한 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="90982-112">시간을 빼서 시간 모호한 경우는 <xref:System.TimeSpan> 표준 시간대에서 반환 된 개체 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="90982-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="90982-113">호출 된 `static` (`Shared` Visual Basic.net에서) <xref:System.DateTime.SpecifyKind%2A> UTC 날짜 및 시간 값의 설정 하는 방법은 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="90982-114">예제</span><span class="sxs-lookup"><span data-stu-id="90982-114">Example</span></span>

<span data-ttu-id="90982-115">다음 예제에는 현지 표준 시간대의 표준 시간을 나타내는 것으로 가정 하 모호한 시간에서 UTC로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90982-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="90982-116">이 예제에서는 명명 된 메서드로 구성 `ResolveAmbiguousTime` 결정 하는 여부는 <xref:System.DateTime> 전달 된 값은 모호 합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="90982-117">메서드 반환 값은 모호는 <xref:System.DateTime> 해당 UTC 시간을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="90982-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="90982-118">현지 표준 시간대의 값을 빼서이 변환을 처리 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 현지 시간에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="90982-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="90982-119">모호한 시간 호출 하 여 처리 되는 일반적으로 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 의 배열을 검색 하는 메서드 <xref:System.TimeSpan> 모호한 시간 UTC를 포함 하는 개체 만큼 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="90982-120">그러나 이 예제에서는 모호한 시간이 표준 시간대의 표준 시간으로 항상 매핑되어야 한다고 임의로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="90982-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성 간의 표준 시간대의 표준 시간과 UTC 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="90982-122">이 예제에서는 현지 표준 시간대에 대 한 모든 참조를 통해 이루어집니다는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성; 영역 개체 변수 할당 되지 않으므로 로컬 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="90982-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="90982-123">때문에이 권장된 방법에 대 한 호출에서 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 메서드 현지 표준 시간대에 할당 된 모든 개체가 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="90982-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="90982-124">Compiling the code</span></span>

<span data-ttu-id="90982-125">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="90982-125">This example requires:</span></span>

* <span data-ttu-id="90982-126">System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90982-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="90982-127"><xref:System> 네임 스페이스를 가져올 때는 `using` 문 (C# 코드에 필요).</span><span class="sxs-lookup"><span data-stu-id="90982-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="90982-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90982-128">See also</span></span>

<span data-ttu-id="90982-129">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[하는 방법: 사용자가 모호한 시간 확인](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="90982-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>
