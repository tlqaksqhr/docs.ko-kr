---
title: "방법: 날짜 및 시간 값 라운드트립 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "날짜 및 시간 값 라운드트립"
  - "날짜[.NET Framework], 값 라운드트립"
  - "표준 시간대[.NET Framework], 날짜 및 시간 값 라운드트립"
  - "시간[.NET Framework], 값 라운드트립"
  - "문자열 형식 지정[.NET Framework], 값 라운드트립"
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 날짜 및 시간 값 라운드트립
대부분의 응용 프로그램에서 날짜 및 시간 값은 특정 시점을 명확하게 식별합니다.  이 항목에서는 복원된 값이 저장된 값과 같은 시간을 식별하도록 <xref:System.DateTime> 값, <xref:System.DateTimeOffset> 값 및 날짜\/시간 값을 표준 시간대 정보와 함께 저장 및 복원하는 방법을 보여 줍니다.  
  
### DateTime 값을 라운드트립하려면  
  
1.  "o" 서식 지정자와 함께 <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> 메서드를 호출하여 <xref:System.DateTime> 값을 해당 문자열 표현으로 변환합니다.  
  
2.  <xref:System.DateTime> 값에 대한 문자열 표현을 파일에 저장하거나 프로세스, 응용 프로그램 도메인 또는 시스템 경계로 전달합니다.  
  
3.  <xref:System.DateTime> 값을 나타내는 문자열을 검색합니다.  
  
4.  <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> 메서드를 호출한 다음 <xref:System.Globalization.DateTimeStyles?displayProperty=fullName>를 `styles` 매개 변수의 값으로 전달합니다.  
  
 다음 예제에서는 <xref:System.DateTime> 값을 라운드트립하는 방법을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 이 방법으로 <xref:System.DateTime> 값을 라운드트립하면 모든 현지 시간 및 UTC 시간 값이 유지됩니다.  예를 들어, 로컬 <xref:System.DateTime> 값이 미국 태평양 표준 시간대에 저장되고, 미국 중앙 표준 시간대의 시스템에 저장되면, 그 저장된 날짜와 시간은 원래 시간보다 2시간이 늦고, 이것은 두 시간대의 시간 차이를 보여줍니다.  하지만 지정되지 않은 시간을 이 방법으로 라운드트립하면 결과가 정확하지 않을 수도 있습니다.  <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind>인 <xref:System.DateTime> 값은 모두 현지 시간으로 처리됩니다.  그렇지 않으면 <xref:System.DateTime>이 올바른 시점을 식별하지 못합니다.  이 문제를 해결하려면 날짜 및 시간 값을 해당 표준 시간대와 함께 저장 및 복원합니다.  
  
### DateTimeOffset 값을 라운드트립하려면  
  
1.  "o" 서식 지정자와 함께<xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> 메서드를 호출하여  <xref:System.DateTimeOffset> 값을 해당 문자열 표현으로 변환합니다.  
  
2.  <xref:System.DateTimeOffset> 값에 대한 문자열 표현을 파일에 저장하거나 프로세스, 응용 프로그램 도메인 또는 시스템 경계로 전달합니다.  
  
3.  <xref:System.DateTimeOffset> 값을 나타내는 문자열을 검색합니다.  
  
4.  <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> 메서드를 호출한 다음 <xref:System.Globalization.DateTimeStyles?displayProperty=fullName>를 `styles` 매개 변수의 값으로 전달합니다.  
  
 다음 예제에서는 <xref:System.DateTimeOffset> 값을 라운드트립하는 방법을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 이 방법으로 라운드트립하면 <xref:System.DateTimeOffset> 값이 항상 특정 시점으로 명확하게 식별됩니다.  그런 다음 <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=fullName> 메서드를 호출하여 값을 UTC\(협정 세계시\)로 변환하거나 <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=fullName> 또는 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> 메서드를 호출하여 값을 특정 표준 시간대의 시간으로 변환할 수 있습니다.  이 방법을 사용할 경우 특정 표준 시간대의 시간을 나타내는 <xref:System.DateTimeOffset> 값에 대해 날짜 및 시간 산술 연산을 수행하면 해당 표준 시간대에 대해 정확한 결과가 생성되지 않을 수도 있습니다.  이는 <xref:System.DateTimeOffset> 값이 인스턴스화될 때 해당 표준 시간대에서 분리되기 때문입니다.  따라서 날짜 및 시간을 계산할 때 해당 표준 시간대의 조정 규칙이 더 이상 적용되지 않습니다.  날짜 및 시간 값과 해당 표준 시간대가 모두 포함된 사용자 지정 형식을 정의하면 이 문제를 해결할 수 있습니다.  
  
### 표준 시간대와 함께 날짜 및 시간 값을 라운드트립하려면  
  
1.  두 개의 필드가 있는 클래스나 구조체를 정의합니다.  첫 번째 필드는 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 개체이고 두 번째 필드는 <xref:System.TimeZoneInfo> 개체입니다.  다음 예제는 이 형식의 간단한 버전입니다.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  클래스를 <xref:System.SerializableAttribute> 특성으로 표시합니다.  
  
3.  <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName> 메서드를 사용하여 개체를 serialize합니다.  
  
4.  <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> 메서드를 사용하여 개체를 복원합니다.  
  
5.  deserialize된 개체를 올바른 형식의 개체로 캐스팅하거나\(C\#의 경우\) 변환합니다\(Visual Basic의 경우\).  
  
 다음 예제에서는 날짜 및 시간과 표준 시간대 정보가 모두 저장된 개체를 라운드트립하는 방법을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 이 방법으로 라운드트립하면 저장 및 복원 전후의 정확한 시점이 항상 명확하게 반영됩니다. 단, 날짜 및 시간과 표준 시간대 개체를 조합했을 때 날짜 값이 표준 시간대 값과 항상 동기화되어야 합니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   C\# `using` 문 또는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` 문을 사용하여 다음 네임스페이스를 가져와야 합니다.  
  
    -   <xref:System>\(C\# 전용\)  
  
    -   <xref:System.Globalization?displayProperty=fullName>.  
  
    -   <xref:System.IO?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=fullName>.  
  
-   System.Core.dll에 대해 참조합니다.  
  
-   각 코드 예제는 `DateInTimeZone` 클래스가 아닌 클래스 또는 Visual Basic 모듈에 포함되어야 하고 메서드에 래핑되어야 하며 `Main` 메서드에서 호출되어야 합니다.  
  
## 참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../ocs/standard/datetime/choosing-between-datetime.md)   
 [표준 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)