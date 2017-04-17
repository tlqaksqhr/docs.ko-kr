---
title: "추상 클래스 디자인 | Microsoft Docs"
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
  - "형식 디자인 지침, 추상 클래스"
  - "추상 클래스를 디자인 지침"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 클래스"
  - "추상 클래스 [.NET Framework]"
  - "클래스 [.NET Framework] 디자인 지침"
  - "클래스 형식 디자인 지침"
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 추상 클래스 디자인
**X 하지 않으려면** 추상 형식에 public 또는 protected 내부 생성자를 정의 합니다.  
  
 생성자는 사용자가 해당 형식의 인스턴스를 만드는 해야 하는 경우에 공용 이어야 합니다. 때문에 추상 형식의 인스턴스를 만들 수 없는 public 생성자가 있는 추상 형식은 않습니다 제대로 디자인 되 고 사용자에 게 잘못 인식.  
  
 **✓ 수행** 추상 클래스에서 보호 된 또는 내부 생성자가 정의 합니다.  
  
 Protected 생성자 문제는 자주 및 단순히 하위 형식을 만들면 자체 초기화 작업을 수행 하기 위해 기본 클래스를 허용 합니다.  
  
 클래스를 정의 하는 어셈블리에는 추상 클래스의 구체적인 구현 제한 하는 내부 생성자를 사용할 수 있습니다.  
  
 **✓ 수행** 배송 된 각 추상 클래스에서 상속 되는 하나 이상의 구체적 형식을 제공 합니다.  
  
 이 사용이 하면 추상 클래스의 디자인 유효성 검사를 수행 합니다. 예를 들어  <xref:System.IO.FileStream?displayProperty=fullName> 의 구현인는 <xref:System.IO.Stream?displayProperty=fullName> 추상 클래스입니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)