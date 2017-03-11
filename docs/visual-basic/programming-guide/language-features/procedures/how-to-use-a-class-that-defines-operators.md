---
title: "How to: Use a Class that Defines Operators (Visual Basic) | Microsoft Docs"
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
  - "operator procedures, calling"
  - "procedures, operator"
  - "procedures, calling"
  - "examples [Visual Basic], CType"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "return values, Operator procedures"
  - "operator overloading"
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Use a Class that Defines Operators (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

연산자를 자체적으로 정의하는 클래스나 구조체를 사용하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 해당 연산자에 액세스할 수 있습니다.  
  
 클래스 또는 구조체에서 연산자를 정의하는 것을 연산자 *오버로딩*이라고도 합니다.  
  
## 예제  
 다음 예제에서는 SQL 문자열과 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문자열 사이의 양방향 변환 연산자\([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)\)를 정의하는 SQL 구조체 <xref:System.Data.SqlTypes.SqlString>에 액세스합니다.  `CType(`*SQL string expression*, `String)`을 사용하여 SQL 문자열을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문자열로 변환하고 `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)`을 사용하여 반대 방향으로 변환합니다.  
  
 [!code-vb[VbVbcnProcedures#30](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-use-a-class-that-_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-use-a-class-that-_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString> 구조체는 `String`을 <xref:System.Data.SqlTypes.SqlString>으로, <xref:System.Data.SqlTypes.SqlString>을 `String`으로 변환하는 변환 연산자\([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)\)를 정의합니다.  `title`을 `jobTitle`에 할당하는 문에서는 첫 번째 연산자를 사용하고, <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출에서는 두 번째 연산자를 사용합니다.  
  
## 코드 컴파일  
 사용 중인 클래스나 구조체에서 사용할 연산자를 정의해야 합니다.  연산자를 정의한 클래스나 구조체라도 오버로드에 사용할 수 없는 경우가 있습니다.  사용할 수 있는 연산자의 목록은 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)을 참조하십시오.  
  
 소스 파일의 시작 부분에 SQL 문자열에 적합한 `Imports` 문\(여기서는 <xref:System.Data.SqlTypes>\)을 포함합니다.  
  
 현재 프로젝트에서는 System.Data와 System.XML에 대한 참조를 사용해야 합니다.  
  
## 참고 항목  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)