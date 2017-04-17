---
title: "DateTime과 DateTimeOffset 간 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DateTimeOffset 및 DateTime 값 변환"
  - "시간 변환"
  - "Date 데이터 형식, 변환"
  - "날짜[.NET Framework], 변환"
  - "DateTime 구조체, 변환"
  - "DateTimeOffset 구조체, 변환"
  - "현지 시간 변환"
  - "표준 시간대[.NET Framework], 변환"
  - "UTC 시간, 변환"
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# DateTime과 DateTimeOffset 간 변환
<xref:System.DateTimeOffset> 구조체가 <xref:System.DateTime> 구조체보다 더 높은 표준 시간대 인식 수준을 제공하지만 메서드 호출에서는 <xref:System.DateTime> 매개 변수가 더 일반적으로 사용됩니다.  따라서 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환하거나 그 반대로 변환하는 기능은 매우 중요합니다.  이 항목에서는 표준 시간대 정보를 최대한 많이 보존하는 방식으로 이러한 변환을 수행하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 형식은 둘 다 표준 시간대의 시간을 표시할 때 몇 가지 제한 사항의 적용을 받습니다.  <xref:System.DateTime> 형식은 해당 <xref:System.DateTime.Kind%2A> 속성으로 UTC\(협정 세계시\)와 시스템의 현지 표준 시간대만 반영할 수 있습니다.  <xref:System.DateTimeOffset> 형식은 UTC에서의 시간 오프셋을 반영하지만 오프셋이 속한 실제 표준 시간대를 반영하지 않습니다.  표준 시간대의 시간 값 및 지원에 대한 자세한 내용은 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../docs/standard/datetime/choosing-between-datetime.md)을 참조하십시오.  
  
## DateTime에서 DateTimeOffset으로의 변환  
 <xref:System.DateTimeOffset> 구조체는 <xref:System.DateTime>에서 <xref:System.DateTimeOffset>으로 변환하는 데 사용할 수 있는 다음과 같은 두 가지 동등한 방법을 제공합니다. 이러한 방법은 대부분의 변환에 적합합니다.  
  
-   <xref:System.DateTime> 값을 기반으로 새 <xref:System.DateTimeOffset> 개체를 만드는 <xref:System.DateTimeOffset.%23ctor%2A> 생성자  
  
-   <xref:System.DateTimeOffset> 개체에 <xref:System.DateTime> 값을 할당할 수 있는 암시적 변환 연산자  
  
 UTC 및 현지 <xref:System.DateTime> 값의 경우 결과 <xref:System.DateTimeOffset> 값의 <xref:System.DateTimeOffset.Offset%2A> 속성이 UTC 또는 현지 표준 시간대 오프셋을 정확하게 반영합니다.  예를 들어, 다음 코드에서는 UTC 시간을 해당 <xref:System.DateTimeOffset> 값으로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]  
  
 이 경우 `utcTime2` 변수의 오프셋은 00:00입니다.  마찬가지로 다음 코드에서는 현지 시간을 해당 <xref:System.DateTimeOffset> 값으로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]  
  
 그러나 해당 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>인 <xref:System.DateTime> 값의 경우 이러한 두 변환 메서드를 사용하면 오프셋이 현지 표준 시간대의 오프셋인 <xref:System.DateTimeOffset> 값이 생성됩니다.  미국 태평양 표준 시간대에서의 실행은 다음 예제에서 보여줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]  
  
 <xref:System.DateTime> 값이 현지 표준 시간대 또는 UTC와 다른 날짜 및 시간을 반영하는 경우 이 값을 <xref:System.DateTimeOffset> 값으로 변환하고 오버로드된 <xref:System.DateTimeOffset.%23ctor%2A> 생성자를 호출하여 해당 표준 시간대 정보를 보존할 수 있습니다.  예를 들어, 다음 예제에서는 중부 표준시를 반영하는 <xref:System.DateTimeOffset> 개체를 인스턴스화합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]  
  
 UTC에서의 시간 오프셋을 나타내는 이 생성자 오버로드에 대한 두 번째 매개 변수인 <xref:System.TimeSpan> 개체는 해당 시간이 속한 표준 시간대의 <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=fullName> 메서드를 호출하여 검색해야 합니다.  이 메서드의 단일 매개 변수는 변환할 날짜와 시간을 나타내는 <xref:System.DateTime> 값입니다.  표준 시간대가 일광 절약 시간을 지원하는 경우 이 매개 변수는 해당 메서드가 특정 날짜와 시간에 대한 적절한 오프셋을 결정할 수 있도록 합니다.  
  
## DateTimeOffset에서 DateTime으로의 변환  
 <xref:System.DateTimeOffset.DateTime%2A> 속성은 <xref:System.DateTimeOffset>을 <xref:System.DateTime>으로 변환하는 작업에 가장 일반적으로 사용되지만  다음 예제와 같이 해당 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind>인 <xref:System.DateTime> 값을 반환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]  
  
 즉, <xref:System.DateTimeOffset.DateTime%2A> 속성이 사용될 때 변환 작업을 수행하면 UTC와 <xref:System.DateTimeOffset> 값의 관계에 대한 모든 정보가 손실됩니다.  이것은 <xref:System.DateTimeOffset.DateTime%2A> 구조체가 해당 <xref:System.DateTime.Kind%2A> 속성에 있는 두 개의 표준 시간대만 반영하므로 UTC 시간이나 시스템의 현지 시간에 해당하는 <xref:System.DateTimeOffset> 값에 영향을 줍니다.  
  
 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환할 때 표준 시간대 정보를 최대한 많이 보존하려면 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> 및 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> 속성을 사용하면 됩니다.  
  
