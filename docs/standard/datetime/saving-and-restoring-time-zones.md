---
title: "저장 및 표준 시간대 복원"
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
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d9451b1b0ff41f32c31ef3574b5684ae5a02e252
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="saving-and-restoring-time-zones"></a><span data-ttu-id="34167-102">저장 및 표준 시간대 복원</span><span class="sxs-lookup"><span data-stu-id="34167-102">Saving and restoring time zones</span></span>

<span data-ttu-id="34167-103"><xref:System.TimeZoneInfo> 클래스가 미리 정의 된 표준 시간대 데이터를 검색 하도록 레지스트리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-103">The <xref:System.TimeZoneInfo> class relies on the registry to retrieve predefined time zone data.</span></span> <span data-ttu-id="34167-104">그러나 레지스트리는 동적 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="34167-104">However, the registry is a dynamic structure.</span></span> <span data-ttu-id="34167-105">또한 레지스트리에 포함 된 표준 시간대 정보는 운영 체제에서 현재 연도 대 한 시간 조정 및 변환을 처리 하는 데 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34167-105">Additionally, the time zone information that the registry contains is used by the operating system primarily to handle time adjustments and conversions for the current year.</span></span> <span data-ttu-id="34167-106">이 표준 시간대를 정확 하 게 데이터를 사용 하는 응용 프로그램에 대 한 두 가지 주요 의미가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-106">This has two major implications for applications that rely on accurate time zone data:</span></span>

* <span data-ttu-id="34167-107">레지스트리에서 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다 또는 그 수 바뀌었거나 레지스트리에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-107">A time zone that is required by an application may not be defined in the registry, or it may have been renamed or removed from the registry.</span></span>

* <span data-ttu-id="34167-108">레지스트리에 정의 된 표준 시간대에는 기록 표준 시간대 변환에 필요한 특정 조정 규칙에 대 한 정보가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-108">A time zone that is defined in the registry may lack information about the particular adjustment rules that are necessary for historical time zone conversions.</span></span>

<span data-ttu-id="34167-109"><xref:System.TimeZoneInfo> (저장) serialization 및 deserialization (복원)의 표준 시간대 데이터에 대 한 지원을 통해 이러한 한계를 해결 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="34167-109">The <xref:System.TimeZoneInfo> class addresses these limitations through its support for serialization (saving) and deserialization (restoring) of time zone data.</span></span>

## <a name="time-zone-serialization-and-deserialization"></a><span data-ttu-id="34167-110">표준 시간대 serialization 및 deserialization</span><span class="sxs-lookup"><span data-stu-id="34167-110">Time zone serialization and deserialization</span></span>

<span data-ttu-id="34167-111">저장 및 직렬화 및 표준 시간대 데이터를 역직렬화 하 여 표준 시간대 복원 두 개의 메서드 호출을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-111">Saving and restoring a time zone by serializing and deserializing time zone data involves just two method calls:</span></span>

* <span data-ttu-id="34167-112">Serialize 할 수 있습니다는 <xref:System.TimeZoneInfo> 해당 개체를 호출 하 여 개체 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="34167-112">You can serialize a <xref:System.TimeZoneInfo> object by calling that object's <xref:System.TimeZoneInfo.ToSerializedString%2A> method.</span></span> <span data-ttu-id="34167-113">메서드 매개 변수를 사용 하 고 표준 시간대 정보를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-113">The method takes no parameters and returns a string that contains time zone information.</span></span>

* <span data-ttu-id="34167-114">Deserialize 할 수는 <xref:System.TimeZoneInfo> 해당 문자열을 전달 하 여 serialize 된 문자열에서 개체는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="34167-114">You can deserialize a <xref:System.TimeZoneInfo> object from a serialized string by passing that string to the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> method.</span></span>

## <a name="serialization-and-deserialization-scenarios"></a><span data-ttu-id="34167-115">Serialization 및 deserialization 시나리오</span><span class="sxs-lookup"><span data-stu-id="34167-115">Serialization and deserialization scenarios</span></span>

