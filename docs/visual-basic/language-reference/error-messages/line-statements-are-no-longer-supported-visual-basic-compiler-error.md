---
title: "&#39;Line&#39; statements are no longer supported (Visual Basic Compiler Error) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30830"
  - "vbc30830"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30830"
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &#39;Line&#39; statements are no longer supported (Visual Basic Compiler Error)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Line 문은 더 이상 지원되지 않습니다.  파일 I\/O 기능은 `Microsoft.VisualBasic.FileSystem.LineInput`으로 사용할 수 있으며 그래픽 기능은 `System.Drawing.Graphics.DrawLine`으로 사용할 수 있습니다.  
  
 **오류 ID:** BC30830  
  
### 이 오류를 해결하려면  
  
1.  파일에 액세스하려면 `Microsoft.VisualBasic.FileSystem.LineInput`을 사용합니다.  
  
2.  그래픽에 액세스하려면 `System.Drawing.Graphics.Drawline`을 사용합니다.  
  
## 참고 항목  
 <xref:System.IO>   
 <xref:System.Drawing>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)