---
title: "제네릭 및 배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 제네릭"
  - "제네릭[C#], 배열"
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 제네릭 및 배열(C# 프로그래밍 가이드)
C\# 2.0 이상에서 하한이 0인 1차원 배열은 자동으로 <xref:System.Collections.Generic.IList%601>을 구현합니다.  이러한 특성으로 인해 동일한 코드를 사용하여 배열 및 기타 컬렉션 형식에서 반복할 수 있는 제네릭 메서드를 만들 수 있습니다.  이 기술은 주로 컬렉션에서 데이터를 읽는 데 유용합니다.  <xref:System.Collections.Generic.IList%601> 인터페이스는 배열에서 요소를 추가하거나 제거하는 데 사용할 수 없습니다.  이 컨텍스트에서 배열에 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>과 같은 <xref:System.Collections.Generic.IList%601> 메서드를 호출하려고 하면 예외가 throw됩니다.  
  
 다음 코드 예제에서는 <xref:System.Collections.Generic.IList%601> 입력 매개 변수를 사용하는 단일 제네릭 메서드에서 목록과 배열\(이 경우 정수 배열\) 모두를 통해 반복하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-arrays_1.cs)]  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [제네릭](../Topic/Generics%20in%20the%20.NET%20Framework.md)