---
title: "날짜 및 시간에 대한 산술 연산 수행 | Microsoft Docs"
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
  - "산술 연산[.NET Framework], 날짜 및 시간"
  - "날짜[.NET Framework], 산술 연산자"
  - "날짜[.NET Framework], 비교"
  - "DateTime 구조체, 산술 연산자"
  - "DateTimeOffset 구조체, 산술 연산자"
  - "표준 시간대[.NET Framework], 산술 연산자"
  - "시간[.NET Framework], 산술 연산자"
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 날짜 및 시간에 대한 산술 연산 수행
<xref:System.DateTime> 및 <xref:System.DateTimeOffset> 구조체는 둘 다 해당 값에 대해 산술 연산을 수행하는 멤버를 제공하지만 산술 연산의 결과는 전혀 다릅니다.  이 항목에서는 이러한 차이점을 검토하고, 이러한 차이점을 날짜 및 시간 데이터의 표준 시간대 인식 수준에 연결하고, 날짜 및 시간 데이터를 사용하여 완전 표준 시간대 인식 작업을 수행하는 방법에 대해 설명합니다.  
  
## DateTime 값에 대한 비교 및 산술 연산  
 .NET Framework version 2.0부터는 <xref:System.DateTime> 값에 제한된 표준 시간대 인식 수준이 적용됩니다.  <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성을 사용하면 <xref:System.DateTimeKind> 값을 날짜와 시간에 할당하여 날짜와 시간이 현지 시간, UTC\(협정 세계시\) 또는 지정되지 않은 표준 시간대의 시간 중 무엇을 나타내는지 지정할 수 있습니다.  그러나 <xref:System.DateTime> 값을 사용하여 날짜와 시간에 대해 비교 또는 산술 연산을 수행할 때는 이 제한된 표준 시간대 정보가 무시됩니다.  다음 예제에서는 현재 현지 시간과 현재 UTC 시간을 비교하여 이를 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]  
  
 <xref:System.DateTime.CompareTo%28System.DateTime%29> 메서드는 현지 시간이 UTC 시간보다 빠르거나 느리다고 보고하고, 빼기 연산은 미국 태평양 표준 시간대에 있는 시스템의 UTC와 현지 시간 간 차이가 일곱 시간임을 나타냅니다.  그러나 이러한 두 값은 서로 다른 특정 시간 표현을 제공하므로 이 경우 이 시간 간격이 전적으로 UTC에서의 현지 표준 시간대 오프셋 때문이라는 것을 쉽게 알 수 있습니다.  
  
 일반적으로 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성은 동일한 두 시점의 비교가 나타내는 바와 같이 <xref:System.DateTime> 비교 및 산술 메서드에서 반환하는 결과에 영향을 주지 않는 반면 이러한 결과의 해석에는 영향을 줄 수 있습니다.  예를 들면 다음과 같습니다.  
  
-   해당 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성이 둘 다 <xref:System.DateTimeKind>인 두 날짜 및 시간 값에 대해 수행된 모든 산술 연산의 결과는 두 값 간의 실제 시간 간격을 반영합니다.  마찬가지로 이러한 두 시간 및 날짜 값의 비교는 시간 간의 관계를 정확하게 반영합니다.  
  
-   해당 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성이 둘 다 <xref:System.DateTimeKind>인 두 날짜 및 시간 값이나 <xref:System.DateTime.Kind%2A?displayProperty=fullName> 속성 값이 서로 다른 두 날짜 및 시간 값에 대해 수행된 모든 산술 또는 비교 연산의 결과는 두 값 간의 차이를 클럭 시간으로 반영합니다.  
  
-   현지 날짜 및 시간 값에 대한 산술 또는 비교 연산은 특정 값이 모호하거나 올바르지 않다는 것도 고려하지 않고 현지 표준 시간대와 일광 절약 시간제 간의 전환에 따라 조정 규칙이 달라지는 것도 고려하지 않습니다.  
  
-   UTC와 현지 시간 간의 차이를 비교하거나 계산하는 연산에는 결과에 있는 UTC에서의 현지 표준 시간대 오프셋과 동일한 시간 간격이 포함됩니다.  
  
-   지정되지 않은 시간과 UTC 또는 현지 시간 간의 차이를 비교하거나 계산하는 연산은 단순 클럭 시간을 반영합니다.  표준 시간대 차이는 고려되지 않으며, 표준 시간대 조정 규칙의 적용 여부도 결과에 반영되지 않습니다.  
  
-   지정되지 않은 두 값 간의 차이를 비교하거나 계산하는 연산에는 서로 다른 두 표준 시간대의 시간 차이를 반영하는 알 수 없는 간격이 포함될 수 있습니다.  
  
 표준 시간대 차이가 날짜 및 시간 계산에 영향을 주지 않거나\([DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../docs/standard/datetime/choosing-between-datetime.md) 참조\) 날짜 및 시간 데이터의 컨텍스트에서 비교 또는 산술 연산의 의미를 정의하는 경우도 있을 수 있습니다.  
  
