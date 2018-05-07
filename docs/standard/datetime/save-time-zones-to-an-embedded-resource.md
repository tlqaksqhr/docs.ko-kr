---
title: '방법: 포함 된 표준 시간대 저장'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dd7e6db78b76d737cb4646c2fad79d96fb60aee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>방법: 포함 된 표준 시간대 저장

종종 표준 시간대 인식 응용 프로그램 특정 표준 시간대가 있어야 합니다. 그러나 때문에 개별 가용성 <xref:System.TimeZoneInfo> 로컬 시스템의 레지스트리에 저장 된 정보에 종속 된 개체, 관례적도 사용할 수 있는 표준 시간대는 없을 수 있습니다. 또한 사용자 지정 표준 시간대에 대 한 정보를 사용 하 여 인스턴스화할는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드 레지스트리의 다른 표준 시간대 정보가 저장 되지 않습니다. 을 보장 하기 위해 필요할 때 이러한 표준 시간대를 사용할 수 있는지를 직렬화 하 여 저장할 수 있으며 나중에 역직렬화 하 여 복원할 키를 누릅니다.

일반적으로 직렬화는 <xref:System.TimeZoneInfo> 개체가 표준 시간대 인식 응용 프로그램 외에도 발생 합니다. Serialize 된 보관 하는 데 데이터 저장소에 따라 <xref:System.TimeZoneInfo> 개체 (예: 데이터 응용 프로그램 레지스트리 키에 저장 될 때), 설치 과정의 일환으로 또는 실행 되는 유틸리티 루틴의 일환으로 표준 시간대 데이터를 serialize 할 수 하기 전에 (예를 들어, serialize 된 데이터 저장 된 경우에.NET XML 리소스 (.resx) 파일)은 최종 응용 프로그램과 컴파일합니다.

응용 프로그램으로 컴파일된 리소스 파일 외에 표준 시간대 정보에 대 한 몇 가지 다른 데이터 저장소를 사용할 수 있습니다. 이러한 요구 사항은 다음과 같습니다.

* 레지스트리 합니다. HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time 영역의 하위 키를 사용 하는 것이 아니라 사용자 지정 표준 시간대 데이터를 저장 하는 응용 프로그램 자체 응용 프로그램 키의 하위 키를 사용 해야 함을 note 합니다.

* 구성 파일입니다.

* 다른 시스템 파일입니다.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>.Resx 파일에 직렬화 하 여 표준 시간대를 저장 하려면

1. 새 표준 시간대를 만들거나 기존 표준 시간대를 검색 합니다.

   기존 표준 시간대를 검색 하려면 참조 [하는 방법: 미리 정의 된 UTC와 현지 표준 시간대 개체 액세스](../../../docs/standard/datetime/access-utc-and-local.md) 및 [하는 방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)합니다.

   새 표준 시간대를 만들려면 오버 로드 중 하나를 호출는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드. 자세한 내용은 참조 [하는 방법: 조정 규칙 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [하는 방법: 조정 규칙에 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.

2. 호출 된 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드 표준 시간대의 데이터를 포함 하는 문자열을 만듭니다.

3. 인스턴스화하는 <xref:System.IO.StreamWriter> 개체의 이름 및 필요에 따라.resx 파일의 경로 제공 하는 <xref:System.IO.StreamWriter> 클래스 생성자입니다.

4. 인스턴스화하는 <xref:System.Resources.ResXResourceWriter> 전달 하 여 개체는 <xref:System.IO.StreamWriter> 개체를 <xref:System.Resources.ResXResourceWriter> 클래스 생성자입니다.

5. 패스에서 표준 시간대의 문자열을 직렬화는 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> 메서드.

6. <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드를 호출합니다.

7. <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 메서드를 호출합니다.

8. 닫기는 <xref:System.IO.StreamWriter> 개체를 호출 하 여 해당 <xref:System.IO.StreamWriter.Close%2A> 메서드.

9. 응용 프로그램의 Visual Studio 프로젝트에 생성 된.resx 파일을 추가 합니다.

10. 사용 하는 **속성** Visual Studio 창에 표시 되도록.resx 파일의 **빌드 작업** 속성이로 설정 되어 **포함 리소스**합니다.

## <a name="example"></a>예제

다음 예제에서는 serialize 한 <xref:System.TimeZoneInfo> 중부 표준시를 나타내는 개체와 <xref:System.TimeZoneInfo> SerializedTimeZones.resx 라고 하는.NET XML 리소스 파일에 Palmer 스테이션, 남극 대륙 시간을 나타내는 개체입니다. 레지스트리에; 중부 표준시 정의 일반적으로 Palmer 스테이션 남극 대륙 사용자 지정 표준 시간대입니다.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

이 예제에서는 serialize <xref:System.TimeZoneInfo> 있습니다 사용할 수 있도록 리소스 파일에 컴파일 타임에 개체입니다.

때문에 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드는.NET XML 리소스 파일에 전체 헤더 정보를 추가, 기존 파일에 리소스를 추가 하는 데 사용 될 수 없습니다. 예제 SerializedTimeZones.resx 파일을 확인 하 여이 처리 하 고 있는 경우 모든 리소스가 아닌 다른 저장 두 직렬화 된 표준 시간대를 제네릭 <xref:System.Collections.Generic.Dictionary%602> 개체입니다. 기존 파일은 삭제 되 고 기존 리소스 새 SerializedTimeZones.resx 파일에 추가 됩니다. Serialize 된 표준 시간대 데이터는이 파일에도 추가 됩니다.

키 (또는 **이름**) 리소스의 필드에 포함 된 공백이 없어야 합니다. <xref:System.String.Replace%28System.String%2CSystem.String%29> 메서드를 호출 하는 리소스 파일에 할당 되기 전에 표준 시간대 식별자에 포함 된 모든 공백을 제거 합니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Windows.Forms.dll 및 System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스 가져와야 합니다.

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
