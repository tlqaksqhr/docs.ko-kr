---
title: "방법: 사용자가 모호한 시간 확인"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d0122ca1469b32692fa9c4ef2bd37cda39622bd7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>방법: 사용자가 모호한 시간 확인

모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다. 표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다. 모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.

* 모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.

* 시간을 UTC로 매핑하는 방법에 대해 가정합니다. 예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.

이 항목에서는 사용자 모호한 시간을 해결 하는 방법을 보여 줍니다.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>사용자가 모호한 시간을 확인하도록 허용하려면

1. 사용자가 입력한 시간과 날짜를 가져옵니다.

2. 호출의 <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 메서드 시간이 모호한 인지 여부를 확인 합니다.

3. 호출 시간이 모호한 경우는 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 의 배열을 검색 하는 메서드 <xref:System.TimeSpan> 개체입니다. 배열의 각 요소는 모호한 시간에 매핑할 수 있는 UTC 오프셋을 포함 합니다.

4. 사용자가 원하는 오프셋을 선택하도록 합니다.

5. 현지 시간에서 사용자가 선택한 오프셋을 빼서 UTC 날짜 및 시간을 가져옵니다.

6. 호출 된 `static` (`Shared` Visual Basic.net에서) <xref:System.DateTime.SpecifyKind%2A> UTC 날짜 및 시간 값의 설정 하는 방법은 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>합니다.

## <a name="example"></a>예

다음 예제에서는 날짜와 시간을 입력하라는 메시지가 표시되며 모호한 경우 모호한 시간이 매핑하는 UTC 시간을 사용자가 선택할 수 있습니다.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

예제 코드의 핵심 배열을 사용 하 여 <xref:System.TimeSpan> 모호한 시간 측정 된 UTC에서의 가능한 오프셋을 나타내는 개체입니다. 그러나 이러한 오프셋은 사용자에게 유용하지 않을 가능성이 높습니다. 오프셋의 의미를 분명히 하기 위해 코드는 오프셋이 현지 표준 시간대의 표준 시간 또는 일광 절약 시간을 나타내는지를 적어둡니다. 코드는 시간이 표준 인지를 확인 하 고 어떤 시간은 일광 오프셋의 값을 비교 하 여는 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성입니다. 이 속성은 UTC와 표준 시간대의 표준 시간 사이의 차이를 나타냅니다.

이 예제에서는 현지 표준 시간대에 대 한 모든 참조를 통해 이루어집니다는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 속성; 영역 개체 변수 할당 되지 않으므로 로컬 시간입니다. 때문에이 권장된 방법에 대 한 호출에서 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 메서드 현지 표준 시간대에 할당 된 모든 개체가 무효화 합니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* <xref:System> 네임 스페이스를 가져올 때는 `using` 문 (C# 코드에 필요).

## <a name="see-also"></a>참고 항목

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[하는 방법: 모호한 시간 확인](../../../docs/standard/datetime/resolve-ambiguous-times.md)
