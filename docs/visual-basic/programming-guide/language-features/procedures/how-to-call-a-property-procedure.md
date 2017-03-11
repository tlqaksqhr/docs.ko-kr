---
title: "How to: Call a Property Procedure (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "procedures, calling"
  - "properties [Visual Basic], property procedures"
  - "procedure calls, property procedures"
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Call a Property Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값을 속성에 저장하거나 해당 값을 검색하여 속성 프로시저를 호출합니다.  변수에 액세스할 때와 같은 방법으로 속성에 액세스할 수 있습니다.  
  
 속성의 `Set` 프로시저는 값을 저장하며 속성의 `Get` 프로시저는 값을 검색합니다.  그러나 사용자가 이러한 프로시저 이름을 명시적으로 호출하지는 않습니다.  변수의 값을 저장하거나 검색할 때와 마찬가지로 대입문이나 식에서 속성을 사용합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 속성의 프로시저가 호출됩니다.  
  
### 속성의 Get 프로시저를 호출하려면  
  
1.  변수 이름을 사용할 때와 같은 방법으로 식에서 속성 이름을 사용합니다.  변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.  
  
     또는  
  
     대입문에서 등호 기호\(`=`\) 뒤에 속성 이름을 입력합니다.  
  
     다음 예제에서는 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> 속성 값을 읽습니다. 이때 해당 `Get` 프로시저가 암시적으로 호출됩니다.  
  
     [!code-vb[VbVbalrDateProperties#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/VbVbalrDateProperties/Module1.vb#4)]  
  
2.  속성에 인수가 사용되는 경우 속성 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  속성에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
 속성 값은 변수 또는 상수와 같은 방식으로 식에 사용된 다음 대입문 왼쪽의 변수 또는 속성에 저장됩니다.  
  
### 속성의 Set 프로시저를 호출하려면  
  
1.  대입문의 왼쪽에 속성 이름을 입력합니다.  
  
     다음 예제에서는 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> 속성 값을 설정합니다. 이때 `Set` 프로시저가 암시적으로 호출됩니다.  
  
     [!code-vb[VbVbcnProcedures#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-a-property-p_2.vb)]  
  
2.  속성에 인수가 사용되는 경우 속성 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  속성에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
 이렇게 하면 대입문의 오른쪽에 생성된 값이 속성에 저장됩니다.  
  
## 참고 항목  
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)   
 [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)