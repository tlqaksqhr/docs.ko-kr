---
title: "Permission denied (Visual Basic) | Microsoft Docs"
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
  - "vbrID70"
dev_langs: 
  - "VB"
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Permission denied (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쓰기 금지된 디스크에 쓰거나 잠긴 파일에 액세스하려고 했습니다.  
  
### 이 오류를 해결하려면  
  
1.  쓰기 금지된 파일을 열려면 파일의 쓰기 금지 특성을 변경합니다.  
  
2.  다른 프로세스에서 파일을 잠근 경우 해제될 때까지 기다린 다음 파일을 엽니다.  
  
3.  레지스트리에 액세스하려면 사용자 권한을 확인하여 이 형식의 레지스트리 액세스를 포함하고 있는지 확인합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)