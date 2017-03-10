---
title: "WithEvents (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.WithEvents"
  - "WithEvents"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "WithEvents keyword"
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# WithEvents (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 선언된 멤버 변수가 이벤트를 발생시킬 수 있는 클래스 인스턴스를 참조하도록 지정합니다.  
  
## 설명  
 `WithEvents`를 사용하여 변수를 정의하는 경우 메서드에서 `Handles` 키워드를 사용하여 변수 이벤트를 처리하도록 선언적으로 지정할 수 있습니다.  
  
 `WithEvents`는 클래스 또는 모듈 수준에서만 사용할 수 있습니다.  즉, `WithEvents` 변수에 대한 선언 컨텍스트는 클래스이거나 모듈이어야 하며 소스 파일, 네임스페이스, 구조체, 프로시저 등이 될 수 없습니다.  
  
 구조체 멤버에서는 `WithEvents`를 사용할 수 없습니다.  
  
 `WithEvents`를 사용하면 개별 변수만 선언할 수 있고 배열은 선언할 수 없습니다.  
  
## 규칙  
  
-   **요소 형식.** `WithEvents` 변수는 개체 변수로 선언되어야 클래스 인스턴스를 받아들일 수 있으며  `Object`로 선언할 수는 없습니다.  이벤트를 발생시킬 수 있는 특정 클래스로 선언해야 합니다.  
  
 `WithEvents` 한정자는 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) 컨텍스트에서 사용될 수 있습니다.  
  
## 참고 항목  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)