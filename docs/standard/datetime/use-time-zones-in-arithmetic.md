---
title: "방법: 날짜 및 시간 산술 연산의 표준 시간대 사용 | Microsoft Docs"
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
  - "날짜[.NET Framework], 더하기 및 빼기"
  - "표준 시간대[.NET Framework], 산술 연산자"
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 날짜 및 시간 산술 연산의 표준 시간대 사용
일반적으로 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 값을 사용하여 날짜 및 시간 연산을 수행할 경우에는 표준 시간대 조정 규칙이 결과에 반영되지 않습니다.  이것은 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind>로 설정된 경우와 같이 날짜 및 시간 값의 표준 시간대를 명확히 식별할 수 있는 경우에도 적용됩니다.  이 항목에서는 특정 표준 시간대에 속한 날짜 및 시간 값에 대한 산술 연산을 수행하는 방법을 보여 줍니다.  산술 연산의 결과에는 표준 시간대의 조정 규칙이 반영됩니다.  
  
### 날짜 및 시간 연산에 조정 규칙을 적용하려면  
  
1.  날짜 및 시간 값을 이 값이 속한 표준 시간대와 밀접하게 결합하는 일부 메서드를 구현합니다.  예를 들어 날짜 및 시간 값과 해당 표준 시간대를 모두 포함하는 구조체를 선언합니다.  다음 예제에서는 이 방법을 사용하여 <xref:System.DateTime> 값을 해당 표준 시간대에 연결합니다.  
  
     [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
     [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]  
  
2.  <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 메서드 또는 <xref:System.TimeZoneInfo.ConvertTime%2A> 메서드를 호출하여 시간을 UTC\(협정 세계시\)로 변환합니다.  
  
3.  UTC 시간에 대해 산술 연산을 수행합니다.  
  
4.  <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=fullName> 메서드를 사용하여 시간을 UTC에서 원래 시간과 관련된 표준 시간대로 변환합니다.  
  
## 예제  
 다음 예제에서는 중부 표준시 2008년 3월 9일 오전 1시 30분에 2시간 30분을 더합니다.  30분 뒤인 2008년 3월 9일 오전 2시에 영역 시간대가 일광 절약 시간으로 변합니다.  이 예제에서는 앞 단원의 네 단계를 수행하므로 결과 시간이 2008년 3월 9일 오전 5시로 올바르게 보고됩니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]  
  
 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값은 모두 해당 값이 속할 수 있는 표준 시간대와 분리되어 있습니다.  표준 시간대의 조정 규칙을 자동으로 적용하는 방식으로 날짜 및 시간 연산을 수행하려면 날짜 및 시간 값이 속한 표준 시간대를 즉시 식별할 수 있어야 합니다.  즉, 날짜 및 시간과 관련 표준 시간대가 밀접하게 결합되어 있어야 합니다.  다음과 같은 여러 가지 방법으로 이렇게 할 수 있습니다.  
  
-   응용 프로그램에서 사용되는 모든 시간이 특정 표준 시간대에 속한다고 가정합니다.  일부 경우에는 적합하지 않지만 이 방법은 제한된 융통성과 이식성을 제공할 수 있습니다.  
  
-   날짜 및 시간과 관련 표준 시간대를 모두 해당 형식의 필드로 포함하여 밀접하게 결합하는 형식을 정의합니다.  날짜 및 시간과 표준 시간대를 두 개의 멤버 필드에 저장하는 구조체를 정의하는 아래 코드 예제에서 이 방법이 사용됩니다.  
  
 이 예제에서는 표준 시간대 조정 규칙이 결과에 적용되도록 <xref:System.DateTime> 값에 대한 산술 연산을 수행하는 방법을 보여 줍니다.  그러나 <xref:System.DateTimeOffset> 값도 쉽게 사용할 수 있습니다.  따라서 다음 예제에서는 원래 예제의 코드를 변경하여 <xref:System.DateTime> 값 대신 <xref:System.DateTimeOffset>을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]  
  
 <xref:System.DateTimeOffset> 값을 먼저 UTC로 변환하지 않고 이 값에 대해 이러한 더하기를 간단히 수행하는 경우 결과에는 올바른 시점이 반영되지만 오프셋에는 해당 시간에 대해 지정한 표준 시간대의 오프셋이 반영되지 않습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   <xref:System> 네임스페이스를 `using` 문을 사용하여 가져와야 합니다\(C\# 코드인 경우 필요\).  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [날짜 및 시간에 대한 산술 연산 수행](../../../docs/standard/datetime/performing-arithmetic-operations.md)