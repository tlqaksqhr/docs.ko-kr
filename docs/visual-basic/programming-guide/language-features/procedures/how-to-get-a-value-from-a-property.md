---
title: "How to: Get a Value from a Property (Visual Basic) | Microsoft Docs"
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
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Get a Value from a Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식에 속성 이름을 포함하여 속성 값을 가져올 수 있습니다.  
  
 속성의 `Get` 프로시저에서 값을 가져오지만 사용자가 이 프로시저 이름을 명시적으로 호출하지는 않습니다.  사용자는 마치 변수를 사용하는 것처럼 속성을 사용하고  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 속성의 프로시저가 호출됩니다.  
  
### 속성에서 값을 가져오려면  
  
1.  변수 이름을 사용할 때와 같은 방법으로 식에서 속성 이름을 사용합니다.  변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.  
  
     또는  
  
     대입문에서 등호 기호\(`=`\) 뒤에 속성 이름을 입력합니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] `Now` 속성 값을 읽습니다. 이때 해당 `Get` 프로시저가 암시적으로 호출됩니다.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  속성에 인수가 사용되는 경우 속성 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  속성에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
 속성 값은 변수 또는 상수와 같은 방식으로 식에 사용된 다음 대입문 왼쪽의 변수 또는 속성에 저장됩니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)