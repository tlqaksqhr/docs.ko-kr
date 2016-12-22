---
title: "Too many files | Microsoft Docs"
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
  - "vbrID67"
dev_langs: 
  - "VB"
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Too many files
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

운영 시스템에서 허용하는 개수보다 많은 파일이 루트 디렉터리에 만들어졌거나 CONFIG.SYS 파일의 **files\=** 설정에 지정된 개수보다 많은 파일이 열려 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  현재 프로그램에서 루트 디렉터리의 파일에 대해 열기, 닫기 또는 저장 작업을 수행하고 있으면 해당 작업을 하위 디렉터리에서 수행하도록 프로그램을 변경합니다.  
  
2.  CONFIG.SYS 파일에서 **files\=** 설정에 지정된 파일 개수를 늘린 다음 컴퓨터를 다시 시작합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)