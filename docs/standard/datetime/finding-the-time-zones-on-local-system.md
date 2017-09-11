---
title: "로컬 시스템에 정의된 표준 시간대 찾기"
description: "로컬 시스템에 정의된 표준 시간대 찾기"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e61017e2a0e26295c3be7e8265674b1a5d2ae5a3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="26dbd-104">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="26dbd-104">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="26dbd-105">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 클래스는 public 생성자를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not expose a public constructor.</span></span> <span data-ttu-id="26dbd-106">따라서 `new` 키워드는 새 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-106">As a result, the `new` keyword cannot be used to create a new [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="26dbd-107">대신 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체는 운영 체제에서 미리 정의된 표준 시간대 정보를 검색하여 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-107">Instead, [TimeZoneInfo](xref:System.TimeZoneInfo) objects are instantiated by retrieving information on predefined time zones from the operating system.</span></span> <span data-ttu-id="26dbd-108">이 항목에서는 운영 체제에서 저장한 데이터로부터 표준 시간대를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-108">This topic discusses instantiating a time zone from data stored by the operating system.</span></span> <span data-ttu-id="26dbd-109">또한 [TimeZoneInfo](xref:System.TimeZoneInfo) 클래스의 `static`(Visual Basic의 경우 `Shared`) 속성은 협정 세계시(UTC) 및 현지 표준 시간대에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-109">In addition, `static` (`Shared` in Visual Basic) properties of the [TimeZoneInfo](xref:System.TimeZoneInfo) class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="26dbd-110">개별 표준 시간대 액세스</span><span class="sxs-lookup"><span data-stu-id="26dbd-110">Accessing Individual Time Zones</span></span>

<span data-ttu-id="26dbd-111">[TimeZoneInfo](xref:System.TimeZoneInfo) 클래스는 UTC 시간과 현지 표준 시간대를 나타내는 미리 정의된 표준 시간대 개체 두 개를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-111">The [TimeZoneInfo](xref:System.TimeZoneInfo) class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="26dbd-112">두 개체는 각각 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 및 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 속성에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-112">They are available from the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) and [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) properties, respectively.</span></span> <span data-ttu-id="26dbd-113">UTC 또는 현지 표준 시간대의 액세스에 대한 지침은 [방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 대한 액세스](access-utc-and-local.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26dbd-113">For instructions on accessing the UTC or local time zones, see [How to: access the predefined UTC and local time zone objects](access-utc-and-local.md).</span></span> 

<span data-ttu-id="26dbd-114">또한 운영 체제에서 정의한 표준 시간대를 나타내는 [TimeZoneInfo](xref:System.TimeZoneInfo) 개체를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-114">You can also instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents any time zone defined by the operating system.</span></span> <span data-ttu-id="26dbd-115">특정 표준 시간대 개체의 인스턴스화에 대한 지침은 [방법: TimeZoneInfo 개체 인스턴스화](instantiate-time-zone-info.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26dbd-115">For instructions on instantiating a specific time zone object, see [How to: instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="26dbd-116">표준 시간대 식별자</span><span class="sxs-lookup"><span data-stu-id="26dbd-116">Time Zone Identifiers</span></span>

<span data-ttu-id="26dbd-117">표준 시간대 식별자는 표준 시간대를 고유하게 식별하는 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-117">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="26dbd-118">대부분 키는 비교적 짧지만 표준 시간대 식별자는 비교적 깁니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-118">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="26dbd-119">대부분 경우 해당 값은 표준 시간대의 표준 시간 이름을 제공하는 데 사용되는 [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-119">In most cases, its value corresponds to the [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="26dbd-120">그러나 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-120">However, there are exceptions.</span></span> <span data-ttu-id="26dbd-121">올바른 식별자를 제공하는지 확인하는 가장 좋은 방법은 시스템에서 사용 가능한 표준 시간대를 열거하고 관련 식별자를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26dbd-121">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span> <span data-ttu-id="26dbd-122">표준 시간대 열거에 대한 지침은 [방법: 컴퓨터에 있는 표준 시간대 열거](enumerate-time-zones.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26dbd-122">For instructions on enumerating time zones, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26dbd-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26dbd-123">See Also</span></span>

[<span data-ttu-id="26dbd-124">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="26dbd-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="26dbd-125">방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="26dbd-125">How to: access the predefined UTC and local time zone objects</span></span>](access-utc-and-local.md)

[<span data-ttu-id="26dbd-126">방법: TimeZoneInfo 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="26dbd-126">How to: instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)

[<span data-ttu-id="26dbd-127">방법: 컴퓨터에 있는 표준 시간대 열거</span><span class="sxs-lookup"><span data-stu-id="26dbd-127">How to: enumerate time zones present on a computer</span></span>](enumerate-time-zones.md)

[<span data-ttu-id="26dbd-128">표준 시간대 간에 시간 변환</span><span class="sxs-lookup"><span data-stu-id="26dbd-128">Converting times between time zones</span></span>](converting-between-time-zones.md)
