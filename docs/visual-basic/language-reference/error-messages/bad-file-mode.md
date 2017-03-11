---
title: "Bad file mode | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID54"
dev_langs: 
  - "VB"
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Bad file mode
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파일 내용을 조작하는 데 사용된 문은 대상 파일의 모드에 적합해야 합니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   `FilePutObject` 또는 `FileGetObject` 문에서 순차적 파일을 지정했습니다.  
  
-   `Print` 문에서 `Output`이나 `Append`가 아닌 액세스 모드로 열린 파일을 지정했습니다.  
  
-   `Input` 문에서 `Input`이 아닌 액세스 모드로 열린 파일을 지정했습니다.  
  
-   읽기 전용 파일에 쓰려고 했습니다.  
  
### 이 오류를 해결하려면  
  
-   `FilePutObject` 및 `FileGetObject`가 `Random` 또는 `Binary` 액세스로 열린 파일만 참조하고 있는지 확인합니다.  
  
-   `Print`에서 `Output` 또는 `Append` 액세스 모드로 열린 파일을 지정하는지 확인합니다.  그렇지 않으면 다른 문을 사용하여 데이터를 파일에 놓거나 적합한 모드로 파일을 다시 엽니다.  
  
-   `Input`에서 `Input`으로 열린 파일을 지정하는지 확인합니다.  그렇지 않으면 다른 문을 사용하여 데이터를 파일에 놓거나 적합한 모드로 파일을 다시 엽니다.  
  
-   읽기 전용 파일에 쓰려면 파일의 읽기\/쓰기 상태를 변경하거나 이 파일에 쓰지 않도록 합니다.  
  
-   `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem>   
 [Troubleshooting: Reading from and Writing to Text Files](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)