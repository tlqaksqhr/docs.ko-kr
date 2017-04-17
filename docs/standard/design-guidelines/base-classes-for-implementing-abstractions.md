---
title: "추상화 구현을 위한 기본 클래스 | Microsoft Docs"
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
  - "추상화 [.NET Framework]"
  - "기본 클래스를 추상화"
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 추상화 구현을 위한 기본 클래스
엄격히 말해서, 클래스 다른 클래스에서 파생 하는 경우 기본 클래스를 수 있습니다. 그러나이 섹션 기본 클래스는 클래스는 일반적인 추상화를 제공 합니다. 또는 일부를 재사용할 수 있는 다른 클래스에 대 한 기본 구현을 통해 상속을 주로. 기본 클래스는 일반적으로 중간 계층의 루트를 추상화 하 고 맨 아래에 몇 가지 사용자 지정 구현을 사이의 상속 계층 구조에 유지 합니다.  
  
 추상화 구현을 위한 구현 도우미로 작동 하기. 예를 들어는 항목의 정렬 된 컬렉션에 대 한 프레임 워크의 추상화 중 하나는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다. 구현 <xref:System.Collections.Generic.IList%601> 하며, 따라서 프레임 워크를 제공 몇 가지 기본 클래스와 같은 <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.Collections.ObjectModel.KeyedCollection%602>, 사용자 지정 컬렉션을 구현 하기 위한 도우미 역할도입니다.  
  
 기본 클래스는 일반적으로 하지 자체로 추상화로 제공 하는 데 적합 너무 많은 구현이 포함 쉽 거. 예를 들어는 `Collection<T>` 기본 클래스 구현 제네릭이 아닌을 구현 한다는 사실에 관련 된 많은 포함 `IList` 제네릭이 아닌 컬렉션을 더 잘 통합\) \(에 대 한 인터페이스 및 해당 필드 중 하나에 메모리에 저장 된 항목의 컬렉션 임을 사실에 있습니다.  
  
 앞에서 설명한 대로 기본 클래스 추상화를 구현 해야 하는 사용자에 대 한 귀중 한 도움말을 제공할 수 있지만 동시에 중요 한 책임 수 있습니다. 노출 영역을 추가 하 고 상속 계층 구조 깊이 늘릴 하며 개념상 프레임 워크 복잡해 집니다. 따라서 프레임 워크의 사용자에 게 중요 한 가치를 제공 하는 경우에 기본 클래스를 사용 해야 합니다. 기본 클래스에서 상속 하는 대신 내부 구현에 대 한 사례 위임을 강력 하 게 고려해 야 프레임 워크의 구현자에만 값을 제공 하는 경우 사용 하지 마십시오.  
  
 **✓ 고려** 하면서 기본 클래스에 추상 모든 추상 멤버를 포함 하지 않는다는 하는 경우에 합니다. 이 명확 하 게 통신 하는 사용자 클래스에서 상속 하는 데에 사용할 수는 있습니다.  
  
 **✓ 고려** 주요 시나리오 형식에서 별도 네임 스페이스의 기본 클래스를 배치 합니다. 기본적으로 기본 클래스는 오버 로드는 고급 확장성 시나리오와 따라서는 대부분의 사용자와 관련이 없습니다.  
  
 **X 방지** 클래스는 공용 Api에서 사용 하기 위한 경우 "기본" 접미사를 갖는 기본 클래스 이름을 지정 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)