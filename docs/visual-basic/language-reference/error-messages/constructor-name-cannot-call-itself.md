---
title: "Constructor &#39;&lt;name&gt;&#39; cannot call itself | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30298"
  - "vbc30298"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30298"
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Constructor &#39;&lt;name&gt;&#39; cannot call itself
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스 또는 구조체에 있는 `Sub New` 프로시저는 자신을 호출할 수 없습니다.  
  
 생성자는 클래스 또는 구조체가 처음 만들어질 때 클래스 또는 구조체의 인스턴스를 초기화하는 데 사용합니다.  각 생성자가 서로 다른 매개 변수 목록을 가지고 있는 경우 클래스 또는 구조체에 여러 개의 생성자를 포함할 수 있습니다.  생성자는 자신 외에도 다른 생성자를 호출하여 기능을 수행할 수 있습니다.  하지만 생성자가 자신을 호출하는 것은 무의미하며 허용하는 경우 무한 재귀가 발생할 수 있습니다.  
  
 **오류 ID:** BC30298  
  
### 이 오류를 해결하려면  
  
1.  호출될 생성자의 매개 변수 목록을 확인합니다.  호출을 수행하는 생성자와 달라야 합니다.  
  
2.  다른 생성자를 호출하지 않으려면 `Sub New` 호출을 완전히 제거합니다.  
  
## 참고 항목  
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)