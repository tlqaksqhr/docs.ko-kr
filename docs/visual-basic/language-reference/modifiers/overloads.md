---
title: "Overloads (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Overloads"
  - "Overloads"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Overloads keyword"
  - "hiding by signature"
  - "Shadows keyword"
  - "signature, hiding by"
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Overloads (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성 또는 프로시저에서 하나 이상의 기존 속성 또는 프로시저를 같은 이름으로 다시 선언할 수 있도록 지정합니다.  
  
## 설명  
 *오버로드*는 같은 범위에서 지정된 속성 또는 프로시저 이름에 대한 정의를 두 개 이상 제공하는 방법입니다.  속성이나 프로시저를 다른 서명으로 다시 선언하는 것을 *시그니처로 숨김*이라고도 합니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** 속성 또는 프로시저 선언문에서만 `Overloads`를 사용할 수 있습니다.  
  
-   **결합된 한정자.** `Overloads`는 동일한 프로시저 선언에서 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)와 함께 지정할 수 없습니다.  
  
-   **차이 필요.** 이 선언의 *서명*은 오버로드되는 모든 속성 또는 프로시저의 서명과 달라야 합니다.  서명은 다음 항목과 함께 속성 또는 프로시저 이름으로 구성됩니다.  
  
    -   매개 변수 수  
  
    -   매개 변수의 순서  
  
    -   매개 변수의 데이터 형식  
  
    -   형식 매개 변수의 수\(제네릭 프로시저의 경우\)  
  
    -   반환 형식\(변환 연산자 프로시저의 경우만\)  
  
     모든 오버로드는 이름이 같아야 하지만 앞에서 설명한 하나 이상의 측면과 관련하여 각각은 다른 모든 오버로드와 달라야 합니다.  그러면 컴파일러가 코드에서 속성 또는 프로시저를 호출할 때 사용할 버전을 구분할 수 있습니다.  
  
-   **차이 허용 안 함.** 다음 중 하나 이상은 서명의 일부가 아니므로 속성 또는 프로시저를 오버로드하기 위해 변경할 수 없습니다.  
  
    -   값을 반환하는지 여부\(프로시저의 경우\)  
  
    -   반환 값의 데이터 형식\(변환 연산자 제외\)  
  
    -   매개 변수 또는 형식 매개 변수의 이름  
  
    -   형식 매개 변수에 대한 제약 조건\(제네릭 프로시저의 경우\)  
  
    -   매개 변수 한정자 키워드\(예: `ByRef` 또는 `Optional`\)  
  
    -   속성 또는 프로시저 한정자 키워드\(예: `Public` 또는 `Shared`\)  
  
-   **선택적 한정자.** 동일한 클래스에서 오버로드된 속성 또는 프로시저를 여러 개 정의하려는 경우 `Overloads` 한정자를 사용할 필요가 없습니다.  그러나 선언 중 하나에서 `Overloads`를 사용하는 경우에는 모든 선언에서 사용해야 합니다.  
  
-   **섀도잉 및 오버로드.** `Overloads`는 기본 클래스에서 기존 멤버 또는 오버로드된 멤버 집합을 섀도잉하는 데 사용할 수도 있습니다.  이런 방식으로 `Overloads`를 사용하는 경우 기본 클래스 멤버와 동일한 이름 및 동일한 매개 변수 목록을 사용하여 속성 또는 메서드를 선언하고 `Shadows` 키워드는 제공하지 않습니다.  
  
 `Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C\#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.  
  
 `Overloads` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)