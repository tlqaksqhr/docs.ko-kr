---
title: "Set Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Set"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "property procedures, Set statements"
  - "Set statement"
  - "Set statement, syntax"
  - "write-only properties"
  - "properties [Visual Basic], write-only"
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Set Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성에 값을 할당하는 데 사용하는 `Set` 속성 프로시저를 선언합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## 요소  
 `attributelist`  
 선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.  
  
 `accessmodifier`  
 선택적 요소이며 이 속성의 `Get` 및 `Set` 문 중 하나에서만 사용할 수 있습니다.  다음 중 하나일 수 있습니다.  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.  
  
 `value`  
 필수 요소.  속성에 대한 새 값을 포함하는 매개 변수입니다.  
  
 `datatype`  
 `Option Strict`가 `On`이면 필수적 요소입니다.  `value` 매개 변수의 데이터 형식입니다.  지정된 데이터 형식이 이 `Set` 문이 선언된 속성의 데이터 형식과 같아야 합니다.  
  
 `statements`  
 선택적 요소.  `Set` 속성 프로시저를 호출할 때 실행되는 하나 이상의 문입니다.  
  
 `End Set`  
 필수 요소.  `Set` 속성 프로시저의 정의를 종료합니다.  
  
## 설명  
 `ReadOnly`로 표시되어 있지 않은 이상 모든 속성에 `Set` 속성 프로시저가 있어야 합니다.  `Set` 프로시저는 속성 값을 설정하는 데 사용됩니다.  
  
 Visual Basic은 할당문이 속성에 저장될 값을 제공할 때 속성의 `Set` 프로시저를 자동으로 호출합니다.  
  
 Visual Basic은 속성을 할당하는 동안 `Set` 프로시저에 매개 변수를 전달합니다.  `Set`에 대한 매개 변수를 지정하지 않으면 IDE\(통합 개발 환경\)에서 `value`라는 암시적 매개 변수를 사용합니다.  이 매개 변수에는 속성에 할당할 값이 포함되어 있습니다.  일반적으로 이 값을 전용 지역 변수에 저장하고 `Get` 프로시저가 호출될 때마다 이 값을 반환합니다.  
  
 속성 선언 본문의 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)과 `End Property` 문 사이에 속성의 `Get` 및 `Set` 프로시저만 포함할 수 있습니다.  이러한 프로시저 외에는 아무 것도 저장할 수 없습니다.  특히 속성의 현재 값은 저장할 수 없습니다.  이 값을 속성 프로시저 중 하나의 내부에 저장하면 다른 속성 프로시저가 이 값에 액세스할 수 없으므로 이 값을 속성 외부에 저장해야 합니다.  일반적으로 속성과 동일한 수준에서 선언된 [Private](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장합니다.  `Set` 프로시저는 해당 프로시저가 적용되는 속성 내에 정의해야 합니다.  
  
 `Set` 문에 `accessmodifier`를 사용하지 않는 한 `Set` 프로시저는 기본적으로 포함하는 해당 속성의 액세스 수준입니다.  
  
## 규칙  
  
-   **혼합 액세스 수준.** 읽기\/쓰기 속성을 정의하는 경우 `Get` 또는 `Set` 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있지만 두 프로시저 모두에 다른 액세스 수준을 지정할 수는 없습니다.  이렇게 하려면 프로시저 액세스 수준이 속성의 액세스 수준보다 제한적이어야 합니다.  예를 들어 속성이 `Friend`로 선언된 경우 `Set` 프로시저를 `Public`이 아닌 `Private`으로 선언할 수 있습니다.  
  
     `WriteOnly` 속성을 정의하는 경우 `Set` 프로시저는 전체 속성을 나타냅니다.  `Set`에 다른 액세스 수준을 선언할 수 없습니다. 다른 액세스 수준을 선언하면 속성에 두 가지 액세스 수준이 설정됩니다.  
  
## 동작  
  
-   **속성 프로시저에서 반환.** `Set` 프로시저가 호출 코드로 반환되면 저장할 값을 제공한 문 다음에서 실행이 계속됩니다.  
  
     `Set` 속성 프로시저는 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) 또는 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)을 사용하여 반환할 수 있습니다.  
  
     `Exit Property`와 `Return` 문은 속성 프로시저를 바로 끝냅니다.  프로시저 내의 임의의 위치에 여러 개의 `Exit Property` 및 `Return` 문을 사용할 수 있으며 `Exit Property` 문과 `Return` 문을 혼합하여 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Set` 문을 사용하여 속성 값을 설정합니다.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## 참고 항목  
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Property 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)