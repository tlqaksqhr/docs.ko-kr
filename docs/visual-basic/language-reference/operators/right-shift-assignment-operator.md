---
title: "&gt;&gt;= Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.>>="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "operator >>= [Visual Basic]"
  - "compound assignment statements"
  - ">>= operator [Visual Basic]"
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &gt;&gt;= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수 또는 속성 값에 대해 산술 오른쪽 시프트 연산을 수행하고 결과를 다시 변수 또는 속성에 할당합니다.  
  
## 구문  
  
```  
  
variableorproperty >>= amount  
```  
  
## 요소  
 `variableorproperty`  
 필수 요소.  정수 계열 형식\(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` 또는 `ULong`\)의 변수 또는 속성입니다.  
  
 `amount`  
 필수 요소.  `Integer`로 확장되는 데이터 형식의 숫자 식입니다.  
  
## 설명  
 `>>=` 연산자의 왼쪽 요소는 단순 스칼라 변수, 속성 또는 배열 요소가 될 수 있습니다.  변수나 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 될 수 없습니다.  
  
 `>>=`연산자를 먼저 수행 산술 오른쪽이동하다를변수또는속성값을 합니다.   연산자는 다음 다시변수또는속성에 해당 연산의 결과를 할당합니다.  
  
 산술 시프트 연산은 순환되지 않습니다. 즉, 한 쪽 끝에서 이동하여 빠져나가는 비트가 다른 쪽 끝으로 다시 들어가지 않습니다.  산술 오른쪽 시프트 연산에서는 맨 오른쪽 비트 위치를 벗어나 이동하는 비트는 무시되고 맨 왼쪽 비트는 왼쪽의 비워진 비트 위치로 전파됩니다.  즉, `variableorproperty`에 음수 값이 있으면 비워진 위치는 1로 설정됩니다.  `variableorproperty`가 양수이거나 해당 데이터 형식이 부호 없는 형식인 경우에는 비워진 위치가 0으로 설정됩니다.  
  
## 오버로딩  
 [\>\> Operator](../Topic/%3E%3E%20Operator%20\(Visual%20Basic\).md)는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `>>` 연산자를 오버로드하면 `>>=` 연산자의 동작이 영향을 받습니다.  코드에서 `>>`를 오버로드하는 클래스나 구조체에 대해 `>>=`을 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `>>=` 연산자를 사용하여 `Integer` 변수의 비트 패턴을 지정한 양만큼 오른쪽으로 이동하고 결과를 변수에 할당합니다.  
  
 [!CODE [VbVbalrOperators#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#15)]  
  
## 참고 항목  
 [\>\> Operator](../Topic/%3E%3E%20Operator%20\(Visual%20Basic\).md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Bit Shift Operators](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)