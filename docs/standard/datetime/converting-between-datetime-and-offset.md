---
title: DateTime과 DateTimeOffset 간 변환
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dec0e5138ecf08783f11d21cd28d7291d27ea68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578250"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>DateTime과 DateTimeOffset 간 변환

하지만 <xref:System.DateTimeOffset> 구조는 더 높은 수준의 보다 시간대 인식 제공는 <xref:System.DateTime> 구조, <xref:System.DateTime> 메서드 호출에 매개 변수가 일반적으로 사용 됩니다. 따라서 변환 기능을 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값 및 반대의 작업은 특히 중요 합니다. 이 항목에는 최대한 많은 표준 시간대 정보를 유지 하는 방식으로 이러한 변환을 수행 하는 방법을 보여 줍니다.

> [!NOTE]
> 둘 다는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 형식 시간대의 시간을 나타낼 때 몇 가지 제한 사항이 있습니다. 와 해당 <xref:System.DateTime.Kind%2A> 속성 <xref:System.DateTime> utc (협정 세계시) 및 시스템의 현지 표준 시간대를 반영할 수 있습니다. <xref:System.DateTimeOffset> 한 번 UTC에서 오프셋 되지만 실제 표준 시간대 오프셋이 있는 속한 반영 되지 않습니다 반영 합니다. 시간 값 및 표준 시간대에 대 한 지원에 대 한 세부 정보를 참조 하십시오. [Choosing Between DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)합니다.

## <a name="conversions-from-datetime-to-datetimeoffset"></a>DateTime에서 DateTimeOffset으로 변환

<xref:System.DateTimeOffset> 구조에 해당 하는 두 가지 방법으로 수행할 수는 제공 <xref:System.DateTime> 를 <xref:System.DateTimeOffset> 대부분 변환에 적합 한 변환:

* <xref:System.DateTimeOffset.%23ctor%2A> 새 생성자 <xref:System.DateTimeOffset> 기반 개체는 <xref:System.DateTime> 값입니다.

* 할당할 수 있도록 하는 암시적 변환 연산자에는 <xref:System.DateTime> 값을 한 <xref:System.DateTimeOffset> 개체입니다.

UTC 및 현지 <xref:System.DateTime> 값의 <xref:System.DateTimeOffset.Offset%2A> 결과 속성 <xref:System.DateTimeOffset> 값은 표준 시간대 오프셋을 UTC 또는 현지 시간을 정확 하 게 반영 합니다. 다음 코드는 해당 하는 UTC 시간을 변환 하는 예를 들어 <xref:System.DateTimeOffset> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

이 경우 `utcTime2` 변수의 오프셋은 00:00입니다. 다음 코드는 해당 하는 현지 시간을 변환 하는 마찬가지로, <xref:System.DateTimeOffset> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

그러나 <xref:System.DateTime> 값을 갖는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 이러한 두 변환 메서드를 생성 한 <xref:System.DateTimeOffset> 현지 표준 시간대의 오프셋이 값입니다. 미국 태평양 표준시에서 실행되는 다음 예제에서 이러한 변환을 보여 줍니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

경우는 <xref:System.DateTime> 를 변환할 수 있습니다, 날짜 및 시간을 현지 표준 시간대 또는 utc 형식이 아닌 다른 값은 반영는 <xref:System.DateTimeOffset> 값 및 오버 로드 된 호출 하 여 해당 표준 시간대 정보를 보존 <xref:System.DateTimeOffset.%23ctor%2A> 생성자입니다. 예를 들어 다음 예제에서는 인스턴스화하는 <xref:System.DateTimeOffset> 중부 표준시 반영 하는 개체입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

이 생성자 오버 로드에 두 번째 매개 변수는 <xref:System.TimeSpan> UTC에서의 시간 오프셋을 나타내는 개체를 호출 하 여 검색할는 <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> 시간에서 해당 표준 시간대의 메서드. 메서드의 단일 매개 변수는 <xref:System.DateTime> 변환할 날짜 및 시간을 나타내는 값입니다. 표준 시간대에서 일광 절약 시간제를 지원하는 경우 이 매개 변수를 사용하면 특정 날짜와 시간에 적절한 오프셋을 해당 메서드에서 결정할 수 있습니다.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>DateTimeOffset에서 DateTime으로 변환

<xref:System.DateTimeOffset.DateTime%2A> 속성은 가장 일반적으로 수행 하는 데 사용 됩니다 <xref:System.DateTimeOffset> 를 <xref:System.DateTime> 변환 합니다. 그러나 반환 된 <xref:System.DateTime> 값 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified>다음 예제와 같이 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

즉, 모든 정보에 대 한는 <xref:System.DateTimeOffset> 변환에 의해 손실 되는 값의 관계 UTC로 때는 <xref:System.DateTimeOffset.DateTime%2A> 속성을 사용 합니다. 이 영향을 줍니다 <xref:System.DateTimeOffset> 있기 때문에 시스템의 현지 시간 또는 UTC 시간에 일치 하는 값은 <xref:System.DateTimeOffset.DateTime%2A> 구조에만 이러한 두 표준 시간대에 반영 해당 <xref:System.DateTime.Kind%2A> 속성입니다.

