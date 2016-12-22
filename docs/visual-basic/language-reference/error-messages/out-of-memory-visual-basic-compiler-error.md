---
title: "Out of memory (Visual Basic Compiler Error) | Microsoft Docs"
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
  - "vbc2004"
  - "bc2004"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC2004"
ms.assetid: 6bc0939c-e279-4875-a91c-f4076860b5b9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Out of memory (Visual Basic Compiler Error)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

사용 가능한 메모리 이상의 메모리가 필요합니다.  
  
 **오류 ID:** BC2004  
  
### 이 오류를 해결하려면  
  
-   불필요한 응용 프로그램, 문서 및 소스 파일을 닫습니다.  
  
-   불필요한 컨트롤과 폼을 제거하여 한꺼번에 로드되는 항목의 개수를 줄입니다.  
  
-   `Public` 변수의 개수를 줄입니다.  
  
-   사용 가능한 디스크 공간을 확인하십시오.  
  
-   추가 메모리를 설치하거나 메모리를 다시 할당하여 사용 가능한 RAM을 늘립니다.  
  
-   더 이상 필요 없는 메모리가 해제되도록 합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)