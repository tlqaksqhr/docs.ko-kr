---
title: "Differences Between Shadowing and Overriding (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "shadowing, vs. overriding"
  - "overriding, vs. shadowing"
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Differences Between Shadowing and Overriding (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

기본 클래스에서 상속하는 클래스를 정의할 때 파생 클래스에서 하나 이상의 기본 클래스 요소를 다시 정의하려는 경우가 있습니다.  숨기기와 재정의는 모두 이러한 용도로 사용할 수 있습니다.  
  
## 비교  
 숨기기와 재정의 모두 파생된 클래스가 기본 클래스에서 상속할 때 사용되며, 하나의 선언된 요소를 다른 요소로 재정의하지만  둘 사이에는 상당한 차이점이 있습니다.  
  
 다음 표에서는 숨김과 재정의를 비교합니다.  
  
||||  
|-|-|-|  
|비교 관점|숨김|재정의|  
|목적|파생된 클래스에 이미 정의된 멤버를 사용하여 기본 클래스가 더 이상 수정되지 않도록 방지함|호출 시퀀스<sup>1</sup>가 동일한 프로시저나 속성을 다르게 구현하여 다형성을 제공함|  
|재정의되는 요소|모든 선언된 요소 형식|프로시저\(`Function`, `Sub` 또는 `Operator`\) 또는 속성만|  
|재정의 요소|모든 선언된 요소 형식|호출 시퀀스<sup>1</sup>가 같은 프로시저 또는 속성만|  
|다시 정의하는 요소의 액세스 수준|모든 액세스 수준|재정의된 요소의 액세스 수준을 변경할 수 없음|  
|다시 정의하는 요소의 읽기 및 쓰기 가능성|모든 조합|재정의된 속성의 읽기 가능성 또는 쓰기 가능성을 변경할 수 없음|  
|다시 정의에 대한 제어|기본 클래스 요소는 숨김을 적용하거나 금지할 수 없음|기본 클래스 요소는 `MustOverride`, `NotOverridable` 또는 `Overridable`를 지정할 수 있음|  
|키워드 사용법|파생된 클래스에는 `Shadows`를 사용하는 것이 좋음. `Shadows`와 `Overrides` 중 어느 것도 지정하지 않으면 `Shadows`로 간주됨<sup>2</sup>|기본 클래스에는 반드시 `Overridable` 또는 `MustOverride`를 사용하고, 파생된 클래스에는 `Overrides`를 사용해야 함|  
|파생된 클래스로부터 다시 클래스를 파생할 때 재정의 요소 상속|추가로 파생되는 클래스에 의해 상속되는 요소 숨김. 숨겨진 요소는 계속 숨겨진 상태로 유지됨<sup>3</sup>|추가로 파생되는 클래스에 의해 상속되는 요소 재정의. 재정의된 요소는 계속 재정의된 상태로 유지됨|  
  
 <sup>1</sup> *호출 시퀀스*는 요소 형식\(`Function`, `Sub`, `Operator` 또는 `Property`\), 이름, 매개 변수 목록 및 반환 형식으로 구성됩니다.  프로시저를 속성으로 재정의하거나 그 반대로 재정의할 수 없습니다.  또한 한 종류의 프로시저\(`Function`, `Sub` 또는 `Operator`\)를 다른 종류의 프로시저로 재정의할 수 없습니다.  
  
 <sup>2</sup> `Shadows`나 `Overrides`를 지정하지 않으면 사용할 재정의 유형을 확인할 수 있도록 컴파일러에서 경고 메시지를 보냅니다.  이 경고를 무시하면 숨김 메커니즘이 사용됩니다.  
  
 <sup>3</sup> 추가로 파생되는 클래스에서 숨기는 요소에 액세스할 수 없는 경우 숨김은 상속되지 않습니다.  예를 들어, 숨기는 요소를 `Private`으로 선언하면 파생된 클래스에서 다시 파생되는 클래스는 숨기는 요소 대신 원래 요소를 상속합니다.  
  
## 지침  
 일반적으로 다음 경우에 재정의를 사용합니다.  
  
-   다형 파생 클래스를 정의하는 경우  
  
-   안전을 위해 컴파일러에서 동일한 요소 형식과 호출 시퀀스를 적용하도록 하려는 경우  
  
 일반적으로 다음 경우에 숨기기를 사용합니다.  
  
-   기본 클래스가 수정되거나 사용자의 클래스와 동일한 이름의 요소를 정의할 수 있다고 예상하는 경우  
  
-   요소 형식이나 호출 시퀀스를 자유롭게 변경하려는 경우  
  
## 참고 항목  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)