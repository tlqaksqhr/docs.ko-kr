---
title: "방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "컬렉션 클래스[C#], foreach 문"
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 코드 예제에서는 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)와 함께 사용할 수 있는 제네릭이 아닌 컬렉션 클래스의 작성 방법을 보여 줍니다.  이 예제에서는 문자열 토크나이저 클래스를 정의합니다.  
  
> [!NOTE]
>  이 예제에서 보여 주는 방법은 제네릭 컬렉션 클래스를 사용할 수 없는 경우에만 사용하는 것이 좋습니다.  <xref:System.Collections.Generic.IEnumerable%601>을 지원하는 형식이 안전한 제네릭 컬렉션 클래스를 구현하는 방법에 대한 예를 보려면 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 이 예제에서 다음 코드 세그먼트는 `Tokens` 클래스를 사용하여 "This is a sample sentence." 문장에 대해 ' ' 및 '\-'을 구분 기호로 사용하여 문장을 여러 토큰으로 분리합니다.  그런 다음 `foreach` 문을 사용하여 토큰을 표시합니다.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## 예제  
 내부적으로 `Tokens` 클래스에는 토큰을 저장하기 위한 배열이 사용됩니다.  배열은 <xref:System.Collections.IEnumerator> 및 <xref:System.Collections.IEnumerable>을 구현하기 때문에 이 코드 예제에서는 `Tokens` 클래스에서 메서드를 정의하는 대신 배열의 열거형 메서드\(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.Current%2A>\)가 사용될 수 있었습니다.  메서드 정의는 메서드의 정의 방식 및 각 메서드의 역할을 명확히 나타내기 위해 예제에 포함되었습니다.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 C\#에서는 컬렉션 클래스가 `foreach`와의 호환을 위해 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 구현할 필요가 없습니다.  필수 요소인 <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.Current%2A> 멤버가 클래스에 있기만 하면 `foreach`를 사용할 수 있습니다.  인터페이스를 생략하면 `Current`의 반환 형식을 <xref:System.Object>보다 구체적으로 정의할 수 있는 이점이 있습니다.  이러한 이점은 형식 안전성을 제공합니다.  
  
 예를 들어, 이전 예제에서 다음 줄을 변경합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 `Current`에서는 문자열을 반환하므로 다음 코드와 같이 호환되지 않는 형식이 `foreach` 문에 사용되면 컴파일러에서 이를 감지할 수 있습니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 생략하면 기타 공용 언어 런타임 언어의 `foreach` 문이나 그에 상응하는 문에서 컬렉션 클래스를 상호 운용할 수 없다는 단점이 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)