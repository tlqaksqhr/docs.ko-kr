---
title: "방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스 | Microsoft Docs"
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
  - "현지 표준 시간대 액세스"
  - "미리 정의된 표준 시간대"
  - "표준 시간대[.NET Framework], 로컬"
  - "표준 시간대[.NET Framework], 검색"
  - "표준 시간대[.NET Framework], UTC"
  - "UTC 시간, 미리 정의"
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스
<xref:System.TimeZoneInfo> 클래스에서는 두 가지 속성 즉, 미리 정의된 표준 시간대 개체에 대한 코드 액세스 권한을 부여하는 <xref:System.TimeZoneInfo.Utc%2A> 및 <xref:System.TimeZoneInfo.Local%2A>을 제공합니다.  이 항목에서는 이러한 속성에서 반환되는 <xref:System.TimeZoneInfo> 개체에 액세스하는 방법에 대해 설명합니다.  
  
### UTC\(협정 세계시\) TimeZoneInfo 개체에 액세스하려면  
  
1.  `static`\(Visual Basic의 경우 `Shared`\) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> 속성을 사용하여 협정 세계시에 액세스합니다.  
  
2.  이 속성에서 반환되는 <xref:System.TimeZoneInfo> 개체를 개체 변수에 할당하지 않고 계속해서 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> 속성을 통해 협정 세계시에 액세스합니다.  
  
### 현지 표준 시간대에 액세스하려면  
  
1.  `static`\(Visual Basic의 경우 `Shared`\) <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 속성을 사용하여 로컬 시스템의 표준 시간대에 액세스합니다.  
  
2.  이 속성에서 반환되는 <xref:System.TimeZoneInfo> 개체를 개체 변수에 할당하지 않고 계속해서 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 속성을 통해 현지 표준 시간대에 액세스합니다.  
  
## 예제  
 다음 코드는 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 및 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> 속성을 미국과 캐나다 동부 표준 시간대로부터 시간을 변환할 때 사용합니다. 또한 표준 시간대 이름을 콘솔에 표시 합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
 [!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]  
  
 현지 표준 시간대를 <xref:System.TimeZoneInfo>개체 변수에 할당하지 않고 항상 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> 속성을 통해 현지 표준 시간대에 액세스해야 합니다.  마찬가지로 UTC 시간대를 <xref:System.TimeZoneInfo> 개체 변수에 할당하지 않고 항상 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> 속성을 통해 협정 세계시에 액세스해야 합니다.  이렇게 하면 <xref:System.TimeZoneInfo> 개체 변수가 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName> 메서드에 대한 호출로 무효화되지 않습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   <xref:System> 네임스페이스를 `using` 문을 사용하여 가져와야 합니다\(C\# 코드인 경우 필요\).  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [로컬 시스템에 정의된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)   
 [방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)