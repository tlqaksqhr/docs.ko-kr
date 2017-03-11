---
title: "How to: Put a Value in a Property (Visual Basic) | Microsoft Docs"
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
  - "property values"
  - "Visual Basic code, procedures"
  - "values, properties"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], values"
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Put a Value in a Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

대입문의 왼쪽에 속성 이름을 입력하여 속성에 값을 저장할 수 있습니다.  
  
 속성의 `Set` 프로시저에서 값을 저장하지만 사용자가 이 프로시저 이름을 명시적으로 호출하지는 않습니다.  사용자는 마치 변수를 사용하는 것처럼 속성을 사용하고  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 속성의 프로시저가 호출됩니다.  
  
### 속성에 값을 저장하려면  
  
1.  대입문의 왼쪽에 속성 이름을 입력합니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] `TimeOfDay` 속성 값을 정오로 설정합니다. 이때 해당 `Set` 프로시저가 암시적으로 호출됩니다.  
  
     [!code-vb[VbVbcnProcedures#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-put-a-value-in-a-_1.vb)]  
  
2.  속성에 인수가 사용되는 경우 속성 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  속성에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
4.  이렇게 하면 대입문의 오른쪽에 생성된 값이 속성에 저장됩니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)