<span data-ttu-id="34167-116">저장 (또는 serialize 할) 수는 <xref:System.TimeZoneInfo> 나중에 사용할 개체를 문자열로 및 복원 하거나 deserialize 하기를 높아지고 유틸리티의 유연성은 <xref:System.TimeZoneInfo> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="34167-116">The ability to save (or serialize) a <xref:System.TimeZoneInfo> object to a string and to restore (or deserialize) it for later use increases both the utility and the flexibility of the <xref:System.TimeZoneInfo> class.</span></span> <span data-ttu-id="34167-117">이 섹션에서는 직렬화 및 역직렬화 유용한 지는 경우.</span><span class="sxs-lookup"><span data-stu-id="34167-117">This section examines some of the situations in which serialization and deserialization are most useful.</span></span>

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a><span data-ttu-id="34167-118">직렬화 및 응용 프로그램의 표준 시간대 데이터를 역직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-118">Serializing and deserializing time zone data in an application</span></span>

<span data-ttu-id="34167-119">필요한 경우 serialize 된 표준 시간대는 문자열에서 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-119">A serialized time zone can be restored from a string when it is needed.</span></span> <span data-ttu-id="34167-120">응용 프로그램에서 레지스트리로부터 검색 표준 시간대의 날짜와 특정 날짜 범위 내에서 시간으로 올바르게 변환 하기 수 없는 경우 이렇게 주어 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-120">An application might do this if the time zone retrieved from the registry is unable to correctly convert a date and time within a particular date range.</span></span> <span data-ttu-id="34167-121">예를 들어 Windows XP 레지스트리에서 표준 시간대 데이터는 일반적으로 Windows Vista 레지스트리에 정의 된 표준 시간대 조정 규칙에 대 한 두 가지 정보를 제공 하는 동안 하나의 조정 규칙을를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-121">For example, time zone data in the Windows XP registry supports a single adjustment rule, while time zones defined in the Windows Vista registry typically provide information about two adjustment rules.</span></span> <span data-ttu-id="34167-122">즉, 있는지 기록 시간 변환 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-122">This means that historical time conversions may be inaccurate.</span></span> <span data-ttu-id="34167-123">표준 시간대 데이터의 serialization 및 deserialization에는이 제한 사항은 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-123">Serialization and deserialization of time zone data can handle this limitation.</span></span>

<span data-ttu-id="34167-124">다음 예제에서는 사용자 지정에서에서 <xref:System.TimeZoneInfo> 미국을 나타내도록 정의 조정 규칙 없이 클래스 동부 표준시 조정에서를 미국에서 일광 절약 시간제의 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-124">In the following example, a custom <xref:System.TimeZoneInfo> class that has no adjustment rules is defined to represent the U.S. Eastern Standard Time zone from 1883 to 1917, before the introduction of daylight saving time in the United States.</span></span> <span data-ttu-id="34167-125">사용자 지정 표준 시간대는 전역 범위를 가진 변수에 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34167-125">The custom time zone is serialized in a variable that has global scope.</span></span> <span data-ttu-id="34167-126">표준 시간대 변환 메서드 `ConvertUtcTime`, 변환할 Coordinated Universal Time (UTC) 시간에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34167-126">The time zone conversion method, `ConvertUtcTime`, is passed Coordinated Universal Time (UTC) times to convert.</span></span> <span data-ttu-id="34167-127">날짜 및 시간 또는 이전 버전 1917에서 발생 하는 경우 사용자 지정 동부 표준시 표준 시간대 serialize 된 문자열에서 복원 하 고 표준 시간대에서 레지스트리로부터 검색을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-127">If the date and time occurs in 1917 or earlier, the custom Eastern Standard Time zone is restored from a serialized string and replaces the time zone retrieved from the registry.</span></span>

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a><span data-ttu-id="34167-128">표준 시간대 예외 처리</span><span class="sxs-lookup"><span data-stu-id="34167-128">Handling time zone exceptions</span></span>

