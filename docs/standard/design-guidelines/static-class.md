---
title: "정적 클래스 디자인 | Microsoft Docs"
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
  - "정적 클래스 형식 디자인 지침"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 클래스"
  - "클래스 [.NET Framework] 정적"
  - "정적 클래스 [.NET Framework]"
  - "클래스 [.NET Framework] 디자인 지침"
  - "클래스 형식 디자인 지침"
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 정적 클래스 디자인
정적 클래스는 정적 멤버만 포함 하는 클래스로 정의 됩니다 \(에서 상속 된 인스턴스 멤버 외에도 물론 <xref:System.Object?displayProperty=fullName> 와 전용 생성자 수 있음\). 일부 언어는 정적 클래스에 대 한 기본 제공 지원을 제공 합니다. C\# 2.0 이상에서는 클래스를 정적를 선언 하는 봉인 된 추상 하 고, 없는 인스턴스 멤버를 재정의 하거나 선언 합니다.  
  
 정적 클래스는 순수 개체 지향 설계과 단순성을 절충입니다. 다른 작업에 대 한 바로 가기를 제공 하는 데 흔히 사용 \(예: <xref:System.IO.File?displayProperty=fullName>\), 소유자의 확장 메서드 또는 전체 개체 지향 래퍼 릴리스됩니다 되지 않는 기능입니다. \(같은 <xref:System.Environment?displayProperty=fullName>\).  
  
 **✓ 수행** 정적 클래스를 제한적으로 사용 합니다.  
  
 정적 클래스는 개체 지향 프레임 워크의 핵심에 대 한 지원 클래스로만 사용 해야 합니다.  
  
 **X 하지 않으려면** 를 기타 버킷으로 정적 클래스를 처리 합니다.  
  
 **X 하지 않으려면** 선언 또는 정적 클래스의 인스턴스 멤버를 재정의 합니다.  
  
 **✓ 수행** 봉인, 추상으로 정적 클래스를 선언 하 고 정적 클래스에 대 한 기본 제공 지원 프로그래밍 언어에 없는 경우 개인 인스턴스 생성자를 추가 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)