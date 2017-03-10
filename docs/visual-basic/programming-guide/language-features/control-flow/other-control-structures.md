---
title: "Other Control Structures (Visual Basic) | Microsoft Docs"
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
  - "statements [Visual Basic], control flow"
  - "control structures"
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Other Control Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 리소스를 삭제하거나 개체 참조의 반복 횟수를 줄이는 데 유용한 제어 구조를 제공합니다.  
  
## Using...End Using 구문  
 `Using...End Using` 구문은 SQL 연결 등의 리소스를 사용할 수 있는 문 블록을 구성합니다.  `Using` 문을 사용하여 리소스를 선택적으로 가져올 수 있습니다.  `Using` 블록을 종료하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 다른 코드에서 사용할 수 있도록 리소스를 자동으로 삭제합니다.  리소스는 로컬이며 삭제할 수 있어야 합니다.  자세한 내용은 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하십시오.  
  
## With...End With 구문  
 `With...End With` 구문을 사용하면 개체 참조를 한 번만 지정한 다음 해당 멤버에 액세스하는 여러 문을 실행할 수 있습니다.  이렇게 하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 해당 멤버에 액세스하는 각 문에 대해 참조를 다시 설정할 필요가 없으므로 코드가 간단해지고 성능이 향상됩니다.  자세한 내용은 [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)을 참조하십시오.  
  
## 참고 항목  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)