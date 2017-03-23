---
title: "Bad file name or number | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID52"
dev_langs: 
  - "VB"
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Bad file name or number
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정된 파일에 액세스하려는 동안 오류가 발생했습니다.  이 오류가 발생하는 몇 가지 원인은 다음과 같습니다.  
  
-   문에서 `FileOpen` 문에 지정되지 않았거나 `FileOpen` 문에 지정됐지만 그 후에 닫힌 파일 이름 또는 번호를 사용하여 파일을 참조했습니다.  
  
-   문에서 파일 번호의 범위를 벗어난 번호를 사용하여 파일을 참조했습니다.  
  
-   문에서 잘못된 파일 이름 또는 번호를 참조했습니다.  
  
### 이 오류를 해결하려면  
  
1.  파일 이름이 `FileOpen` 문에 지정되었는지 확인합니다.  `FileClose` 문을 인수 없이 호출하면 열린 파일이 모두 닫힐 수 있습니다.  
  
2.  코드에서 알고리즘을 통해 파일 번호를 생성하는 경우 번호가 올바른지 확인합니다.  
  
3.  파일 이름이 운영 체제 규칙에 맞는지 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)