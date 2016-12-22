---
title: "How to: Determine Whether Two Objects Are Identical (Visual Basic) | Microsoft Docs"
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
  - "testing, objects"
  - "objects [Visual Basic], comparing"
  - "object variables, determining identity"
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Determine Whether Two Objects Are Identical (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 두 변수 참조의 포인터가 같은 경우, 즉 두 변수가 모두 메모리의 동일한 클래스 인스턴스를 가리키는 경우 두 변수 참조를 동일한 것으로 간주합니다.  예를 들어, Windows Forms 응용 프로그램에서 현재 인스턴스\(`Me`\)가 `Form2` 등의 특정 인스턴스와 동일한지 확인하려는 경우 비교를 수행할 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 포인터를 비교하기 위한 두 개의 연산자를 제공합니다.  [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)는 개체가 동일할 경우 `True`를 반환하고, [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)는 개체가 동일하지 않을 경우 `True`를 반환합니다.  
  
## 두 개체가 동일한지 확인  
  
#### 두 개체가 동일한지 확인하려면  
  
1.  두 개체를 테스트하기 위한 `Boolean` 식을 설정합니다.  
  
2.  테스트 식에 `Is` 연산자를 사용하고 피연산자로 두 개체를 지정합니다.  
  
     `Is`는 두 개체가 동일한 클래스 인스턴스를 가리킬 경우 `True`를 반환합니다.  
  
## 두 개체가 동일하지 않은지 확인  
 두 개체가 동일하지 않으면 작업을 수행해야 할 수도 있는데, 이 경우 `If Not obj1 Is obj2`처럼 `Not`과 `Is`를 결합하면 좋지 않을 수 있습니다.  이런 경우 `IsNot` 연산자를 사용할 수 있습니다.  
  
#### 두 개체가 동일하지 않은지 확인하려면  
  
1.  두 개체를 테스트하기 위한 `Boolean` 식을 설정합니다.  
  
2.  테스트 식에 `IsNot` 연산자를 사용하고 피연산자로 두 개체를 지정합니다.  
  
     `IsNot`은 두 개체가 동일한 클래스 인스턴스를 가리키지 않을 경우 `True`를 반환합니다.  
  
## 예제  
 다음 예제에서는 `Object` 변수 쌍을 테스트하여 두 변수가 동일한 클래스 인스턴스를 가리키는지 확인합니다.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 위 예제의 결과는 다음과 같습니다.  
  
 `objA different from objB?  True`  
  
 `objA identical to objC?  True`  
  
## 참고 항목  
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)