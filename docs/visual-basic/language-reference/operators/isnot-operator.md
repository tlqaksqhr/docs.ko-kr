---
title: "IsNot Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.isnot"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsNot operator"
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# IsNot Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 개체 참조 변수를 비교합니다.  
  
## 구문  
  
```  
  
result = object1 IsNot object2  
```  
  
## 요소  
 `result`  
 필수 요소.  `Boolean` 값입니다.  
  
 `object1`  
 필수 요소.  임의의 `Object` 변수 또는 식입니다.  
  
 `object2`  
 필수 요소.  임의의 `Object` 변수 또는 식입니다.  
  
## 설명  
 `IsNot` 연산자는 두 개체 참조가 서로 다른 개체를 참조하는지 여부를 결정하지만  값을 비교하지는 않습니다.  `object1`과 `object2`가 모두 똑같은 개체 인스턴스를 참조하면 `result`가 `False`이고 그렇지 않으면 `result`가 `True`입니다.  
  
 `IsNot`은 `Is` 연산자와 반대되는 연산자입니다.  `IsNot`의 장점은 `Not`과 `Is`를 함께 사용하여 읽기 어려운 복잡한 구문이 되는 것을 피할 수 있다는 것입니다.  
  
 `Is`와 `IsNot` 연산자를 사용하면 초기 바인딩 및 런타임에 바인딩 개체를 모두 테스트할 수 있습니다.  
  
> [!NOTE]
>  `IsNot` 연산자는 `TypeOf` 연산자에서 반환된 식을 비교하는 데 사용할 수 없습니다.  대신 `Not` 및 `Is` 연산자를 사용해야 합니다.  
  
## 예제  
 다음 코드 예제에서는 `Is` 연산자와 `IsNot` 연산자를 모두 사용하여 동일한 비교를 수행합니다.  
  
 [!CODE [VbVbalrOperators#29](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#29)]  
  
## 참고 항목  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [How to: Test Whether Two Objects Are the Same](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)