---
title: "AndAlso Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.AndAlso"
  - "AndAlso"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "short-circuiting"
  - "AndAlso operator"
  - "operators [Visual Basic], short-circuiting"
  - "operators [Visual Basic], conjunction"
  - "short-circuit evaluation"
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# AndAlso Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 식의 단락\(short circuit\) 논리곱 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 AndAlso expression2  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`result`|필수 요소.  `Boolean` 식입니다.  결과는 두 식을 비교한 `Boolean` 결과입니다.|  
|`expression1`|필수 요소.  `Boolean` 식입니다.|  
|`expression2`|필수 요소.  `Boolean` 식입니다.|  
  
## 설명  
 컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 건너뛸 수 있는 경우의 논리 연산을 *단락\(short circuit\)*이라고 합니다.  계산된 첫째 식의 결과가 연산의 최종 결과를 결정하는 경우에는 둘째 식을 계산해도 최종 결과가 변경되지 않으므로 둘째 식을 계산할 필요가 없습니다.  단락\(short circuit\)을 사용하면 건너뛸 식이 복잡하거나 식에 프로시저 호출이 포함된 경우 성능을 향상시킬 수 있습니다.  
  
 두 식이 모두 `True`이면 `result`는 `True`입니다.  다음 표에서는 `result`가 결정되는 방식을 보여 줍니다.  
  
||||  
|-|-|-|  
|`expression1`의 값|`expression2`의 값|`result`의 값|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|\(계산되지 않음\)|`False`|  
  
## 데이터 형식  
 `AndAlso` 연산자는 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)에 대해서만 정의됩니다.  Visual Basic에서는 각 피연산자를 필요에 따라 `Boolean`으로 변환하고 연산을 완전 `Boolean` 형식으로 수행합니다.  결과를 숫자 형식에 할당하면 Visual Basic에서 결과 형식이 `Boolean`에서 해당 형식으로 변환됩니다.  이렇게 되면 예기치 않은 동작이 발생할 수 있습니다.  예를 들어, `5 AndAlso 12`의 결과는 `Integer`로 변환될 경우 `–1`이 됩니다.  
  
## 오버로딩  
 [And Operator](../../../visual-basic/language-reference/operators/and-operator.md)와 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 피연산자의 동작을 다시 정의할 수 있습니다.  `And`와 `IsFalse` 연산자를 오버로드하면 `AndAlso` 연산자의 동작이 영향을 받습니다.  코드에서 `And`와 `IsFalse`를 오버로드하는 클래스나 구조체에 대해 `AndAlso`를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `AndAlso` 연산자를 사용하여 두 식의 논리곱 연산을 수행합니다.  결과는 결합된 전체 식이 true인지 여부를 나타내는 `Boolean` 값입니다.  첫째 식이 `False`이면 둘째 식은 계산되지 않습니다.  
  
 [!CODE [VbVbalrOperators#24](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#24)]  
  
 위 예제의 결과는 각각 `True`, `False` 및 `False`가 됩니다.  `secondCheck` 계산에서는 첫째 식이 이미 `False`이므로 둘째 식은 계산되지 않습니다.  그러나 `thirdCheck` 계산에서는 둘째 식이 계산됩니다.  
  
## 예제  
 다음 예제에서는 배열 요소들 중에서 지정된 값을 검색하는 `Function` 프로시저를 보여 줍니다.  배열이 비어 있거나 배열 길이가 초과된 경우 `While` 문은 검색 결과에 대해 배열 요소를 테스트하지 않습니다.  
  
 [!CODE [VbVbalrOperators#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#25)]  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [And Operator](../../../visual-basic/language-reference/operators/and-operator.md)   
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)