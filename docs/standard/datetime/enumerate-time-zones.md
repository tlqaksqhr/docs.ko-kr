---
title: "방법: 컴퓨터에 있는 표준 시간대를 열거 합니다."
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
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2318a42040388adfe327f9d0075754daa1aa22a6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="7aadc-102">방법: 컴퓨터에 있는 표준 시간대를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="7aadc-103">지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대 관련 정보를 시스템에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="7aadc-104">Windows XP 및 Windows Vista 운영 체제 레지스트리에이 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="7aadc-105">그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="7aadc-106">또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="7aadc-107">따라서 언제나 응용 프로그램에서 특정 표준 시간대가 정의되어 있고 시스템에서 사용할 수 있다고 가정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="7aadc-108">표준 시간대 정보 응용 프로그램을 사용하는 많은 응용 프로그램의 첫 번째 단계는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="7aadc-109">이렇게 하려면 응용 프로그램에서 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="7aadc-110">응용 프로그램이 로컬 시스템에서 정의할 수 없습니다. 특정 표준 시간대의 현재 상태를 사용 하는 경우 응용 프로그램 직렬화 및 표준 시간대에 대 한 정보를 역직렬화 하 여 존재를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="7aadc-111">표준 시간대 다음 추가할 수 있습니다는 목록 컨트롤에는 응용 프로그램 사용자가 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="7aadc-112">자세한 내용은 참조 [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="7aadc-113">로컬 시스템에 있는 표준 시간대를 열거하려면</span><span class="sxs-lookup"><span data-stu-id="7aadc-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="7aadc-114"><xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7aadc-115">메서드가 제네릭 반환 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션 <xref:System.TimeZoneInfo> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="7aadc-116">컬렉션의 항목을 기준으로 정렬 되며 해당 <xref:System.TimeZoneInfo.DisplayName%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="7aadc-117">예:</span><span class="sxs-lookup"><span data-stu-id="7aadc-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="7aadc-118">개별 열거 <xref:System.TimeZoneInfo> 를 사용 하 여 컬렉션의 개체는 `foreach` 루프 (C#) 또는 `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="7aadc-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="7aadc-119">루프 (Visual Basic의 경우) 및 각 개체에 대해 필요한 처리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="7aadc-120">예를 들어 다음 코드 열거는 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션 <xref:System.TimeZoneInfo> 1 단계를에서 반환 된 개체를 콘솔에 각 표준 시간대의 표시 이름을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="7aadc-121">사용자 로컬 시스템에 표준 시간대의 목록을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="7aadc-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="7aadc-122"><xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7aadc-123">메서드가 제네릭 반환 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션 <xref:System.TimeZoneInfo> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="7aadc-124">1 단계에서 반환 된 컬렉션 할당는 `DataSource` 속성 forms 또는 ASP.NET 목록 컨트롤의는 Windows.</span><span class="sxs-lookup"><span data-stu-id="7aadc-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="7aadc-125">검색 된 <xref:System.TimeZoneInfo> 사용자가 선택한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="7aadc-126">예제에서는 Windows 응용 프로그램에 대 한 그림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="7aadc-127">예</span><span class="sxs-lookup"><span data-stu-id="7aadc-127">Example</span></span>

<span data-ttu-id="7aadc-128">이 예제에서는 목록 상자에서 시스템에 정의 된 표준 시간대를 표시 하는 Windows 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="7aadc-129">이 예제에서는 다음의 값을 포함 하는 대화 상자를 표시는 <xref:System.TimeZoneInfo.DisplayName%2A> 사용자가 선택한 표준 시간대 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="7aadc-130">대부분의 목록 컨트롤 (같은 <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> 또는 <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> 컨트롤) 사용 개체 변수의 컬렉션을 할당할 수 있습니다 해당 `DataSource` 속성을 구현 하는 컬렉션으로는 <xref:System.Collections.IEnumerable> 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="7aadc-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="7aadc-131">(제네릭 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 클래스는이 수행 합니다.) 컨트롤 컬렉션의 개별 개체를 표시 하려면 해당 개체를 호출 `ToString` 메서드는 개체를 나타내는 데 사용 되는 문자열을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="7aadc-132">경우 <xref:System.TimeZoneInfo> 개체는 `ToString` 메서드가 반환 되는 <xref:System.TimeZoneInfo> 개체의 표시 이름 (값을 해당 <xref:System.TimeZoneInfo.DisplayName%2A> 속성).</span><span class="sxs-lookup"><span data-stu-id="7aadc-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="7aadc-133">목록 컨트롤 개체의 호출 하므로 `ToString` 메서드 컬렉션을 할당할 수 있습니다 <xref:System.TimeZoneInfo> 개체를 컨트롤에 있는 각 개체에 대 한 의미 있는 이름을 표시 하 고 검색할 컨트롤의 <xref:System.TimeZoneInfo> 사용자가 선택한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="7aadc-134">이 컬렉션에 있는 각 개체에 대 한 문자열을 추출, 컨트롤의에 다시 할당 된 컬렉션에 문자열을 할당 하지 않아도 `DataSource` 속성을 사용자가 선택한 문자열을 검색 한 다음이 문자열을 사용 하 여 개체를 추출 합니다. 에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="7aadc-135">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7aadc-135">Compiling the code</span></span>

<span data-ttu-id="7aadc-136">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-136">This example requires:</span></span>

* <span data-ttu-id="7aadc-137">System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="7aadc-138">다음 네임 스페이스 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aadc-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="7aadc-139"><xref:System>C# 코드에서</span><span class="sxs-lookup"><span data-stu-id="7aadc-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="7aadc-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aadc-140">See also</span></span>

<span data-ttu-id="7aadc-141">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="7aadc-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
