---
title: "Variable uses an Automation type not supported in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID458"
dev_langs: 
  - "VB"
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Variable uses an Automation type not supported in Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 지원하지 않는 데이터 형식을 가진 형식 라이브러리 또는 개체 라이브러리에 정의된 변수를 사용하려고 했습니다.  
  
### 이 오류를 해결하려면  
  
-   [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 인식할 수 있는 형식의 변수를 사용합니다.  
  
     또는  
  
-   `FileGet` 또는 `FileGetOBject`를 사용하는 동안 이 오류가 발생한 경우에는 사용하려는 파일이 `FilePut` 또는 `FilePutObject`를 통해 작성되었는지 확인합니다.  
  
## 참고 항목  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)