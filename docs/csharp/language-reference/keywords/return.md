---
title: "return(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "return_CSharpKeyword"
  - "return"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "return 키워드[C#]"
  - "return 문[C#]"
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# return(C# 참조)
`return` 문은 자신이 속한 메서드의 실행을 종료하고 호출한 메서드로 제어를 반환합니다.  선택적 값을 반환할 수도 있습니다.  `void` 형식의 메서드인 경우 `return` 문을 생략할 수 있습니다.  
  
 return 문이 `try` 블록 내부에 있을 경우 `finally` 블록이 존재한다면 호출 메서드로 컨트롤을 반환하기 전에 해당 블록이 실행됩니다.  
  
## 예제  
 아래 예제에서 `A()` 메서드는 [double](../../../csharp/language-reference/keywords/double.md) 값으로 `Area` 변수를 반환합니다.  
  
 [!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [return 문](/visual-cpp/cpp/return-statement-cpp)   
 [점프 문](../../../csharp/language-reference/keywords/jump-statements.md)