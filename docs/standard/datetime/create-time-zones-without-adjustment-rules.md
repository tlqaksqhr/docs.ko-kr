---
title: '방법: 조정 규칙 하지 않고 표준 시간대 만들기'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214e3bca811f87f4b8367b459564449d16e7c289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572904"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>방법: 조정 규칙 하지 않고 표준 시간대 만들기

응용 프로그램에 필요한 정확한 표준 시간대 정보가 여러 가지 이유로 특정 시스템에 존재할 수 있습니다.

* 로컬 시스템 레지스트리에서 표준 시간대를 정의 하지 않았습니다.

* 표준 시간대에 대 한 데이터 수정 되거나 레지스트리에서 제거 합니다.

* 표준 시간대 존재 하지만 중요 한 특정 기간에 대 한 표준 시간대 조정에 대 한 정확한 정보를 갖지 않습니다.

이러한 경우에 호출할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 응용 프로그램에 필요한 표준 시간대를 정의 합니다. 조정 규칙을 표준 시간대 만들를이 메서드의 오버 로드를 사용할 수 있습니다. 표준 시간대 일광 절약 시간을 지 원하는 경우에 고정 또는 부동 조정 규칙 중 하나를 사용 하 여 조정을 정의할 수 있습니다. (이러한 용어의 정의에서 "시간대 용어" 섹션을 참조 [시간대 개요](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> 호출 하 여 만든 사용자 지정 표준 시간대는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에 추가 되지 않습니다. 대신,에서 반환 된 개체 참조를 통해서만 액세스할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출 합니다.

이 항목에는 조정 규칙 하지 않고 표준 시간대를 만드는 방법을 보여 줍니다. 표준 시간대 일광 절약 시간 조정 규칙을 지 원하는 참조 하십시오 [하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>조정 규칙 하지 않고 표준 시간대를 만들려면

1. 표준 시간대의 표시 이름을 정의 합니다.

   표시 이름은 시간 표준 시간대 오프셋을 utc (협정 세계시) 괄호로 묶인 및 다음에 하나 또는 도시 또는 표준 시간대에 더 이상의 cou의 표준 시간대를 식별 하는 문자열은 대개 표준 형식을 따릅니다. ntries 또는 표준 시간대의 영역입니다.

2. 표준 시간대의 표준 시간 이름을 정의 합니다. 일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.

3. 다른 표준 시간대의 표준 이름 식별자를 사용 하려는 경우 표준 시간대 식별자를 정의 합니다.

4. 인스턴스화하는 <xref:System.TimeSpan> utc에서 표준 시간대 오프셋을 정의 하는 개체입니다. UTC 보다 늦은 시간 표준 시간대 오프셋은 양수입니다. 시간 표준 시간대의 UTC 보다 이전에 음수 오프셋이 있어야 합니다.

5. 호출 된 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> 새 표준 시간대를 인스턴스화하는 방법입니다.

## <a name="example"></a>예제

다음 예제에서는 모슨, 조정 규칙 없이 남극 대륙에 대 한 사용자 지정 표준 시간대를 정의 합니다.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

에 할당 된 문자열은 <xref:System.TimeZoneInfo.DisplayName%2A> 속성에는 UTC 표준 시간대의 오프셋이 뒤에 표준 시간대에 대 한 간단한 설명과 표준 형식을 따릅니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스 가져와야 합니다.

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
