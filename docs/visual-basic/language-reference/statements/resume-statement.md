---
title: "Resume Statement | Microsoft Docs"
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
  - "vb.Resume"
  - "vb.ResumeNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Next statement, Resume"
  - "Resume Next statement"
  - "execution, resuming"
  - "run-time errors, resuming after"
  - "Resume statement, syntax"
  - "errors [Visual Basic], resuming after"
  - "Error statement, and Resume statement"
  - "execution"
  - "Resume statement"
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Resume Statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

오류 처리 루틴이 완료된 후 실행을 다시 시작합니다.  
  
 가능 하면 코드에서 구조적된 예외 처리는 비구조적된 예외 처리를 사용 하 여 대신 사용 하는 것이 좋습니다 하는 `On Error` 및 `Resume` 문입니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
## 구문  
  
```  
Resume [ Next | line ]  
```  
  
## 요소  
 `Resume`  
 필수 요소.  오류 처리기와 같은 프로시저에서 오류가 발생한 경우 오류가 처음 발생한 문에서 실행을 다시 시작합니다.  호출된 프로시저에서 오류가 발생한 경우 오류 처리 루틴을 포함하는 프로시저에서 마지막으로 호출한 문에서 실행을 다시 시작합니다.  
  
 `Next`  
 선택적 요소.  오류 처리기와 같은 프로시저에서 오류가 발생한 경우 오류가 발생한 문 바로 다음 문에서 실행을 다시 시작합니다.  호출된 프로시저에서 오류가 발생한 경우 오류 처리 루틴을 포함하는 프로시저에서 마지막으로 호출한 문 바로 다음 문이나 `On Error Resume Next` 문에서 실행을 다시 시작합니다.  
  
 `line`  
 선택적 요소.  필수적 요소인 `line` 인수에 지정된 줄에서 실행을 다시 시작합니다.  `line` 인수는 줄 레이블이나 줄 번호이며 오류 처리기와 같은 프로시저에 있어야 합니다.  
  
## 설명  
  
> [!NOTE]
>  가능 하면 코드에서 구조적된 예외 처리는 비구조적된 예외 처리를 사용 하 여 대신 사용 하는 것이 좋습니다 하는 `On Error` 및 `Resume` 문입니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
 오류 처리 루틴을 제외한 그 밖의 장소에서 `Resume` 문을 사용하면 오류가 발생합니다.  
  
 `Resume` 문은 `Try...Catch...Finally` 문이 포함되어 있는 프로시저에서 사용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 `Resume` 문을 사용하여 프로시저에서 오류 처리를 중지하고 오류를 일으킨 문에서 실행을 다시 시작합니다.  `Resume` 문의 사용법을 설명하기 위해 오류 번호 55가 생성됩니다.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## 요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리\(Microsoft.VisualBasic.dll\)  
  
## 참고 항목  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)