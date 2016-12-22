---
title: "Throw Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Throw"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "structured exception handling, throw statements"
  - "try-catch exception handling, throw statements"
  - "throw statement, about throw statements"
  - "throwing exceptions, throw statement"
  - "exception handling, throw statement"
  - "On Error statement, throwing exceptions"
  - "throwing exceptions"
  - "exception handling, unstructured"
  - "throw statement"
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Throw Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

프로시저 내에서 예외를 throw합니다.  
  
## 구문  
  
```  
Throw [ expression ]  
```  
  
## 파트  
 `expression`  
 throw할 오류에 대한 정보를 제공합니다.  `Catch` 문에 있는 경우에는 선택적 요소이며, 그렇지 않은 경우 필수 요소입니다.  
  
## 설명  
 `Throw` 문에서는 구조적 예외 처리 코드\(`Try`...`Catch`...`Finally`\)나 비구조적 예외 처리 코드\(`On Error GoTo`\)를 사용하여 처리할 수 있는 예외를 throw합니다.  Visual Basic에서는 적절한 예외 처리 코드를 찾을 때까지 호출 스택의 위로 이동하기 때문에 `Throw` 문을 사용하여 코드 내에서 오류를 처리할 수 있습니다.  
  
 식이 없는 `Throw` 문은 `Catch` 문에서만 사용할 수 있습니다. 이러한 경우 `Catch` 문에서 현재 처리하고 있는 예외를 다시 throw합니다.  
  
 `Throw` 문에서는 `expression` 예외의 호출 스택을 다시 설정합니다.  `expression`이 제공되지 않은 경우에는 호출 스택이 그대로 유지됩니다.  <xref:System.Exception.StackTrace%2A> 속성을 통해 예외의 호출 스택에 액세스할 수 있습니다.  
  
## 예제  
 다음 코드에서는 `Throw` 문을 사용하여 예외를 throw합니다.  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## 요구 사항  
 **네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **모듈:** `Interaction`  
  
 **어셈블리:** Visual Basic 런타임 라이브러리\(Microsoft.VisualBasic.dll\)  
  
## 참고 항목  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)