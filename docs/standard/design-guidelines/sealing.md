---
title: "봉인 | Microsoft Docs"
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
  - "확장성 제한"
  - "봉인 클래스 [.NET Framework]"
  - "사용자 지정 방지"
  - "봉인 클래스"
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 봉인
개체 지향 프레임 워크의 기능 중 하나는 개발자가 확장 하 고 프레임 워크 디자이너에서 예기치 않은 방식으로 사용자 지정할 수 있습니다. 이것이 기능과 확장 가능한 디자인 하는 위험입니다. 프레임 워크를 디자인할 때 즉,이 필요한 경우 신중 하 게 확장성에 대 한 디자인 제한 하 고 확장성 위험한 되었을 때 매우 중요 합니다.  
  
 확장성을 방해 하는 강력한 메커니즘을 봉인 합니다. 클래스 또는 개별 멤버를 봉인할 수 있습니다. 클래스 사용자를 클래스에서 상속할 수 없습니다. 멤버를 봉인 사용자를에서 특정 멤버를 재정의할 수 없습니다.  
  
 **X 하지 않으려면** 할 이유가 필요 없이 클래스를 봉인 합니다.  
  
 이유가 없는 확장성 시나리오를 고려할 수 없습니다 있습니다 때문에 클래스를 봉인 합니다. 프레임 워크 사용자 클래스에서 상속 하 여 편리 하 게 멤버를 추가 하는 등 다양 한 nonobvious 이유로 하고자 합니다. 참조 [봉인 되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md) nonobvious 대 한 예에 대 한 사용자 형식에서 상속 하려고 합니다.  
  
 클래스에 대 한 좋은 이유는 다음과 같습니다.  
  
-   클래스는 정적 클래스입니다.[정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)을 참조하세요.  
  
-   클래스는 보호 된 상속 된 멤버에 보안에 민감한 기밀 정보를 저장합니다.  
  
-   많은 가상 멤버를 상속 하는 클래스 및 봉인의 개별적으로 비용에는 봉인 되지 않은 클래스를 끝낼 이점 보다 큰 것입니다.  
  
-   클래스가 초고속 런타임 조회 해야 하는 특성입니다. 봉인 되지 않은 것 보다 약간 더 높은 성능 수준에 봉인 된 특성은.[특성](../../../docs/standard/design-guidelines/특성.md)을 참조하세요.  
  
 **X 하지 않으려면** sealed 형식에 대해 보호 또는 가상 멤버를 선언 합니다.  
  
 기본적으로 봉인 된 형식에서 상속할 수 없습니다. 즉, sealed 형식에 대해 보호 된 멤버를 호출할 수 없습니다, 봉인 된 형식에 대 한 가상 메서드를 재정의할 수 없습니다.  
  
 **✓ 고려** 재정의 하는 멤버를 봉인 합니다.  
  
 가상 멤버를 침투 시킬 수 있는 문제 \(에 설명 된 [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)\) 약간 낮은 수준으로 지원 하지만, 재정의에 적용 합니다. 재정의가 봉인 하면 상속 계층의 해당 지점에서 시작 하는 이러한 문제 로부터 보호 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [봉인 되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md)