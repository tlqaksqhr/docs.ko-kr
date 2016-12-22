---
title: "EscapeQuote가 True로 설정되어 있으면 큰따옴표가 구분된 필드의 올바른 주석 토큰이 아닙니다. | Microsoft Docs"
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
  - "vbrTextFieldParser_InvalidComment"
dev_langs: 
  - "VB"
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# EscapeQuote가 True로 설정되어 있으면 큰따옴표가 구분된 필드의 올바른 주석 토큰이 아닙니다.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`TextFieldParser`에 대한 구분 기호로 따옴표가 제공되었지만 `EscapeQuotes`가 `True`로 설정되어 있습니다.  
  
### 이 오류를 해결하려면  
  
-   `EscapeQuotes`를 `False`로 설정합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 [How to: Read From Comma\-Delimited Text Files](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)