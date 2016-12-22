---
title: "&#39;Optional&#39; expected | Microsoft Docs"
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
  - "bc30202"
  - "vbc30202"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30202"
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Optional&#39; expected
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

프로시저 선언에서 선택적 인수 다음에 필수 인수가 있습니다.  선택적 인수 다음에 나오는 인수는 모두 선택적이어야 합니다.  
  
 **오류 ID:** BC30202  
  
### 이 오류를 해결하려면  
  
1.  해당 인수가 필수 인수이면 인수 목록에서 첫째 선택적 인수 앞으로 이동합니다.  
  
2.  해당 인수가 선택적 인수이면 `Optional` 키워드를 사용합니다.  
  
## 참고 항목  
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)