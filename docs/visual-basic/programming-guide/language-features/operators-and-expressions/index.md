---
title: "Operators and Expressions in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "operators [Visual Basic], operands"
  - "operators [Visual Basic]"
  - "operands, definition"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "operands"
  - "expressions [Visual Basic]"
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operators and Expressions in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*연산자*는 값을 가지고 있는 하나 이상의 코드 요소에서 연산을 수행하는 코드 요소입니다.  값 요소에는 변수, 상수, 리터럴, 속성, `Function` 및 `Operator` 프로시저의 반환 값, 식 등이 있습니다.  
  
 *식*은 연산자와 결합되어 새 값을 생성하는 일련의 값 요소입니다.  연산자는 계산, 비교 또는 다른 연산을 수행하여 값 요소에 따라 동작합니다.  
  
## 연산자 종류  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 다음과 같은 연산자를 제공합니다.  
  
-   [산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)는 숫자 값의 비트 패턴을 변경하는 것을 포함하여 숫자 값 계산을 수행합니다.  
  
-   [비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)는 두 식을 비교하여 비교 결과를 나타내는 `Boolean` 값을 반환합니다.  
  
-   [연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)는 여러 문자열을 단일 문자열로 조인합니다.  
  
-   [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)는 `Boolean` 또는 숫자 값을 결합하여 동일한 데이터 형식으로 결과 값을 반환합니다.  
  
 연산자와 결합되는 값 요소를 해당 연산자의 *피연산자*라고 합니다.  값 요소와 결합된 연산자\(할당 연산자 제외\)가 식을 구성하고, 이러한 식이 *문*을 구성합니다.  자세한 내용은 [Statements](../../../../visual-basic/programming-guide/language-features/statements.md)을 참조하십시오.  
  
## 식 계산  
 식의 최종 결과는 `Boolean`, `String`, 숫자 형식 등과 같이 익숙한 데이터 형식 값으로 표시됩니다.  
  
 다음은 식의 예입니다.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 다음 예제에서와 같이 단일 식 또는 문에서 여러 가지 연산자를 사용하여 작업을 수행할 수 있습니다.  
  
 [!CODE [VbVbalrOperators#56](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#56)]  
  
 위 예제에서 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 할당 연산자\(`=`\)의 오른쪽에 있는 식에서 연산을 수행한 다음 결과 값을 왼쪽에 있는 `x` 변수에 할당합니다.  식에 사용할 수 있는 연산자 수에는 제한이 없지만 결과를 예측하기 위해 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 알아 두는 것이 필요합니다.  
  
 자세한 내용과 예제는 [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)를 참조하십시오.  
  
## 참고 항목  
 [Operators](../../../../visual-basic/language-reference/operators/index.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)