<span data-ttu-id="34167-129">레지스트리 동적 구조 이기 때문에 해당 내용을 실수로 또는 의도적으로 수정 하지 않고도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34167-129">Because the registry is a dynamic structure, its contents are subject to accidental or deliberate modification.</span></span> <span data-ttu-id="34167-130">즉, 레지스트리에 정의 되어 있어야 하 고 성공적으로 실행 하도록 응용 프로그램에 필요한 표준 시간대 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-130">This means that a time zone that should be defined in the registry and that is required for an application to execute successfully may be absent.</span></span> <span data-ttu-id="34167-131">하려면 결과 처리 하지만 선택의 여지가 거의 시간대 serialization 및 deserialization에 대 한 지원 없이 있는 <xref:System.TimeZoneNotFoundException> 응용 프로그램을 종료 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-131">Without support for time zone serialization and deserialization, you have little choice but to handle the resulting <xref:System.TimeZoneNotFoundException> by ending the application.</span></span> <span data-ttu-id="34167-132">그러나 표준 시간대 직렬화 및 역직렬화를 사용 하 여 처리할 수 있습니다는 예기치 않은 <xref:System.TimeZoneNotFoundException> 복원 하 여 직렬화 된 문자열 및 응용 프로그램에서 필요한 표준 시간대는 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-132">However, by using time zone serialization and deserialization, you can handle an unexpected <xref:System.TimeZoneNotFoundException> by restoring the required time zone from a serialized string, and the application will continue to run.</span></span>

<span data-ttu-id="34167-133">다음 예제에서는 만들고 사용자 지정 중앙 표준 시간대를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-133">The following example creates and serializes a custom Central Standard Time zone.</span></span> <span data-ttu-id="34167-134">그런 다음 레지스트리에서 중앙 표준 시간대를 검색 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-134">It then tries to retrieve the Central Standard Time zone from the registry.</span></span> <span data-ttu-id="34167-135">검색 작업 중 하나를 throw 하는 경우는 <xref:System.TimeZoneNotFoundException> 또는 <xref:System.InvalidTimeZoneException>, 예외 처리기는 표준 시간대를 역직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-135">If the retrieval operation throws either a <xref:System.TimeZoneNotFoundException> or an <xref:System.InvalidTimeZoneException>, the exception handler deserializes the time zone.</span></span>

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a><span data-ttu-id="34167-136">Serialize 된 문자열을 저장 하 고 필요할 때 복원</span><span class="sxs-lookup"><span data-stu-id="34167-136">Storing a serialized string and restoring it when needed</span></span>

<span data-ttu-id="34167-137">앞의 예제에서는 문자열 변수에 표준 시간대 정보를 저장 있으며 필요할 때 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34167-137">The previous examples have stored time zone information to a string variable and restored it when needed.</span></span> <span data-ttu-id="34167-138">그러나 serialize 된 표준 시간대 정보 자체에 저장할 수 외부 파일에 리소스 파일 등의 일부 저장 미디어를 포함 하는 문자열은 응용 프로그램 또는 레지스트리에 포함.</span><span class="sxs-lookup"><span data-stu-id="34167-138">However, the string that contains serialized time zone information can itself be stored in some storage medium, such as an external file, a resource file embedded in the application, or the registry.</span></span> <span data-ttu-id="34167-139">(참고 하 여 사용자 지정 표준 시간대에 대 한 정보는 시스템의 표준 시간대 레지스트리 키 외에도 저장 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="34167-139">(Note that information about custom time zones should be stored apart from the system's time zone keys in the registry.)</span></span>

<span data-ttu-id="34167-140">응용 프로그램 자체에서 표준 시간대 작성 루틴 또한 구분 이런이 방식으로 직렬화 된 표준 시간대 문자열을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-140">Storing a serialized time zone string in this manner also separates the time zone creation routine from the application itself.</span></span> <span data-ttu-id="34167-141">예를 들어 표준 시간대 작성 루틴 실행을 응용 프로그램에서 사용할 수 있는 기록 표준 시간대 정보를 포함 하는 데이터 파일을 만들 수 합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-141">For example, a time zone creation routine can execute and create a data file that contains historical time zone information that an application can use.</span></span> <span data-ttu-id="34167-142">데이터 파일 일 수 있습니다 다음 응용 프로그램을 함께 설치할 수 열 수 있습니다 및 응용 프로그램에서 필요로 하는 경우 하나 이상의 표준 시간대를 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34167-142">The data file can be then be installed with the application, and it can be opened and one or more of its time zones can be deserialized when the application requires them.</span></span>

<span data-ttu-id="34167-143">포함된 리소스를 사용 하 여 serialize 된 표준 시간대 데이터를 저장 하는 예제를 보려면 [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34167-143">For an example that uses an embedded resource to store serialized time zone data, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34167-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34167-144">See also</span></span>

[<span data-ttu-id="34167-145">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="34167-145">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
