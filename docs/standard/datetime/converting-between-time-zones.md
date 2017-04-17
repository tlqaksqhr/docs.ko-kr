---
title: "표준 시간대 간에 시간 변환 | Microsoft Docs"
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
  - "시간 변환"
  - "현지 시간 변환"
  - "표준 시간대[.NET Framework], 변환"
  - "시간[.NET Framework], 변환"
  - "UTC 시간, 변환"
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# 표준 시간대 간에 시간 변환
날짜 및 시간을 사용하여 작업하는 응용 프로그램에서 표준 시간대 간의 차이를 처리하는 것이 더욱 중요해지고 있습니다.  응용 프로그램에서는 더 이상 <xref:System.DateTime> 구조체를 통해 얻을 수 있는 시간인 현지 시간으로 모든 시간을 표시할 수 있다고 가정할 수 없습니다.  예를 들어 미국 동부 지역의 현재 시간을 표시하는 웹 페이지는 동아시아의 고객에게는 신뢰성이 떨어집니다.  이 항목에서는 한 표준 시간대에서 다른 표준 시간대로 변환하는 방법 및 표준 시간대 인식 수준이 제한된 <xref:System.DateTimeOffset> 값을 변환하는 방법에 대해 설명합니다.  
  
## 협정 세계시로 변환  
 UTC\(협정 세계시\)는 고정밀도 원자 시간 표준입니다.  전 세계의 표준 시간대는 UTC에서의 양 또는 음의 오프셋으로 표시됩니다.  따라서 UTC는 어느 정도 표준 시간대에서 자유롭거나 표준 시간대에 대해 중립적인 시간을 제공합니다.  컴퓨터 간에 날짜 및 시간의 이식성이 중요한 경우 UTC 시간을 사용하는 것이 좋습니다. 날짜 및 시간 사용에 대한 자세한 내용 및 기타 유용한 정보는 [Coding Best Practices Using DateTime in the .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342) 를 참조하십시오. 개별 표준 시간대를 UTC로 변환하면 보다 쉽게 시간을 비교할 수 있습니다.  
  
> [!NOTE]
>  또한 <xref:System.DateTimeOffset> 구조체를 serialize하여 단일 시점을 명확하게 나타낼 수 있습니다.  <xref:System.DateTimeOffset> 개체에서는 날짜 및 시간 값과 UTC에서의 오프셋을 함께 저장하므로 항상 UTC를 기준으로 특정 시점을 나타냅니다.  
  
 시간을 UTC로 변환하는 가장 쉬운 방법은 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> 메서드를 호출하는 것입니다.  이 메서드에서 수행되는 정확한 변환은 다음 표와 같이 `dateTime` 매개 변수의 <xref:System.DateTime.Kind%2A> 속성 값에 따라 다릅니다.  
  
|DateTime.Kind 속성|변환|  
|----------------------|--------|  
|<xref:System.DateTimeKind?displayProperty=fullName>|현지 시간을 UTC로 변환합니다.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|`dateTime` 매개 변수가 현지 시간인 것으로 가정하고 현지 시간을 UTC로 변환합니다.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|`dateTime` 매개 변수를 변경하지 않고 반환합니다.|  
  
 다음 코드에서는 현재 현지 시간을 UTC로 변환하고 결과를 콘솔에 표시합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
 [!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]  
  
