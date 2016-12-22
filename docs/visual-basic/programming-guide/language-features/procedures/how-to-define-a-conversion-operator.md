---
title: "How to: Define a Conversion Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, defining"
  - "operators [Visual Basic], defining"
  - "procedures, operator"
  - "operators [Visual Basic], overloading"
  - "return values, Operator procedures"
  - "operator overloading"
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Define a Conversion Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

클래스나 구조체를 정의한 경우 클래스 또는 구조체의 형식과 다른 데이터 형식\(예: `Integer`, `Double` 또는 `String`\) 간에 형식 변환 연산자를 정의할 수 있습니다.  
  
 이때 형식 변환을 클래스 또는 구조체 내의 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 프로시저로 정의합니다.  모든 변환 프로시저는 `Public Shared`여야 하고 각 프로시저는 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) 또는 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)을 지정해야 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의하는 것을 연산자 *오버로딩*이라고도 합니다.  
  
## 예제  
 다음 예제에서는  `digit`  및 `Byte` 구조체 간에 변환 연산자를 정의합니다.  
  
 [!code-vb[VbVbcnProcedures#27](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 다음 코드를 사용하여 `digit` 구조체를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#28](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## 참고 항목  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Call an Operator Procedure](../Topic/How%20to:%20Call%20an%20Operator%20Procedure%20\(Visual%20Basic\).md)   
 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)