---
title: "멤버 디자인 지침 | Microsoft Docs"
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
  - "멤버 디자인 지침에 대 한 멤버 디자인 지침 [.NET Framework]"
  - "멤버 [.NET Framework] 디자인 지침"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 멤버"
  - "멤버 디자인 지침 [.NET Framework]"
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 멤버 디자인 지침
메서드, 속성, 이벤트, 생성자 및 필드 통칭 하 여 구성원 이라고 합니다. 멤버는 궁극적으로 프레임 워크 기능 프레임 워크의 최종 사용자에 게 노출 되는 의미입니다.  
  
 멤버 가상 또는 비가상, 구체적인 또는 추상 정적 또는 인스턴스 수 및 액세스 가능성의 다양 한 범위를 가질 수 있습니다. 이 모든 다양이 한 놀라운 표현을 제공 하지만 동시에 프레임 워크 디자이너 일부에 대해서는 주의 해야 합니다.  
  
 이 장에서 모든 형식의 멤버를 디자인할 때 따라야 할 기본적인 지침을 제공 합니다.  
  
## 단원 내용  
 [멤버 오버 로드](../../../docs/standard/design-guidelines/member-overloading.md)  
 [속성 디자인](../../../docs/standard/design-guidelines/property.md)  
 [생성자 디자인](../../../docs/standard/design-guidelines/constructor.md)  
 [이벤트 디자인](../../../docs/standard/design-guidelines/event.md)  
 [필드 디자인](../../../docs/standard/design-guidelines/field.md)  
 [확장명 메서드](../../../docs/standard/design-guidelines/extension-methods.md)  
 [연산자 오버 로드](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [매개 변수 디자인](../../../docs/standard/design-guidelines/parameter-design.md)  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)