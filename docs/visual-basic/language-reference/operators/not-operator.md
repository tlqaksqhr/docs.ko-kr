---
title: "Not Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.Not"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean expressions, negating"
  - "operators [Visual Basic], bitwise"
  - "negation operator"
  - "inverse bit values in variables"
  - "bitwise operators, NOT operator"
  - "bitwise comparison"
  - "Not operator [Visual Basic]"
  - "logical negation"
  - "operators [Visual Basic], negation"
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Not Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Boolean` 식의 논리 부정 연산을 수행하거나 숫자 식의 비트 부정 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = Not expression  
```  
  
## 요소  
 `result`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
 `expression`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
## 설명  
 다음 표에서는 `Boolean` 식에서 `result`가 결정되는 방식을 보여 줍니다.  
  
|`expression`의 값|`result`의 값|  
|---------------------|-----------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 숫자 식의 경우 `Not` 연산자는 모든 숫자 식의 비트 값을 반전하고 다음 표에 따라 `result`의 해당 비트를 설정합니다.  
  
|`expression`의 비트|`result`의 비트|  
|----------------------|------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계 연산자보다 우선 순위가 낮으므로 올바르게 실행하려면 모든 비트 연산을 괄호로 묶어야 합니다.  
  
## 데이터 형식  
 부울 부정에서는 결과의 데이터 형식이 `Boolean`이고  비트 부정에서는 결과 데이터 형식이 `expression`의 형식과 동일합니다.  그러나 식이 `Decimal` 형식이면 결과는 `Long` 형식입니다.  
  
## 오버로딩  
 `Not` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Not` 연산자를 사용하여 `Boolean` 식의 논리 부정 연산을 수행합니다.  결과는 식의 값을 반대로 나타내는 `Boolean` 값입니다.  
  
 [!CODE [VbVbalrOperators#33](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#33)]  
  
 위 예제의 결과는 각각 `False` 및 `True`가 됩니다.  
  
## 예제  
 다음 예제에서는 `Not` 연산자를 사용하여 숫자 식의 개별 비트에 대한 논리 부정 연산을 수행합니다.  결과 패턴의 비트는 부호 비트를 포함하여 피연산자 패턴에 있는 해당 비트의 반대로 설정됩니다.  
  
 [!CODE [VbVbalrOperators#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#34)]  
  
 위 예제의 결과는 각각 \-11, \-9 및 \-7이 됩니다.  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)