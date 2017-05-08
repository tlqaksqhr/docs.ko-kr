---
title: "확장명 메서드 | Microsoft Docs"
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
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# 확장명 메서드
확장 메서드는 정적 메서드를 인스턴스 메서드 호출 구문을 사용 하 여 호출할 수 있도록 하는 언어 기능. 이러한 메서드 방법은에서 작동 하는 인스턴스를 나타내는 하나 이상의 매개 변수를 취해야 합니다.  
  
 이러한 확장 메서드를 정의 하는 클래스는 "스폰서" 클래스 라고 하 고 정적으로 선언 되어야 합니다. 확장 메서드를 사용 하려면 스폰서 클래스를 정의 하는 네임 스페이스 하나 가져와야 합니다.  
  
 **X 방지** frivolously 소유 하지 않은 형식에서 특히 확장 메서드를 정의 합니다.  
  
 형식의 소스 코드를 소유한 수행 하는 경우 대신 일반 인스턴스 메서드를 사용 하는 것이 좋습니다. 소유 하지 않은 메서드를 추가 하려는 경우에 매우 주의 해야 합니다. 확장 메서드를 자유롭게 사용 하 여 이러한 메서드가 있는 것으로 설계 되지 않은 형식의 Api를 어지럽히지의 있습니다.  
  
 **✓ 고려** 확장 메서드를 사용 하 여 다음과 같은 시나리오 중 하나:  
  
-   도우미를 제공 하는 핵심 인터페이스 측면에서 기능 이라고 하는 경우 모든 구현 된 인터페이스의 관련 기능을 작성할 수 있습니다. 즉, 구체적인 구현은 그렇지 않은 경우 인터페이스에 할당할 수 없습니다. 예를 들어는 `LINQ to Objects` 연산자는 모두에 대 한 확장 메서드로 구현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> 형식입니다. 따라서 `IEnumerable<>` 구현에서 자동으로 LINQ를 사용할 수 있습니다.  
  
-   일부 형식에 대 한 종속성이 있지만 이러한 종속성 인스턴스 메서드인 것 소개 하는 경우 종속성 관리 규칙 중단 합니다. 예를 들어, 종속성 <xref:System.String> 를 <xref:System.Uri?displayProperty=fullName> 는 것은 바람직하지 않을 하므로 `String.ToUri()` 반환 하는 인스턴스 메서드 `System.Uri` 종속성 관리 측면에서 잘못 된 디자인 됩니다. 정적 확장 메서드 `Uri.ToUri(this string str)` 반환 `System.Uri` 것이 훨씬 더 나은 디자인입니다.  
  
 **X 방지** 에서 확장 메서드를 정의 <xref:System.Object?displayProperty=fullName>합니다.  
  
 VB 사용자 확장 메서드 구문을 사용 하 여 개체 참조에서 이러한 메서드를 호출할 수 없습니다. VB VB에서 바인딩된 개체 강제로 되도록 런타임에 대 한 모든 메서드 호출으로 대 한 참조를 선언 하기 때문에 이러한 메서드 호출을 지원 하지 않습니다 \(라는 실제 멤버는 런타임에 결정 됨\), \(초기 바인딩\) 컴파일 타임에 바인딩 확장 메서드를 결정 하는 동안.  
  
 동일한 바인딩 동작 있으면 다른 언어에 적용 됩니다 지침 또는 확장 메서드가 지원 되지 않습니다.  
  
 **X 하지 않으려면** 형식이 인터페이스에 메서드 추가 또는 종속성 관리에 대 한 확장된 유형으로는 동일한 네임 스페이스에 확장 메서드를 배치 합니다.  
  
 **X 방지** 다른 네임 스페이스에 상주 하는 경우에 동일한 시그니처를 가진 두 개 이상의 확장 메서드를 정의 합니다.  
  
 **✓ 고려** 형식이 인터페이스 및 경우에 확장 메서드에 대부분 또는 모든 경우에는 확장된 유형으로는 동일한 네임 스페이스에서 확장 메서드를 정의 합니다.  
  
 **X 하지 않으려면** 일반적으로 다른 기능과 관련 된 네임 스페이스에는 기능을 구현 하는 확장 메서드를 정의 합니다. 대신에 속해 있는 기능과 관련 된 네임 스페이스에서 정의 합니다.  
  
 **X 방지** 확장 메서드 \(예: "확장"\)에 네임 스페이스의 일반 이름을 지정 합니다. 설명이 포함 된 이름을 사용 하 여 \(예: "라우팅"\) 대신 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)