---
title: "File is too large to read into a byte array | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# File is too large to read into a byte array
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

바이트 배열로 읽으려는 파일 크기가 4GB를 초과합니다.  `My.Computer.FileSystem.ReadAllBytes` 메서드는 이 크기를 초과하는 파일을 읽을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   <xref:System.IO.StreamReader>를 사용하여 파일을 읽습니다.  자세한 내용은 [.NET Framework 파일 I\/O 및 파일 시스템의 기본 사항\(Visual Basic\)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:System.IO.StreamReader>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)   
 [How to: Read Text from Files with a StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)