---
title: "방법: 조정 규칙 하지 않고 표준 시간대 만들기"
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 181d61de62ec9560b46732ad304b4934d4f55fa2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="c1a57-102">방법: 조정 규칙 하지 않고 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="c1a57-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="c1a57-103">응용 프로그램에 필요한 정확한 표준 시간대 정보가 여러 가지 이유로 특정 시스템에 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="c1a57-104">로컬 시스템 레지스트리에서 표준 시간대를 정의 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="c1a57-105">표준 시간대에 대 한 데이터 수정 되거나 레지스트리에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="c1a57-106">표준 시간대 존재 하지만 중요 한 특정 기간에 대 한 표준 시간대 조정에 대 한 정확한 정보를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="c1a57-107">이러한 경우에 호출할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 응용 프로그램에 필요한 표준 시간대를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="c1a57-108">조정 규칙을 표준 시간대 만들를이 메서드의 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="c1a57-109">표준 시간대 일광 절약 시간을 지 원하는 경우에 고정 또는 부동 조정 규칙 중 하나를 사용 하 여 조정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="c1a57-110">(이러한 용어의 정의에서 "시간대 용어" 섹션을 참조 [시간대 개요](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="c1a57-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1a57-111">호출 하 여 만든 사용자 지정 표준 시간대는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="c1a57-112">대신,에서 반환 된 개체 참조를 통해서만 액세스할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="c1a57-113">이 항목에는 조정 규칙 하지 않고 표준 시간대를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="c1a57-114">표준 시간대 일광 절약 시간 조정 규칙을 지 원하는 참조 하십시오 [하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="c1a57-115">조정 규칙 하지 않고 표준 시간대를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c1a57-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="c1a57-116">표준 시간대의 표시 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="c1a57-117">표시 이름은 시간 표준 시간대 오프셋을 utc (협정 세계시) 괄호로 묶인 및 다음에 하나 또는 도시 또는 표준 시간대에 더 이상의 cou의 표준 시간대를 식별 하는 문자열은 대개 표준 형식을 따릅니다. ntries 또는 표준 시간대의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="c1a57-118">표준 시간대의 표준 시간 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="c1a57-119">일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="c1a57-120">다른 표준 시간대의 표준 이름 식별자를 사용 하려는 경우 표준 시간대 식별자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="c1a57-121">인스턴스화하는 <xref:System.TimeSpan> utc에서 표준 시간대 오프셋을 정의 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="c1a57-122">UTC 보다 늦은 시간 표준 시간대 오프셋은 양수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="c1a57-123">시간 표준 시간대의 UTC 보다 이전에 음수 오프셋이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="c1a57-124">호출 된 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> 새 표준 시간대를 인스턴스화하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="c1a57-125">예제</span><span class="sxs-lookup"><span data-stu-id="c1a57-125">Example</span></span>

<span data-ttu-id="c1a57-126">다음 예제에서는 모슨, 조정 규칙 없이 남극 대륙에 대 한 사용자 지정 표준 시간대를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="c1a57-127">에 할당 된 문자열은 <xref:System.TimeZoneInfo.DisplayName%2A> 속성에는 UTC 표준 시간대의 오프셋이 뒤에 표준 시간대에 대 한 간단한 설명과 표준 형식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c1a57-128">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c1a57-128">Compiling the code</span></span>

<span data-ttu-id="c1a57-129">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-129">This example requires:</span></span>

* <span data-ttu-id="c1a57-130">System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-130">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="c1a57-131">다음 네임 스페이스 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a57-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="c1a57-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1a57-132">See also</span></span>

<span data-ttu-id="c1a57-133">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span><span class="sxs-lookup"><span data-stu-id="c1a57-133">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span></span>
