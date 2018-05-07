---
title: '방법: 조정 규칙에 표준 시간대 만들기'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c63b93e0dc587571605edb305979b8f97bf54cb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>방법: 조정 규칙에 표준 시간대 만들기

응용 프로그램에 필요한 정확한 표준 시간대 정보가 여러 가지 이유로 특정 시스템에 존재할 수 있습니다.

* 로컬 시스템 레지스트리에서 표준 시간대를 정의 하지 않았습니다.

* 표준 시간대에 대 한 데이터 수정 되거나 레지스트리에서 제거 합니다.

* 표준 시간대는 중요 한 특정 기간에 대 한 표준 시간대 조정에 대 한 정확한 정보는 없습니다.

이러한 경우에 호출할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 응용 프로그램에 필요한 표준 시간대를 정의 합니다. 조정 규칙을 표준 시간대 만들를이 메서드의 오버 로드를 사용할 수 있습니다. 표준 시간대 일광 절약 시간을 지 원하는 경우에 고정 또는 부동 조정 규칙 중 하나를 사용 하 여 조정을 정의할 수 있습니다. (이러한 용어의 정의에서 "시간대 용어" 섹션을 참조 [시간대 개요](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> 호출 하 여 만든 사용자 지정 표준 시간대는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에 추가 되지 않습니다. 대신,에서 반환 된 개체 참조를 통해서만 액세스할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출 합니다.

이 항목에서는 표준 시간대 조정 규칙을 만드는 방법을 보여 줍니다. 일광 절약 시간 조정 규칙을 지원 하지 않는 시간대를 만들려면 참조 [하는 방법: 조정 규칙 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)합니다.

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>조정 규칙 부동 된 표준 시간대를 만들려면

1. (즉에서 각 전환에 대 한 및 특정 시간 간격에 대해 표준 시간으로 다시) 각 조정에 대해 다음을 수행 합니다.

    1. 표준 시간대 조정에 대 한 시작 전환 시간을 정의 합니다.

       호출 해야 합니다는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 메서드 전달는 <xref:System.DateTime> 전환, 전환의 월을 정의 하는 정수 값, 전환이 발생 주를 정의 하는 정수 값의 시간을 정의 하는 값 및 <xref:System.DayOfWeek> 전환을 수행할 요일을 정의 하는 값입니다. 이 메서드 호출에서 인스턴스화하는 <xref:System.TimeZoneInfo.TransitionTime> 개체입니다.

    2. 표준 시간대 조정에 대 한 끝 전환 시간을 정의 합니다. 이것은 다른 호출에는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 메서드. 이 메서드 호출은 두 번째 인스턴스화합니다 <xref:System.TimeZoneInfo.TransitionTime> 개체입니다.

    3. 호출 된 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 메서드 유효한 시작 및 종료 날짜를 조정, 전달 및는 <xref:System.TimeSpan> 전환 하며, 두에 시간을 정의 하는 개체 <xref:System.TimeZoneInfo.TransitionTime> 시기를 정의 하는 개체와 일광 절약 시간제 전환을 시간에 발생 합니다. 이 메서드 호출에서 인스턴스화하는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다.

    4. 할당 된 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열로 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다.

2. 표준 시간대의 표시 이름을 정의 합니다. 표시 이름은 시간 표준 시간대 오프셋을 utc (협정 세계시) 괄호로 묶인 및 다음에 하나 또는 도시 또는 표준 시간대에 더 이상의 cou의 표준 시간대를 식별 하는 문자열은 대개 표준 형식을 따릅니다. ntries 또는 표준 시간대의 영역입니다.

3. 표준 시간대의 표준 시간 이름을 정의 합니다. 일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.

4. 표준 시간대의 일광 절약 시간제의 이름을 정의 합니다.

5. 다른 표준 시간대의 표준 이름 식별자를 사용 하려는 경우 표준 시간대 식별자를 정의 합니다.

6. 인스턴스화하는 <xref:System.TimeSpan> utc에서 표준 시간대 오프셋을 정의 하는 개체입니다. UTC 보다 늦은 시간 표준 시간대 오프셋은 양수입니다. 시간 표준 시간대의 UTC 보다 이전에 음수 오프셋이 있어야 합니다.

7. 호출 된 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 새 표준 시간대를 인스턴스화하는 방법입니다.

## <a name="example"></a>예제

다음 예제에서는 다양 한 현재 1918에서 시간 간격에 대 한 조정 규칙을 포함 하는 United States에 대 한 중앙 표준 시간대를 정의 합니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

이 예제에서 만든 표준 시간대에 여러 조정 규칙이 있습니다. 유효한 시작 및 종료 날짜 조정 규칙의 다른 조정 규칙의 날짜와 겹치지 않는 되도록 주의 해야 합니다. 겹치는 경우는 <xref:System.InvalidTimeZoneException> throw 됩니다.

조정 규칙이 부동 값 5는 형식에 전달는 `week` 의 매개 변수는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드 달의 지난 주에 전환이 발생 함을 나타냅니다.

배열을 만드는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체에서 사용 하는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 메서드 호출 코드에 표준 시간대에 대해 생성 될 조정의 수에 필요한 크기를 해당 배열을 초기화할 수 있습니다. 이 코드 예제에서는 호출 하는 대신,는 <xref:System.Collections.Generic.List%601.Add%2A> 메서드를 제네릭 각 조정 규칙 <xref:System.Collections.Generic.List%601> 의 컬렉션 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다. 호출에서 <xref:System.Collections.Generic.List%601.CopyTo%2A> 메서드를이 컬렉션의 멤버를 배열에 복사 합니다.

또한이 예제에서는 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 고정 날짜 조정을 정의 하는 메서드. 이 호출 비슷합니다는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드, 시간, 월 및 일의 전환 매개 변수 필요 하다는 점을 제외 하 고 있습니다.

이 예제는 다음과 같은 코드를 사용 하 여 테스트할 수 있습니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스 가져와야 합니다.

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 조정 규칙 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
