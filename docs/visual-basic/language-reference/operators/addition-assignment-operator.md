---
title: "+= Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.+="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "+= operator [Visual Basic]"
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "+= operator [Visual Basic], appending strings"
  - "compound assignment statements"
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# += Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

숫자 식의 값을 숫자 변수 또는 속성 값과 더하여 결과를 해당 변수 또는 속성에 할당합니다.  `String` 식을 `String` 변수나 속성에 연결하고 그 결과를 해당 변수나 속성에 할당하는 데도 사용할 수 있습니다.  
  
## 구문  
  
```  
  
variableorproperty += expression  
```  
  
## 요소  
 `variableorproperty`  
 필수 요소.  임의의 숫자 또는 `String` 변수나 속성입니다.  
  
 `expression`  
 필수 요소.  임의의 숫자 식 또는 `String` 식입니다.  
  
## 설명  
 `+=` 연산자의 왼쪽 요소는 단순 스칼라 변수, 속성 또는 배열 요소가 될 수 있습니다.  변수나 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 될 수 없습니다.  
  
 `+=` 연산자는 오른쪽에 변수나 속성의 왼쪽에 있는 값을 추가 하 고 결과를 변수 또는 속성의 왼쪽에 할당 됩니다.  `+=` 연산자 사용 수도 연결 하는 `String` 식의 오른쪽에는 `String` 변수 또는 속성에는 왼쪽이 고 결과를 변수에 할당 하거나 속성의 왼쪽에.  
  
> [!NOTE]
>  `+=` 연산자를 사용하는 경우 더하기 또는 문자열 연결 연산의 발생 여부를 확인할 수 없습니다.  그러나 `&=` 연산자를 사용하여 연결하면 이러한 모호성을 제거할 수 있고 자체 문서 작성 코드를 사용할 수 있습니다.  
  
 컴파일 환경에서 엄격한 의미 체계를 적용하는 경우 이 할당 연산자는 암시적으로 확대 변환을 수행합니다.  이러한 변환에 대한 자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  엄격한 의미 체계와 관대한 의미 체계에 대한 자세한 내용은 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 참조하십시오.  
  
 관대한 의미 체계가 허용되는 경우 `+=` 연산자는 `+` 연산자가 수행하는 변환과 동일한 여러 가지 문자열 및 숫자 변환을 암시적으로 수행합니다.  이러한 변환에 대한 자세한 내용은 [\+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md)를 참조하십시오.  
  
## 오버로딩  
 `+` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `+` 연산자를 오버로드하면 `+=` 연산자의 동작이 영향을 받습니다.  코드에서 `+`를 오버로드하는 클래스나 구조체에 대해 `+=`을 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `+=` 연산자를 사용하여 변수의 값을 다른 변수의 값에 결합합니다.  첫 번째 부분에서는 `+=`을 숫자 변수와 함께 사용하여 값을 다른 값에 더합니다.  두 번째 부분에서는 `+=`을 `String` 변수와 함께 사용하여 값을 다른 값에 연결합니다.  두 경우 모두 결과를 첫째 변수에 할당합니다.  
  
 [!CODE [VbVbalrOperators#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#7)]  
  
 [!CODE [VbVbalrOperators#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#8)]  
  
 `num1`의 값은 13이 되고 `str1`의 값은 "103"이 됩니다.  
  
## 참고 항목  
 [\+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Concatenation Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)