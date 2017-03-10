---
title: "Get Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Get"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Get statement, syntax"
  - "Get statement"
  - "properties [Visual Basic], read-only"
  - "read-only properties"
  - "Get keyword"
  - "property procedures, Get statements"
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Get Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성 값을 검색하는 데 사용하는 `Get` 속성 프로시저를 선언합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attributelist`|선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.|  
|`accessmodifier`|선택적 요소이며 이 속성의 `Get` 및 `Set` 문 중 하나에서만 사용할 수 있습니다.  다음 중 하나일 수 있습니다.<br /><br /> -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.|  
|`statements`|선택적 요소.  `Get` 속성 프로시저를 호출할 때 실행되는 하나 이상의 문입니다.|  
|`End Get`|필수 요소.  `Get` 속성 프로시저의 정의를 종료합니다.|  
  
## 설명  
 속성이 `WriteOnly`로 표시되지 않는 경우 모든 속성에 `Get` 속성 프로시저가 있어야 합니다.  `Get` 프로시저는 현재 속성 값을 반환하는 데 사용됩니다.  
  
 Visual Basic에서는 식에서 속성 값을 요청할 때 자동으로 속성의 `Get` 프로시저를 호출합니다.  
  
 속성 선언 본문의 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)과 `End Property` 문 사이에 속성의 `Get` 및 `Set` 프로시저만 포함할 수 있습니다.  이러한 프로시저 외에는 아무 것도 저장할 수 없습니다.  특히 속성의 현재 값은 저장할 수 없습니다.  이 값을 속성 프로시저 중 하나의 내부에 저장하면 다른 속성 프로시저가 이 값에 액세스할 수 없으므로 이 값을 속성 외부에 저장해야 합니다.  일반적으로 속성과 동일한 수준에서 선언된 [Private](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장합니다.  `Get` 프로시저가 적용될 속성 내부에 해당 프로시저를 정의해야 합니다.  
  
 `Get` 문에서 `accessmodifier`를 사용하지 않는 경우 `Get` 프로시저의 기본값은 포함하는 속성의 액세스 수준이 됩니다.  
  
## 규칙  
  
-   **혼합 액세스 수준.** 읽기\/쓰기 속성을 정의하는 경우 `Get` 또는 `Set` 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있지만 두 프로시저 모두에 다른 액세스 수준을 지정할 수는 없습니다.  이렇게 하려면 프로시저 액세스 수준이 속성의 액세스 수준보다 제한적이어야 합니다.  예를 들어, 속성이 `Friend`로 선언된 경우 `Get` 프로시저를 `Private`으로 선언할 수 있지만 `Public`으로 선언할 수는 없습니다.  
  
     `ReadOnly` 속성을 선언하는 경우 `Get` 프로시저는 전체 속성을 나타냅니다.  `Get`에 대한 다른 액세스 수준을 선언하면 해당 속성에 대해 두 개의 액세스 수준이 설정되므로 다른 액세스 수준을 선언할 수 없습니다.  
  
-   **반환 형식.** [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)은 반환하는 값의 데이터 형식을 선언할 수 있습니다.  `Get` 프로시저는 데이터 형식을 자동으로 반환합니다.  열거형, 구조체, 클래스 또는 인터페이스의 이름 또는 모든 데이터 형식을 지정할 수 있습니다.  
  
     `Property` 문이 `returntype`을 지정하지 않는 경우 프로시저는 `Object`를 반환합니다.  
  
## 동작  
  
-   **프로시저에서 반환.** `Get` 프로시저가 호출 코드로 반환되면 속성 값을 요청한 문 내에서 실행이 계속됩니다.  
  
     `Get` 속성 프로시저는 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)을 사용하거나 속성 이름에 반환 값을 할당하여 값을 반환할 수 있습니다.  자세한 내용은 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)의 "반환 값"을 참조하십시오.  
  
     `Exit Property`와 `Return` 문은 속성 프로시저를 바로 끝냅니다.  프로시저 내의 임의의 위치에 여러 개의 `Exit Property` 및 `Return` 문을 사용할 수 있으며 `Exit Property` 문과 `Return` 문을 혼합하여 사용할 수 있습니다.  
  
-   **반환 값.** `Get` 프로시저에서 값을 반환하려면 속성 이름에 값을 할당하거나 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)에 값을 포함합니다.  `Return` 문은 동시에 `Get` 프로시저 반환 값을 할당하고 프로시저를 끝냅니다.  
  
     속성 이름에 값을 할당하지 않고 `Exit Property`를 사용하는 경우 `Get` 프로시저는 속성의 데이터 형식에 대해 기본값을 반환합니다.  자세한 내용은 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)의 "반환 값"을 참조하십시오.  
  
     다음 예제에서는 읽기 전용 속성 `quoteForTheDay`가 전용 변수 `quoteValue`에 저장된 값을 반환할 수 있는 두 가지 방법을 보여 줍니다.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/get-statement_3.vb)]  
  
## 예제  
 다음 예제에서는 `Get` 문을 사용하여 속성 값을 반환합니다.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/get-statement_4.vb)]  
  
## 참고 항목  
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Walkthrough: Defining Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)