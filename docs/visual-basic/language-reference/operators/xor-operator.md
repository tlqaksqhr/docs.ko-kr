---
title: "Xor Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Xor"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "exclusive OR operator"
  - "logical exclusion"
  - "operators [Visual Basic], exclusive or"
  - "exclusion operator"
  - "operators [Visual Basic], bitwise"
  - "bitwise operators, XOR operator"
  - "Xor operator [Visual Basic]"
  - "Xor keyword"
  - "bitwise comparison"
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Xor Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 `Boolean` 식의 배타적 논리합을 수행하거나 두 숫자 식의 배타적 비트 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 Xor expression2  
```  
  
## 요소  
 `result`  
 필수 요소.  임의의 `Boolean` 또는 숫자 변수입니다.  부울 비교의 경우 `result`는 두 `Boolean` 값의 배타적 논리합입니다.  비트 연산의 경우 `result`는 두 숫자 비트 패턴의 배타적 비트 연산\(배타적 비트 논리합\)을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수 요소.  임의의 `Boolean` 또는 숫자 식입니다.  
  
## 설명  
 부울 비교의 경우 `result`는 `expression1` 및 `expression2` 중 정확히 하나가 `True`인 경우에만 `True`입니다.  즉, `expression1`과 `expression2`의 `Boolean` 값이 서로 반대인 경우만 이에 해당합니다.  다음 표에서는 `result`가 결정되는 방식을 보여 줍니다.  
  
|`expression1`의 값|`expression2`의 값|`result`의 값|  
|----------------------|----------------------|-----------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  부울 비교에서 `Xor` 연산자는 항상 두 식을 계산하고 프로시저 호출을 포함할 수 있습니다.  항상 두 피연산자에 따라 결과가 달라지기 때문에 `Xor`에 상응하는 단락\(short circuit\) 연산자는 없습니다.  *단락\(short circuit\)* 논리 연산자에 대한 자세한 내용은 [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) 및 [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)를 참조하십시오.  
  
 비트 연산의 경우 `Xor` 연산자는 두 숫자 식에 있는 동일한 위치의 비트에 대한 비트 비교를 수행하며, 다음 표에 따라 해당하는 비트를 `result`에 설정합니다.  
  
|`expression1`의 비트|`expression2`의 비트|`result`의 비트|  
|-----------------------|-----------------------|------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계 연산자보다 우선 순위가 낮으므로 올바르게 실행하려면 모든 비트 연산을 괄호로 묶어야 합니다.  
  
 예를 들어 5 `Xor` 3은 6입니다.  이렇게 계산되는 이유를 알아보려면 5와 3을 이진수 표현인 101과 011로 변환한 다음  위에 나와 있는 표를 사용하여 101 Xor 011이 110임을 확인합니다. 이는 10진수 6의 이진수 표현입니다.  
  
## 데이터 형식  
 피연산자가 `Boolean` 식 하나와 숫자 식 하나로 구성되어 있는 경우 Visual Basic에서는 `Boolean` 식을 숫자 값\(`True`인 경우 –1, `False`인 경우 0\)으로 변환하고 비트 연산을 수행합니다.  
  
 `Boolean` 비교 결과의 데이터 형식은 `Boolean`이며  비트 비교 결과의 데이터 형식은 `expression1` 및 `expression2`의 데이터 형식에 적합한 숫자 형식입니다.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)의 "관계 및 비트 비교" 표를 참조하십시오.  
  
## 오버로딩  
 `Xor` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Xor` 연산자를 사용하여 두 식의 배타적 논리합 연산을 수행합니다.  결과는 두 식 중 하나가 `True`인지 여부를 나타내는 `Boolean` 값입니다.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xor-operator_1.vb)]  
  
 위 예제의 결과는 각각 `False`, `True` 및 `False`가 됩니다.  
  
## 예제  
 다음 예제에서는 `Xor` 연산자를 사용하여 두 숫자 식의 개별 비트에 대한 배타적 논리합 연산을 수행합니다.  피연산자의 해당 비트 중 하나만 1로 설정되면 결과 패턴의 비트도 설정됩니다.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xor-operator_2.vb)]  
  
 위 예제의 결과는 각각 2, 12 및 14가 됩니다.  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)