---
title: "Overridable (Visual Basic) | Microsoft Docs"
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
  - "Overridable"
  - "vb.Overridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elements, concrete"
  - "properties [Visual Basic], redefining"
  - "overriding, Overridable keyword"
  - "elements, virtual"
  - "virtual elements"
  - "procedures, overriding"
  - "concrete elements"
  - "procedures, redefining"
  - "Overridable keyword"
  - "properties [Visual Basic], overriding"
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성이나 프로시저가 파생 클래스에서 같은 이름의 속성 또는 프로시저에 의해 재정의될 수 있다는 것을 지정합니다.  
  
## 설명  
 `Overridable` 한정자 있습니다 속성 또는 메서드가 파생된 클래스에서 재정의 하는 클래스에 있습니다.  [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) 한정자를 방지 속성 또는 메서드가 파생된 클래스에서 재정의 합니다.  자세한 내용은 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)를 참조하십시오.  
  
 경우는 `Overridable` 또는 `NotOverridable` 한정자가 지정 되지 않은,를 여부를 속성이 나 메서드에 기본 클래스 속성 또는 메서드 재정의에서 기본 설정에 따라 달라 집니다.  속성 또는 메서드는 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정 된 `Overridable`. 그렇지 않으면입니다 `NotOverridable`.  
  
 숨김 또는 재정의를 통해 상속된 요소를 다시 정의할 수 있지만 두 방식에는 큰 차이가 있습니다.  자세한 내용은 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조하십시오.  
  
 재정의 가능한 요소를 *가상* 요소라고도 합니다.  재정의할 수 있지만 반드시 재정의하지 않아도 되는 요소를 *구체적인* 요소라고도 합니다.  
  
 속성이나 프로시저 선언 문에서만 `Overridable`를 사용할 수 있습니다.  
  
## 한정자 결합된  
 지정할 수 없습니다. `Overridable` 또는 `NotOverridable` 에 있는 `Private` 메서드.  
  
 하나의 선언에서 `Overridable`을 `MustOverride`, `NotOverridable` 또는 `Shared`와 함께 지정할 수 없습니다.  
  
 재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`을 `Overrides`와 함께 사용할 수 없습니다.  
  
## 용도  
 `Overridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Modifiers](../../../visual-basic/language-reference/modifiers/index.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)