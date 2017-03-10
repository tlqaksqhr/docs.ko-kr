---
title: "Procedure Overloading (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "signatures"
  - "Overloads keyword"
  - "hiding by signature"
  - "Visual Basic code, procedures"
  - "procedures, signatures for"
  - "procedures, overloading"
  - "procedures, multiple versions"
  - "parameters, lists"
  - "signatures, procedure"
  - "parameter lists"
  - "Visual Basic code, parameter lists"
  - "Shadows keyword"
  - "procedure overloading"
  - "procedures, parameter lists"
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Procedure Overloading (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저 *오버로딩*은 이름은 동일하게 하되 서로 다른 매개 변수 목록을 사용하여 여러 버전으로 프로시저를 정의하는 것을 의미합니다.  오버로딩은 이름을 다르게 지정하지 않고도 밀접하게 관련된 여러 버전의 프로시저를 정의하기 위해서 사용하며  프로시저에 서로 다른 매개 변수 목록을 사용하여 수행할 수 있습니다.  
  
## 오버로딩 규칙  
 프로시저를 오버로드할 때 적용되는 규칙은 다음과 같습니다.  
  
-   **동일한 이름**.  각 오버로드된 버전에는 같은 프로시저 이름을 사용해야 합니다.  
  
-   **서로 다른 시그니처**.  다른 오버로드된 버전과 비교하여 각 오버로드된 버전은 다음 중 하나 이상이 달라야 합니다.  
  
    -   매개 변수의 개수  
  
    -   매개 변수의 순서  
  
    -   매개 변수의 데이터 형식  
  
    -   형식 매개 변수의 개수\(제네릭 프로시저의 경우\)  
  
    -   반환 형식\(변환 연산자에만 해당\)  
  
     프로시저 이름과 함께 위와 같은 항목들을 통틀어 프로시저의 *시그니처*라고 합니다.  오버로드된 프로시저를 호출하면 컴파일러에서 시그니처를 사용하여 호출이 해당 정의와 정확하게 일치하는지 확인합니다.  
  
-   **시그니처에 포함되지 않는 항목**.  프로시저를 오버로드하려면 시그니처가 달라야 합니다.  인수 목록이 아니라 다음과 같은 항목이 다른 경우에는 프로시저를 오버로드할 수 없습니다.  
  
    -   `Public`, `Shared`, `Static`과 같은 프로시저 한정자 키워드  
  
    -   매개 변수 또는 형식 매개 변수 이름  
  
    -   형식 매개 변수 제약 조건\(제네릭 프로시저의 경우\)  
  
    -   `ByRef`, `Optional`과 같은 매개 변수 한정자 키워드  
  
    -   값을 반환하는지 여부  
  
    -   반환 값의 데이터 형식\(변환 연산자는 제외\)  
  
     앞의 목록에 있는 항목은 시그니처에 해당하는 항목이 아닙니다.  이러한 항목을 사용하여 오버로드된 버전을 구분할 수는 없지만 해당 시그니처로 적절히 구분되어 있는 오버로드된 버전 간에 이러한 항목을 서로 다르게 지정할 수 있습니다.  
  
-   **런타임에 바인딩 인수**.  런타임에 바인딩되는 개체 변수를 오버로드된 버전에 전달하려면 적절한 매개 변수를 <xref:System.Object>로 선언해야 합니다.  
  
## 여러 버전의 프로시저  
 고객의 잔고에 대한 트랜잭션을 게시하는 `Sub` 프로시저를 작성하고 이름 또는 계정 번호로 고객을 참조하려는 경우를 예로 들면,  다음과 같이 두 개의 다른 `Sub` 프로시저를 사용하면 됩니다.  
  
 [!code-vb[VbVbcnProcedures#73](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_1.vb)]  
  
### 오버로드된 버전  
 그러나 이와 달리 하나의 프로시저 이름을 오버로드하는 방법도 사용할 수 있습니다.  다음과 같이 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용하여 각 매개 변수 목록에 대한 프로시저 버전을 정의할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_2.vb)]  
  
#### 추가 오버로드  
 거래액을 `Decimal` 또는 `Single`로 받아들이려면 `post`를 추가로 오버로드하면 됩니다.  앞의 예제에서 각 오버로드에 대해 이 작업을 수행한다면 이름은 같지만 네 개의 시그니처가 서로 다른 `Sub` 프로시저가 네 개 만들어집니다.  
  
## 오버로딩의 장점  
 프로시저를 오버로드하면 호출할 때 여러 인수를 사용할 수 있습니다.  앞의 예제에서 선언한 `post` 프로시저를 사용하려면 호출 코드에서 `String` 또는 `Integer`로 고객 ID를 가져온 다음 각각의 경우에 동일한 프로시저를 호출하면 됩니다.  다음 예제는 이러한 과정을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#56](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_4.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)