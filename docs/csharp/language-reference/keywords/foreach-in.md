---
title: "foreach, in(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "foreach"
  - "foreach_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "foreach 키워드[C#]"
  - "foreach 문[C#]"
  - "in 키워드[C#]"
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# foreach, in(C# 참조)
`foreach` 문은 배열이나 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 구현하는 개체 컬렉션에 있는 각 요소에 대해 포함 문 그룹을 반복하여 실행합니다.  `foreach` 문은 컬렉션을 반복 실행하여 원하는 정보를 얻는 용도로 사용할 수 있지만 예측할 수 없는 부작용을 방지하면서 소스 컬렉션의 항목을 추가하거나 제거하는 용도로는 사용할 수 없습니다.  소스 컬렉션에서 항목을 추가하거나 제거해야 한다면 [for](../../../csharp/language-reference/keywords/for.md) 루프를 사용하십시오.  
  
 배열 또는 컬렉션의 각 요소에 대해 포함 문이 계속 실행됩니다.  컬렉션의 모든 요소에 대해 해당 문이 계속 실행된 후에 제어가 `foreach` 블록 다음 문으로 전달됩니다.  
  
 `foreach` 블록의 모든 위치에서 [break](../../../csharp/language-reference/keywords/break.md) 키워드를 사용하여 루프를 벗어나거나 [continue](../../../csharp/language-reference/keywords/continue.md) 키워드를 사용하여 루프의 다음 반복을 단계별로 실행할 수 있습니다.  
  
 `foreach` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 사용하여 종료할 수도 있습니다.  
  
 `foreach` 키워드에 대한 자세한 내용과 코드 예제는 다음 항목을 참조하십시오.  
  
 [배열에 foreach 사용](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [방법: foreach를 사용하여 컬렉션 클래스 액세스](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## 예제  
 다음 코드에서는 세 가지 예제를 보여줍니다.  
  
-   정수 배열의 내용을 표시하는 일반적인 `foreach` 루프입니다.  
  
-   동일한 기능을 수행하는 [for](../../../csharp/language-reference/keywords/for.md) 루프  
  
-   배열에 있는 요소의 수를 유지하는 `foreach` 루프  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/csharp/foreach-in_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)   
 [for](../../../csharp/language-reference/keywords/for.md)