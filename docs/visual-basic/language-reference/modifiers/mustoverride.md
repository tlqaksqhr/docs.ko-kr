---
title: "MustOverride (Visual Basic) | Microsoft Docs"
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
  - "vb.MustOverride"
  - "MustOverride"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "virtual elements, pure"
  - "elements, pure virtual"
  - "properties [Visual Basic], redefining"
  - "procedures, overriding"
  - "overriding, MustOverride keyword"
  - "procedures, redefining"
  - "pure virtual elements"
  - "MustOverride keyword"
  - "properties [Visual Basic], overriding"
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# MustOverride (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성이나 프로시저를 이 클래스에서 구현하지 않고 파생 클래스에서 재정의해야 사용할 수 있도록 지정합니다.  
  
## 설명  
 속성이나 프로시저 선언 문에서만 `MustOverride`를 사용할 수 있습니다.  `MustOverride`를 지정하는 속성이나 프로시저는 클래스의 멤버여야 하며 해당 클래스는 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)으로 표시되어야 합니다.  
  
## 규칙  
  
-   **불완전한 선언.** `MustOverride`를 지정할 때는 속성이나 프로시저는 물론 `End Function`, `End Property` 또는 `End Sub` 문에 대해서도 코드 줄을 추가로 지정하지 않습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `MustOverride`를 `NotOverridable`, `Overridable` 또는 `Shared`와 함께 지정할 수 없습니다.  
  
-   **숨김 및 재정의.** 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방식에는 큰 차이가 있습니다.  자세한 내용은 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조하십시오.  
  
-   **대체 조건.** 재정의에서만 사용할 수 있는 요소를 *순수 가상* 요소라고도 합니다.  
  
 `MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)