---
title: "using 문(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using 문[C#]"
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# using 문(C# 참조)
<xref:System.IDisposable> 개체를 올바르게 사용할 수 있게 해 주는 편리한 구문을 제공합니다.  
  
## 예제  
 다음 예제에서는 using 문을 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## 설명  
 <xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스\(이 경우 파일 핸들 및 장치 컨텍스트\)에 액세스하는 관리되는 형식의 예제입니다.  관리되는 형식을 캡슐화하는 관리되지 않는 리소스 및 클래스 라이브러리 형식에는 여러 가지가 있습니다.  이러한 모든 형식은 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.  
  
 일반적으로 `IDisposable` 개체를 사용할 때는 `using` 문에서 해당 개체를 선언하고 인스턴스화해야 합니다.  `using` 문은 개체의 <xref:System.IDisposable.Dispose%2A> 메서드를 올바른 방법으로 호출하며, 앞에서 보여 준 것과 같이 사용할 경우 <xref:System.IDisposable.Dispose%2A>가 호출되면 즉시 해당 개체 자체가 범위를 벗어나도록 합니다.  `using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.  
  
 `using` 문은 개체의 메서드를 호출하는 동안 예외가 발생하는 경우에도 <xref:System.IDisposable.Dispose%2A>가 호출되도록 합니다.  try 블록 내에 개체를 배치한 다음 finally 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 이 방식은 컴파일러에서 `using` 문이 변환되는 방식입니다.  이전의 코드 예제는 컴파일 타임에 다음 코드로 확장됩니다. 중괄호를 추가하면 개체의 제한된 범위가 만들어집니다.  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 다음 예제에서와 같이 형식의 여러 인스턴스를 `using` 문에서 선언할 수 있습니다.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 리소스 개체를 인스턴스화하고 `using` 문에 변수를 전달할 수도 있지만 이 방법은 가장 좋은 방법은 아닙니다.  이 경우 관리되지 않는 리소스에 더 이상 액세스할 수 없더라도 제어가 `using` 블록을 벗어난 후 개체는 범위에 남아 있습니다.  즉, 개체는 더 이상 완전히 초기화되지 않습니다.  `using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 수 있습니다.  이러한 이유로 `using` 문에서 개체를 인스턴스화하고 해당 범위를 `using` 블록으로 제한하는 것이 일반적으로 더 좋습니다.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)   
 [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)