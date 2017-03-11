---
title: "Implements Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ImplementsClause"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface implementation, reimplementation"
  - "interface members, reimplementation"
  - "interface members, Implements keyword"
  - "interface members"
  - "members, reimplementation"
  - "interface implementation, Implements keyword"
  - "interface members, implementing"
  - "Implements keyword"
  - "Implements statement, about Implements"
  - "members, implementing"
  - "members, Implements keyword"
  - "reimplementation"
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Implements Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스 또는 구조체 멤버가 인터페이스에 정의된 멤버에 대한 구현을 제공하는 것을 나타냅니다.  
  
## 설명  
 `Implements` 키워드는 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)과 동일하지 않습니다.  `Implements` 문을 사용하여 클래스나 구조체가 하나 이상의 인터페이스를 구현하도록 지정한 다음 각 멤버에 대해 `Implements` 키워드를 사용하여 각 멤버가 구현하는 인터페이스와 멤버를 지정할 수 있습니다.  
  
 클래스나 구조체가 인터페이스를 구현할 때는 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)이나 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) 바로 다음에 `Implements` 문을 포함해야 하고 인터페이스에서 정의한 모든 멤버를 구현해야 합니다.  
  
## 다시 구현  
 파생 클래스에서는 기본 클래스에 의해 이미 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.  이는 다음과 같은 점에서 기본 클래스 멤버를 재정의하는 것과 다릅니다.  
  
-   기본 클래스 멤버는 다시 구현되기 위해 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)일 필요가 없습니다.  
  
-   멤버를 다른 이름으로 다시 구현할 수 있습니다.  
  
 `Implements` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)