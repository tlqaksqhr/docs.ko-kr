---
title: "형식 디자인 지침 | Microsoft Docs"
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
  - "형식 디자인 지침"
  - "형식 디자인 지침에 대 한 형식 디자인 지침"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 형식 디자인 지침"
  - "형식 [.NET Framework] 디자인 지침"
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 형식 디자인 지침
CLR 관점에서 보면는 두 가지 범주의 형식\-참조 형식과 값 형식\-하지만 프레임 워크 디자인에 대 한 문서에서 상황 각기 고유한 특정 디자인 규칙 보다 논리적인 그룹으로 형식 나눕니다.  
  
 클래스는 참조 형식의 일반적인 경우입니다. 대부분의 프레임 워크에서 형식의 대량을 구성 합니다. 클래스는 다양 한 개체 지향 기능을 지원 하 고 일반 적용할 수 있는지를 인기도 미납 합니다. 기본 클래스와 추상 클래스는 확장성와 관련 된 특별 한 논리 그룹입니다.  
  
 인터페이스는 참조 형식과 값 형식으로 구현할 수 있는 형식입니다. 따라서 루트 참조 형식 및 값 형식의 다형 계층으로 사용할 수 있습니다. 또한 CLR에서 지원 되지 않는 다중 상속을 시뮬레이션 하 인터페이스를 사용할 수 있습니다.  
  
 구조체의 값 형식 일반적인 경우는 하며 언어 기본 형식에 비슷한 간단한 형식에 대 한 예약 해야 합니다.  
  
 열거형은 짧은 집합 일의 주, 콘솔 색 등과 같은 값을 정의 하는 데 사용 되는 값 형식의 특수 한 경우입니다.  
  
 정적 클래스는 정적 멤버에 대 한 컨테이너를 사용 하는 형식. 이러한 작업은 일반적으로 다른 작업에 대 한 바로 가기를 제공 하는 데 사용 됩니다.  
  
 대리자, 예외, 특성, 배열 및 컬렉션은 특정 용도 위한 참조 형식의 모든 특별 한 경우 및 지침의 디자인 및 사용에 대 한이 가이드의 다른 곳에서 설명 합니다.  
  
 **✓ 수행** 각 종류의 관련 되지 않은 기능 임의의 컬렉션 뿐만 아니라 관련된 멤버의 잘 정의 된 집합 인지 확인 합니다.  
  
## 단원 내용  
 [클래스와 구조체 간의 선택](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [추상 클래스 디자인](../../../docs/standard/design-guidelines/abstract-class.md)  
 [정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)  
 [인터페이스 디자인](../../../docs/standard/design-guidelines/interface.md)  
 [구조체 디자인](../../../docs/standard/design-guidelines/struct.md)  
 [열거형 디자인](../../../docs/standard/design-guidelines/enum.md)  
 [중첩 형식](../../../docs/standard/design-guidelines/nested-types.md)  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)