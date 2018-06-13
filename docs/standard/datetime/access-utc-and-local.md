---
title: '방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7ddf7ba69d8bed84f62d329fd26794e2641d954
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571149"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="d15eb-102">방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스</span><span class="sxs-lookup"><span data-stu-id="d15eb-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="d15eb-103"><xref:System.TimeZoneInfo> 클래스 두 개 속성도 제공 <xref:System.TimeZoneInfo.Utc%2A> 및 <xref:System.TimeZoneInfo.Local%2A>, 미리 정의 된 표준 시간대 개체에 대 한 코드 액세스 권한이 부여 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="d15eb-104">이 항목에서는 이러한 속성들이 반환하는 <xref:System.TimeZoneInfo> 개체에 액세스하는 방법에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="d15eb-105">UTC TimeZoneInfo 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="d15eb-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="d15eb-106">사용 하 여는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Coordinated Universal Time을 액세스 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="d15eb-107">할당 하는 대신는 <xref:System.TimeZoneInfo> 개체 변수에 속성에서 반환 되는 개체에 계속 액세스할 통해 Coordinated Universal Time의 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="d15eb-108">현지 표준 시간대 TimeZoneInfo 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="d15eb-108">To access the local time zone</span></span>

1. <span data-ttu-id="d15eb-109">사용 하 여는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 로컬 시스템 표준 시간대를 액세스 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="d15eb-110">할당 하는 대신는 <xref:System.TimeZoneInfo> 개체 변수에 속성에서 반환 되는 개체에 계속 액세스할 통해 현지 표준 시간대는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="d15eb-111">예제</span><span class="sxs-lookup"><span data-stu-id="d15eb-111">Example</span></span>

<span data-ttu-id="d15eb-112">다음 코드에서는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 및 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 속성을 사용하여 시간을 미국 및 캐나다 동부 표준 시간대에서 변환하고 해당 표준 시간대 이름을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="d15eb-113">항상 통해 현지 표준 시간대에 액세스 해야는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 현지 시간을 할당 하는 것이 아니라 속성 영역에 <xref:System.TimeZoneInfo> 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="d15eb-114">마찬가지로, 협정 세계시를 통해 항상 액세스 해야는 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 는 UTC를 할당 하는 것이 아니라 속성 영역에 <xref:System.TimeZoneInfo> 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="d15eb-115">이렇게 하면는 <xref:System.TimeZoneInfo> 개체 변수를 호출 하 여 무효화 되지는 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d15eb-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="d15eb-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d15eb-116">Compiling the code</span></span>

<span data-ttu-id="d15eb-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-117">This example requires:</span></span>

* <span data-ttu-id="d15eb-118">System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d15eb-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="d15eb-119"><xref:System> 네임 스페이스를 가져올 때는 `using` 문 (C# 코드에 필요).</span><span class="sxs-lookup"><span data-stu-id="d15eb-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="d15eb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="d15eb-120">See also</span></span>

<span data-ttu-id="d15eb-121">[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[로컬 시스템에 정의 된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span><span class="sxs-lookup"><span data-stu-id="d15eb-121">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span></span>
