---
title: "보호 된 멤버 | Microsoft Docs"
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
  - "보호 된 멤버 [.NET Framework]"
  - "보호 된 멤버"
  - "봉인 되지 않은 클래스 [.NET Framework]"
  - "클래스 [.NET Framework], 보호 된 멤버"
  - "봉인 되지 않은 클래스"
  - "클래스 동작 사용자 지정"
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 보호 된 멤버
단독으로 보호 된 멤버는 확장성을 제공 하지 않으면 없지만 서브클래싱을 통해 확장성을 더 강력한 만들 수 있습니다. 기본 공용 인터페이스를 불필요 하 게 복잡해 집니다 하지 않고 고급 사용자 지정 옵션을 노출 하 사용할 수 있습니다.  
  
 프레임 워크 디자이너에 주의를 기울여야 보호 된 멤버 이름 "보호" 잘못 된 생각 보안을 지정할 수 없기 때문에 필요 합니다. 누구나 하위 클래스는 봉인 되지 않은 클래스 및 멤버에 보호 된 액세스를을 수 공용 멤버에 사용 되는 코딩 관례 보호 된 멤버에 적용 되는 하므로 모두 동일 합니다.  
  
 **✓ 고려** 를 사용 하 여 고급 사용자 지정에 대 한 멤버를 보호 합니다.  
  
 **✓ 수행** 보안, 설명서 및 호환성 분석 하기 위해 공용으로 봉인 되지 않은 클래스의 보호 된 멤버를 처리 합니다.  
  
 모든 사용자 클래스에서 상속 하 고 보호 된 멤버에 액세스할 수 있습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)