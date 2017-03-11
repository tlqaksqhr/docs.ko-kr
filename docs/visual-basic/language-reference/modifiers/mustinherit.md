---
title: "MustInherit (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MustInherit"
  - "vb.MustInherit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic], abstract"
  - "MustInherit classes, MustInherit keyword"
  - "abstract classes, MustInherit class"
  - "MustInherit keyword"
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# MustInherit (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스를 기본 클래스로만 사용할 수 있으며 이 클래스에서 개체를 직접 만들 수 없도록 지정합니다.  
  
## 설명  
 *기본 클래스*\(*추상 클래스*라고도 함\)는 기본 클래스로부터 파생된 모든 클래스에 공통되는 기능을 정의하는 것입니다.  이렇게 하면 파생 클래스는 공통 요소를 다시 정의할 필요가 없습니다.  경우에 따라 이 공통 기능은 유용한 개체를 만들 수 있을 만큼 완벽하지 않으므로 누락된 기능은 각 파생 클래스에서 정의됩니다.  이러한 경우에는 사용하는 코드에서 파생 클래스에서만 개체를 만들도록 할 수 있습니다.  기본 클래스에서 `MustInherit`를 사용하여 이를 적용할 수 있습니다.  
  
 또한 관련된 클래스 집합에만 설정되도록 변수를 제한하려는 경우에 `MustInherit` 클래스를 사용합니다.  기본 클래스를 정의하고 이러한 모든 관련 클래스를 기본 클래스로부터 파생시킬 수 있습니다.  기본 클래스는 모든 파생 클래스에 공통된 기능을 제공할 필요는 없지만 변수에 값을 할당하기 위한 필터로 사용될 수 있습니다.  사용하는 코드에서 변수를 기본 클래스로 선언할 경우 Visual Basic에서는 파생 클래스 중 하나의 개체만 해당 변수에 할당할 수 있습니다.  
  
 .NET Framework는 <xref:System.Array>, <xref:System.Enum>, <xref:System.ValueType> 등을 비롯하여 여러 `MustInherit` 클래스를 정의합니다.  <xref:System.ValueType>은 변수를 제한하는 기본 클래스의 한 예입니다.  모든 값 형식은 <xref:System.ValueType>에서 파생됩니다.  변수를 <xref:System.ValueType>으로 선언할 경우 값 형식만 해당 변수에 할당할 수 있습니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Class` 문에서만 `MustInherit`를 사용할 수 있습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `MustInherit`를 `NotInheritable`과 함께 지정할 수 없습니다.  
  
## 예제  
 다음은 강제 상속과 강제 재정의에 대한 예입니다.  기본 클래스 `shape`는 `acrossLine` 변수를 정의합니다.  `circle` 및 `square` 클래스는 `shape`에서 파생됩니다.  이러한 클래스는 `acrossLine`의 정의를 상속하지만 각 도형 유형에 대한 계산이 다르기 때문에 `area` 함수를 정의해야 합니다.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/visualbasic/mustinherit_1.vb)]  
  
 `shape1` 및 `shape2`를 `shape` 형식으로 선언할 수 있습니다.  그러나 `area` 함수 기능이 없고 `MustInherit` 표시가 있기 때문에 `shape`에서는 개체를 만들 수 없습니다.  
  
 `shape1` 및 `shape2` 변수는 `shape`로 선언되기 때문에 파생 클래스 `circle` 및 `square`의 개체만 사용하도록 제한됩니다.  Visual Basic에서는 이러한 변수에 다른 개체를 할당할 수 없기 때문에 형식 안전성이 향상됩니다.  
  
## 용도  
 `MustInherit` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## 참고 항목  
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)