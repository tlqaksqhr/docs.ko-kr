---
title: "Initializer expected | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30996"
  - "bc30996"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30996"
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Initializer expected
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 예제와 같이 이니셜라이저 목록이 비어 있는 개체 이니셜라이저를 사용하여 클래스의 인스턴스를 선언하려고 했습니다.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 다음 예제와 같이 이니셜라이저 목록에서 필드나 속성을 하나 이상 초기화해야 합니다.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **오류 ID:** BC30996  
  
### 이 오류를 해결하려면  
  
1.  이니셜라이저에서 필드나 속성을 하나 이상 초기화하거나 개체 이니셜라이저를 사용하지 마십시오.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)