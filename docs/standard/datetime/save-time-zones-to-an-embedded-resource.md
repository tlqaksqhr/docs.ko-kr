---
title: "방법: 포함 된 표준 시간대 저장"
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
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96dd3f0a3ed27a9e09c62f3ad4f450ced5a8e644
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="fcdb7-102">방법: 포함 된 표준 시간대 저장</span><span class="sxs-lookup"><span data-stu-id="fcdb7-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="fcdb7-103">종종 표준 시간대 인식 응용 프로그램 특정 표준 시간대가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="fcdb7-104">그러나 때문에 개별 가용성 <xref:System.TimeZoneInfo> 로컬 시스템의 레지스트리에 저장 된 정보에 종속 된 개체, 관례적도 사용할 수 있는 표준 시간대는 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="fcdb7-105">또한 사용자 지정 표준 시간대에 대 한 정보를 사용 하 여 인스턴스화할는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드 레지스트리의 다른 표준 시간대 정보가 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="fcdb7-106">을 보장 하기 위해 필요할 때 이러한 표준 시간대를 사용할 수 있는지를 직렬화 하 여 저장할 수 있으며 나중에 역직렬화 하 여 복원할 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="fcdb7-107">일반적으로 직렬화는 <xref:System.TimeZoneInfo> 개체가 표준 시간대 인식 응용 프로그램 외에도 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="fcdb7-108">Serialize 된 보관 하는 데 데이터 저장소에 따라 <xref:System.TimeZoneInfo> 개체 (예: 데이터 응용 프로그램 레지스트리 키에 저장 될 때), 설치 과정의 일환으로 또는 실행 되는 유틸리티 루틴의 일환으로 표준 시간대 데이터를 serialize 할 수 하기 전에 (예를 들어, serialize 된 데이터 저장 된 경우에.NET XML 리소스 (.resx) 파일)은 최종 응용 프로그램과 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="fcdb7-109">응용 프로그램으로 컴파일된 리소스 파일 외에 표준 시간대 정보에 대 한 몇 가지 다른 데이터 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="fcdb7-110">이러한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-110">These include the following:</span></span>

* <span data-ttu-id="fcdb7-111">레지스트리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-111">The registry.</span></span> <span data-ttu-id="fcdb7-112">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time 영역의 하위 키를 사용 하는 것이 아니라 사용자 지정 표준 시간대 데이터를 저장 하는 응용 프로그램 자체 응용 프로그램 키의 하위 키를 사용 해야 함을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="fcdb7-113">구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-113">Configuration files.</span></span>

* <span data-ttu-id="fcdb7-114">다른 시스템 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="fcdb7-115">.Resx 파일에 직렬화 하 여 표준 시간대를 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="fcdb7-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="fcdb7-116">새 표준 시간대를 만들거나 기존 표준 시간대를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="fcdb7-117">기존 표준 시간대를 검색 하려면 참조 [하는 방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스](../../../docs/standard/datetime/access-utc-and-local.md) 및 [하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="fcdb7-118">새 표준 시간대를 만들려면 오버 로드 중 하나를 호출는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="fcdb7-119">자세한 내용은 참조 [하는 방법: 조정 규칙 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="fcdb7-120">호출 된 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드 표준 시간대의 데이터를 포함 하는 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="fcdb7-121">인스턴스화하는 <xref:System.IO.StreamWriter> 개체의 이름 및 필요에 따라.resx 파일의 경로 제공 하는 <xref:System.IO.StreamWriter> 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="fcdb7-122">인스턴스화하는 <xref:System.Resources.ResXResourceWriter> 전달 하 여 개체는 <xref:System.IO.StreamWriter> 개체를 <xref:System.Resources.ResXResourceWriter> 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="fcdb7-123">패스에서 표준 시간대의 문자열을 직렬화는 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="fcdb7-124"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="fcdb7-125"><xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="fcdb7-126">닫기는 <xref:System.IO.StreamWriter> 개체를 호출 하 여 해당 <xref:System.IO.StreamWriter.Close%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="fcdb7-127">응용 프로그램의 Visual Studio 프로젝트에 생성 된.resx 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="fcdb7-128">사용 하는 **속성** Visual Studio 창에 표시 되도록.resx 파일의 **빌드 작업** 속성이로 설정 되어 **포함 리소스**합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="fcdb7-129">예제</span><span class="sxs-lookup"><span data-stu-id="fcdb7-129">Example</span></span>

<span data-ttu-id="fcdb7-130">다음 예제에서는 serialize 한 <xref:System.TimeZoneInfo> 중부 표준시를 나타내는 개체와 <xref:System.TimeZoneInfo> SerializedTimeZones.resx 라고 하는.NET XML 리소스 파일에 Palmer 스테이션, 남극 대륙 시간을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="fcdb7-131">레지스트리에; 중부 표준시 정의 일반적으로 Palmer 스테이션 남극 대륙 사용자 지정 표준 시간대입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="fcdb7-132">이 예제에서는 serialize <xref:System.TimeZoneInfo> 있습니다 사용할 수 있도록 리소스 파일에 컴파일 타임에 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="fcdb7-133">때문에 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드는.NET XML 리소스 파일에 전체 헤더 정보를 추가, 기존 파일에 리소스를 추가 하는 데 사용 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="fcdb7-134">예제 SerializedTimeZones.resx 파일을 확인 하 여이 처리 하 고 있는 경우 모든 리소스가 아닌 다른 저장 두 직렬화 된 표준 시간대를 제네릭 <xref:System.Collections.Generic.Dictionary%602> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="fcdb7-135">기존 파일은 삭제 되 고 기존 리소스 새 SerializedTimeZones.resx 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="fcdb7-136">Serialize 된 표준 시간대 데이터는이 파일에도 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="fcdb7-137">키 (또는 **이름**) 리소스의 필드에 포함 된 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="fcdb7-138"><xref:System.String.Replace%28System.String%2CSystem.String%29> 메서드를 호출 하는 리소스 파일에 할당 되기 전에 표준 시간대 식별자에 포함 된 모든 공백을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="fcdb7-139">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fcdb7-139">Compiling the code</span></span>

<span data-ttu-id="fcdb7-140">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-140">This example requires:</span></span>

* <span data-ttu-id="fcdb7-141">System.Windows.Forms.dll 및 System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="fcdb7-142">다음 네임 스페이스 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcdb7-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="fcdb7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcdb7-143">See also</span></span>

<span data-ttu-id="fcdb7-144">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="fcdb7-144">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
