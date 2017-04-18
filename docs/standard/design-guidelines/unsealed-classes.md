---
title: "봉인 되지 않은 클래스 | Microsoft Docs"
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
  - "봉인 되지 않은 클래스 [.NET Framework]"
  - "봉인 되지 않은 클래스"
  - "상속, 클래스"
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 봉인 되지 않은 클래스
봉인된 클래스에서 상속 될 수 없습니다 및 확장성을 방지 합니다. 반면, 클래스에서 상속 될 수 있는 봉인 되지 않은 클래스 라고 합니다.  
  
 **✓ 고려** 가상 또는 보호 된 멤버 추가 없이 봉인 되지 않은 클래스를 사용 하 여 저렴 한 비용을 제공 하는 훌륭한 방법을 아직 훨씬 감사는 프레임 워크를 확장 합니다.  
  
 개발자는 대개 사용자 정의 생성자, 새 메서드 또는 메서드 오버 로드와 같은 편의 멤버를 추가 하기 위해 봉인 되지 않은 클래스에서 상속 하려고 합니다. 예를 들어  `System.Messaging.MessageQueue` 봉인 되지 않으며 사용자가 특정 시나리오에 대 한 API를 단순화 하는 사용자 지정 메서드를 추가 하려면 하거나 특정 큐 경로에 기본 사용자 지정 큐를 만들 수 있습니다.  
  
 클래스는 대부분의 프로그래밍 언어에서 기본적으로 봉인 되지 않은 및 프레임 워크에서 대부분의 클래스에 대 한 권장 되는 기본 이기도 합니다. 봉인 되지 않은 형식에서 제공 하는 확장성 프레임 워크 사용자가 훨씬 감사 및 봉인 되지 않은 형식에 연결 된 상대적으로 낮은 테스트 비용 때문에 제공 하기 매우 저렴 한가  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [봉인](../../../docs/standard/design-guidelines/sealing.md)