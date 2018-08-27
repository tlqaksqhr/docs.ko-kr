---
title: 표준 시간대 간 시간 변환
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b971e71019359cebc1493a410e748a1fd7b7cb
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933500"
---
# <a name="converting-times-between-time-zones"></a>표준 시간대 간 시간 변환

날짜 및 시간을 사용하는 응용 프로그램에서 표준 시간대 간의 차이를 처리하는 것이 더욱 중요해지고 있습니다. 응용 프로그램 현지 시간을 항상을 표현할 수 있는 것을 가정할 수 더 이상 시간에서 사용할 수 있는 <xref:System.DateTime> 구조입니다. 예를 들어 동아시아 지역 고객에게는 미국 동부 지역의 현재 시간을 표시하는 웹 페이지의 신뢰성이 떨어집니다. 이 항목에서는 변환 하는 방법 뿐만 아니라 다른 시간대의 시간을 변환 하는 방법 설명 <xref:System.DateTimeOffset> 표준 시간대 인식 제한 된 값입니다.

## <a name="converting-to-coordinated-universal-time"></a>UTC로 변환

UTC(협정 세계시)는 고정밀 원자 시간 표준입니다. 전세계의 표준 시간대가 UTC의 양 또는 음 오프셋으로 표시됩니다. 따라서 UTC는 어느 정도 표준 시간대에서 자유롭거나 중립적인 시간을 제공합니다. 컴퓨터 간에 날짜 및 시간의 이식성이 중요한 경우 UTC 시간을 사용하는 것이 좋습니다. (날짜 및 시간을 사용 하 여 기타 모범 사례와 세부 정보에 대 한 참조 [.NET Framework에서 DateTime을 사용한 최상의 코딩 방법](https://msdn.microsoft.com/library/ms973825.aspx).) 개별 표준 시간대를 UTC로 변환하면 시간을 보다 쉽게 비교할 수 있습니다.

> [!NOTE]
> Serialize 할 수도 있습니다는 <xref:System.DateTimeOffset> 명확 하 게 나타낼 단일 지점 시간에서 구조입니다. 때문에 <xref:System.DateTimeOffset> utc에서 오프셋과 함께 날짜 및 시간 값을 저장 하는 개체, 항상 나타내는 특정 지점 관계의 지정 시간에서을 UTC입니다.

UTC로 변환 하는 가장 쉬운 방법은 호출 하는 것은 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> 메서드. 메서드에 의해 수행 되는 정확한 변환은 값에 따라 달라 집니다 합니다 `dateTime` 매개 변수의 <xref:System.DateTime.Kind%2A> 다음 표와 같이 속성입니다.

| `DateTime.Kind`            | 변환                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | 현지 시간을 UTC로 변환합니다.                                                    |
| `DateTimeKind.Unspecified` | `dateTime` 매개 변수가 현지 시간인 것으로 가정하고 현지 시간을 UTC로 변환합니다. |
| `DateTimeKind.Utc`         | 변경하지 않은 `dateTime` 매개 변수를 반환합니다.                                    |

다음 코드에서는 현재 현지 시간을 UTC로 변환하고 그 결과를 콘솔에 표시합니다.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> 합니다 <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> 메서드는 반드시 동일한 결과 생성 하지는 <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> 고 <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> 메서드. 호스트 시스템의 현지 표준 시간대 여러 조정 규칙을 포함 <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> 특정 날짜 및 시간에 적절 한 규칙을 적용 합니다. 다른 두 메서드는 항상 최신 조정 규칙을 적용합니다.

날짜 및 시간 값이 현지 시간 또는 UTC를 나타내지 않는 경우는 <xref:System.DateTime.ToUniversalTime%2A> 메서드는 잘못 된 결과가 반환 수 있습니다. 그러나 사용할 수는 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> 지정된 된 표준 시간대의 날짜 및 시간을 변환 하는 방법. (검색에 대 한 세부 정보에 대 한는 <xref:System.TimeZoneInfo> 대상 표준 시간대를 나타내는 개체를 참조 하세요 [로컬 시스템에 정의 된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) 다음 코드에서는 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> 동부 표준시를 UTC로 변환 하는 방법입니다.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

이 메서드가 throw 하는 참고를 <xref:System.ArgumentException> 경우는 <xref:System.DateTime> 개체의 <xref:System.DateTime.Kind%2A> 속성과 표준 시간대 일치 하지 않습니다. 불일치가 발생 하는 경우는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Local?displayProperty=nameWithType> 하지만 <xref:System.TimeZoneInfo> 개체의 현지 표준 시간대를 나타내지 않는 경우는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> 되지만 <xref:System.TimeZoneInfo> 개체와 같지 않습니다 <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

이러한 메서드의 모든 시간이 <xref:System.DateTime> 매개 변수 및 반환 값을 <xref:System.DateTime> 값입니다. 에 대 한 <xref:System.DateTimeOffset> 값을 <xref:System.DateTimeOffset> 구조에는 <xref:System.DateTimeOffset.ToUniversalTime%2A> 인스턴스 날짜와 현재 인스턴스의 시간을 UTC로 변환 하는 메서드. 다음 예제에서는 <xref:System.DateTimeOffset.ToUniversalTime%2A> 현지 시간과 여러 다른 시간을 utc (협정 세계시)로 변환 하는 방법입니다.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>UTC를 지정한 표준 시간대로 변환

UTC를 현지 시간으로 변환 하려면 다음에 나오는 "변환 UTC를 현지 시간" 섹션을 참조 하세요. 지정 하는 모든 표준 시간대의 시간을 UTC로 변환 하려면 호출을 <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> 메서드. 이 메서드에서 사용하는 두 개의 매개 변수는 다음과 같습니다.

* 변환할 UTC. 이어야 합니다는 <xref:System.DateTime> 값 <xref:System.DateTime.Kind%2A> 속성이 `Unspecified` 또는 `Utc`합니다.

* UTC를 변환한 값이 속하게 될 표준 시간대

다음 코드는 UTC를 중부 표준시로 변환합니다.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>UTC를 현지 시간으로 변환

UTC를 현지 시간으로 변환 하려면 호출을 <xref:System.DateTime.ToLocalTime%2A> 메서드는 <xref:System.DateTime> 개체 시간을 변환 합니다. 개체의 값에 따라 메서드의 정확한 동작은 <xref:System.DateTime.Kind%2A> 다음 표와 같이 속성입니다.

| `DateTime.Kind`            | 변환                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | 반환 된 <xref:System.DateTime> 변경 되지 않은 값입니다.                                      |
| `DateTimeKind.Unspecified` | 가정 된 <xref:System.DateTime> 값 UTC 이며 UTC를 현지 시간으로 변환 합니다. |
| `DateTimeKind.Utc`         | 변환 된 <xref:System.DateTime> 값을 현지 시간입니다.                                 |

> [!NOTE]
> 합니다 <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> 메서드는 동일 하 게 동작 합니다 `DateTime.ToLocalTime` 메서드. 변환할 날짜 및 시간 값을 단일 매개 변수를 사용 합니다.

사용 하 여 지정 된 표준 시간대의 시간을 현지 시간 변환할 수도 있습니다는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> 메서드. 이 방법은 다음 섹션에 설명 되어 있습니다.

## <a name="converting-between-any-two-time-zones"></a>두 표준 시간대 간 변환

다음 두 가지 중 하나를 사용 하 여 두 표준 시간대 간에 변환할 수 있습니다 `static` (`Shared` Visual basic에서)의 메서드는 <xref:System.TimeZoneInfo> 클래스:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  이 메서드의 매개이 변수는 변환할 날짜 및 시간 값을 `TimeZoneInfo` 날짜 및 시간 값의 표준 시간대를 나타내는 개체 및 `TimeZoneInfo` 날짜 및 시간 값을 변환할 표준 시간대를 나타내는 개체입니다.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  이 메서드의 매개이 변수는 날짜 및 시간 값을 변환할 날짜 및 시간 값으로 변환할 날짜 및 시간 값의 표준 시간대의 식별자 및 표준 시간대의 식별자는.

두 메서드 모두 필요 합니다 <xref:System.DateTime.Kind%2A> 변환할 날짜 및 시간 값의 속성 및 <xref:System.TimeZoneInfo> 해당 표준 시간대를 나타내는 개체 또는 표준 시간대 식별자가 서로 일치 합니다. 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다. 예를 들어 경우는 `Kind` 날짜 및 시간 값의 속성은 `DateTimeKind.Local`, 경우 예외가 throw 됩니다 합니다 `TimeZoneInfo` 메서드에 매개 변수로 전달 된 개체가 같지 않습니다. `TimeZoneInfo.Local`합니다. 메서드에 매개 변수로 전달 된 식별자와 같지 않습니다. 경우에 예외가 throw 됩니다 `TimeZoneInfo.Local.Id`합니다.

다음 예제에서는 <xref:System.TimeZoneInfo.ConvertTime%2A> 하와이 표준시를 현지 시간으로 변환 하는 방법입니다.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>DateTimeOffset 값 변환

날짜 및 시간 값을 나타내는 <xref:System.DateTimeOffset> 개체는 완전히 시간대 인스턴스화된 개체 시 해당 표준 시간대에서 분리 되므로 인식 합니다. 그러나 많은 경우에는 응용 프로그램에서 특정 표준 시간대의 시간이 아니라 단순히 서로 다른 UTC 오프셋 두 개를 기준으로 날짜 및 시간을 변환하면 됩니다. 이 변환을 수행 하려면 현재 인스턴스를 호출할 수 있습니다 <xref:System.DateTimeOffset.ToOffset%2A> 메서드. 메서드의 단일 매개 변수는 새 날짜 및 메서드를 반환 하는 시간 값의 오프셋입니다.

예를 들어 사용자가 웹 페이지에서 요청한 날짜 및 시간이 알려져 있고 이 값이 MM/dd/yyyy hh:mm:ss zzzz 형식의 문자열로 serialize된 경우 뒤따르는 `ReturnTimeOnServer` 메서드에서 이 날짜 및 시간 값을 웹 서버의 날짜 및 시간 값으로 변환합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

UTC보다 다섯 시간 빠른 표준 시간대의 날짜 및 시간을 나타내는 "9/1/2007 5:32:07 -05:00" 문자열이 메서드에 전달되는 경우 이 메서드에서는 미국 태평양 표준 시간대에 있는 서버에 대해 9/1/2007 3:32:07 AM -07:00을 보여 줍니다.

<xref:System.TimeZoneInfo> 클래스의 오버 로드도 포함 되어 있습니다 합니다 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 사용 하 여 표준 시간대 변환을 수행 하는 메서드 <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> 값입니다. 메서드의 매개 변수는 <xref:System.DateTimeOffset> 값 및 시간 변환 되는 표준 시간대에 대 한 참조입니다. 메서드 호출이 반환 된 <xref:System.DateTimeOffset> 값입니다. 예를 들어 합니다 `ReturnTimeOnServer` 이전 예제의 메서드를 호출 다음과 같이 작성할 수 없습니다는 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> 메서드.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>참고자료

<xref:System.TimeZoneInfo>
[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[로컬 시스템에 정의 된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
