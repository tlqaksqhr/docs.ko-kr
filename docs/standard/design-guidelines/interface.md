---
title: "인터페이스 디자인 | Microsoft Docs"
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
  - "인터페이스 [.NET Framework] 디자인 지침"
  - "인터페이스 형식 디자인 지침"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 인터페이스"
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 인터페이스 디자인
대부분의 Api는 클래스 및 구조체를 사용 하 여 모델링 가장 있지만 인터페이스에 더 적합 또는 유일한 옵션은 경우가 있습니다.  
  
 CLR 다중 상속을 지원 하지 않습니다 \(즉, CLR 클래스에서에서 상속할 수 없는 둘 이상의 기본 클래스\), 하지만 기본 클래스에서 상속 하는 것 외에도 하나 이상의 인터페이스를 구현 하는 형식 수입니다. 따라서 인터페이스가 다중 상속의 효과 달성 하기 위해 자주 사용 됩니다. 예를 들어 <xref:System.IDisposable> disposability 독립적으로 참여 하고자 하는 다른 상속 계층 구조를 지원 하기 위한 형식을 허용 하는 인터페이스입니다.  
  
 인터페이스는 적절 한 정의 다른 상황에서 일부 값 형식은 같은 여러 형식을 지원할 수 있는 공통 인터페이스를 만드는 경우 값 형식 이외의 다른 형식에서 상속할 수 없습니다 <xref:System.ValueType>, 를 했지만 인터페이스 구현을 하므로 인터페이스를 사용 하는 공통 기본 형식을 제공 하기 위해 유일한 옵션입니다.  
  
 **✓ 수행** 몇 가지 일반적인 API 값 형식을 포함 하는 형식 집합에서 지원 하도록 해야 할 경우에 인터페이스를 정의 합니다.  
  
 **✓ 고려** 이미 다른 형식에서 상속 된 형식에서 해당 기능을 지원 해야 하는 경우 인터페이스를 정의 합니다.  
  
 **X 방지** 표식 인터페이스 \(멤버 없이 인터페이스\)를 사용 합니다.  
  
 클래스를 구체적인 특징 \(표식\)을 가진 것으로 표시 해야 할 경우 일반적으로 사용 하 여 인터페이스 보다는 사용자 지정 특성입니다.  
  
 **✓ 수행** 는 인터페이스의 구현 되는 하나 이상의 형식을 제공 합니다.  
  
 이 사용이 하면 인터페이스의 디자인 유효성 검사를 수행 합니다. 예를 들어 <xref:System.Collections.Generic.List%601> 의 구현인는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다.  
  
 **✓ 수행** 정의한 각 인터페이스를 사용 하는 하나 이상의 API를 제공 \(인터페이스로 형식화 된 인터페이스 매개 변수 또는 속성으로 수행 하는 메서드\).  
  
 이 사용이 하면 인터페이스 디자인 유효성 검사를 수행 합니다. 예를 들어 <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> 소비는 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 인터페이스입니다.  
  
 **X 하지 않으려면** 이전에 제공한 하는 인터페이스에 멤버를 추가 합니다.  
  
 이렇게 흐 인터페이스의 구현입니다. 버전 관리 문제를 방지 하기 위해 새 인터페이스를 만들어야 합니다.  
  
 이러한 지침에 설명 된 경우를 제외 하 고, 일반적으로 선택 해야 인터페이스 대신 클래스에 관리 되는 코드 재사용 가능 라이브러리 디자인 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)