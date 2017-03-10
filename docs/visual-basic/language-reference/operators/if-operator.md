---
title: "If Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.IfOperator"
  - "IfOperator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ternary operators"
  - "conditional execution"
  - "If expressions [Visual Basic]"
  - "conditional operator [Visual Basic]"
  - "If Operator [Visual Basic]"
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# If Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

단락\(short\-circuit\) 계산을 사용하여 두 값 중 하나를 조건부로 반환합니다.  `If` 연산자는 세 개의 인수 또는 두 개의 인수를 사용하여 호출할 수 있습니다.  
  
## 구문  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## 세 개의 인수로 호출된 If 연산자  
 세 개의 인수를 사용하여 `If`를 호출하면 첫 번째 인수가 `Boolean`로 캐스팅될 수 있는 값으로 계산됩니다.  이 `Boolean` 값은 나머지 두 인수 중 무엇이 계산되고 반환되는지를 결정합니다.  다음 목록은 세 개의 인수를 사용하여 `If` 연산자를 호출한 경우에만 적용됩니다.  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`argument1`|필수 요소.  `Boolean`.  나머지 두 인수 중 무엇이 계산되고 반환되는지를 결정합니다.|  
|`argument2`|필수 요소.  `Object`.  `argument1`이 `True`로 계산되는 경우 계산되고 반환됩니다.|  
|`argument3`|필수 요소.  `Object`.  계산 하 고 반환 된 경우 `argument1` 로 평가 `False` 또는 `argument1` 되는  [null 허용 여부가](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean`산출변수 [아무것도](../../../visual-basic/language-reference/nothing.md).|  
  
 세 개의 인수를 사용하여 호출된 `If` 연산자는 단락 계산을 사용한다는 점을 제외하고는 `IIf` 함수처럼 작동합니다.  `IIf` 함수는 항상 세 개의 인수를 모두 계산하는 반면, 세 개의 인수가 있는 `If` 연산자는 그 중 두 개만 계산합니다.  첫 번째 `If` 인수가 계산되고 결과는 `Boolean` 값인 `True` 또는 `False`로 캐스팅됩니다.  값이 `True`일 경우 `argument2`는 계산되고 해당 값이 반환되지만 `argument3`은 계산되지 않습니다.  `Boolean` 식의 값이 `False`일 경우 `argument3`은 계산되고 해당 값이 반환되지만 `argument2`는 계산되지 않습니다.  다음 예제에서는 세 개의 인수가 사용될 때 `If`의 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_1.vb)]  
  
 다음 예제에서는 단락 계산의 값을 보여 줍니다.  이 예제에서는 `number` 변수를 `divisor` 변수로 나누려고 하는 두 가지 시도를 보여 줍니다. 단, `divisor`가 0인 경우는 제외됩니다.  이 경우에는 0이 반환되므로 나누기를 시도해서는 안 됩니다. 나누기를 시도하면 런타임 오류가 발생합니다.  `If` 식은 단락 계산을 사용하기 때문에 첫 번째 인수의 값에 따라 두 번째 또는 세 번째 인수를 계산합니다.  첫 번째 인수가 true이면 제수가 0이 아니므로 안전하게 두 번째 인수를 계산하고 나누기를 수행할 수 있습니다.  첫 번째 인수가 false이면 세 번째 인수만 계산되고 0이 반환됩니다.  따라서 제수가 0인 경우에는 나누기를 수행하지 않으며 오류가 발생하지 않습니다.  그러나 `IIf`는 단락 계산을 사용하지 않기 때문에 첫 번째 인수가 false일 때도 두 번째 인수가 계산됩니다.  이로 인해 런타임에서 0으로 나누기 오류가 발생합니다.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_2.vb)]  
  
## 두 개의 인수로 호출된 If 연산자  
 `If`에 대한 첫 번째 인수는 생략할 수 있습니다.  따라서 두 개의 인수만 사용하여 연산자를 호출할 수 있습니다.  다음 목록은 두 개의 인수를 사용하여 `If` 연산자를 호출한 경우에만 적용됩니다.  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`argument2`|필수 요소.  `Object`.  참조 형식 또는 nullable 형식이어야 합니다.  `Nothing`이 아닌 다른 값으로 계산될 때 계산되고 반환됩니다.|  
|`argument3`|필수 요소.  `Object`.  `argument2`이 `Nothing`로 계산되는 경우 계산되고 반환됩니다.|  
  
 `Boolean` 인수가 생략된 경우에는 첫 번째 인수가 참조 또는 nullable 형식이어야 합니다.  첫 번째 인수가 `Nothing`으로 계산되면 두 번째 인수의 값이 반환됩니다.  그 외의 모든 경우에는 첫 번째 인수의 값이 반환됩니다.  다음 예제에서는 이 계산의 작동 방식을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/if-operator_3.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)