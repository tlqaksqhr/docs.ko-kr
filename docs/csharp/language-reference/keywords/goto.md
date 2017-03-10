---
title: "goto(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "goto_CSharpKeyword"
  - "goto"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "goto 키워드[C#]"
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# goto(C# 참조)
`goto` 문은 프로그램의 제어를 레이블 문으로 직접 전달합니다.  
  
 일반적으로 `goto`는 `switch` 문에서 특정 switch\-case 레이블이나 기본 레이블로 제어를 전달하는 데 사용합니다.  
  
 `goto` 문은 깊이 중첩된 루프를 벗어나는 경우에도 유용하게 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `goto`를 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/csharp/goto_1.cs)]  
  
## 예제  
 아래 예제에서는 `goto`를 사용하여 중첩된 루프를 중단하는 방법을 설명합니다.  
  
 [!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/csharp/goto_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [goto 문](/visual-cpp/cpp/goto-statement-cpp)   
 [점프 문](../../../csharp/language-reference/keywords/jump-statements.md)