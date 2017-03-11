---
title: "Visual Basic Naming Conventions | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "names, Visual Basic rules"
  - "naming conventions"
  - "naming conventions, Visual Basic"
  - "Visual Basic code, naming conventions"
  - "conventions, Visual Basic coding"
  - "names, naming conventions"
  - "naming conventions, classes"
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Visual Basic Naming Conventions
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic 응용 프로그램의 요소 이름을 지정할 때 해당 이름의 첫 문자는 영문자 또는 밑줄이어야 합니다.  그러나 밑줄로 시작하는 이름은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격이 아닙니다.  
  
 이름을 지정할 때의 권장 사항은 다음과 같습니다.  
  
-   이름의 각 단어는 대문자로 시작합니다\(예: `FindLastRecord`, `RedrawMyForm`\).  
  
-   함수 및 메서드 이름은 동사로 시작합니다\(예: `InitNameArray`, `CloseDialog`\).  
  
-   클래스, 구조체, 모듈 및 속성 이름은 명사로 시작합니다\(예: `EmployeeName` 또는 `CarAccessory`\).  
  
-   인터페이스 이름은 접두사 "I"로 시작한 다음 명사나 명사구를 쓰거나\(예: `IComponent`\) 해당 인터페이스의 동작을 설명하는 형용사를 씁니다\(예: `IPersistable`\).  밑줄은 사용되지 않으며 약어는 혼동의 여지가 있으므로 가급적 사용하지 않습니다.  
  
-   이벤트 처리기의 이름은 해당 이벤트의 형식을 설명하는 명사로 시작한 후 접미사 "`EventHandler`"를 씁니다\(예: `MouseEventHandler`\).  
  
-   이벤트 인수 클래스의 이름에는 접미사 "`EventArgs`"가 포함됩니다.  
  
-   이벤트에 "과거"나 "미래"의 시간 개념이 있으면 현재 또는 과거 시제의 접미사를 사용합니다\(예: "`ControlAdd`", "`ControlAdded`"\).  
  
-   길거나 자주 사용되는 용어의 길이는 약어를 사용하여 적절히 줄입니다\(예: "Hypertext Markup Language" 대신 "HTML" 사용\).  일반적으로 해상도가 낮게 설정된 모니터에서는 32자를 넘는 변수 이름을 읽기가 어렵습니다.  또한 약어는 응용 프로그램 전체에 걸쳐 일치하도록 합니다.  예를 들어, 한 프로젝트에서 "HTML"과 "Hypertext Markup Language"를 혼용하면 혼동이 생길 수 있습니다.  
  
-   외부 범위의 이름과 동일한 이름을 내부 범위에서 사용하지 않도록 합니다.  잘못된 변수에 액세스하면 오류가 발생될 수 있습니다.  변수와 동일한 이름의 키워드 사이에 충돌이 일어나는 경우에는 키워드 앞에 적절한 형식 라이브러리를 사용하여 변수와 키워드를 구별해야 합니다.  예를 들어, `Date`라는 변수가 있는 경우 내장 `Date` 함수는 <xref:System.DateTime.Date%2A?displayProperty=fullName>를 호출해야만 사용할 수 있습니다.  
  
## 참고 항목  
 [Keywords as Element Names in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)