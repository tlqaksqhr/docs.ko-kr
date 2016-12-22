---
title: "Delegate Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Delegate"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegate keyword"
  - "Delegate statement"
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Delegate Statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

대리자를 선언하는 데 사용합니다.  대리자는 형식의 `Shared` 메서드 또는 개체의 인스턴스 메서드를 참조하는 참조 형식입니다.  이 대리자 클래스의 인스턴스를 만들기 위해 매개 변수 및 반환 형식이 일치하는 모든 프로시저를 사용할 수 있습니다.  이러한 프로시저는 대리자 인스턴스를 통해 나중에 호출될 수 있습니다.  
  
## 구문  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attrlist`|선택적 요소.  이 대리자에 적용되는 특성의 목록으로,  특성이 여러 개 있으면 쉼표로 구분됩니다.  [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md)은 꺾쇠괄호\("`<`" 및 "`>`"\)로 묶어야 합니다.|  
|`accessmodifier`|선택적 요소.  대리자에 액세스할 수 있는 코드를 지정하며,  다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md).  대리자를 선언하는 요소에 액세스할 수 있는 모든 코드에서 액세스할 수 있습니다.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md).  대리자의 클래스나 파생 클래스 안에 있는 코드에서만 액세스할 수 있습니다.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  같은 어셈블리 안에 있는 코드에서만 대리자에 액세스할 수 있습니다.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md).  대리자를 선언하는 요소 안에 있는 코드에서만 액세스할 수 있습니다.<br /><br /> `Protected Friend`를 지정하면 대리자의 클래스, 파생 클래스 또는 같은 어셈블리에 있는 코드에서 액세스할 수 있습니다.|  
|`Shadows`|선택적 요소.  이 대리자는 기본 클래스에서 같은 이름의 프로그래밍 요소나 오버로드된 요소 집합을 다시 선언하고 숨기도록 지정합니다.  다른 요소를 사용하여 선언된 모든 요소를 숨길 수 있습니다.<br /><br /> 숨겨진 요소는 해당 요소를 숨기는 파생 클래스에서 사용할 수 없지만 숨기는 요소를 액세스할 수 없는 클래스에서는 사용할 수 있습니다.  예를 들어, `Private` 요소가 기본 클래스 요소를 숨기면 `Private` 요소에 대한 액세스 권한이 없는 코드에서는 기본 클래스 요소에 대신 액세스합니다.|  
|`Sub`|선택적 요소. `Sub`나 `Function` 중 하나가 반드시 있어야 합니다.  값을 반환하지 않는 대리자 `Sub` 프로시저로 이 프로시저를 선언합니다.|  
|`Function`|선택적 요소. `Sub`나 `Function` 중 하나가 반드시 있어야 합니다.  값을 반환하는 대리자 `Function` 프로시저로 이 프로시저를 선언합니다.|  
|`name`|필수 요소.  대리자 형식의 이름이며, 표준 변수 명명 규칙을 따릅니다.|  
|`typeparamlist`|선택적 요소.  이 대리자에 대한 형식 매개 변수 목록입니다.  형식 매개 변수가 여러 개 있으면 쉼표로 구분합니다.  필요한 경우 `In` 및 `Out` 제네릭 한정자를 사용하여 각 형식 매개 변수를 variant로 선언할 수 있습니다.  [Type List](../../../visual-basic/language-reference/statements/type-list.md)은 괄호로 묶어야 하며 `Of` 키워드를 사용하여 정의해야 합니다.|  
|`parameterlist`|선택적 요소.  프로시저를 호출할 때 프로시저에 전달하는 매개 변수 목록입니다.  [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)은 괄호로 묶어야 합니다.|  
|`type`|`Function` 프로시저를 지정하는 경우 필수적 요소입니다.  반환 값의 데이터 형식입니다.|  
  
## 설명  
 `Delegate` 문은 대리자 클래스의 매개 변수와 반환 형식을 정의합니다.  이 대리자 클래스의 인스턴스를 만들기 위해 매개 변수 및 반환 형식이 일치하는 모든 프로시저를 사용할 수 있습니다.  이러한 프로시저는 대리자의 `Invoke` 메서드를 호출하여 대리자 인스턴스를 통해 나중에 호출될 수 있습니다.  
  
 대리자는 네임스페이스, 모듈, 클래스 또는 구조체 수준에서 선언할 수 있고 프로시저 내에서는 선언할 수 없습니다.  
  
 각 대리자 클래스는 개체 메서드의 사양이 전달되는 생성자를 정의합니다.  대리자 생성자의 인수는 메서드에 대한 참조이거나 람다 식이어야 합니다.  
  
 메서드에 대한 참조를 지정하려면 다음 구문을 사용합니다.  
  
 `AddressOf` \[`expression`.\]`methodname`  
  
 `expression`의 컴파일 타임 형식은 지정된 이름의 시그니처가 대리자 클래스의 시그니처와 일치하는 메서드가 포함된 클래스 또는 인터페이스의 이름이어야 합니다.  `methodname`은 공유 메서드 또는 인스턴스 메서드가 될 수 있습니다.  `methodname`은 클래스의 기본 메서드에 대한 대리자를 만드는 경우에도 반드시 지정해야 합니다.  
  
 람다 식을 지정하려면 다음 구문을 사용합니다.  
  
 `Function` \(\[`parm` As `type`, `parm2` As `type2`, ...\]\) `expression`  
  
 함수의 시그니처는 대리자 형식의 시그니처와 일치해야 합니다.  람다 식에 대한 자세한 내용은 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하십시오.  
  
 대리자에 대한 자세한 내용은 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Delegate` 문을 사용하여 두 수에 대한 연산을 수행하고 하나의 숫자를 반환하는 대리자를 선언합니다.  `DelegateTest` 메서드는 이 형식의 대리자 인스턴스를 사용하고 이를 통해 숫자 쌍에 대한 연산을 수행합니다.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## 참고 항목  
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)