> [!NOTE]
>  <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> 메서드의 결과가 <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=fullName> 및 <xref:System.DateTime.ToUniversalTime%2A?displayProperty=fullName> 메서드와 다를 수도 있습니다.  호스트 시스템의 현지 표준 시간대에 여러 조정 규칙이 포함된 경우 , <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName>는 특정 날짜 및 시간에 적절한 규칙을 적용합니다.  다른 두 메서드는 항상 최신 조정 규칙을 적용합니다.  
  
 날짜 및 시간 값이 현지 시간이나 UTC를 나타내지 않는 경우 <xref:System.DateTime.ToUniversalTime%2A> 메서드에서 잘못된 결과가 반환될 수 있습니다.  그러나 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> 메서드를 사용하여 지정된 표준 시간대의 날짜 및 시간을 변환할 수 있습니다. 대상 표준 시간대를 나타내는 <xref:System.TimeZoneInfo> 개체를 검색하는 방법에 대한 자세한 내용은 [로컬 시스템에 정의된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)를 참조하십시오. 다음 코드에서는 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> 메서드를 사용하여 동부 표준시를 UTC로 변환합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
 [!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]  
  
 <xref:System.DateTime> 개체의 <xref:System.DateTime.Kind%2A> 속성과 표준 시간대가 일치하지 않는 경우 이 메서드에서는 <xref:System.ArgumentException>을 throw합니다.  <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>이지만 <xref:System.TimeZoneInfo> 개체가 현지 표준 시간대를 나타내지 않는 경우 또는 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>이지만 <xref:System.TimeZoneInfo> 개체가 <xref:System.DateTimeKind?displayProperty=fullName>와 같지 않은 경우에 불일치가 발생합니다.  
  
 이러한 모든 메서드에서는 <xref:System.DateTime> 값을 매개 변수로 사용하고 <xref:System.DateTime> 값을 반환합니다.  <xref:System.DateTimeOffset> 값의 경우 <xref:System.DateTimeOffset> 구조체에 현재 인스턴스의 날짜 및 시간을 UTC로 변환하는 <xref:System.DateTimeOffset.ToUniversalTime%2A> 인스턴스 메서드가 있습니다.  다음 예제에서는 <xref:System.DateTimeOffset.ToUniversalTime%2A> 메서드를 호출하여 현지 시간과 여러 다른 시간을 UTC\(협정 세계시\)로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
 [!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]  
  
## UTC를 지정한 표준 시간대로 변환  
 UTC를 현지 시간으로 변환하려면 다음에 나오는 "UTC를 현지 시간으로 변환" 단원을 참조하십시오.  UTC를 사용자가 지정하는 표준 시간대의 시간으로 변환하려면 <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> 메서드를 호출합니다.  이 메서드에서는 다음과 같이 두 개의 매개 변수를 사용합니다.  
  
-   변환할 UTC.  <xref:System.DateTime> 값이어야 합니다. 이 값은 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName> 또는 <xref:System.DateTimeKind?displayProperty=fullName> 로 설정됩니다.  
  
-   UTC를 변환할 표준 시간대  
  
 다음 코드에서는 UTC를 중부 표준시로 변환합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
 [!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]  
  
## UTC를 현지 시간으로 변환  
 UTC를 현지 시간으로 변환하려면 시간을 변환할 <xref:System.DateTime> 개체의 <xref:System.DateTime.ToLocalTime%2A> 메서드를 호출합니다.  이 메서드의 정확한 동작은 다음 표에서 보여 주는 것처럼 개체의 <xref:System.DateTime.Kind%2A> 속성 값에 따라 다릅니다.  
  
|`DateTime.Kind` 속성|변환|  
|------------------------|--------|  
|`DateTimeKind.Local`|<xref:System.DateTime> 값을 변경하지 않고 반환합니다.|  
|`DateTimeKind.Unspecified`|<xref:System.DateTime> 값이 UTC인 것으로 가정하고 UTC를 현지 시간으로 변환합니다.|  
|`DateTimeKind.Utc`|<xref:System.DateTime> 값을 현지 시간으로 변환합니다.|  
  
 **참고** <xref:System.TimeZone.ToLocalTime%2A?displayProperty=fullName> 메서드는 `DateTime.ToLocalTime` 메서드와 똑같이 동작합니다.  이 메서드는 변환할 날짜 및 시간 값이라는 한 개의 매개 변수를 사용합니다.  
  
 또한 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=fullName> 메서드를 사용하여 지정한 표준 시간대의 시간을 현지 시간으로 변환할 수 있습니다.  이 방법에 대해서는 다음 단원에서 설명합니다.  
  
