---
title: "How to: Declare a Property with Mixed Access Levels (Visual Basic) | Microsoft Docs"
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
  - "access levels, properties"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "mixed access levels"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], access levels"
  - "Property statement, declaring mixed access levels"
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Declare a Property with Mixed Access Levels (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성에 대한 `Get` 프로시저와 `Set` 프로시저의 액세스 수준을 서로 다르게 하려면 `Property` 문에서는 좀 더 관대한 수준을 사용하고 `Get` 또는 `Set` 문에서는 좀 더 제한적인 수준을 사용하면 됩니다.  코드의 특정 구성 요소에서는 속성 값을 가져올 수 있도록 하고 다른 구성 요소에서는 속성 값을 변경할 수 있도록 하려면 해당 속성에 대해 액세스 수준을 혼합하여 사용합니다.  
  
 액세스 수준에 대한 자세한 내용은 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
### 액세스 수준이 혼합된 속성을 선언하려면  
  
1.  속성을 일반적인 방식으로 선언하고 `Property` 문에서 덜 제한적인 액세스 수준\(예: `Public`\)을 지정합니다.  
  
2.  보다 제한적인 액세스 수준\(예: `Friend`\)을 지정하는 `Get` 또는 `Set` 프로시저를 선언합니다.  
  
3.  다른 속성 프로시저에는 액세스 수준을 지정하지 않습니다.  해당 프로시저에 `Property` 문에서 액세스 수준이 선언된 것으로 가정합니다.  속성 프로시저 중 하나에 대해서만 액세스를 제한할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#10](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-declare-a-propert_1.vb)]  
  
     위 예제에서 `Get` 프로시저에는 속성 자체와 동일한 `Protected` 액세스가 지정되지만, `Set` 프로시저에는 `Private` 액세스가 지정됩니다.  `employee`에서 파생된 클래스는 `salary` 값을 읽을 수 있지만 값 설정은 `employee` 클래스만이 할 수 있습니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)