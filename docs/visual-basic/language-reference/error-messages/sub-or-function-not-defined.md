---
title: "Sub or Function not defined (Visual Basic) | Microsoft Docs"
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
  - "vbrID35"
dev_langs: 
  - "VB"
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub or Function not defined (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Sub` 또는 `Function`은 반드시 정의한 다음 호출해야 합니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   프로시저 이름의 철자가 잘못되었습니다.  
  
-   **참조** 대화 상자에서 해당 프로젝트에 명시적으로 참조를 추가하지 않고 다른 프로젝트에서 프로시저를 호출하려고 했습니다.  
  
-   호출하는 프로시저에서는 보이지 않는 프로시저를 지정했습니다.  
  
-   지정된 라이브러리 또는 코드 리소스에 없는 Windows DLL\(동적 연결 라이브러리\) 루틴 또는 Macintosh 코드 리소스 루틴을 선언했습니다.  
  
### 이 오류를 해결하려면  
  
1.  프로시저 이름의 철자가 올바른지 확인합니다.  
  
2.  **참조** 대화 상자에서 호출하고자 하는 프로시저가 들어 있는 프로젝트의 이름을 찾습니다.  표시되지 않으면 **찾아보기** 단추를 클릭하여 찾습니다.  프로젝트 이름 왼쪽의 확인란을 선택한 다음 **확인**을 클릭합니다.  
  
3.  루틴의 이름을 확인합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)