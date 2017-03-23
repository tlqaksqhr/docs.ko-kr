---
title: "Bad record length | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID59"
dev_langs: 
  - "VB"
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Bad record length
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 오류가 발생하는 몇 가지 원인은 다음과 같습니다.  
  
-   `FileGet`, `FileGetObject`, `FilePut` 또는 `FilePutObject` 문에 지정된 레코드 변수의 길이가 해당 `FileOpen` 문에 지정된 길이와 다릅니다.  
  
-   `FilePut` 또는 `FilePutObject` 문에 있는 변수가 가변 길이 문자열이거나 이를 포함합니다.  
  
-   `FilePut` 또는 `FilePutObject`에 있는 변수가 `Variant`형식이거나 이를 포함합니다**.**  
  
### 이 오류를 해결하려면  
  
1.  레코드 변수의 형식을 정의하는 사용자 정의 형식에 있는 고정 길이 변수 크기의 합이 `FileOpen` 문의 `Len` 절에 명시된 값과 같은지 확인합니다.  
  
2.  `FilePut` 또는 `FilePutObject` 문에 있는 변수가 가변 길이 문자열이거나 이를 포함하면 가변 길이 문자열이 `FileOpen` 문의 `Len` 절에 지정된 레코드 길이보다 2자 이상 짧은지 확인합니다.  
  
3.  `FilePut` 또는 `FilePutObject`에 있는 변수가 `Variant`이거나 이를 포함하면 가변 길이 문자열이 `FileOpen` 문의 `Len` 절에 지정된 레코드 길이보다 4바이트 이상 짧은지 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>