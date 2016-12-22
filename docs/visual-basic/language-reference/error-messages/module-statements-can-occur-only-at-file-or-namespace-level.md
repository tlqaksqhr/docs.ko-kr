---
title: "&#39;Module&#39; statements can occur only at file or namespace level | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30617"
  - "vbc30617"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30617"
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Module&#39; statements can occur only at file or namespace level
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Module` 문은 소스 파일의 위쪽, 즉 `Option` 문, `Imports` 문, 전역 특성 및 네임스페이스 선언을 제외한 다른 선언의 앞에 나와야 합니다.  
  
 **오류 ID:** BC30617  
  
### 이 오류를 해결하려면  
  
-   `Module` 문을 네임스페이스 선언 또는 소스 파일의 위쪽으로 이동합니다.  
  
## 참고 항목  
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)