---
title: "방법: TimeZoneInfo 개체 인스턴스화"
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
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: defc8c9981b8476660c9c99d20bc50142ee9dfad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="9a967-102">방법: TimeZoneInfo 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="9a967-102">How to: Instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="9a967-103"><xref:System.TimeZoneInfo> 개체를 인스턴스화하는 가장 일반적인 방법은 레지스트리에서 해당 정보를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-103">The most common way to instantiate a <xref:System.TimeZoneInfo> object is to retrieve information about it from the registry.</span></span> <span data-ttu-id="9a967-104">이 항목에서는 로컬 시스템 레지스트리에서 <xref:System.TimeZoneInfo> 개체를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-104">This topic discusses how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

### <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="9a967-105">TimeZoneInfo 개체를 인스턴스화하려면</span><span class="sxs-lookup"><span data-stu-id="9a967-105">To instantiate a TimeZoneInfo object</span></span>

1. <span data-ttu-id="9a967-106"><xref:System.TimeZoneInfo> 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-106">Declare a <xref:System.TimeZoneInfo> object.</span></span>

2. <span data-ttu-id="9a967-107">호출 된 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9a967-107">Call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method.</span></span>

3. <span data-ttu-id="9a967-108">메서드에서 발생한 예외, 특히 레지스트리에서 표준 시간대가 정의되지 않은 경우 발생하는 <xref:System.TimeZoneNotFoundException> 을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-108">Handle any exceptions thrown by the method, particularly the <xref:System.TimeZoneNotFoundException> that is thrown if the time zone is not defined in the registry.</span></span>

## <a name="example"></a><span data-ttu-id="9a967-109">예제</span><span class="sxs-lookup"><span data-stu-id="9a967-109">Example</span></span>

<span data-ttu-id="9a967-110">다음 코드는 동부 표준시 표준 시간대를 나타내고 현지 시간에 해당하는 동부 표준시를 표시하는 <xref:System.TimeZoneInfo> 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-110">The following code retrieves a <xref:System.TimeZoneInfo> object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<span data-ttu-id="9a967-111"><xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> 메서드의 단일 매개 변수는 표준 시간대를 검색 하려는 개체의에 해당 하는 식별자 <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-111">The <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9a967-112">표준 시간대 식별자는 표준 시간대를 고유하게 식별하는 키 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-112">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="9a967-113">대부분 키는 비교적 짧지만 표준 시간대 식별자는 비교적 깁니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-113">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="9a967-114">대부분의 경우 해당 값은 표준 시간대의 표준 시간 이름을 제공하는 데 사용되는 <xref:System.TimeZoneInfo.StandardName%2A> 개체의 <xref:System.TimeZoneInfo> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-114">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A> property of a <xref:System.TimeZoneInfo> object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="9a967-115">그러나 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-115">However, there are exceptions.</span></span> <span data-ttu-id="9a967-116">유효한 식별자를 제공하는지 확인하는 가장 좋은 방법은 시스템에서 사용 가능한 표준 시간대를 열거하고 표시된 표준 시간대의 식별자를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-116">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="9a967-117">자세한 내용은 [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a967-117">For an illustration, see [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span></span> <span data-ttu-id="9a967-118">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) 항목에는 선택한 표준 시간대 식별자 목록도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-118">The [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="9a967-119">표준 시간대가 있는 경우 메서드는 해당 <xref:System.TimeZoneInfo> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-119">If the time zone is found, the method returns its <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="9a967-120">표준 시간대가 없는 경우 메서드에서 <xref:System.TimeZoneNotFoundException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-120">If the time zone is not found, the method throws a <xref:System.TimeZoneNotFoundException>.</span></span> <span data-ttu-id="9a967-121">표준 시간대가 있지만 해당 데이터가 손상되었거나 불완전한 경우 메서드에서 <xref:System.InvalidTimeZoneException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-121">If the time zone is found but its data is corrupted or incomplete, the method throws an <xref:System.InvalidTimeZoneException>.</span></span>

<span data-ttu-id="9a967-122">응용 프로그램에서 사용하는 표준 시간대가 있어야 하는 경우 먼저 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드를 호출하여 레지스트리에서 표준 시간대 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-122">If your application relies on a time zone that must be present, you should first call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method to retrieve the time zone information from the registry.</span></span> <span data-ttu-id="9a967-123">메서드 호출이 실패하면 예외 처리기가 표준 시간대의 새 인스턴스를 만들거나 직렬화된 <xref:System.TimeZoneInfo> 개체를 역직렬화하여 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-123">If the method call fails, your exception handler should then either create a new instance of the time zone or re-create it by deserializing a serialized <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="9a967-124">참조 [하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) 예에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a967-124">See [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) for an example.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a967-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a967-125">See also</span></span>

<span data-ttu-id="9a967-126">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[로컬 시스템에 정의 된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[하는 방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스](../../../docs/standard/datetime/access-utc-and-local.md)</span><span class="sxs-lookup"><span data-stu-id="9a967-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)</span></span>
