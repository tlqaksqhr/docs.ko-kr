---
title: "Error Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "exceptions, types"
  - "errors [Visual Basic], types"
  - "errors [Visual Basic], logic"
  - "errors [Visual Basic], syntax"
  - "logic errors, Visual Basic"
  - "run-time errors, types of errors"
  - "syntax errors, Visual Basic"
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 오류\(*예외*라고도 함\)는 구문 오류, 런타임 오류 및 논리 오류의 세 가지 범주로 분류됩니다.  
  
## 구문 오류  
 *구문 오류*는 코드 작성 중에 발생하는 오류입니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 사용자가 **코드 편집기** 창에 코드를 입력할 때 이를 검사하여 철자를 잘못 입력하거나 언어 요소를 올바르지 않게 사용하는 등의 실수가 있으면 알려 줍니다.  이러한 구문 오류가 가장 흔한 형태의 오류이며,  발생 즉시 코딩 환경에서 쉽게 수정할 수 있습니다.  
  
> [!NOTE]
>  `Option Explicit` 문은 구문 오류를 방지할 수 있는 한 가지 방법입니다.  이 문을 사용하려면 응용 프로그램에서 사용할 모든 변수를 미리 선언해야 합니다.  이렇게 하면 코드에서 해당 변수를 사용할 때 철자 오류가 발생할 경우 즉시 catch하여 수정할 수 있습니다.  
  
## 런타임 오류  
 *런타임 오류*는 코드를 컴파일하여 실행한 후에만 나타나는 오류입니다.  런타임 오류에는 구문 오류가 없기 때문에 올바른 것처럼 보이지만 실행되지 않는 코드가 포함됩니다.  예를 들어, 파일을 여는 코드 한 줄을 올바르게 작성했어도  파일이 손상되었으면 해당 응용 프로그램이 `Open` 기능을 수행하지 못하고 실행이 중단됩니다.  대부분의 런타임 오류는 잘못된 코드를 다시 작성한 다음 다시 컴파일하고 실행하여 수정할 수 있습니다.  
  
## 논리 오류  
 *논리 오류*는 응용 프로그램을 사용할 때 나타나는 오류입니다.  주로 사용자의 작업에 대한 응답으로 원하지 않거나 예기치 않은 결과가 발생하는 경우가 논리 오류에 해당합니다.  예를 들면, 키를 잘못 입력하는 등의 외부 요인으로 인해 예상된 매개 변수와 동작하도록 되어 있는 응용 프로그램이 중단될 수 있습니다.  논리 오류는 일반적으로 오류 발생 원인이 분명하지 않기 때문에 가장 해결하기 어려운 형태의 오류입니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [디버거 기본 사항](/visual-studio/debugger/debugger-basics)