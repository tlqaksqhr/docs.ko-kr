---
title: "How to: Test Whether Two Objects Are the Same (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], reference"
  - "Is operator [Visual Basic], comparing objects"
  - "reference variables"
  - "variables [Visual Basic], referring to same object"
  - "objects [Visual Basic], variables referring to same"
  - "Visual Basic code, operators"
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Test Whether Two Objects Are the Same (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체를 참조하는 두 개의 변수가 있는 경우 `Is` 연산자와 `IsNot` 연산자 중 하나 또는 둘 다를 사용하여 두 개체가 동일한 인스턴스를 참조하는지 여부를 확인할 수 있습니다.  
  
### 두 개체가 동일한지 여부를 테스트하려면  
  
-   두 변수를 피연산자로 사용하는 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)나 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)를 사용합니다.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-test-whether-two-_1.vb)]  
  
 두 개체가 동일한 인스턴스를 참조하는지 여부에 따라 특별한 조치가 필요할 수 있습니다.  앞의 예제에서는 `c` 컨트롤을 `f` 폼의 활성 컨트롤과 비교합니다.  활성 컨트롤이 없는 경우 또는 `c`와 동일하지 않은 컨트롤 인스턴스가 하나 있는 경우 `If` 문은 실패하고 프로시저는 더 이상 처리하지 않고 반환합니다.  
  
 `Is`와 `IsNot` 중 사용자가 사용하기에 편리한 연산자를 사용하면 됩니다.  주어진 식에서 하나가 다른 것보다 읽기 쉬울 수 있습니다.  
  
## 참고 항목  
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)