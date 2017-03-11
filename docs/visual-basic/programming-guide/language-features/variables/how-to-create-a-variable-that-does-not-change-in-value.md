---
title: "How to: Create a Variable that Does Not Change in Value (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], read-only"
  - "variables [Visual Basic], constant value"
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Create a Variable that Does Not Change in Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값이 변경되지 않는 변수라는 개념은 모순되게 보일 수 있습니다.  그러나 때로는 상수는 적합하지 않고 값이 고정된 변수를 사용하는 것이 유용한 경우가 있습니다.  이런 경우 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드를 사용하여 멤버 변수를 정의할 수 있습니다.  
  
 다음과 같은 경우에는 [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)을 사용하여 상수 값을 선언하고 할당할 수 없습니다.  
  
-   사용하려는 데이터 형식을 `Const` 문에서 허용하지 않는 경우  
  
-   컴파일 타임에 값을 모르는 경우  
  
-   컴파일 타임에 상수 값을 계산할 수 없는 경우  
  
### 값이 변경되지 않는 변수를 만들려면  
  
1.  모듈 수준에서 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 멤버 변수를 선언하고 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드를 포함합니다.  
  
    ```  
  
    Dim ReadOnly timeStarted  
    ```  
  
     멤버 변수에만 `ReadOnly`를 지정할 수 있습니다.  따라서 모듈 수준에서, 즉 모든 프로시저의 외부에서 변수를 정의해야 합니다.  
  
2.  컴파일 타임에 단일 문의 값을 계산할 수 있으면 `Dim` 문에 초기화 절을 사용합니다.  [As](../../../../visual-basic/language-reference/statements/as-clause.md) 절 뒤에 등호\(`=`\)를 추가하고 그 다음에 식을 씁니다.  컴파일러에서 이 식을 상수 값으로 계산할 수 있는지 확인합니다.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     `ReadOnly` 변수에는 값을 한 번만 할당할 수 있습니다.  값을 할당한 후에는 코드에서 해당 값을 절대로 변경할 수 없습니다.  
  
     컴파일 타임에 값을 모르거나 단일 문에서 컴파일 타임에 값을 계산할 수 없는 경우 생성자에서 런타임에 값을 할당할 수 있습니다.  이렇게 하려면 클래스 또는 구조체 수준에서 `ReadOnly` 변수를 선언해야 합니다.  해당 클래스 또는 구조체의 생성자에서 변수의 고정 값을 계산한 다음 생성자에서 반환하기 전에 이 값을 변수에 할당합니다.  
  
## 참고 항목  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)