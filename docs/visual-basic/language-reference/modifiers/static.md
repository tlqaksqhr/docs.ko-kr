---
title: "Static (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Static"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "static modifier"
  - "Static keyword"
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Static (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 선언된 지역 변수는 해당 변수가 선언된 프로시저가 끝난 후에도 계속 존재하고 최신 값을 그대로 유지하도록 지정합니다.  
  
## 설명  
 일반적으로 프로시저의 지역 변수는 프로시저가 중지되면 바로 소멸됩니다.  정적 변수는 계속 존재하며 최신 값을 그대로 유지합니다.  코드에서 프로시저를 다음에 호출할 때 변수는 다시 초기화되지 않고 해당 변수에 할당된 마지막 값을 그대로 유지합니다.  정적 변수는 정의된 클래스 또는 모듈의 수명 동안 계속 존재합니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Static`은 지역 변수에서만 사용할 수 있습니다.  즉, `Static` 변수의 선언 컨텍스트는 프로시저이거나 프로시저 내부의 블록이어야 하며 소스 파일, 네임스페이스, 클래스, 구조체 또는 모듈일 수는 없습니다.  
  
     `Static`은 구조체 프로시저에서는 사용할 수 없습니다.  
  
-   `Static` 지역 변수의 데이터 형식은 유추할 수 없습니다.  자세한 내용은 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조하십시오.  
  
-   **결합 한정자.** 하나의 선언에서 `Static`을 `ReadOnly`, `Shadows` 또는 `Shared`와 함께 지정할 수 없습니다.  
  
## 동작  
 정적 변수를 선언할 때는 `Shared` 프로시저를 정적 변수의 복사본을 하나만 전체 응용 프로그램에 대해 사용할 수 있습니다.  전화는 `Shared` 클래스의 인스턴스를 가리키는 변수가 아니라 클래스를 사용 하 여 프로시저 이름을 지정 합니다.  
  
 없는 프로시저의 정적 변수를 선언할 때 `Shared`, 변수 복사본 하나를 클래스의 각 인스턴스에 대해 사용할 수 있는.  클래스의 특정 인스턴스를 가리키는 변수를 사용 하 여 공유 되지 않는 프로시저를 호출 합니다.  
  
## 예제  
 다음 예제는 `Static`의 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 `Static` 변수 `totalSales`는 0으로 한 번만 초기화됩니다.  `updateSales`를 입력할 때마다 `totalSales`에는 가장 최근에 계산된 값이 유지됩니다.  
  
 `Static` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## 참고 항목  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)