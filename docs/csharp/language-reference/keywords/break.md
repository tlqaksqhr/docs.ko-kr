---
title: "break(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "break"
  - "break_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "break 키워드[C#]"
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# break(C# 참조)
`break` 문은 자신이 속한 가장 가까운 바깥쪽 루프 또는 [switch](../../../csharp/language-reference/keywords/switch.md) 문을 종료합니다.  종료된 문 뒤에 문이 있는 경우 제어가 해당 문으로 전달됩니다.  
  
## 예제  
 이 예제에서는 조건문에 1부터 100까지 세는 카운터가 있지만 `break` 문 때문에 네 번 센 다음 루프가 종료됩니다.  
  
 [!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/csharp/break_1.cs)]  
  
## 예제  
 이 예제에서는 `break` 문을 사용하여 내부 중첩 루프를 중단하고 외부 루프에 컨트롤을 반환합니다.  
  
 [!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/csharp/break_2.cs)]  
  
## 예제  
 이 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `break`를 사용하는 것을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/csharp/break_3.cs)]  
  
 `4`를 입력하면 다음과 같이 출력됩니다.  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [점프 문](../../../csharp/language-reference/keywords/jump-statements.md)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)