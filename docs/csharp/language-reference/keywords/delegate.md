---
title: "delegate(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "delegate_CSharpKeyword"
  - "delegate"
  - "CS0123"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegate 키워드[C#]"
  - "함수 포인터[C#]"
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# delegate(C# 참조)
대리자 형식의 선언은 메서드 시그니처와 비슷하므로,  반환 값을 가지며 모든 유형의 매개 변수를 원하는 수만큼 사용할 수 있습니다.  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 `delegate`는 명명된 메서드나 익명 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식입니다.  대리자는 C\+\+의 함수 포인터와 비슷하지만 형식 안전성과 보안성을 제공한다는 점이 다릅니다.  대리자 응용 프로그램에 대한 자세한 내용은 [대리자](../../../csharp/programming-guide/delegates/index.md) 및 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하십시오.  
  
## 설명  
 대리자는 [이벤트](../../../csharp/programming-guide/events/index.md)의 기반을 형성합니다.  
  
 대리자는 명명된 메서드나 무명 메서드와 연결하여 인스턴스화할 수 있습니다.  자세한 내용은 [명명된 메서드](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 및 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)를 참조하십시오.  
  
 대리자는 호환되는 반환 형식과 입력 매개 변수가 있는 메서드나 람다 식으로 인스턴스화해야 합니다.  메서드 시그니처에 허용되는 변동 범위에 대한 자세한 내용은 [대리자의 가변성](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  무명 메서드와 함께 사용하는 경우 대리자 및 대리자와 연결된 코드가 함께 선언됩니다.  이 단원에서는 대리자를 인스턴스화하는 두 가지 방법을 모두 설명합니다.  
  
## 예제  
 [!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [명명된 메서드와 익명 메서드의 대리자 비교](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)   
 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)