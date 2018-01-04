---
title: "로컬 시스템에 정의된 표준 시간대 찾기"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e61f05741c1edd86d9baad4f6ebc9f4e91318250
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="a0615-102">로컬 시스템에 정의된 표준 시간대 찾기</span><span class="sxs-lookup"><span data-stu-id="a0615-102">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="a0615-103"><xref:System.TimeZoneInfo> 클래스는 public 생성자를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-103">The <xref:System.TimeZoneInfo> class does not expose a public constructor.</span></span> <span data-ttu-id="a0615-104">따라서 `new` 키워드는 새 <xref:System.TimeZoneInfo> 개체를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-104">As a result, the `new` keyword cannot be used to create a new <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="a0615-105">대신, <xref:System.TimeZoneInfo> 개체는 레지스트리에서 미리 정의된 표준 시간대에 대한 정보를 검색하거나 사용자 지정 표준 시간대를 만드는 방식으로 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-105">Instead, <xref:System.TimeZoneInfo> objects are instantiated either by retrieving information on predefined time zones from the registry or by creating a custom time zone.</span></span> <span data-ttu-id="a0615-106">이 항목에서는 레지스트리에 저장된 데이터에서 표준 시간대를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-106">This topic discusses instantiating a time zone from data stored in the registry.</span></span> <span data-ttu-id="a0615-107">또한 <xref:System.TimeZoneInfo> 클래스의 `static`(Visual Basic의 `shared`) 속성은 협정 세계시(UTC) 및 로컬 시간대에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-107">In addition, `static` (`shared` in Visual Basic) properties of the <xref:System.TimeZoneInfo> class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

> [!NOTE]
> <span data-ttu-id="a0615-108">레지스트리에 정의되지 않은 표준 시간대의 경우 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드의 오버로드를 호출하여 사용자 지정 시간대를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-108">For time zones that are not defined in the registry, you can create custom time zones by calling the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="a0615-109">에 대해서는 설명 사용자 지정 표준 시간대 만들기는 [하는 방법: 조정 규칙 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-109">Creating a custom time zone is discussed in the [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) topics.</span></span> <span data-ttu-id="a0615-110">또한 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드를 사용하여 serialize된 문자열에서 복원하는 방식으로 <xref:System.TimeZoneInfo> 개체를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-110">In addition, you can instantiate a <xref:System.TimeZoneInfo> object by restoring it from a serialized string with the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span> <span data-ttu-id="a0615-111">직렬화 및 역직렬화는 <xref:System.TimeZoneInfo> 개체에 대해서는 설명의 [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [하는 방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-111">Serializing and deserializing a <xref:System.TimeZoneInfo> object is discussed in the [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore Time Zones from an Embedded Resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) topics.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="a0615-112">개별 표준 시간대 액세스</span><span class="sxs-lookup"><span data-stu-id="a0615-112">Accessing individual time zones</span></span>

<span data-ttu-id="a0615-113"><xref:System.TimeZoneInfo> 클래스는 UTC 시간과 로컬 시간대를 나타내는 미리 정의 된 표준 시간대 개체 두 개를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-113">The <xref:System.TimeZoneInfo> class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="a0615-114">두 개체는 각각 <xref:System.TimeZoneInfo.Utc%2A> 및 <xref:System.TimeZoneInfo.Local%2A> 속성에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-114">They are available from the <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A> properties, respectively.</span></span> <span data-ttu-id="a0615-115">UTC 또는 현지 표준 시간대를 액세스 하는 지침은 참조 하십시오. [하는 방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스](../../../docs/standard/datetime/access-utc-and-local.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-115">For instructions on accessing the UTC or local time zones, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md).</span></span>

<span data-ttu-id="a0615-116">또한 레지스트리에 정의된 표준 시간대를 나타내는 <xref:System.TimeZoneInfo> 개체를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-116">You can also instantiate a <xref:System.TimeZoneInfo> object that represents any time zone defined in the registry.</span></span> <span data-ttu-id="a0615-117">특정 표준 시간대 개체 인스턴스화, 참조 [하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-117">For instructions on instantiating a specific time zone object, see [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="a0615-118">표준 시간대 식별자</span><span class="sxs-lookup"><span data-stu-id="a0615-118">Time zone identifiers</span></span>

<span data-ttu-id="a0615-119">표준 시간대 식별자는 표준 시간대를 고유하게 식별하는 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-119">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="a0615-120">대부분 키는 비교적 짧지만 표준 시간대 식별자는 비교적 깁니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-120">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="a0615-121">대부분 경우에 해당 값은 표준 시간대의 표준 시간 이름을 제공하는 데 사용되는 <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-121">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType> property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="a0615-122">그러나 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-122">However, there are exceptions.</span></span> <span data-ttu-id="a0615-123">올바른 식별자를 제공하는지 확인하는 가장 좋은 방법은 시스템에서 사용 가능한 표준 시간대를 열거하고 관련 식별자를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0615-123">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0615-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0615-124">See also</span></span>

<span data-ttu-id="a0615-125">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[하는 방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스](../../../docs/standard/datetime/access-utc-and-local.md)
[하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md) 
 [표준 시간대 간에 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)</span><span class="sxs-lookup"><span data-stu-id="a0615-125">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)
[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md)</span></span>
