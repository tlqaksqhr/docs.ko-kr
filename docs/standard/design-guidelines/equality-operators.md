---
title: "같음 연산자 | Microsoft Docs"
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
  - "클래스 라이브러리 디자인 지침 [.NET Framework] Equals 메서드"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 같음 연산자"
  - "같음 연산자 (= =) [.NET Framework]"
  - "Equals 메서드"
  - "= = 연산자 (같음) [.NET Framework]"
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 같음 연산자
이 섹션 같음 연산자를 오버 로드에 대해 설명 하 고 참조 `operator==` 및 `operator!=` 같음 연산자입니다.  
  
 **X 하지 않으려면** 같음 연산자 및 다른 중 하나를 오버 로드 합니다.  
  
 **✓ 수행** 되도록 <xref:System.Object.Equals%2A?displayProperty=fullName> 와 같음 연산자는 정확히 동일한 의미 체계 및 유사한 성능 특성입니다.  
  
 종종 즉 `Object.Equals` 같음 연산자를 오버 로드 될 때 재정의할 수 해야 합니다.  
  
 **X 방지** 같음 연산자에서 예외를 throw 합니다.  
  
 예를 들어 인수 중 하나를 throw 하지 않고 null 이면 false를 반환 `NullReferenceException`합니다.  
  
## 값 형식에 같음 연산자  
 **✓ 수행** 같음이 의미가 있을 경우에 값 형식에 같음 연산자를 오버 로드 합니다.  
  
 대부분의 프로그래밍 언어에는 기본 구현 된 `operator==` 값 형식에 대 한 합니다.  
  
## 참조 형식에 같음 연산자  
 **X 방지** 변경 가능한 참조 형식에 같음 연산자를 오버 로드 합니다.  
  
 많은 언어에는 참조 형식에 대 한 기본 같음 연산자입니다. 기본 제공 연산자 일반적으로 참조 일치를 구현 하 고 대부분의 개발자는 기본 동작 값을 다르게 변경 되 면 놀랄 키를 누릅니다.  
  
 이 문제는 불변성 더 어렵게 참조 일치와 값 일치의 차이 인식 하기 때문에 변경할 수 없는 참조 형식에 대 한 완화 됩니다.  
  
 **X 방지** 참조 일치 하는 것 보다 크게 느려지지 구현 되는 경우에 참조 형식에 같음 연산자를 오버 로드 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)