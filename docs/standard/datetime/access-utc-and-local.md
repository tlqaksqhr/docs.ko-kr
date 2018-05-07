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
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스

<xref:System.TimeZoneInfo> 클래스 두 개 속성도 제공 <xref:System.TimeZoneInfo.Utc%2A> 및 <xref:System.TimeZoneInfo.Local%2A>, 미리 정의 된 표준 시간대 개체에 대 한 코드 액세스 권한이 부여 하는 합니다. 이 항목에서는 이러한 속성들이 반환하는 <xref:System.TimeZoneInfo> 개체에 액세스하는 방법에 설명합니다.

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>UTC TimeZoneInfo 개체에 액세스하려면

1. 사용 하 여는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Coordinated Universal Time을 액세스 하는 속성입니다.

2. 할당 하는 대신는 <xref:System.TimeZoneInfo> 개체 변수에 속성에서 반환 되는 개체에 계속 액세스할 통해 Coordinated Universal Time의 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 속성입니다.

### <a name="to-access-the-local-time-zone"></a>현지 표준 시간대 TimeZoneInfo 개체에 액세스하려면

1. 사용 하 여는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 로컬 시스템 표준 시간대를 액세스 하는 속성입니다.

2. 할당 하는 대신는 <xref:System.TimeZoneInfo> 개체 변수에 속성에서 반환 되는 개체에 계속 액세스할 통해 현지 표준 시간대는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성입니다.

## <a name="example"></a>예제

다음 코드에서는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 및 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 속성을 사용하여 시간을 미국 및 캐나다 동부 표준 시간대에서 변환하고 해당 표준 시간대 이름을 콘솔에 표시합니다.

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

항상 통해 현지 표준 시간대에 액세스 해야는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 현지 시간을 할당 하는 것이 아니라 속성 영역에 <xref:System.TimeZoneInfo> 개체 변수입니다. 마찬가지로, 협정 세계시를 통해 항상 액세스 해야는 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 는 UTC를 할당 하는 것이 아니라 속성 영역에 <xref:System.TimeZoneInfo> 개체 변수입니다. 이렇게 하면는 <xref:System.TimeZoneInfo> 개체 변수를 호출 하 여 무효화 되지는 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 메서드.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* <xref:System> 네임 스페이스를 가져올 때는 `using` 문 (C# 코드에 필요).

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[로컬 시스템에 정의 된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)
