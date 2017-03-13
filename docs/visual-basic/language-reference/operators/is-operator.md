---
title: "Is Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.is"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparison operators"
  - "equivalent objects"
  - "TypeOf...Is expression"
  - "Is operator [Visual Basic]"
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Is Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 개체 참조 변수를 비교합니다.  
  
## 구문  
  
```  
  
result = object1 Is object2  
```  
  
## 요소  
 `result`  
 필수 요소.  임의의 `Boolean` 값입니다.  
  
 `object1`  
 필수 요소.  임의의 `Object` 이름입니다.  
  
 `object2`  
 필수 요소.  임의의 `Object` 이름입니다.  
  
## 설명  
 `Is` 연산자는 두 개체 참조가 같은 개체를 참조하는지 여부를 결정하지만  값을 비교하지는 않습니다.  `object1`과 `object2`가 모두 똑같은 개체 인스턴스를 참조하면 `result`가 `True`이고 그렇지 않으면 `result`가 `False`입니다.  
  
 `Is`를 `TypeOf` 키워드와 함께 사용하여 개체 변수가 데이터 형식과 호환되는지 테스트하는 `TypeOf`...`Is` 식을 만들 수도 있습니다.  
  
> [!NOTE]
>  `Is` 키워드는 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)에서도 사용됩니다.  
  
## 예제  
 다음 예제에서는 `Is` 연산자를 사용하여 개체 참조 쌍을 비교합니다.  두 개체가 동일한지 여부를 나타내는 `Boolean` 값이 결과에 할당됩니다.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 위 예제에 나오는 것처럼 `Is` 연산자를 사용하여 초기 바인딩 및 런타임에 바인딩 개체를 모두 테스트할 수 있습니다.  
  
## 참고 항목  
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)