---
title: "File already open | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# File already open
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

일부 경우 다른 `FileOpen` 또는 다른 작업이 발생하기 전에 파일을 닫아야 합니다.  이 오류가 발생하는 몇 가지 원인은 다음과 같습니다.  
  
-   순차적 출력 모드 `FileOpen` 작업이 이미 열린 파일에 대해 실행되었습니다.  
  
-   문에서 열린 파일을 참조했습니다.  
  
### 이 오류를 해결하려면  
  
1.  문을 실행하기 전에 파일을 닫습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>