## DateTimeOffset 값에 대한 비교 및 산술 연산  
 <xref:System.DateTimeOffset> 값에는 날짜와 시간뿐만 아니라 UTC를 기준으로 해당 날짜와 시간을 명확하게 정의하는 오프셋도 포함됩니다.  따라서 <xref:System.DateTime> 값과는 약간 다른 방식으로 같음을 정의할 수 있습니다.  <xref:System.DateTime> 값은 날짜 및 시간 값이 같으면 같은 반면에 <xref:System.DateTimeOffset> 값은 같은 시점을 참조하면 같습니다.  따라서 <xref:System.DateTimeOffset> 값은 두 날짜 및 시간 간의 간격을 결정하며, 비교 연산 및 대부분의 산술 연산에 사용될 때 더 정확한 반면에 더 적은 해석을 필요로 합니다.  현지 및 UTC <xref:System.DateTime> 값을 비교하는 이전 예제와 동일한 <xref:System.DateTimeOffset>인 다음 예제에서는 이러한 동작의 차이를 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]  
  
 이 예제에서 <xref:System.DateTimeOffset.CompareTo%2A> 메서드는 현재 현지 시간과 현재 UTC 시간이 같음을 나타내고 <xref:System.DateTimeOffset> 값의 빼기는 두 시간 간의 차이가 <xref:System.TimeSpan.Zero?displayProperty=fullName>임을 나타냅니다.  
  
 날짜 및 시간 연산에 <xref:System.DateTimeOffset> 값 사용과 관련된 주요 제한 사항은 <xref:System.DateTimeOffset> 값의 표준 시간대 인식 수준이 완전하지 않고 제한적이라는 것입니다.  <xref:System.DateTimeOffset> 변수에 값이 처음 할당될 때는 <xref:System.DateTimeOffset> 값의 오프셋이 UTC에서의 표준 시간대 오프셋을 반영하지만 이후부터는 표준 시간대와 분리됩니다.  식별 가능한 시간과 더 이상 직접 연결되지 않기 때문에 날짜 및 시간 간격의 더하기 및 빼기 연산에는 표준 시간대의 조정 규칙이 고려되지 않습니다.  
  
 설명 하기 위해, 2008 년 3 월 9 일 오전 2시에 미국 일광 절약 시간에서 미국 중부 표준 시간 영역으로 바뀝니다.  즉, 2008년 3월 9일 오전 1시 30분의 중부 표준 시간의 2시간 30분 간격을 2008년 3월 9일 오전 5시의 추가 날짜와 시간을 만들어야 합니다.  그러나 다음 예제와 같이 이 더하기 연산의 결과는 2008년 3월 9일 오전 4시가 됩니다.  이것은 이 연산 결과는 올바른 시점을 나타내지만 해당 시간이 표준 시간대의 시간이 아니기 때문입니다. 즉, 예상된 표준 시간대 오프셋이 반영되지 않았기 때문입니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]  
  
## 표준 시간대의 시간에 대한 산술 연산  
 <xref:System.TimeZoneInfo> 클래스에는 한 표준 시간대에서 다른 표준 시간대로 시간을 변환할 때 자동으로 조정을 적용하는 여러 변환 메서드가 포함되어 있습니다.  이러한 요구 사항은 다음과 같습니다.  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A> 및 <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> 메서드는 두 표준 시간대 간에 시간을 변환합니다.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> 및 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 메서드는 특정 표준 시간대의 시간을 UTC로 변환하거나 UTC를 특정 표준 시간대의 시간으로 변환합니다.  
  
 자세한 내용은 [표준 시간대 간에 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)를 참조하십시오.  
  
 <xref:System.TimeZoneInfo> 클래스는 날짜 및 시간 연산을 수행할 때 자동으로 조정 규칙을 적용하는 메서드를 제공하지 않습니다.  그러나 표준 시간대의 시간을 UTC로 변환하고 산술 연산을 수행한 다음 UTC를 다시 표준 시간대의 시간으로 변환하면 자동으로 조정 규칙을 적용할 수 있습니다.  자세한 내용은 [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)를 참조하십시오.  
  
 예를 들어 다음 코드는 2008년 3월 9일 오전 2시에 2시간 30분을 더하는 이전 코드와 비슷합니다.  그러나 이 코드에서는 먼저 중부 표준시를 UTC로 변환하고 날짜 및 시간 연산을 수행한 다음 이 연산 결과에서 UTC를 중부 표준시로 다시 변환합니다. 그러면 결과 시간에 중부 표준시가 일광 절약 시간제로 전환된 것이 반영됩니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)