---
title: "Function evaluation is disabled because a previous function evaluation timed out | Microsoft Docs"
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
  - "bc30957"
  - "vbc30957"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30957"
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Function evaluation is disabled because a previous function evaluation timed out
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.함수를 다시 실행하려면 단계별로 다시 실행하거나 디버깅을 다시 시작하십시오.  
  
 Visual Studio 디버거에서 식이 프로시저 호출을 지정하지만 다른 실행 시간이 초과되었습니다.  
  
 프로시저 호출 시간이 초과된 원인이 *무한 루프* 때문일 수도 있습니다.  자세한 내용은 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)을 참조하십시오.  
  
 무한 루프의 특수한 경우는 *재귀*입니다.  자세한 내용은 [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)을 참조하십시오.  
  
 **오류 ID:** BC30957  
  
### 이 오류를 해결하려면  
  
1.  가능하면 이전 함수 실행 결과를 확인하고 시간이 초과된 이유가 무엇인지 확인합니다.  그렇지 않으면 이 오류가 다시 발생할 수 있습니다.  
  
2.  디버깅 단계를 다시 수행하거나 디버깅을 종료하고 다시 시작합니다.  
  
## 참고 항목  
 [Visual Studio의 디버깅](/visual-studio/debugger/debugging-in-visual-studio)   
 [디버거로 코드 탐색](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Visual Basic의 식](../Topic/Expressions%20in%20Visual%20Basic.md)