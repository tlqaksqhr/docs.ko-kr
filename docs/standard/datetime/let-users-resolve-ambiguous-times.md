---
title: "방법: 사용자의 모호한 시간 확인 작업 허용 | Microsoft Docs"
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
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 사용자의 모호한 시간 확인 작업 허용
모호한 시간은 두 가지 이상의 UTC\(협정 세계시\)로 매핑되는 시간입니다.  표준 시간대의 일광 절약 시간에서 표준 시간으로의 전환과 같이 클럭 시간이 제시간에 원래 시간으로 맞춰질 때 이러한 시간이 발생합니다.  모호한 시간을 처리하려면 다음 중 하나를 수행할 수 있습니다.  
  
-   모호한 시간이 사용자가 입력한 데이터 항목인 경우 사용자가 모호성을 해결하도록 그대로 둘 수 있습니다.  
  
-   시간이 UTC로 매핑되는 방식을 가정합니다.  예를 들어 모호한 시간이 항상 표준 시간대의 표준 시간으로 표시된다고 가정할 수 있습니다.  
  
 이 항목에서는 사용자가 모호한 시간을 해결하도록 허용하는 방법을 보여 줍니다.  
  
### 사용자가 모호한 시간을 해결하도록 허용하려면  
  
1.  사용자가 입력한 날짜 및 시간을 가져옵니다.  
  
2.  <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> 메서드를 호출하여 모호한 시간인지 여부를 확인합니다.  
  
3.  시간이 모호한 경우 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> 메서드를 호출하여 <xref:System.TimeSpan> 개체의 배열을 검색합니다.  배열의 각 요소에는 모호한 시간이 매핑될 수 있는 UTC 오프셋이 포함되어 있습니다.  
  
4.  사용자가 원하는 오프셋을 선택하게 합니다.  
  
5.  현지 시간에서 사용자가 선택한 오프셋을 빼서 UTC 날짜 및 시간을 얻습니다.  
  
6.  `static`\(Visual Basic .NET의 경우 `Shared`\) <xref:System.DateTime.SpecifyKind%2A> 메서드를 호출하여 UTC 날짜 및 시간 값의 <xref:System.DateTime.Kind%2A> 속성을 <xref:System.DateTimeKind?displayProperty=fullName>로 설정합니다.  
  
## 예제  
 다음 예제에서는 사용자에게 날짜 및 시간을 입력하라는 메시지를 표시하고, 입력한 시간이 모호한 경우 사용자가 모호한 시간을 매핑할 UTC 시간을 선택하도록 합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
 [!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]  
  
 예제 코드의 핵심 부분에서는 모호한 시간과 UTC 사이의 가능한 오프셋을 나타내는 <xref:System.TimeSpan> 개체의 배열을 사용합니다.  그러나 이러한 오프셋은 사용자에게 거의 의미가 없습니다.  또한 오프셋의 의미를 명확하게 하기 위해 코드에서는 오프셋이 현지 표준 시간대의 표준 시간을 나타내는지, 아니면 일광 절약 시간을 나타내는지 확인합니다.  이 코드에서는 오프셋을 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> 속성 값과 비교하여 시간이 표준 시간인지 일광 절약 시간인지 확인합니다.  이 속성은 UTC와 표준 시간대의 표준 시간 간의 차이를 나타냅니다.  
  
 이 예제에서는 현지 표준 시간대에 대한 모든 참조가 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 속성을 통해 이루어지므로 현지 표준 시간대가 개체 변수에 할당되지 않습니다.  <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName> 메서드 호출에서는 현지 표준 시간대가 할당된 모든 개체가 무효화되므로 이 방법을 사용하는 것이 좋습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   <xref:System> 네임스페이스를 `using` 문을 사용하여 가져와야 합니다\(C\# 코드인 경우 필요\).  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [방법: 모호한 시간 확인](../../../docs/standard/datetime/resolve-ambiguous-times.md)