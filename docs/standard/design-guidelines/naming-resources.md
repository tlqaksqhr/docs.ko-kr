---
title: "리소스 명명 | Microsoft Docs"
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
  - "리소스 지역화 된 이름 [.NET Framework]"
  - "지역화를 명명 지침"
  - "리소스 이름"
  - "명명 지침의 전역 응용 프로그램"
  - "국가별 응용 프로그램, 명명 지침"
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 리소스 명명
마치 속성 것 처럼 특정 개체를 통해 지역화 가능한 리소스를 참조할 수 있습니다, 리소스에 대 한 명명 지침 되므로 속성 지침과 비슷합니다.  
  
 **✓ 수행** PascalCasing 리소스 키에 사용 합니다.  
  
 **✓ 수행** 설명 하는 대신 짧은 식별자를 제공 합니다.  
  
 **X 하지 않으려면** 주 CLR 언어의 언어 관련 키워드를 사용 합니다.  
  
 **✓ 수행** 영숫자 문자 및 밑줄만 사용할 리소스 명명에 사용 합니다.  
  
 **✓ 수행** 예외 메시지 리소스에 대 한 다음과 같은 명명 규칙을 사용 합니다.  
  
 예외 형식 이름과 예외의 짧은 식별자는 리소스 식별자 여야 합니다.  
  
 `ArgumentExceptionIllegalCharacters`   
 `ArgumentExceptionInvalidName`   
 `ArgumentExceptionFileNameIsMalformed`  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)