---
title: "확장성을 위한 디자인 | Microsoft Docs"
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
  - "클래스 라이브러리 확장"
  - ".NET Framework에서 클래스 라이브러리 확장성"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 확장성"
  - "클래스 라이브러리 확장성 [.NET Framework]"
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 확장성을 위한 디자인
프레임 워크를 디자인할 때의 중요 한 측면 있는지 확인 하는 프레임 워크의 확장성을 신중 하 게 고려 했습니다. 이 비용과 관련 된 다양 한 확장성 메커니즘 이점을 이해 해야 합니다. 이 장에서 확장성 메커니즘을 결정 하 고\-하위 클래스 지정, 이벤트, 가상 멤버, 콜백 및 등\-프레임 워크의 요구 사항을 최대한 충족할 수 있습니다.  
  
 프레임 워크의 확장성을 허용 하는 방법은 여러 가지가 있습니다. 매우 강력 하지만 비용이 많이 드는에 강력 하지만 비용이 덜 드는 다양합니다. 모든 지정 된 확장성 요구 사항에 대 한 요구 사항을 충족 하는 가장 비용이 많이 드는 확장성 메커니즘을 선택 해야 합니다. 일반적으로 나중에 보다 높은 확장성을 추가할 수는 벗어날 수 있지만 수 것 바로 주요 변경 없이 염두에서에 둬야 합니다.  
  
## 단원 내용  
 [봉인 되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [보호 된 멤버](../../../docs/standard/design-guidelines/protected-members.md)  
 [이벤트 및 콜백](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)  
 [추상화 \(추상 형식 및 인터페이스\)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [추상화 구현을 위한 기본 클래스](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [봉인](../../../docs/standard/design-guidelines/sealing.md)  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)