---
title: "How to: Call an Operator Procedure (Visual Basic) | Microsoft Docs"
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
  - "procedure calls, operator overloading"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "return values, Operator procedures"
  - "overloaded operators, calling"
  - "operator overloading"
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Call an Operator Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식에서 연산자 기호를 사용하여 연산자 프로시저를 호출합니다.  변환 연산자의 경우 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)를 호출하여 값의 데이터 형식을 변환합니다.  
  
 연산자 프로시저는 명시적으로 호출하지 않습니다.  연산자를 사용하는 일반적인 방법으로 할당문이나 식에서 연산자 또는 `CType` 함수를 사용하면 됩니다.  이렇게 하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산자 프로시저를 호출합니다.  
  
 클래스 또는 구조체에서 연산자를 정의하는 것을 연산자 *오버로딩*이라고도 합니다.  
  
### 연산자 프로시저를 호출하려면  
  
1.  일반적인 방법으로 식에서 연산자 기호를 사용합니다.  
  
2.  피연산자의 데이터 형식이 연산자에 적합하고 순서가 올바른지 확인합니다.  
  
3.  연산자가 식의 값에 예상한 대로 기여합니다.  
  
### 변환 연산자 프로시저를 호출하려면  
  
1.  식에서 `CType`을 사용합니다.  
  
2.  피연산자의 데이터 형식이 변환에 적합하고 순서가 올바른지 확인합니다.  
  
3.  `CType`은 변환 연산자 프로시저를 호출하고 변환된 값을 반환합니다.  
  
## 예제  
 다음 예제에서는 두 <xref:System.TimeSpan> 구조체를 만들어 함께 추가한 다음 결과를 세 번째 <xref:System.TimeSpan> 구조체에 저장합니다.  <xref:System.TimeSpan> 구조체는 여러 표준 연산자를 오버로드하도록 연산자 프로시저를 정의합니다.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <xref:System.TimeSpan>은 표준 `+` 연산자를 오버로드하기 때문에 이전 예제에서는 `combinedSpan` 값을 계산할 때 연산자 프로시저를 호출합니다.  
  
 변환 연산자 프로시저 호출에 대한 예제는 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)을 참조하십시오.  
  
## 코드 컴파일  
 사용 중인 클래스나 구조체에서 사용할 연산자를 정의해야 합니다.  
  
## 참고 항목  
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)