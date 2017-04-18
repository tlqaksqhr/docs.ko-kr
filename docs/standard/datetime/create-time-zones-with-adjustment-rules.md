---
title: "방법: 조정 규칙을 사용하여 표준 시간대 만들기 | Microsoft Docs"
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
  - "조정 규칙[.NET Framework]"
  - "표준 시간대[.NET Framework], 조정 규칙"
  - "표준 시간대[.NET Framework], 만들기"
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 조정 규칙을 사용하여 표준 시간대 만들기
응용 프로그램에 필요한 정확한 표준 시간대 정보가 다음과 같은 몇 가지 원인 때문에 특정 시스템에 없을 수 있습니다.  
  
-   로컬 시스템의 레지스트리에서 표준 시간대를 정의하지 않았습니다.  
  
-   레지스트리에서 표준 시간대에 대한 데이터를 수정하거나 제거했습니다.  
  
-   중요한 특정 기간 동안의 표준 시간대 조정에 대한 정확한 정보가 표준 시간대에 없습니다.  
  
 이러한 경우 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출하여 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다.  이 메서드의 오버로드를 사용하면 조정 규칙을 사용하거나 사용하지 않고 표준 시간대를 만들 수 있습니다.  표준 시간대에서 일광 절약 시간을 지원하는 경우 고정 조정 규칙이나 유동 조정 규칙을 사용하여 조정을 정의할 수 있습니다. 이러한 용어에 대한 정의는 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)에서 "표준 시간대 용어" 단원을 참조하십시오.  
  
> [!IMPORTANT]
>  <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출하여 만든 사용자 지정 표준 시간대는 레지스트리에 추가되지 않습니다.  대신 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드 호출에서 반환되는 개체 참조를 통해서만 이러한 표준 시간대에 액세스할 수 있습니다.  
  
 이 항목에서는 조정 규칙을 사용하여 표준 시간대를 만드는 방법을 보여 줍니다.  일광 절약 시간 조정 규칙을 지원하지 않는 표준 시간대를 만들려면 [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)를 참조하십시오.  
  
### 유동 조정 규칙을 사용하여 표준 시간대를 만들려면  
  
1.  각 조정에 대해 즉, 특정 시간 간격으로 반복되는 표준 시간에서 또는 표준 시간으로의 각 전환에 대해 다음을 수행합니다.  
  
    1.  표준 시간대 조정에 대한 시작 전환 시간을 정의합니다.  
  
         <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName> 메서드를 호출하고 전환 시간을 정의하는 <xref:System.DateTime> 값, 전환이 발생하는 월을 정의하는 정수 값, 전환이 발생하는 주를 정의하는 정수 값 및 전환이 발생하는 요일을 정의하는 <xref:System.DayOfWeek> 값을 이 메서드에 전달해야 합니다.  이 메서드 호출에서는 <xref:System.TimeZoneInfo.TransitionTime> 개체가 인스턴스화됩니다.  
  
    2.  표준 시간대 조정에 대한 종료 전환 시간을 정의합니다.  이를 위해서는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName> 메서드를 또 한번 호출해야 합니다.  이 메서드 호출에서는 두 번째 <xref:System.TimeZoneInfo.TransitionTime> 개체가 인스턴스화됩니다.  
  
    3.  <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 메서드를 호출하고 조정의 유효한 시작 날짜 및 종료 날짜, 전환에 걸리는 시간을 정의하는 <xref:System.TimeSpan> 개체 및 특정 시간대에서 일광 절약 시간 사이의 전환이 이루어지는 시기를 정의하는 두 개의 <xref:System.TimeZoneInfo.TransitionTime> 개체를 이 메서드에 전달합니다.  이 메서드 호출에서는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체가 인스턴스화됩니다.  
  
    4.  <xref:System.TimeZoneInfo.AdjustmentRule> 개체를 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열에 할당합니다.  
  
2.  표준 시간대의 표시 이름을 정의합니다.  표시 이름은 표준 시간대의 UTC\(협정 세계시\) 오프셋을 괄호로 묶고 그 뒤에 표준 시간대를 식별하는 문자열, 해당 표준 시간대 내에 있는 하나 이상의 도시 또는 하나 이상의 국가나 지역이 오는 일반적인 형식을 따릅니다.  
  
3.  표준 시간대 표준 시간의 이름을 정의합니다.  일반적으로 이 문자열은 표준 시간대의 식별자로도 사용됩니다.  
  
4.  표준 시간대 일광 절약 시간의 이름을 정의합니다.  
  
5.  표준 시간대의 표준 이름과 다른 식별자를 사용하려면 표준 시간대 식별자를 정의합니다.  
  
6.  표준 시간대의 UTC 오프셋을 정의하는 <xref:System.TimeSpan> 개체를 인스턴스화합니다.  시간이 UTC보다 늦은 표준 시간대의 오프셋은 양수이고  UTC보다 이른 표준 시간대의 오프셋은 음수입니다.  
  
7.  [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName> 메서드를 호출하여 새 표준 시간대를 인스턴스화합니다.  
  
## 예제  
 다음 예제에서는 1918년에서 현재 사이의 여러 시간 간격에 대한 조정 규칙이 포함된 미국의 중부 표준시를 정의합니다.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
 [!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]  
  
 이 예제에서 만드는 표준 시간대에는 여러 조정 규칙이 포함됩니다.  조정 규칙의 유효한 시작 및 종료 날짜가 다른 조정 규칙의 날짜와 겹치지 않도록 주의를 기울여야 합니다.  겹치는 경우 <xref:System.InvalidTimeZoneException>이 throw됩니다.  
  
 유동 조정 규칙의 경우 값 5를 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드의 `week` 매개 변수로 전달하여 전환이 특정 월의 마지막 주에 발생하도록 지정합니다.  
  
 [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName> 메서드 호출에서 사용할 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열을 만들 때 코드에서 표준 시간대에 대해 만들 조정의 수에 필요한 크기로 해당 배열을 초기화할 수 있습니다.  대신 이 코드에서는 <xref:System.Collections.Generic.List%601.Add%2A> 메서드를 호출하여 각 조정 규칙을 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 제네릭 <xref:System.Collections.Generic.List%601> 컬렉션에 추가합니다.  그런 다음 <xref:System.Collections.Generic.List%601.CopyTo%2A> 메서드를 호출하여 이 컬렉션의 멤버를 배열에 복사합니다.  
  
 또한 이 예제에서는 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 메서드를 사용하여 고정 날짜 조정을 정의합니다.  이는 전환 매개 변수 중 시간, 월 및 요일만 필요하다는 점만 제외하면 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드를 호출하는 것과 유사합니다.  
  
 다음과 같은 코드를 사용하여 이 예제를 테스트할 수 있습니다.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
 [!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   다음 네임스페이스를 가져와야 합니다.  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)   
 [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)