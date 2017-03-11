---
title: "How to: Define an Operator (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "operators [Visual Basic], defining"
  - "procedures, operator"
  - "Visual Basic code, operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "operator procedures, about operator procedures"
  - "return values, Operator procedures"
  - "operator overloading"
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Define an Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스나 구조체를 정의한 경우 두 피연산자 중 하나 또는 모두가 클래스나 구조체의 형식일 때 수행할 표준 연산자\(예: `*`, `<>` 또는 `And`\) 동작을 정의할 수 있습니다.  
  
 표준 연산자를 클래스나 구조체 내의 연산자 프로시저로 정의합니다.  모든 연산자 프로시저는 `Public` `Shared`여야 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의하는 것을 연산자 *오버로딩*이라고도 합니다.  
  
## 예제  
 다음 예제에서는 `height`라는 구조체에 대한 `+` 연산자를 정의합니다.  이 구조체는 피트와 인치로 측정된 높이를 사용합니다.  1*인치*는 2.54센티미터이고 1*피트*는 12인치입니다.  정규화된 값\(인치 \< 12.0\)을 유지하기 위해 생성자는 *modulo* 12 산술 연산을 수행합니다.  `+` 연산자는 생성자를 사용하여 정규화된 값을 생성합니다.  
  
 [!code-vb[VbVbcnProcedures#25](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-define-an-operator_1.vb)]  
  
 다음 코드를 사용하여  `height`  구조체를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#26](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-define-an-operator_2.vb)]  
  
 자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)를 참조하십시오.  
  
## 참고 항목  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)