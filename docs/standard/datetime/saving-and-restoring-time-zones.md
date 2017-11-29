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
ms.openlocfilehash: d4e04de61ed5636d0102af694220dce06c256751
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="saving-and-restoring-time-zones"></a>저장 및 표준 시간대 복원

<xref:System.TimeZoneInfo> 클래스가 미리 정의 된 표준 시간대 데이터를 검색 하도록 레지스트리를 사용 합니다. 그러나 레지스트리는 동적 구조입니다. 또한 레지스트리에 포함 된 표준 시간대 정보는 운영 체제에서 현재 연도 대 한 시간 조정 및 변환을 처리 하는 데 주로 사용 됩니다. 이 표준 시간대를 정확 하 게 데이터를 사용 하는 응용 프로그램에 대 한 두 가지 주요 의미가 같습니다.

* 레지스트리에서 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다 또는 그 수 바뀌었거나 레지스트리에서 제거 합니다.

* 레지스트리에 정의 된 표준 시간대에는 기록 표준 시간대 변환에 필요한 특정 조정 규칙에 대 한 정보가 없을 수 있습니다.

<xref:System.TimeZoneInfo> (저장) serialization 및 deserialization (복원)의 표준 시간대 데이터에 대 한 지원을 통해 이러한 한계를 해결 하는 클래스입니다.

## <a name="time-zone-serialization-and-deserialization"></a>표준 시간대 serialization 및 deserialization

저장 및 직렬화 및 표준 시간대 데이터를 역직렬화 하 여 표준 시간대 복원 두 개의 메서드 호출을 수행 해야 합니다.

* Serialize 할 수 있습니다는 <xref:System.TimeZoneInfo> 해당 개체를 호출 하 여 개체 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드. 메서드 매개 변수를 사용 하 고 표준 시간대 정보를 포함 하는 문자열을 반환 합니다.

* Deserialize 할 수는 <xref:System.TimeZoneInfo> 해당 문자열을 전달 하 여 serialize 된 문자열에서 개체는 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> 메서드.

## <a name="serialization-and-deserialization-scenarios"></a>Serialization 및 deserialization 시나리오

저장 (또는 serialize 할) 수는 <xref:System.TimeZoneInfo> 나중에 사용할 개체를 문자열로 및 복원 하거나 deserialize 하기를 높아지고 유틸리티의 유연성은 <xref:System.TimeZoneInfo> 클래스입니다. 이 섹션에서는 직렬화 및 역직렬화 유용한 지는 경우.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>직렬화 및 응용 프로그램의 표준 시간대 데이터를 역직렬화 합니다.

필요한 경우 serialize 된 표준 시간대는 문자열에서 복원할 수 있습니다. 응용 프로그램에서 레지스트리로부터 검색 표준 시간대의 날짜와 특정 날짜 범위 내에서 시간으로 올바르게 변환 하기 수 없는 경우 이렇게 주어 할 수도 있습니다. 예를 들어 Windows XP 레지스트리에서 표준 시간대 데이터는 일반적으로 Windows Vista 레지스트리에 정의 된 표준 시간대 조정 규칙에 대 한 두 가지 정보를 제공 하는 동안 하나의 조정 규칙을를 지원 합니다. 즉, 있는지 기록 시간 변환 부정확할 수 있습니다. 표준 시간대 데이터의 serialization 및 deserialization에는이 제한 사항은 처리할 수 있습니다.

다음 예제에서는 사용자 지정에서에서 <xref:System.TimeZoneInfo> 미국을 나타내도록 정의 조정 규칙 없이 클래스 동부 표준시 조정에서를 미국에서 일광 절약 시간제의 소개 합니다. 사용자 지정 표준 시간대는 전역 범위를 가진 변수에 serialize 됩니다. 표준 시간대 변환 메서드 `ConvertUtcTime`, 변환할 Coordinated Universal Time (UTC) 시간에 전달 됩니다. 날짜 및 시간 또는 이전 버전 1917에서 발생 하는 경우 사용자 지정 동부 표준시 표준 시간대 serialize 된 문자열에서 복원 하 고 표준 시간대에서 레지스트리로부터 검색을 대체 합니다.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>표준 시간대 예외 처리

레지스트리 동적 구조 이기 때문에 해당 내용을 실수로 또는 의도적으로 수정 하지 않고도 적용 됩니다. 즉, 레지스트리에 정의 되어 있어야 하 고 성공적으로 실행 하도록 응용 프로그램에 필요한 표준 시간대 없을 수 있습니다. 하려면 결과 처리 하지만 선택의 여지가 거의 시간대 serialization 및 deserialization에 대 한 지원 없이 있는 <xref:System.TimeZoneNotFoundException> 응용 프로그램을 종료 하 여 합니다. 그러나 표준 시간대 직렬화 및 역직렬화를 사용 하 여 처리할 수 있습니다는 예기치 않은 <xref:System.TimeZoneNotFoundException> 복원 하 여 직렬화 된 문자열 및 응용 프로그램에서 필요한 표준 시간대는 계속 실행 합니다.

다음 예제에서는 만들고 사용자 지정 중앙 표준 시간대를 serialize 합니다. 그런 다음 레지스트리에서 중앙 표준 시간대를 검색 하려고 합니다. 검색 작업 중 하나를 throw 하는 경우는 <xref:System.TimeZoneNotFoundException> 또는 <xref:System.InvalidTimeZoneException>, 예외 처리기는 표준 시간대를 역직렬화 합니다.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>Serialize 된 문자열을 저장 하 고 필요할 때 복원

앞의 예제에서는 문자열 변수에 표준 시간대 정보를 저장 있으며 필요할 때 복원 됩니다. 그러나 serialize 된 표준 시간대 정보 자체에 저장할 수 외부 파일에 리소스 파일 등의 일부 저장 미디어를 포함 하는 문자열은 응용 프로그램 또는 레지스트리에 포함. (참고 하 여 사용자 지정 표준 시간대에 대 한 정보는 시스템의 표준 시간대 레지스트리 키 외에도 저장 됩니다.)

응용 프로그램 자체에서 표준 시간대 작성 루틴 또한 구분 이런이 방식으로 직렬화 된 표준 시간대 문자열을 저장 합니다. 예를 들어 표준 시간대 작성 루틴 실행을 응용 프로그램에서 사용할 수 있는 기록 표준 시간대 정보를 포함 하는 데이터 파일을 만들 수 합니다. 데이터 파일 일 수 있습니다 다음 응용 프로그램을 함께 설치할 수 열 수 있습니다 및 응용 프로그램에서 필요로 하는 경우 하나 이상의 표준 시간대를 deserialize 할 수 있습니다.

포함된 리소스를 사용 하 여 serialize 된 표준 시간대 데이터를 저장 하는 예제를 보려면 [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.

## <a name="see-also"></a>참고 항목

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
