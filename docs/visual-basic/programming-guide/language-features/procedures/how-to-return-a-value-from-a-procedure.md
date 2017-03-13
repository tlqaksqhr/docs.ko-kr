---
title: "How to: Return a Value from a Procedure (Visual Basic) | Microsoft Docs"
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
  - "procedures, returning from"
  - "procedures, returning a value"
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Return a Value from a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function` 프로시저는 `Return` 문을 실행하거나 `Exit Function` 또는 `End Function` 문을 사용하여 호출 코드에 값을 반환합니다.  
  
### Return 문을 사용하여 값을 반환하려면  
  
1.  프로시저의 작업이 완료되는 지점에 `Return` 문을 삽입합니다 .  
  
2.  `Return` 키워드 다음에 호출 코드로 반환할 값을 만드는 식을 지정합니다.  
  
3.  같은 프로시저 내에서 `Return` 문을 두 개 이상 사용할 수 있습니다.  
  
     다음 `Function` 프로시저에서는 직각 삼각형의 가장 긴 변\(빗변\)의 길이를 계산하여 그 값을 호출 코드로 반환합니다.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     다음 예제에서는 `hypotenuse`를 호출하여 반환된 값을 저장하는 일반적인 방법을 보여 줍니다.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### Exit Function 또는 End Function을 사용하여 값을 반환하려면  
  
1.  `Function` 프로시저에서 적어도 한 번은 프로시저의 이름에 값을 할당합니다.  
  
2.  `Exit Function` 또는 `End Function` 문을 실행하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 최근에 프로시저의 이름에 할당된 값을 반환합니다.  
  
3.  같은 프로시저에서 `Exit Function` 문을 두 번 이상 사용할 수 있으며, `Return` 문과 `Exit Function` 문을 같은 프로시저에서 함께 사용할 수도 있습니다.  
  
4.  `End Function` 문은 `Function` 프로시저에서 한 번만 사용할 수 있습니다.  
  
     자세한 내용과 예제는 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)에서 "반환 값"을 참조하십시오.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)