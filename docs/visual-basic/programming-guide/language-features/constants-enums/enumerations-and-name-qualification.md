---
title: "Enumerations and Name Qualification (Visual Basic) | Microsoft Docs"
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
  - "declarations, enumerations"
  - "Imports statement, namespace declarations"
  - "declaring namespaces, enumerations"
  - "name collisions"
  - "ambiguous names, enumerations"
  - "enumerations [Visual Basic], name qualification"
  - "names, avoiding conflicts"
  - "namespaces, declaring"
  - "naming conflicts, enumerations"
  - "naming conflicts, qualifying names"
  - "declaring enumerations"
  - "references, enumeration members"
  - "naming conventions, naming conflicts"
  - "declarations, namespaces"
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Enumerations and Name Qualification (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

많은 열거형을 참조할 때, 일반적으로 열거형 이름을 사용하여 해당 멤버 이름을 한정해야 합니다.  예를 들어 `Days` 열거형의 `Sunday` 멤버를 참조하려면 다음 구문을 사용합니다.  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## Imports 문 사용  
 다음 예제와 같이 코드의 네임스페이스 선언 섹션에`Imports` 문을 추가하면 정규화된 이름을 사용하지 않아도 됩니다.  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 `Imports` 문은 참조된 프로젝트 및 어셈블리에서 또는 해당 문이 나타나는 모듈과 동일한 프로젝트 내에서 네임스페이스 이름을 가져옵니다.  이 문이 추가되면 다음과 같이 한정자 없이 열거형 멤버를 참조할 수 있습니다.  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 열거형에서 관련 상수 집합을 구성하면 다른 컨텍스트에서 동일한 상수 이름을 사용할 수 있습니다.  예를 들면 `Days` 및 `WorkDays` 열거형에서 평일 상수에 대해 같은 이름을 사용할 수 있습니다.  열거형에 `Imports` 문을 사용하는 경우 참조가 모호해지지 않도록 주의해야 합니다.  다음 예제를 참조하십시오.  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 `Monday`가 `Days` 열거형과 `Workdays` 열거형 둘 다의 멤버라고 가정하면 이 코드는 컴파일러 오류를 생성하게 됩니다.  각 상수를 참조하는 경우 참조가 모호해지지 않게 하려면 해당 열거형을 사용하여 상수 이름을 한정하십시오.  다음 코드는 `Days` 열거형과 `WorkDays` 열거형의 `Saturday` 상수를 참조합니다.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## 참고 항목  
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)