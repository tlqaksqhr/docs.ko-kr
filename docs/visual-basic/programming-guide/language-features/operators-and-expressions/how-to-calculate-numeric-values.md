---
title: "How to: Calculate Numeric Values (Visual Basic) | Microsoft Docs"
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
  - "operator precedence"
  - "operators [Visual Basic]"
  - "expressions [Visual Basic], numeric"
  - "calculations, numeric expressions"
  - "precedence, of operators"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "numeric expressions"
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Calculate Numeric Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

숫자 식을 사용하여 숫자 값을 계산할 수 있습니다.  *숫자 식*은 숫자 값을 나타내는 리터럴, 상수, 변수 및 이러한 값에 따라 동작하는 연산자를 포함하는 식입니다.  
  
## 숫자 값 계산  
  
#### 숫자 값을 계산하려면  
  
-   하나 이상의 숫자 리터럴, 상수 및 변수를 숫자 식에 결합합니다.  다음 예제에서는 유효한 숫자 식을 보여 줍니다.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     처음 세 줄은 리터럴, 상수 및 변수를 나타냅니다.  각 줄은 그 자체로 유효한 숫자 식을 구성합니다.  마지막 줄은 변수와 두 리터럴의 조합을 나타냅니다.  
  
     숫자 식 자체만으로 완벽한 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문을 구성할 수는 없습니다.  식을 전체 문에 포함해야 합니다.  
  
#### 숫자 값을 저장하려면  
  
-   다음 예제에서와 같이 할당문을 사용하여 숫자 식으로 나타내는 값을 변수에 할당할 수 있습니다.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-calculate-numeric_1.vb)]  
  
     위 예제에서 같음 연산자\(`=`\)의 오른쪽에 있는 식의 값이 왼쪽에 있는 변수 `j`에 할당되므로 `j`는 276으로 계산됩니다.  
  
     자세한 내용은 [Statements](../../../../visual-basic/language-reference/statements/index.md)을 참조하십시오.  
  
## 다중 연산자  
 숫자 식에 연산자가 둘 이상 포함되어 있는 경우 연산자 계산 순서는 연산자 우선 순위 규칙에 따라 결정됩니다.  연산자 우선 순위 규칙을 무시하려면 위의 예제와 같이 식을 괄호로 묶습니다. 그러면 괄호 안의 식이 가장 먼저 계산됩니다.  
  
#### 일반 연산자 우선 순위를 재정의하려면  
  
-   가장 먼저 수행하려는 연산을 괄호로 묶습니다.  다음 예제에서는 동일한 연산자와 피연산자를 사용한 서로 다른 두 가지 결과를 보여 줍니다.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-calculate-numeric_2.vb)]  
  
     위 예제에서는 `(67 + i)`의 괄호가 일반 우선 순위를 무시하기 때문에 `j`에 대한 계산에서 더하기 연산자\(`+`\)가 가장 먼저 수행되므로 `j`에 할당되는 값은 276\(4x69\)입니다.  `k`에 대한 계산에서는 일반 우선 순위\(`*`를 `+`보다 먼저 수행\)에 따라 연산자를 수행하므로 `k`에 할당되는 값은 270\(268\+2\)입니다.  
  
     자세한 내용은 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 참조하십시오.  
  
## 참고 항목  
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)