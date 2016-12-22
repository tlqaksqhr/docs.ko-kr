---
title: "How to: Refer to the Current Instance of an Object (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], object"
  - "objects [Visual Basic], referring to current instance"
  - "instances, referring to current"
  - "current instance"
  - "object variables"
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Refer to the Current Instance of an Object (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

개체의 *현재 인스턴스*는 코드가 현재 실행 중인 인스턴스입니다.  
  
 `Me` 키워드를 사용하여 현재 인스턴스를 참조합니다.  
  
### 현재 인스턴스를 참조하려면  
  
-   일반적으로 개체 변수의 이름을 사용하는 위치에 `Me` 키워드를 사용합니다.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     `Me`는 개체 변수처럼 동작하지만 선언하거나 값을 할당할 수는 없습니다.  `Me`는 항상 현재 인스턴스를 참조합니다.  
  
## 참고 항목  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)