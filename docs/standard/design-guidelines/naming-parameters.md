---
title: "매개 변수 이름 지정 | Microsoft Docs"
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
  - "매개 변수 이름"
  - "매개 변수 이름 [.NET Framework]"
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 매개 변수 이름 지정
가독성의 이유, 외 시각적 디자인 도구에는 Intellisense 및 클래스 검색 기능을 제공 하는 경우 매개 변수는 설명서 및 디자이너에 표시 되기 때문에 매개 변수 이름에 대 한 지침을 수행 해야 합니다.  
  
 **✓ 수행** camelCasing 매개 변수 이름에 사용할 수 있습니다.  
  
 **✓ 수행** 설명이 포함 된 매개 변수 이름을 사용 합니다.  
  
 **✓ 고려** 매개 변수의 형식 보다는 매개 변수의 의미에 따라 이름을 사용 합니다.  
  
### 연산자 오버 로드 매개 변수 이름 지정  
 **✓ 수행** 사용 `left` 및 `right` 이항 연산자 오버 로드 매개 변수 이름 매개 변수에 아무런 의미가 없는 경우.  
  
 **✓ 수행** 사용 `value` 에 대 한 단항 연산자 오버 로드 매개 변수 이름은 매개 변수에 아무런 의미가 없는 경우.  
  
 **✓ 고려** 연산자에 대 한 의미 있는 이름을 추가 되므로 중요 한 경우에 매개 변수를 재정의 합니다.  
  
 **X 하지 않으려면** 사용 약어 또는 연산자에 대 한 숫자 인덱스 매개 변수 이름을 오버 로드 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)