---
title: "방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기 | Microsoft Docs"
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
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기
응용 프로그램에 필요한 정확한 표준 시간대 정보가 다음과 같은 몇 가지 원인 때문에 특정 시스템에 없을 수 있습니다.  
  
-   로컬 시스템의 레지스트리에서 표준 시간대를 정의하지 않았습니다.  
  
-   레지스트리에서 표준 시간대에 대한 데이터를 수정하거나 제거했습니다.  
  
-   표준 시간대가 있지만 중요한 특정 기간 동안의 표준 시간대 조정에 대한 정확한 정보가 없습니다.  
  
 이러한 경우 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출하여 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다.  이 메서드의 오버로드를 사용하면 조정 규칙을 사용하거나 사용하지 않고 표준 시간대를 만들 수 있습니다.  표준 시간대에서 일광 절약 시간을 지원하는 경우 고정 조정 규칙이나 유동 조정 규칙을 사용하여 조정을 정의할 수 있습니다. 이러한 용어에 대한 정의는 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)에서 "표준 시간대 용어" 단원을 참조하십시오.  
  
> [!IMPORTANT]
>  <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출하여 만든 사용자 지정 표준 시간대는 레지스트리에 추가되지 않습니다.  대신 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드 호출에서 반환되는 개체 참조를 통해서만 이러한 표준 시간대에 액세스할 수 있습니다.  
  
 이 항목에서는 조정 규칙을 사용하지 않고 표준 시간대를 만드는 방법을 보여 줍니다.  일광 절약 시간 조정 규칙을 지원하는 표준 시간대를 만들려면 [방법: 조정 규칙을 사용하여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)를 참조하십시오.  
  
### 조정 규칙을 사용하지 않고 표준 시간대를 만들려면  
  
1.  표준 시간대의 표시 이름을 정의합니다.  
  
     표시 이름은 표준 시간대의 UTC\(협정 세계시\) 오프셋을 괄호로 묶고 그 뒤에 표준 시간대를 식별하는 문자열, 해당 표준 시간대 내에 있는 하나 이상의 도시 또는 하나 이상의 국가나 지역이 오는 일반적인 형식을 따릅니다.  
  
2.  표준 시간대 표준 시간의 이름을 정의합니다.  일반적으로 이 문자열은 표준 시간대의 식별자로도 사용됩니다.  
  
3.  표준 시간대의 표준 이름과 다른 식별자를 사용하려면 표준 시간대 식별자를 정의합니다.  
  
4.  표준 시간대의 UTC 오프셋을 정의하는 <xref:System.TimeSpan> 개체를 인스턴스화합니다.  시간이 UTC보다 늦은 표준 시간대의 오프셋은 양수이고  UTC보다 이른 표준 시간대의 오프셋은 음수입니다.  
  
5.  <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=fullName> 메서드를 호출하여 새 표준 시간대를 인스턴스화합니다.  
  
## 예제  
 다음 예제에서는 남극 대륙 모슨에 대한 사용자 지정 표준 시간대를 조정 규칙 없이 정의합니다.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
 [!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]  
  
 <xref:System.TimeZoneInfo.DisplayName%2A> 속성에 할당되는 문자열은 표준 시간대의 UTC 오프셋 다음에 표준 시간대에 대한 이해하기 쉬운 설명이 오는 표준 형식을 따릅니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   다음 네임스페이스를 가져와야 합니다.  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)   
 [방법: 조정 규칙을 사용하여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)