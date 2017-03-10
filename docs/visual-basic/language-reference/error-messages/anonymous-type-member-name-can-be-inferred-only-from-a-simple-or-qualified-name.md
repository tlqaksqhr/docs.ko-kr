---
title: "Anonymous type member name can be inferred only from a simple or qualified name with no arguments | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36556"
  - "bc36556"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36556"
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Anonymous type member name can be inferred only from a simple or qualified name with no arguments
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

복합 식에서는 익명 형식 멤버 이름을 유추할 수 없습니다.  
  
```vb#  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 익명 형식 멤버 이름과 형식을 유추하거나 유추할 수 없는 소스에 대한 자세한 내용은 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)를 참조하십시오.  
  
 **오류 ID:** BC36556  
  
### 이 오류를 해결하려면  
  
-   다음 코드와 같이 멤버 이름에 식을 할당합니다.  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## 참고 항목  
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)