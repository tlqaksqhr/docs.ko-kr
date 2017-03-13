---
title: "ReadOnly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ReadOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ReadOnly keyword"
  - "variables [Visual Basic], read-only"
  - "ReadOnly property"
  - "properties [Visual Basic], read-only"
  - "read-only variables"
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ReadOnly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수나 속성을 읽을 수는 있지만 쓸 수는 없도록 지정합니다.  
  
## 설명  
  
## 규칙  
  
-   **선언 컨텍스트.** `ReadOnly` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, `ReadOnly` 요소의 선언 컨텍스트는 클래스, 구조체 또는 모듈이어야 하며 소스 파일, 네임스페이스 또는 프로시저일 수는 없습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `ReadOnly`를 `Static`과 함께 지정할 수 없습니다.  
  
-   **값 할당.** `ReadOnly` 속성을 사용하는 코드에서는 해당 값을 설정할 수 없습니다.  그러나 내부 저장소에 액세스할 수 있는 코드에서는 언제든지 값을 할당하거나 변경할 수 있습니다.  
  
     `ReadOnly` 변수에 대한 값을 해당 선언이나 클래스 또는 구조체가 정의된 생성자에서만 할당할 수 있습니다.  
  
## ReadOnly 변수를 사용하는 경우  
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)을 사용하여 상수 값을 선언하거나 할당할 수 없는 경우입니다.  예를 들어, 할당할 데이터 형식이 `Const` 문에서 허용되지 않거나 상수 식을 사용하여 컴파일 타임에 값을 계산하지 못할 수 있습니다.  컴파일 타임에 값을 모르는 경우  `ReadOnly` 변수를 사용하여 상수 값을 저장할 수 있습니다.  
  
> [!IMPORTANT]
>  변수의 데이터 형식이 배열 또는 클래스 인스턴스와 같은 참조 형식이면 변수 자체가 `ReadOnly`인 경우에도 해당 멤버를 변경할 수 있습니다.  다음은 이에 대한 예입니다.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 초기화 시에 `characterArray()`가 가리키는 배열은 "x", "y" 및 "z"를 저장합니다.  `characterArray` 변수가 `ReadOnly`이기 때문에 초기화된 후에 해당 값을 변경할 수 없습니다. 즉, 새 배열을 이 변수에 할당할 수 없습니다.  그러나 배열 멤버 중 하나 이상의 값을 변경할 수는 있습니다.  `changeArrayElement` 프로시저가 호출된 후에 `characterArray()`가 가리키는 배열은 "x", "M" 및 "z"를 저장합니다.  
  
 이는 프로시저 매개 변수를 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)이 되도록 선언하여 프로시저에서 호출 인수 자체를 변경할 수 없지만 해당 멤버를 변경할 수 있도록 허용하는 것과 비슷합니다.  
  
## 예제  
 다음 예제에서는 직원이 고용된 날짜에 대해 `ReadOnly` 속성을 정의합니다.  클래스는 내부적으로 속성 값을 `Private` 변수로 저장하며 클래스 안의 코드에서만 해당 값을 변경할 수 있습니다.  그러나 속성이 `Public`이므로 클래스에 액세스할 수 있는 모든 코드에서 속성을 읽을 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 `ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## 참고 항목  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)