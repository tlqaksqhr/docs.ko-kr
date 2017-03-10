---
title: "Identifier is too long | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30033"
  - "vbc30033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30033"
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Identifier is too long
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

모든 프로그래밍 요소의 이름 또는 식별자에는 1023자까지만 사용할 수 있습니다.  또한 정규화된 이름은 1023자를 초과할 수 없습니다.  즉, 전체 식별자 문자열\(`<namespace>.<...>.<namespace>.<class>.<element>`\)의 길이가 멤버 액세스 연산자\(`.`\) 문자를 포함하여 1023자를 초과할 수 없습니다.  
  
 **오류 ID:** BC30033  
  
### 이 오류를 해결하려면  
  
-   식별자의 길이를 줄입니다.  
  
## 참고 항목  
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)