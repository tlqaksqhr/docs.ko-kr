---
title: "NotOverridable (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.NotOverridable"
  - "NotOverridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sealed methods"
  - "NotOverridable keyword"
  - "properties [Visual Basic], redefining"
  - "elements, sealed"
  - "sealed elements"
  - "procedures, overriding"
  - "procedures, redefining"
  - "overriding"
  - "methods [Visual Basic], sealed"
  - "properties [Visual Basic], overriding"
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# NotOverridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파생 클래스에서 속성이나 프로시저를 재정의할 수 없도록 지정합니다.  
  
## 설명  
 `NotOverridable` 한정자를 방지 속성 또는 메서드가 파생된 클래스에서 재정의 합니다.  [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) 한정자 있습니다 속성 또는 메서드가 파생된 클래스에서 재정의 하는 클래스에 있습니다.  자세한 내용은 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)를 참조하십시오.  
  
 경우는 `Overridable` 또는 `NotOverridable` 한정자가 지정 되지 않은,를 여부를 속성이 나 메서드에 기본 클래스 속성 또는 메서드 재정의에서 기본 설정에 따라 달라 집니다.  속성 또는 메서드는 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정 된 `Overridable`. 그렇지 않으면입니다 `NotOverridable`.  
  
 재정의할 수 없는 요소를 *봉인* 요소라고도 합니다.  
  
 속성이나 프로시저 선언 문에서만 `NotOverridable`를 사용할 수 있습니다.  다른 속성이나 프로시저를 재정의하는 속성이나 프로시저에만 `NotOverridable`을 지정할 수 있습니다. 즉, `Overrides`와 함께 사용하는 경우만 가능합니다.  
  
## 한정자 결합된  
 지정할 수 없습니다. `Overridable` 또는 `NotOverridable` 에 있는 `Private` 메서드.  
  
 하나의 선언에서 `NotOverridable`을 `MustOverride`, `Overridable` 또는 `Shared`와 함께 지정할 수 없습니다.  
  
## 용도  
 `NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Modifiers](../../../visual-basic/language-reference/modifiers/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)