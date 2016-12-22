---
title: "Error in loading DLL (Visual Basic) | Microsoft Docs"
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
  - "vbrID48"
dev_langs: 
  - "VB"
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error in loading DLL (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

DLL\(동적 연결 라이브러리\)는 `Declare` 문의 `Lib` 절에 지정된 라이브러리입니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   DLL로 실행할 수 있는 파일이 아닙니다.  
  
-   Microsoft Windows DLL 파일이 아닙니다.  
  
-   DLL이 존재하지 않는 다른 DLL을 참조합니다.  
  
-   경로에 지정된 디렉터리에 DLL 또는 참조 DLL이 없습니다.  
  
### 이 오류를 해결하려면  
  
-   파일이 소스 텍스트 파일이고 따라서 DLL로 실행할 수 없으면 DLL 실행 가능한 형식으로 컴파일하고 연결해야 합니다.  
  
-   파일이 Microsoft Windows DLL이면 해당 Microsoft Windows를 사용합니다.  
  
-   DLL이 존재하지 않는 다른 DLL을 참조하면 참조 DLL을 가져와 사용 가능하게 만듭니다.  
  
-   DLL 또는 참조 DLL이 경로에 지정된 디렉터리에 없으면 DLL을 참조 디렉터리로 이동합니다.  
  
## 참고 항목  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)