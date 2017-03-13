---
title: "while(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "while_CSharpKeyword"
  - "while"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "while 키워드[C#]"
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# while(C# 참조)
`while` 문은 지정된 식이 `false`가 될 때까지 하나의 문 또는 문 블록을 반복하여 실행합니다.  
  
## 예제  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## 예제  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## 예제  
 각 루프를 실행하기 전에 `while` 식을 테스트하기 때문에 `while` 루프는 0번 이상 실행됩니다.  이는 한 번 이상 실행되는 [do](../../../csharp/language-reference/keywords/do.md) 루프와 다른 부분입니다.  
  
 [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문이 제어를 루프 밖으로 전달할 때 `while` 루프를 종료할 수 있습니다.  루프를 종료하지 않고 다음 반복 실행으로 제어를 전달하려면 [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용합니다.  위 세 개의 예제에서 출력은 `int n`이 증가되는 위치에 따라 달라집니다.  다음 예제에서는 출력이 생성되지 않습니다.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [while 문 \(C\+\+\)](/visual-cpp/cpp/while-statement-cpp)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)