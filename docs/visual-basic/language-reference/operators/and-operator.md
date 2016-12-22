---
title: "And Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.And"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operators [Visual Basic], bitwise"
  - "logical conjunction"
  - "bitwise AND operator [Visual Basic]"
  - "conjunction operator"
  - "And operator [Visual Basic]"
  - "bitwise operators, AND operator"
  - "operators [Visual Basic], conjunction"
  - "bitwise comparison"
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# And Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 `Boolean` 식의 논리곱 연산을 수행하거나 두 숫자 식에서 비트 논리곱 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 And expression2  
```  
  
## 요소  
 `result`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  부울 비교의 경우 `result`는 두 `Boolean` 값의 논리곱입니다.  비트 연산의 경우 `result`는 두 개의 숫자 비트 패턴의 비트 논리곱을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
## 설명  
 부울 비교의 경우 `result`는 `expression1` 및 `expression2`가 모두 `True`인 경우에만 `True`입니다.  다음 표에서는 `result`가 결정되는 방식을 보여 줍니다.  
  
|`expression1`의 값|`expression2`의 값|`result`의 값|  
|----------------------|----------------------|-----------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  부울 비교에서 `And` 연산자는 항상 두 식을 계산하고 프로시저 호출을 포함할 수 있습니다.  [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)는 `expression1`이 `False`일 경우 `expression2`를 계산하지 않는 *단락\(short circuit\)* 연산을 수행합니다.  
  
 `And` 연산자를 숫자 값에 적용할 경우 두 숫자 식에 있는 동일한 위치의 비트에 대한 비트 비교가 수행되며, 다음 표에 따라 `result`의 해당 비트가 설정됩니다.  
  
|`expression1`의 비트|`expression2`의 비트|`result`의 비트|  
|-----------------------|-----------------------|------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계 연산자보다 우선 순위가 낮으므로 올바르게 실행하려면 모든 비트 연산을 괄호로 묶어야 합니다.  
  
## 데이터 형식  
 피연산자가 `Boolean` 식 하나와 숫자 식 하나로 구성되어 있는 경우 Visual Basic에서는 `Boolean` 식을 숫자 값\(`True`인 경우 –1, `False`인 경우 0\)으로 변환하고 비트 연산을 수행합니다.  
  
 부울 비교 결과의 데이터 형식은 `Boolean`이며  비트 비교 결과의 데이터 형식은 `expression1` 및 `expression2`의 데이터 형식에 적합한 숫자 형식입니다.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)의 "관계 및 비트 비교" 표를 참조하십시오.  
  
> [!NOTE]
>  `And` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `And` 연산자를 사용하여 두 식의 논리곱 연산을 수행합니다.  결과는 두 식이 모두 `True`인지 여부를 나타내는 `Boolean` 값입니다.  
  
 [!CODE [VbVbalrOperators#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#22)]  
  
 위 예제의 결과는 각각 `True`, `False`가 됩니다.  
  
## 예제  
 다음 예제에서는 `And` 연산자를 사용하여 두 숫자 식의 개별 비트에 대한 논리곱 연산을 수행합니다.  피연산자의 해당 비트가 모두 1로 설정되면 결과 패턴의 비트도 설정됩니다.  
  
 [!CODE [VbVbalrOperators#23](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#23)]  
  
 위 예제의 결과는 각각 8, 2, 0이 됩니다.  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)