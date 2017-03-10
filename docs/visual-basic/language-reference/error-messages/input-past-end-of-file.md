---
title: "Input past end of file | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID62"
dev_langs: 
  - "VB"
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Input past end of file
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Input` 문에서 비어 있거나 모든 데이터가 사용 중인 파일로부터 읽고 있거나, 이진 액세스에 대해 열린 파일에 `EOF` 함수를 사용했습니다.  
  
### 이 오류를 해결하려면  
  
1.  `EOF` 함수를 `Input` 문 바로 앞에 사용하여 파일의 끝을 검색합니다.  
  
2.  파일이 이진 액세스에 대해 열려 있으면 `Seek` 및 `Loc`을 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>