변환 하는 경우 최대한 많은 표준 시간대 정보를 유지 하기 위해는 <xref:System.DateTimeOffset> 에 <xref:System.DateTime> 사용할 수 값을는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 및 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성입니다.

### <a name="converting-a-utc-time"></a>UTC 시간으로 변환

나타내기 위해 변환 된 <xref:System.DateTimeOffset.DateTime%2A> 값은 UTC 시간, 값을 검색할 수 있습니다는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성입니다. 다른는 <xref:System.DateTimeOffset.DateTime%2A> 두 가지 방법으로 속성:

* 반환 된 <xref:System.DateTime> 값 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Utc>합니다.

* 경우는 <xref:System.DateTimeOffset.Offset%2A> 속성 값이 다르면 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, 시간을 UTC로 변환 합니다.

> [!NOTE]
> 응용 프로그램에 필요한 변환 하는 경우 <xref:System.DateTime> 값에에서 단일 시점을 명확 하 게 식별, 사용을 고려해 야는 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 속성을 모두 처리 <xref:System.DateTimeOffset> 를 <xref:System.DateTime> 변환 합니다.

다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 변환 하는 속성을 <xref:System.DateTimeOffset> 오프셋 인 값 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> 에 <xref:System.DateTime> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성에서 표준 시간대 변환 및 형식 변환을 모두 수행 하는 <xref:System.DateTimeOffset> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>현지 시간 변환

나타내기 위해는 <xref:System.DateTimeOffset> 값 현지 시간을 나타내는 전달할 수 있습니다는 <xref:System.DateTime> 에서 반환 된 값은 <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> 속성을는 `static` (`Shared` Visual Basic의) <xref:System.DateTime.SpecifyKind%2A> 메서드. 메서드가 첫 번째 매개 변수로 전달 된 시간과 날짜를 반환 하지만 설정는 <xref:System.DateTime.Kind%2A> 속성을 두 번째 매개 변수에 의해 지정 된 값입니다. 다음 코드에서는 <xref:System.DateTime.SpecifyKind%2A> 변환 하는 경우 메서드는 <xref:System.DateTimeOffset> 해당 오프셋이 현지 표준 시간대에 해당 하는 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

사용할 수도 있습니다는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 변환 하는 속성을 <xref:System.DateTimeOffset> 값을 현지 <xref:System.DateTime> 값입니다. <xref:System.DateTime.Kind%2A> 반환 된 속성 <xref:System.DateTime> 값은 <xref:System.DateTimeKind.Local>합니다. 다음 코드에서는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성 변환 하는 경우는 <xref:System.DateTimeOffset> 해당 오프셋이 현지 표준 시간대의 해당 값입니다. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

검색할 때는 <xref:System.DateTime> 를 사용 하 여 값의 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 속성, 속성의 `get` 접근자 먼저 변환는 <xref:System.DateTimeOffset> 값 UTC로 다음 변환 현지 시간으로 호출 하 여는 <xref:System.DateTimeOffset.ToLocalTime%2A> 메서드. 즉,의 값을 검색할 수는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 형식 변환을 수행 하는 동시에 표준 시간대 변환을 수행 하는 속성입니다. 또한 변환을 수행할 때 현지 표준 시간대의 조정 규칙도 적용됩니다. 다음 코드에서는 사용 된 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 형식과 시간대 변환을 모두 수행 하는 속성입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>범용 변환 메서드

라는 메서드를 정의 하는 다음 예제에서는 `ConvertFromDateTimeOffset` 변환 하 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값입니다. 오프셋에 따라, 결정 여부는 <xref:System.DateTimeOffset> 값은 UTC 시간, 현지 시간 또는 다른 시간에 및 반환 된 날짜 및 시간 값의 정의 <xref:System.DateTime.Kind%2A> 속성 적절 하 게 합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

다음 예제에서는 `ConvertFromDateTimeOffset` 메서드 <xref:System.DateTimeOffset> UTC 시간, 현지 시간 및 미국에는 한 번 표시 하는 값 변환합니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

이 코드에서는 다음 두 가지를 가정합니다. 이러한 가정은 응용 프로그램과 응용 프로그램에서 사용하는 날짜 및 시간 값의 소스에 따라 맞지 않을 수도 있습니다.

* 날짜 및 시간 값 해당 오프셋이 가정 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> UTC를 나타냅니다. 실제로 UTC는 특정 표준 시간대의 시간이 아니라 표준화된 전세계 표준 시간대의 시간입니다. 표준 시간대 오프셋을 가질 수도 있습니다 <xref:System.TimeSpan.Zero>합니다.

* 현지 표준 시간대 오프셋과 동일한 오프셋의 날짜와 시간이 현지 표준 시간대를 나타낸다고 가정합니다. 그러나 날짜 및 시간 값이 원래 표준 시간대와 관련이 없기 때문에 이와 다른 경우가 있을 수 있습니다. 날짜와 시간은 동일한 오프셋을 사용하는 다른 표준 시간대에서 가져올 수 있습니다.

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
