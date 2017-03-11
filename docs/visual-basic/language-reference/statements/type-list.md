---
title: "Type List (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "StructureConstraint"
  - "vb.StructureConstraint"
  - "ClassConstraint"
  - "vb.ClassConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "class constraint"
  - "constraints, Visual Basic generic types"
  - "generic parameters"
  - "generics [Visual Basic], constraints"
  - "generics [Visual Basic], type list"
  - "structure constraint"
  - "constraints, in type parameters"
  - "generics [Visual Basic], generic types"
  - "parameters, type"
  - "constraints, Structure keyword"
  - "type parameters, constraints"
  - "types [Visual Basic], generic"
  - "parameters, generic"
  - "generics [Visual Basic], type parameters"
  - "type parameters"
  - "constraints, Class keyword"
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Type List (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*제네릭* 프로그래밍 요소에 대한 *형식 매개 변수*를 지정합니다.  매개 변수가 여러 개 있으면 쉼표로 구분됩니다.  다음은 단일 형식 매개 변수 구문입니다.  
  
## 구문  
  
```  
  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`genericmodifier`|선택적 요소.  제네릭 인터페이스와 대리자에서만 사용할 수 있습니다.  [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) 키워드를 사용하여 공변\(covariant\) 형식을 선언하거나 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) 키워드를 사용하여 반공변\(contravariant\) 형식을 선언할 수 있습니다.  자세한 내용은 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.|  
|`typename`|필수 요소.  형식 매개 변수 이름입니다.  해당 형식 인수가 제공하는 정의된 형식으로 대체될 자리 표시자입니다.|  
|`constraintlist`|선택적 요소.  `typename`에 제공할 수 있는 데이터 형식을 제한하는 요구 사항 목록입니다.  여러 개의 제약 조건을 사용하는 경우 제약 조건을 중괄호\(`{ }`\)로 묶고 쉼표로 구분합니다.  [As](../../../visual-basic/language-reference/statements/as-clause.md) 키워드를 사용하여 제약 조건 목록을 정의해야 합니다.  `As`는 목록의 시작 부분에 한 번만 사용합니다.|  
  
## 설명  
 모든 제네릭 프로그래밍 요소에는 하나 이상의 형식 매개 변수가 있어야 합니다.  형식 매개 변수는 제네릭 형식의 인스턴스를 만들 때 클라이언트 코드에 지정되는 특정 형식\(*생성된 요소*\)에 대한 자리 표시자입니다.  제네릭 클래스, 구조체, 인터페이스, 프로시저 또는 대리자를 정의할 수 있습니다.  
  
 제네릭 형식 정의 시기에 대한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)을 참조하십시오.  형식 매개 변수 이름에 대한 자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하십시오.  
  
## 규칙  
  
-   **괄호.** 형식 매개 변수 목록을 제공하는 경우 목록을 괄호로 묶은 다음 [Of](../../../visual-basic/language-reference/statements/of-clause.md) 키워드를 사용하여 정의해야 합니다.  `Of`는 목록의 시작 부분에 한 번만 사용합니다.  
  
-   **제약 조건.** 형식 매개 변수에 대한 *제약 조건* 목록에는 다음 항목을 조합하여 포함할 수 있습니다.  
  
    -   인터페이스\(수에 제한 없음\).  제공된 형식은 이 목록의 모든 인터페이스를 구현해야 합니다.  
  
    -   최대 하나의 클래스.  제공된 형식이 해당 클래스에서 상속되어야 합니다.  
  
    -   `New` 키워드입니다.  제공된 형식이 제네릭 형식이 액세스할 수 있는 매개 변수 없는 생성자를 노출해야 합니다.  하나 이상의 인터페이스로 형식 매개 변수를 제한하는 경우에 유용합니다.  인터페이스를 구현하는 형식이 반드시 생성자를 노출할 필요는 없습니다. 생성자의 액세스 수준에 따라 제네릭 형식 내의 코드가 해당 형식에 액세스하지 못할 수도 있습니다.  
  
    -   `Class` 키워드 또는 `Structure` 키워드.  `Class` 키워드는 제네릭 형식 매개 변수에 전달된 모든 형식 인수가 문자열, 배열 또는 대리자와 같은 참조 형식이 되거나 클래스에서 만든 개체가 되도록 제한합니다.  `Structure` 키워드는 제네릭 형식 매개 변수에 전달된 모든 형식 인수가 구조체, 열거형 또는 기본 데이터 형식과 같은 값 형식이 되도록 제한합니다.  `constraintlist` 하나에 `Class`와 `Structure`를 모두 포함할 수는 없습니다.  
  
     사용된 형식이 `constraintlist`에 포함된 모든 요구 사항을 충족해야 합니다.  
  
     각 형식 매개 변수에 대한 제약 조건은 다른 형식 매개 변수에 대한 제약 조건과 별개입니다.  
  
## 동작  
  
-   **컴파일 타임 대체.** 제네릭 프로그래밍 요소에서 생성된 형식을 만드는 경우 각 형식 매개 변수에 대해 정의된 형식을 제공합니다.  Visual Basic 컴파일러는 제네릭 요소 내의 모든 `typename` 항목에 대해 제공된 형식을 사용합니다.  
  
-   **제약 조건 없음.** 형식 매개 변수에 대한 제약 조건을 지정하지 않으면 해당 형식 매개 변수에 대해 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)에서 지원하는 작업과 멤버를 대상으로만 코드를 작성할 수 있습니다.  
  
## 예제  
 다음 예제에서는 새 항목을 사전에 추가하는 기본 함수를 비롯하여 제네릭 사전 클래스의 기본 정의를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_1.vb)]  
  
## 예제  
 `dictionary`가 제네릭이기 때문에 사전을 사용하는 코드는 서로 다른 데이터 형식에 적용되지만 기능이 동일한 다양한 개체를 만들 수 있습니다.  다음 예제에서는 `String` 항목과 `Integer` 키를 사용하여 `dictionary` 개체를 만드는 코드 줄을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_2.vb)]  
  
## 예제  
 다음 예제에서는 앞의 예제에서 생성한 것과 동일한 기본 정의를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/type-list_3.vb)]  
  
## 참고 항목  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [공 분산 및 반공 분산](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)