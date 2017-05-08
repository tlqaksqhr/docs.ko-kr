---
title: "필드 디자인 | Microsoft Docs"
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
  - "필드를 디자인 지침"
  - "읽기 전용 필드"
  - "멤버 디자인 지침, 필드"
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 필드 디자인
캡슐화의 원칙 개체 지향 디자인에서 가장 중요 한 개념 중 하나를입니다. 이 원칙는 개체 내에 저장 된 데이터가 해당 개체에만 액세스할 수 있어야 합니다.  
  
 원칙을 해석 하는 유용한 방법 \(이름 또는 유형 변경 됨\) 해당 형식의 필드에 변경할 수는 형식의 멤버에 대 한 이외의 다른 코드를 중단 하지 않고 있도록 형식을 디자인 해야 하는 말은 이 해석을 즉시 모든 필드를 private 이어야 함을 의미 합니다.  
  
 여기서는 이러한 필드 정의 따라 거의 필요가 없으며 변경 때문에이 엄격한 제한이에서 상수 및 정적 읽기 전용 필드 제외 합니다.  
  
 **X 하지 않으려면** 공용 또는 보호 되는 인스턴스 필드를 제공 합니다.  
  
 Public 또는 protected 있도록 하는 대신 필드에 액세스 하기 위한 속성을 제공 해야 합니다.  
  
 **✓ 수행** 상수 필드는 변경 되지 않는 상수를 사용 합니다.  
  
 컴파일러는 호출 코드에 직접 const 필드의 값을 굽습니다. 따라서 호환성 손상 위험 없이 const 값 수 변경할 수 없습니다.  
  
 **✓ 수행** 공용 정적을 사용 하 여 `readonly` 미리 정의 된 개체 인스턴스에 대 한 필드입니다.  
  
 미리 정의 된 형식 인스턴스의 경우 공용으로 읽기 전용 정적 필드 형식 자체의 선언입니다.  
  
 **X 하지 않으려면** 변경할 수 있는 형식의 인스턴스를 할당할 `readonly` 필드입니다.  
  
 변경 가능한 형식은 인스턴스화되는 후 수정할 수 있는 인스턴스 유형이 있습니다. 예를 들어, 배열, 대부분의 컬렉션 및 스트림 형식은 변경할 수 있는, 하지만 <xref:System.Int32?displayProperty=fullName>, <xref:System.Uri?displayProperty=fullName>, 및 <xref:System.String?displayProperty=fullName> 은 모두 변경할 수 없습니다. 참조 형식 필드에 read\-only 한정자에서 대체 될 필드에 저장 된 인스턴스 없지만 필드의 인스턴스 데이터 멤버를 호출 하는 인스턴스 변경 하 여 수정 되지 않도록 방지 하지는 않습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)