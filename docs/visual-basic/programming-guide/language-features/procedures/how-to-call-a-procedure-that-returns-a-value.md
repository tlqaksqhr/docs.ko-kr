---
title: "How to: Call a Procedure That Returns a Value (Visual Basic) | Microsoft Docs"
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
  - "procedure calls, returning values"
  - "Visual Basic code, procedures"
  - "procedures, calling"
  - "procedures, returning a value"
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Call a Procedure That Returns a Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function` 프로시저는 호출 코드에 값을 반환합니다.  대입문의 오른쪽이나 식에 프로시저 이름과 인수를 포함하여 프로시저를 호출합니다.  
  
### 식에서 Function 프로시저를 호출하려면  
  
1.  변수를 사용할 때와 같은 방법으로 `Function` 프로시저를 사용합니다.  식에서 변수나 상수를 사용할 수 있는 모든 위치에 `Function` 프로시저 호출을 사용할 수 있습니다.  
  
2.  프로시저 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  그러나 괄호를 사용하면 코드가 읽기 쉬워집니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  `Function` 프로시저에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
     또는 이름으로 하나 이상의 인수를 전달할 수도 있습니다.  자세한 내용은 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)을 참조하십시오.  
  
4.  프로시저에서 반환된 값은 변수나 상수 값의 경우와 마찬가지로 식에서 사용됩니다.  
  
### 대입문에서 Function 프로시저를 호출하려면  
  
1.  대입문에서 등호 기호\(`=`\) 다음에 `Function` 프로시저 이름을 입력합니다.  
  
2.  프로시저 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  그러나 괄호를 사용하면 코드가 읽기 쉬워집니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  인수를 이름으로 전달하는 경우가 아니라면 `Function` 프로시저에서 정의하는 해당 매개 변수의 순서와 동일한 순서로 인수를 지정해야 합니다.  
  
4.  프로시저에서 반환되는 값은 대입문의 왼쪽에 있는 변수나 속성에 저장됩니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>를 호출하여 운영 체제 환경 변수의 값을 가져옵니다.  첫째 줄에서는 `Environ`을 식에서 호출하고 둘째 줄에서는 이를 대입문에서 호출합니다.  `Environ`에서는 변수 이름이 유일한 인수로 사용되며,  변수의 값이 호출 코드로 반환됩니다.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## 참고 항목  
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Return a Value from a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)