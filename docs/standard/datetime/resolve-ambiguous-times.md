---
title: "방법: 모호한 시간 확인 | Microsoft Docs"
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
  - "모호한 시간[.NET Framework]"
  - "표준 시간대[.NET Framework], 모호한 시간"
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 모호한 시간 확인
모호한 시간은 두 가지 이상의 UTC\(협정 세계시\)로 매핑되는 시간입니다.  표준 시간대의 일광 절약 시간에서 표준 시간으로의 전환과 같이 클럭 시간이 제시간에 원래 시간으로 맞춰질 때 이러한 시간이 발생합니다.  모호한 시간을 처리하려면 다음 중 하나를 수행할 수 있습니다.  
  
-   시간이 UTC로 매핑되는 방식을 가정합니다.  예를 들어 모호한 시간이 항상 표준 시간대의 표준 시간으로 표시된다고 가정할 수 있습니다.  
  
-   모호한 시간이 사용자가 입력한 데이터 항목인 경우 사용자가 모호성을 해결하도록 그대로 둘 수 있습니다.  
  
 이 항목에서는 모호한 시간이 표준 시간대의 표준 시간을 나타내는 것으로 가정하여 이러한 시간을 해결하는 방법을 보여 줍니다.  
  
### 모호한 시간을 표준 시간대의 표준 시간에 매핑하려면  
  
1.  <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 메서드를 호출하여 모호한 시간인지 여부를 확인합니다.  
  
2.  시간이 모호한 경우 표준 시간대의 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성에서 반환되는 <xref:System.TimeSpan> 개체에서 이 시간을 뺍니다.  
  
3.  `static`\(Visual Basic .NET의 경우 `Shared`\) <xref:System.DateTime.SpecifyKind%2A> 메서드를 호출하여 UTC 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind?displayProperty=fullName>로 설정합니다.  
  
## 예제  
 다음 예제에서는 모호한 시간이 현지 표준 시간대의 표준 시간을 나타내는 것으로 가정하여 이러한 시간을 UTC로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
 [!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]  
  
 이 예제는 전달된 <xref:System.DateTime> 값이 모호한지 여부를 확인하는 `ResolveAmbiguousTime` 메서드로 구성되어 있습니다.  값이 모호한 경우 이 메서드는 해당하는 UTC 시간을 나타내는 <xref:System.DateTime> 값을 반환합니다.  이 메서드에서는 현지 시간에서 현지 표준 시간대의 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성 값을 빼서 이러한 변환을 처리합니다.  
  
 일반적으로 모호한 시간은 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 메서드를 호출하여 모호한 시간에 해당하는 UTC 오프셋이 포함된 <xref:System.TimeSpan> 개체의 배열을 검색하는 방법으로 처리됩니다.  그러나 이 예제에서는 모호한 시간이 항상 표준 시간대의 표준 시간에 매핑되어야 한다고 임의로 가정합니다.  <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성은 UTC와 표준 시간대 표준 시간 사이의 오프셋을 반환합니다.  
  
 이 예제에서는 현지 표준 시간대에 대한 모든 참조가 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 속성을 통해 이루어지므로 현지 표준 시간대가 개체 변수에 할당되지 않습니다.  <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName> 메서드 호출에서는 현지 표준 시간대가 할당된 모든 개체가 무효화되므로 이 방법을 사용하는 것이 좋습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   <xref:System> 네임스페이스를 `using` 문을 사용하여 가져와야 합니다\(C\# 코드인 경우 필요\).  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [방법: 사용자의 모호한 시간 확인 작업 허용](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)