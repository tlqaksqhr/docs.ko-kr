---
title: "&#39;&lt;functionname&gt;&#39; is not declared (Smart Device/Visual Basic Compiler Error) | Microsoft Docs"
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
  - "bc30766"
  - "vbc30766"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30766"
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;functionname&gt;&#39; is not declared (Smart Device/Visual Basic Compiler Error)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<`functionname`\>이\(가\) 선언되지 않았습니다.  파일 I\/O 기능은 보통 `Microsoft.VisualBasic` 네임스페이스에서 사용할 수 있습니다. 하지만 대상으로 지정된 버전의 .NET Compact Framework에서는 파일 I\/O 기능을 지원하지 않습니다.  
  
 **오류 ID:** BC30766  
  
### 이 오류를 해결하려면  
  
-   `System.IO` 네임스페이스에 정의된 함수를 사용하여 파일 작업을 수행합니다.  
  
## 참고 항목  
 <xref:System.IO>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)