## 두 표준 시간대 간에 변환  
 <xref:System.TimeZoneInfo> 클래스의 다음 두 `static`\(Visual Basic의 경우 `Shared`\) 메서드 중 하나를 사용하여 두 표준 시간대 간에 변환할 수 있습니다.  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>  
  
     이 메서드의 매개 변수는 변환할 날짜 및 시간 값, 이 날짜 및 시간 값의 표준 시간대를 나타내는 `TimeZoneInfo` 개체, 날짜 및 시간 값을 변환할 표준 시간대를 나타내는 `TimeZoneInfo` 개체입니다.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>  
  
     이 메서드의 매개 변수는 변환할 날짜 및 시간 값, 이 날짜 및 시간 값의 표준 시간대에 대한 식별자, 날짜 및 시간 값을 변환할 표준 시간대에 대한 식별자입니다.  
  
 두 메서드의 경우 변환할 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A> 속성과 표준 시간대를 나타내는 <xref:System.TimeZoneInfo> 개체 또는 표준 시간대 식별자가 각 메서드에 해당해야 합니다.  그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.  예를 들어 날짜 및 시간 값의 `Kind` 속성이 `DateTimeKind.Local`이면 메서드에 매개 변수로 전달된 `TimeZoneInfo` 개체가 `TimeZoneInfo.Local`과 같지 않은 경우 예외가 throw됩니다.  메서드에 매개 변수로 전달된 식별자가 `TimeZoneInfo.Local.Id`와 같지 않은 경우에도 예외가 throw됩니다.  
  
 다음 예제에서는 <xref:System.TimeZoneInfo.ConvertTime%2A> 메서드를 사용하여 하와이 표준시를 현지 시간으로 변환합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
 [!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]  
  
## DateTimeOffset 값 변환  
 <xref:System.DateTimeOffset>개체는 인스턴스화될 때 표준 시간대에서 분리되므로 이 개체로 나타낸 날짜 및 시간 값이 표준 시간대를 완전하게 인식하지 않습니다.  그러나 많은 경우 응용 프로그램에서는 특정 표준 시간대의 시간을 기준으로 하지 않고 단순히 UTC에서의 서로 다른 두 개의 오프셋을 기준으로 날짜 및 시간을 변환하면 됩니다.  이러한 변환을 수행하려면 현재 인스턴스의 <xref:System.DateTimeOffset.ToOffset%2A> 메서드를 호출합니다.  이 메서드의 단일 매개 변수는 메서드에서 반환할 새 날짜 및 시간 값의 오프셋입니다.  
  
 예를 들어 웹 페이지에 대한 사용자 요청의 날짜 및 시간을 알고 있고 이 값이 MM\/dd\/yyyy hh:mm:ss zzzz 형식의 문자열로 serialize된 경우 다음 `ReturnTimeOnServer` 메서드에서는 이 날짜 및 시간 값을 웹 서버의 날짜 및 시간으로 변환합니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]  
  
 UTC보다 다섯 시간 이른 표준 시간대의 날짜 및 시간을 나타내는 문자열 "9\/1\/2007 5:32:07 \-05:00"이 메서드에 전달되는 경우 이 메서드에서는 미국 태평양 표준 시간대에 있는 서버에 대해 9\/1\/2007 3:32:07 AM \-07:00을 반환합니다.  
  
 <xref:System.TimeZoneInfo> 클래스는 또한 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> 메서드의 오버로드를 포함합니다. 이 메서드는 <xref:System.DateTimeOffset> 로 시간 영역 변환을 수행합니다.  이 메서드의 매개 변수는 <xref:System.DateTimeOffset> 값 및 시간이 변환될 표준 시간대에 대한 참조입니다.  이 메서드를 호출하면 <xref:System.DateTimeOffset> 값이 반환됩니다.  예를 들어 이전 예제의 `ReturnTimeOnServer` 메서드를 다음과 같이 다시 작성하여 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> 메서드를 호출할 수 있습니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]  
  
## 참고 항목  
 <xref:System.TimeZoneInfo>   
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [로컬 시스템에 정의된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)