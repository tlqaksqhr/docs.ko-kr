---
title: "Declared Element Characteristics (Visual Basic) | Microsoft Docs"
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
  - "declared elements, lifetime"
  - "access levels, declared elements"
  - "declared elements, scope"
  - "visibility, declared elements"
  - "elements, programming"
  - "scope, declared elements"
  - "lifetime, declared elements"
  - "declared elements, access level"
  - "data types [Visual Basic], declared elements"
  - "declared elements, visibility"
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Declared Element Characteristics (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언 요소의 *특징*은 코드가 이 요소와 상호 작용하는 방식에 영향을 주는 부분을 말합니다.  선언된 모든 요소에는 다음 특징이 하나 이상 연결되어 있습니다.  
  
-   *데이터 형식* — 요소에 사용할 수 있는 값과 이러한 값이 저장되는 방식  자세한 내용은 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하십시오.  
  
-   *수명* — 요소를 사용할 수 있는 실행 기간  자세한 내용은 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)을 참조하십시오.  
  
-   *범위* — 요소 이름을 한정하지 않고 이를 참조할 수 있는 모든 코드 집합  자세한 내용은 [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)를 참조하십시오.  
  
-   *액세스 수준* — 코드가 요소를 사용할 수 있는 권한  자세한 내용은 [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)를 참조하십시오.  
  
## 요소의 특징  
 다음 표에서는 선언 요소와 각 요소에 해당되는 특징을 보여 줍니다.  
  
|요소|데이터 형식|수명|범위 <sup>1</sup>|액세스 수준|  
|--------|------------|--------|---------------------|------------|  
|변수|예|예|예|예|  
|상수|예|아니요|예|예|  
|열거형|예|아니요|예|예|  
|구조체|아니요|아니요|예|예|  
|Property|예|예|예|예|  
|메서드|아니요|예|예|예|  
|프로시저\(`Sub` 또는 `Function`\)|아니요|예|예|예|  
|프로시저 매개 변수|예|예|예|아니요|  
|함수 반환값|예|예|예|아니요|  
|Operator|예|아니요|예|예|  
|Interface|아니요|아니요|예|예|  
|클래스|아니요|아니요|예|예|  
|Event|아니요|아니요|예|예|  
|대리자|아니요|아니요|예|예|  
  
 <sup>1</sup> 범위를 *표시 유형*이라고도 합니다.  
  
## 참고 항목  
 [Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)