---
title: "&amp; Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "And (&) operator"
  - "ampersand operator (&)"
  - "& operator"
  - "concatenation operators, syntax"
  - "strings [Visual Basic], concatenating"
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &amp; Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 식의 문자열을 연결합니다.  
  
## 구문  
  
```  
  
result = expression1 & expression2  
```  
  
## 요소  
 `result`  
 필수 요소.  임의의 `String` 또는 `Object`변수입니다.  
  
 `expression1`  
 필수 요소.  `String`으로 확장되는 데이터 형식의 식입니다.  
  
 `expression2`  
 필수 요소.  `String`으로 확장되는 데이터 형식의 식입니다.  
  
## 설명  
 `expression1`이나 `expression2`의 데이터 형식이 `String`이 아니지만 `String`으로 확대 변환되는 경우에는 `String`으로 변환됩니다.  데이터 형식 중 하나가 `String`으로 확대 변환되지 않으면 컴파일러에서 오류가 생성됩니다.  
  
 `result`의 데이터 형식은 `String`입니다.  두 식 중 하나 또는 모두가 [Nothing](../../../visual-basic/language-reference/nothing.md)이거나 <xref:System.DBNull.Value?displayProperty=fullName> 값으로 계산되면 "" 값을 가진 문자열로 처리됩니다.  
  
> [!NOTE]
>  `&` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
> [!NOTE]
>  앰퍼샌드\(&\) 문자는 변수를 형식 `Long`으로 식별하는 데 사용할 수도 있습니다.  자세한 내용은 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `&` 연산자를 사용하여 문자열을 연결합니다.  결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## 참고 항목  
 [&\= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Concatenation Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)