### UTC 시간 변환  
 변환된 <xref:System.DateTimeOffset.DateTime%2A> 값이 UTC 시간임을 나타내려면 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> 속성의 값을 검색하면 됩니다.  이 속성은 다음과 같은 두 가지가 <xref:System.DateTimeOffset.DateTime%2A> 속성과 다릅니다.  
  
-   해당 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind>인 <xref:System.DateTime> 값을 반환합니다.  
  
-   <xref:System.DateTimeOffset.Offset%2A> 속성 값이 <xref:System.TimeSpan.Zero?displayProperty=fullName>가 아닐 경우 시간을 UTC로 변환합니다.  
  
> [!NOTE]
>  응용 프로그램에서 변환된 <xref:System.DateTime> 값이 특정 시간을 명확하게 식별해야 하는 경우 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> 속성을 사용하여 <xref:System.DateTimeOffset>에서 <xref:System.DateTime>으로의 변환을 모두 처리할 수 있습니다.  
  
 다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성을 사용하여 해당 오프셋이 <xref:System.TimeSpan.Zero?displayProperty=fullName> 인 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]  
  
 다음 코드에서는 <xref:System.DateTimeOffset.UtcDateTime%2A> 속성을 사용하여 <xref:System.DateTimeOffset> 값에 대한 표준 시간대 변환과 형식 변환을 둘 다 수행합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]  
  
### 현지 시간 변환  
 <xref:System.DateTimeOffset> 값이 현지 시간임을 나타내려면  <xref:System.DateTimeOffset.DateTime%2A?displayProperty=fullName> 속성에서 반환한 <xref:System.DateTime> 값 `static`\(Visual Basic에서는 `Shared` \) 을 <xref:System.DateTime.SpecifyKind%2A> 메서드에 전달하면 됩니다.  이 메서드는 전달받은 날짜와 시간을 첫 번째 매개 변수로 반환하지만 <xref:System.DateTime.Kind%2A> 속성을 두 번째 매개 변수에 지정된 값으로 설정합니다.  다음 코드에서는 해당 오프셋이 현지 표준 시간대의 오프셋인 <xref:System.DateTimeOffset> 값을 변환할 때 <xref:System.DateTime.SpecifyKind%2A> 메서드를 사용합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]  
  
 또한 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> 속성을 사용하여 <xref:System.DateTimeOffset> 값을 현지 <xref:System.DateTime> 값으로 변환할 수도 있습니다.  반환된 <xref:System.DateTime> 값의 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind>입니다.  다음 코드에서는 해당 오프셋이 현지 표준 시간대의 오프셋인 <xref:System.DateTimeOffset> 값을 변환할 때 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> 속성을 사용합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]  
  
 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>속성을 사용하여 <xref:System.DateTime> 값을 검색하면 먼저 해당 속성의 `get` 접근자가 <xref:System.DateTimeOffset> 값을 UTC로 변환한 다음 <xref:System.DateTimeOffset.ToLocalTime%2A> 메서드를 호출하여 UTC를 현지 시간으로 변환합니다.  즉, 형식 변환을 수행하는 동시에 표준 시간대 변환을 수행하기 위해 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> 속성의 값을 검색할 수 있습니다.  또한 변환을 수행할 때 현지 표준 시간대의 조정 규칙이 적용됩니다.  다음 코드에서는 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> 속성을 사용하여 형식 변환과 표준 시간대 변환을 둘 다 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]  
  
### 일반적인 용도의 변환 메서드  
 다음 예제에서는 <xref:System.DateTimeOffset> 값을 <xref:System.DateTime> 값으로 변환하는 `ConvertFromDateTimeOffset`이라는 메서드를 정의합니다.  이 메서드는 해당 오프셋을 기반으로 <xref:System.DateTimeOffset> 값이 UTC 시간, 현지 시간 또는 다른 시간대 중 무엇인지 결정하고 반환된 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A> 속성을 이에 따라 정의합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]  
  
 다음 예제는 `ConvertFromDateTimeOffset` 메서드를 불러 미국 중부 표준시의 시간, UTC 시간, 지역 시간을 나타내는 <xref:System.DateTimeOffset> 값으로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]  
  
 이 코드에서는 다음과 같은 두 가지를 가정합니다. 이러한 가정은 응용 프로그램과 응용 프로그램에서 사용하는 날짜 및 시간 값의 소스에 따라 틀릴 수도 있습니다.  
  
-   해당 오프셋이 <xref:System.TimeSpan.Zero?displayProperty=fullName>인 날짜 및 시간 값이 UTC를 나타낸다고 가정합니다.  사실상 UTC는 특정 표준 시간대의 시간이 아니라 전 세계 표준 시간대의 표준 시간입니다.  표준 시간대에는 <xref:System.TimeSpan.Zero>의 오프셋이 있을 수도 있습니다.  
  
-   해당 오프셋이 현지 표준 시간대의 오프셋인 날짜와 시간이 현지 표준 시간대를 나타낸다고 가정합니다.  그러나 날짜 및 시간 값이 원래 표준 시간대와 관련이 없기 때문에 이와 다른 경우가 있을 수 있습니다. 날짜와 시간은 같은 오프셋을 사용하는 다른 표준 시간대에서 시작될 수 있습니다.  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)