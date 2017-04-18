---
title: "추상화 (추상 형식 및 인터페이스) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "추상 인터페이스 [.NET Framework]"
  - "추상 인터페이스 [.NET Framework]"
  - "추상 형식 [.NET Framework]"
  - "추상 형식 [.NET Framework]"
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 추상화 (추상 형식 및 인터페이스)
추상 형식이 계약에 설명 하는 계약의 전체 구현을 제공 하지 않습니다. 추상화는 일반적으로 추상 클래스 또는 인터페이스를 구현 하 고 잘 정의 된 계약을 구현 하는 형식의 필요한 의미 체계를 설명 하는 참조 설명서 집합은 키를 누릅니다. .NET Framework의 가장 중요 한 추상화 같습니다 <xref:System.IO.Stream>, 를<xref:System.Collections.Generic.IEnumerable%601>, 를 및 <xref:System.Object>합니다.  
  
 추상화의 계약을 지 원하는 구체적인 형식을 구현 하 고 프레임 워크 Api 소비 \(작동 중에\)와이 구체적인 형식을 사용 하 여 프레임 워크를 확장할 수 있는 추상화 합니다.  
  
 디자인 하는 오랜 시간에 견딜 수 있는 의미 있고 유용한 추상화를 매우 어렵습니다. 주요 문제는 올바른 멤버 집합을 더 이상 및 더 적은 들어옵니다. 추상화에 너무 많은 멤버가 어렵거나도 구현 됩니다. 약속 한 기능에 대 한 멤버를 너무 적게 있으면 많은 흥미로운 시나리오에서 사용할 수 없습니다 됩니다.  
  
 프레임 워크에 너무 많은 추상화는 프레임 워크의 유용성에도 부정적인 영향을 미칠 합니다. 구체적인 구현 및 추상화에서 작동 하는 Api의 큰 그림에 어떻게 부합 하는지 알 수 없는 추상화를 이해 하기 매우 어렵습니다. 또한 추상화 및 해당 멤버의 이름은 대개을 사용 하면 복잡 하 고 차갑고 사용의 다양 한 상황을 이해 하지 않고으로 반드시 추상 있습니다.  
  
 그러나 추상화 기타 확장성 메커니즘과 일치 하는 경우가 없습니다 하는 매우 강력한 확장성을 제공 합니다. IoC \(제어\), 파이프라인, 등에 반전 플러그 인과 같은 많은 아키텍처 패턴의 핵심 됩니다. 프레임 워크의 테스트 용이성에 매우 중요 수도 있습니다. 좋은 추상화 단위 테스트 목적으로 많은 종속성을 삭제할 수 있도록 합니다. 요약 하자면, 추상화 최신 개체 지향 프레임 워크의 수요가 다양 한 기능에 대 한 책임이 있습니다.  
  
 **X 하지 않으려면** 여러 구체적인 구현 및 추상화를 사용 하는 Api를 개발 하 여 테스트 하지 않는 한 추상화를 제공 합니다.  
  
 **✓ 수행** 추상화를 디자인할 때, 추상 클래스와 인터페이스를 신중 하 게 선택 합니다.  
  
 **✓ 고려** 추상화의 구체적인 구현에 대 한 참조 테스트를 제공 합니다. 이러한 테스트는 구현 계약을 올바르게 구현 하는지 여부를 테스트 하도록 사용자를 허용 해야 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)