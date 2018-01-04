---
title: "방법: 포함된 리소스에서 표준 시간대 복원"
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
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: efb133d972427a9619581d0670268cba9fbd3ee6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="41acb-102">방법: 포함된 리소스에서 표준 시간대 복원</span><span class="sxs-lookup"><span data-stu-id="41acb-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="41acb-103">이 항목에서는 리소스 파일에 저장 되어 있는 표준 시간대를 복원 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="41acb-104">정보 및 표준 시간대 저장 하는 방법에 대 한 지침을 참조 하세요. [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="41acb-105">포함된 리소스에서 TimeZoneInfo 개체를 deserialize 하기 위해</span><span class="sxs-lookup"><span data-stu-id="41acb-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="41acb-106">사용자 지정 표준 시간대 표준 시간대를 검색할 수 없는 경우이 사용 하 여 인스턴스화하 려는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="41acb-107">인스턴스화하는 <xref:System.Resources.ResourceManager> 포함된 리소스 파일 및 리소스 파일을 포함 하는 어셈블리에 대 한 참조의 정규화 된 이름을 전달 하 여 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="41acb-108">포함된 리소스 파일의 정규화 된 이름을 확인할 수 없으면를 사용 하 여는 [Ildasm.exe (IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 어셈블리의 매니페스트를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="41acb-109">`.mresource` 항목은 리소스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="41acb-110">예제에서는 리소스의 정규화 된 이름이 `SerializeTimeZoneData.SerializedTimeZones`합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="41acb-111">리소스 파일이 시간대 인스턴스화 코드를 포함 하는 동일한 어셈블리에 포함 되는 경우 호출 하 여에 대 한 참조를 검색할 수 있습니다는 `static` (`Shared` Visual basic에서) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="41acb-112">경우에 대 한 호출에서 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드가 실패 하면 사용자 지정 표준 시간대를 인스턴스화할 경우 호출 하 여 serialize 된 표준 시간대를 포함 하는 문자열을 검색 하거나는 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="41acb-113">호출 하 여 표준 시간대 데이터를 deserialize는 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="41acb-114">예</span><span class="sxs-lookup"><span data-stu-id="41acb-114">Example</span></span>

<span data-ttu-id="41acb-115">다음 예제에서는 deserialize는 <xref:System.TimeZoneInfo> 포함된 된.NET XML 리소스 파일에 저장 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="41acb-116">이 코드 되도록 할 예외 처리를 보여 줍니다.는 <xref:System.TimeZoneInfo> 응용 프로그램에 필요한 개체는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="41acb-117">인스턴스화하는 먼저 시도 <xref:System.TimeZoneInfo> 개체에서 사용 하 여 레지스트리 항목을 검색 하 여는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="41acb-118">표준 시간대를 인스턴스화할 수 없는 경우 코드에서 포함된 리소스 파일에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="41acb-119">때문에 사용자 지정 표준 시간대에 대 한 데이터 (표준 시간대를 사용 하 여 인스턴스화할는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드) 저장 되지 않은 레지스트리에 코드 호출 하지 않습니다는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Palmer, 남극 대륙에 대 한 표준 시간대를 인스턴스화할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="41acb-120">대신, 곧바로 호출 하기 전에 표준 시간대의 데이터를 포함 하는 문자열을 검색 하는 포함된 리소스 파일에는 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="41acb-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="41acb-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="41acb-121">Compiling the code</span></span>

<span data-ttu-id="41acb-122">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-122">This example requires:</span></span>

* <span data-ttu-id="41acb-123">System.Windows.Forms.dll 및 System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="41acb-124">다음 네임 스페이스 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41acb-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="41acb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41acb-125">See also</span></span>

<span data-ttu-id="41acb-126">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="41acb-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span></span>
