---
title: "구조체 디자인 | Microsoft Docs"
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
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 구조"
  - "구조체 할당 취소"
  - "구조체 할당"
  - "값 형식 구조"
  - "구조 디자인"
  - "구조 형식 디자인 지침"
  - "구조체 [.NET Framework] 디자인 지침"
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 구조체 디자인
범용 값 형식은 가장 자주 구조체를 해당 C\# 키워드 라고 합니다. 이 섹션 일반 구조체 디자인에 대 한 지침을 제공합니다.  
  
 **X 하지 않으려면** 구조체에 대 한 기본 생성자를 제공 합니다.  
  
 배열의 각 항목에는 생성자를 실행 하지 않고도 만들 구조체의 배열을이 지침을 따르면 있습니다. C\# 없도록 기본 생성자가 하는 구조체를 확인 합니다.  
  
 **X 하지 않으려면** 변경할 수 있는 값 형식을 정의 합니다.  
  
 변경할 수 있는 값 형식에는 몇 가지 문제가 있습니다. 예를 들어, 속성 getter 값 형식을 반환 하는 경우 호출자는 복사본을 받습니다. 복사본 암시적으로 만들어지기 때문에 개발자는 복사 및 원래 값이 아니라 변경 된 인식 아닐 수도 있습니다. 또한 일부 언어 \(특히에서 동적 언어\) 문제가 때문에 변경할 수 있는 값 형식을 사용 하 여 지역 변수를 역참조 시도, 수행 하면 복사 합니다.  
  
 **✓ 수행** 있는지 확인 하세요. 모든 인스턴스 데이터를 상태 0으로 설정 되어 false 또는 null 적절 하 게 유효 합니다.  
  
 이렇게 하면 실수로 잘못 된 인스턴스 만들기를 구조체의 배열을 만들어질 때 않습니다.  
  
 **✓ 수행** 구현 <xref:System.IEquatable%601> 값 형식에 있습니다.  
  
 <xref:System.Object.Equals%2A?displayProperty=fullName> 리플렉션을 사용 하 여 해당 기본 구현은 매우 효율적 이므로 및 값 형식에서 메서드를 boxing을 사용 하면 됩니다.<xref:System.IEquatable%601.Equals%2A> 훨씬 더 나은 성능을 얻을 수 및 boxing이 발생 하지 것입니다 있도록 구현할 수 있습니다.  
  
 **X 하지 않으려면** 명시적으로 확장 <xref:System.ValueType>합니다. 사실 대부분의 언어 이러한 문제를 방지 합니다.  
  
 일반적으로 구조체 매우 유용할 수 있지만 자주 박스형 하지 작은를 변경할 수 없는 단일 값만 사용 해야 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [클래스와 구조체 간의 선택](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)