---
title: "Operator Procedures (Visual Basic) | Microsoft Docs"
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
  - "procedures, operator"
  - "Visual Basic code, operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "overloaded operators"
  - "operator overloading"
  - "operator procedures"
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Operator Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

연산자 프로시저는 정의된 클래스나 구조체에서 표준 연산자\(예: `*`, `<>` 또는 `And`\)의 동작을 정의하는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문입니다.  이를 *연산자 오버로드*라고도 부릅니다.  
  
## 연산자 프로시저를 정의하는 경우  
 클래스나 구조체를 정의한 경우 해당 클래스나 구조체의 형식이 되도록 변수를 선언할 수 있습니다.  경우에 따라 이러한 변수는 식의 일부로서 연산에 사용되어야 합니다.  이렇게 하려면 변수가 연산자의 피연산자여야 합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 자체의 기본 데이터 형식에서만 연산자를 정의합니다.  피연산자 중 하나 또는 둘 다 클래스나 구조체의 형식일 경우 연산자의 동작을 정의할 수 있습니다.  
  
 자세한 내용은 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)을 참조하십시오.  
  
## 연산자 프로시저의 형식  
 연산자 프로시저는 다음 형식 중 하나일 수 있습니다.  
  
-   인수가 클래스나 구조체의 형식인 단항 연산자의 정의  
  
-   적어도 하나 이상의 인수가 클래스나 구조체의 형식인 이항 연산자의 정의  
  
-   인수가 클래스나 구조체의 형식인 변환 연산자의 정의  
  
-   클래스나 구조체의 형식을 반환하는 변환 연산자의 정의  
  
 변환 연산자는 항상 단항이며 정의하려는 연산자로서 항상 `CType`이 사용됩니다.  
  
## 선언 구문  
 연산자 프로시저를 선언하는 구문은 다음과 같습니다.  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`   ``  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 `Widening` 또는 `Narrowing` 키워드는 형식 변환 연산자에서만 사용합니다.  형식 변환 연산자의 경우 연산자 기호는 항상 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)입니다.  
  
 이항 연산자를 정의하기 위해 두 개의 피연산자를 선언하고 형식 변환 연산자를 비롯한 단항 연산자를 정의하기 위해 하나의 피연산자를 선언합니다.  모든 피연산자는 `ByVal`로 선언되어야 합니다.  
  
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)에 대해 매개 변수를 선언할 때와 같은 방법으로 각 피연산자를 선언합니다.  
  
### 데이터 형식  
 정의된 클래스나 구조체에서 연산자를 정의하므로 적어도 피연산자 중 하나가 해당 클래스나 구조체의 데이터 형식이어야 합니다.  형식 변환 연산자의 경우 피연산자 또는 반환 형식이 클래스나 구조체의 데이터 형식이어야 합니다.  
  
 자세한 내용은 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)을 참조하십시오.  
  
## 호출 구문  
 식에서 연산자 기호를 사용하여 연산자 프로시저를 암시적으로 호출합니다.  미리 정의된 연산자의 경우와 같은 방법으로 피연산자를 제공합니다.  
  
 연산자 프로시저를 암시적으로 호출하는 구문은 다음과 같습니다.  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`  
  
### 선언과 호출에 대한 설명  
 다음 구조체는 부호 있는 128비트 정수 값을 상위 및 하위 구성 부분으로 저장합니다.  `+` 연산자를 정의하여 두 개의 `veryLong` 값을 추가하고 결과 `veryLong` 값을 생성합니다.  
  
 [!code-vb[VbVbcnProcedures#23](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/operator-procedures_1.vb)]  
  
 다음 예제에서는 `veryLong`에 정의된 일반적인 `+` 연산자 호출을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#24](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/operator-procedures_2.vb)]  
  
 자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)를 참조하십시오.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)