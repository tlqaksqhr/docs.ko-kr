---
title: "배열에 foreach 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], foreach"
  - "foreach 문[C#], 배열과 함께 사용"
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# 배열에 foreach 사용(C# 프로그래밍 가이드)
C\#에서는 또한 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 제공하여  배열 또는 열거형 컬렉션의 요소를 간단하게 반복할 수 있습니다.  `foreach` 문은 배열 또는 컬렉션 형식의 열거자에서 반환한 순서대로 요소를 처리합니다\(일반적으로 0번째부터 마지막까지\).  예를 들어, 다음 코드에서는 `numbers`라는 배열을 만들어 `foreach` 문으로 배열의 요소를 반복하여 사용합니다.  
  
 [!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/csharp/using-foreach-with-arrays_1.cs)]  
  
 다차원 배열의 경우에도 같은 방법으로 요소를 반복 실행할 수 있습니다. 예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/csharp/using-foreach-with-arrays_2.cs)]  
  
 그러나 다차원 배열에서 중첩 [for](../../../csharp/language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 보다 강력하게 제어할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Array>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [가변 배열](../../../csharp/programming-guide/arrays/jagged-arrays.md)