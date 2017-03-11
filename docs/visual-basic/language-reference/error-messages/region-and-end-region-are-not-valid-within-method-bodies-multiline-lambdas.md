---
title: "&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32025"
  - "vbc32025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32025"
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`#Region` 블록은 클래스, 모듈 또는 네임스페이스 수준에서 선언해야 합니다.  축소 가능한 영역에 하나 이상의 프로시저가 포함될 수 있지만 프로시저 내에서 그러한 영역이 시작이나 끝이 될 수는 없습니다.  
  
 **오류 ID:** BC32025  
  
### 이 오류를 해결하려면  
  
1.  앞에 나온 프로시저가 `End Function` 또는 `End Sub` 문으로 올바르게 종료되는지 확인합니다.  
  
2.  `#Region` 및 `#End Region` 지시문이 동일한 코드 블록에 있는지 확인합니다.  
  
## 참고 항목  
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)