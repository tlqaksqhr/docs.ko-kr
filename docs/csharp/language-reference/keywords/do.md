---
title: "do(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "do_CSharpKeyword"
  - "do"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "do 키워드[C#]"
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# do(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`do` 문은 지정된 식이 `false`가 될 때까지 하나의 문 또는 문 블록을 반복하여 실행합니다.  루프의 본문은 단일 문으로 구성되지 않는 한 중괄호\(`{}`\)로 묶여야 합니다.  이 경우 중괄호는 선택 사항입니다.  
  
## 예제  
 다음 예제의 `do-while` 루프 문은 `x` 변수가 5보다 작은 동안에만 실행합니다.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 `do-while` 루프는 [while](../../../csharp/language-reference/keywords/while.md) 문과 달리 조건식이 계산되기 전에 한 번 실행됩니다.  
  
 `do-while` 블록 내의 모든 위치에서 [break](../../../csharp/language-reference/keywords/break.md) 문을 사용하여 루프를 벗어날 수 있습니다.  [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용하여 `while` 식 계산 문으로 직접 보낼 수 있습니다.  `while` 식이 true이면 루프의 첫 번째 문에서 실행이 계속됩니다.  식이 false이면 `do-while` 루프 다음의 첫 번째 문에서 실행이 계속됩니다.  
  
 `do-while` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 사용하여 종료할 수도 있습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [do\-while 문\(C\+\+\)](/visual-cpp/cpp/do-while-statement-cpp)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)