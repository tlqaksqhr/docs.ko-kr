---
title: "방법: 날짜 및 시간 값 라운드트립"
ms.custom: 
ms.date: 03/30/2017
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
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a>방법: 날짜 및 시간 값 라운드트립
많은 응용 프로그램에서 날짜 및 시간 값은 단일 시점을 명확하게 식별하는 데 사용됩니다. 이 항목에서는 저장 하 고 복원 하는 방법을 보여 줍니다.는 <xref:System.DateTime> 값은 <xref:System.DateTimeOffset> 값 및 시간을 사용 하 여 날짜 및 시간 값을 표준 시간대 정보와 하 여 저장된 된 값과 같은 시간을 식별 하는 복원 된 값입니다.  
  
### <a name="to-round-trip-a-datetime-value"></a>DateTime 값을 라운드트립하려면  
  
1.  변환에서 <xref:System.DateTime> 값을 호출 하 여 해당 문자열 표현에서 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> "o" 서식 지정자를 사용 하 여 메서드.  
  
2.  문자열 표현을 저장는 <xref:System.DateTime> 파일에 값 또는 프로세스, 응용 프로그램 도메인 또는 컴퓨터 경계 너머로 전달 합니다.  
  
3.  나타내는 문자열을 검색 된 <xref:System.DateTime> 값입니다.  
  
4.  호출 된 <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> 메서드와 패스 <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> 의 값으로는 `styles` 매개 변수입니다.  
  
 다음 예제에서는 라운드트립 하는 방법을 <xref:System.DateTime> 값입니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 때 라운드트립은 <xref:System.DateTime> 값,이 기술을 현지 및 범용 모든 시간에 대 한 시간 성공적으로 유지 합니다. 예를 들어 로컬 <xref:System.DateTime> 값이은 미국 영어 시스템에 저장 됩니다. 태평양 표준 시간대는 미국에 있는 시스템에서 복원됩니다. 중앙 표준 시간대인 복원된 날짜 및 시간은 원래 시간보다 2시간이 늦어지며 이것은 두 표준 시간대 사이의 시간 차이를 반영합니다. 그러나 이 기술은 지정되지 않은 시간에 대해 반드시 정확하지는 않습니다. 모든 <xref:System.DateTime> 값을 갖는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified> 는 현지 시간으로 간주 됩니다. 이 경우, 아닌 경우는 <xref:System.DateTime> 성공적으로 올바른 시점 시간으로 식별 하지 것입니다. 이 제한에 대한 해결책은 저장 및 복원 작업의 표준 시간대와 날짜 및 시간 값을 밀접하게 연결하는 것입니다.  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>DateTimeOffset 값을 라운드트립하려면  
  
1.  변환에서 <xref:System.DateTimeOffset> 값을 호출 하 여 해당 문자열 표현에서 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> "o" 서식 지정자를 사용 하 여 메서드.  
  
2.  문자열 표현을 저장는 <xref:System.DateTimeOffset> 파일에 값 또는 프로세스, 응용 프로그램 도메인 또는 컴퓨터 경계 너머로 전달 합니다.  
  
3.  나타내는 문자열을 검색 된 <xref:System.DateTimeOffset> 값입니다.  
  
4.  호출 된 <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> 메서드와 패스 <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> 의 값으로는 `styles` 매개 변수입니다.  
  
 다음 예제에서는 라운드트립 하는 방법을 <xref:System.DateTimeOffset> 값입니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 이 기술은 항상 명확 하 게 식별 하는 <xref:System.DateTimeOffset> 단일 지정 시간으로 값입니다. 값 다음 변환 될 수 utc (협정 세계시)로 호출 하 여는 <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> 호출 하 여 메서드 또는 것을 특정 표준 시간대의 시간으로 변환 수는 <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> 또는 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 메서드. 이 방법의 주요 제한 사항은 해당 날짜 및 시간 산술 연산을 수행 하는 경우는 <xref:System.DateTimeOffset> 특정 표준 시간대의 시간을 나타내는 값 해당 표준 시간대에 대 한 정확한 결과 생성 하지 않을 수 있습니다. 즉 때는 <xref:System.DateTimeOffset> 값 인스턴스화될, 표준 시간대에서 분리 합니다. 따라서 날짜 및 시간 계산을 수행할 경우에 해당 표준 시간대의 조정 규칙은 더 이상 적용될 수 없습니다. 날짜 및 시간 값과 동반되는 표준 시간대를 포함하는 사용자 지정 형식을 정의하여 이 문제를 해결할 수 있습니다.  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>에 해당 표준 시간대를 사용 하 여 날짜 및 시간 값 라운드트립  
  
1.  클래스 또는 구조에 두 필드를 정의 합니다. 첫 번째 필드는 한 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 개체 및 두 번째는는 <xref:System.TimeZoneInfo> 개체입니다. 다음 예제에서는 이러한 형식의 단순 버전이 있습니다.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  고 클래스는 <xref:System.SerializableAttribute> 특성입니다.  
  
3.  사용 하 여 개체를 직렬화는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> 메서드.  
  
4.  사용 하 여 개체 복원의 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> 메서드.  
  
5.  캐스팅 (C#) 하거나 변환 (Visual Basic)의 deserialize 된 개체는 적절 한 형식의 개체 합니다.  
  
 다음 예제에서는 어떻게 날짜 및 시간, 표준 시간대 정보 저장 라운드트립 개체를 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 이 방법 항상 명확 하 게 반영는 올바른 둘 다를 저장 하 고 복원한 후 제공 되는 시간 결합 된 날짜 및 시간과 표준 시간대 개체의 구현와 동기화 날짜 값을 허용 하지 않습니다는 표준 시간대 값입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이러한 예제에는 다음이 필요합니다.  
  
-   다음 네임 스페이스는 C#으로 가져올 수 `using` 문 또는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` 문:  
  
    -   <xref:System>(C#에 해당)입니다.  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>.  
  
    -   <xref:System.IO?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.  
  
-   System.Core.dll에 대 한 참조입니다.  
  
-   이외의 각 코드 예제는 `DateInTimeZone` 클래스, 클래스 또는 Visual Basic 모듈에 포함 된, 메서드에 래핑되어야 하 고 해야에서 호출 된 `Main` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
