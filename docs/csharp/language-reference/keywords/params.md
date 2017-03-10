---
title: "params(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "params_CSharpKeyword"
  - "params"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "매개 변수[C#], params"
  - "params 키워드[C#]"
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# params(C# 참조)
`params` 키워드를 사용하면 여러 개의 인수를 사용하는 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)를 지정할 수 있습니다.  
  
 매개 변수 선언에 지정된 형식의 쉼표로 구분된 인수 목록 또는 지정된 형식의 인수 배열을 보낼 수 있습니다.  인수 없이 보낼 수도 있습니다.  인수를 보내지 않으면 `params` 목록의 길이는 0입니다.  
  
 메서드 선언에서 `params` 키워드 다음에는 매개 변수를 추가할 수 없으며 `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/csharp/params_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)