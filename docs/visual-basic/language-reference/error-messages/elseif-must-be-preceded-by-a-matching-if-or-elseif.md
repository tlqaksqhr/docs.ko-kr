---
title: "&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30014"
  - "bc30014"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30014"
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`#ElseIf`는 조건부 컴파일 지시문입니다.  `#ElseIf` 절은 짝이 되는 `#If` 절이나 `#ElseIf` 절 뒤에 와야 합니다.  
  
 **오류 ID:** BC30014  
  
### 이 오류를 해결하려면  
  
1.  조건부 컴파일 블록을 테스트하기 위해 앞에 오는 `#If`  또는 `#ElseIf`를 `#ElseIf`에서 분리한 것인지 또는 `#End If`가 잘못 사용된 것인지 확인합니다.  
  
2.  `#ElseIf`가 `#Else` 지시문 뒤에 오면 `#Else`를 제거하거나 `#ElseIf`로 변경합니다.  
  
3.  위의 경우에 모두 해당하지 않으면 `#If` 지시문을 조건부 컴파일 블록의 시작 부분에 추가합니다.  
  
## 참고 항목  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)