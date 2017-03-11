---
title: "interface(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "interface_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "interface 키워드[C#]"
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# interface(C# 참조)
인터페이스에는 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md), [이벤트](../../../csharp/programming-guide/events/index.md) 또는 [인덱서](../../../csharp/programming-guide/indexers/index.md)의 시그니처만 포함됩니다.  인터페이스를 구현하는 클래스나 구조체는 인터페이스 정의에 지정된 인터페이스 멤버를 구현해야 합니다.  다음 예제에서는 `ImplementationClass` 클래스가 매개 변수를 사용하지 않고 `void`를 반환하는 `SampleMethod` 메서드를 구현해야 합니다.  
  
 자세한 내용과 예제를 보려면 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)을 참조하십시오.  
  
## 예제  
 [!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/csharp/interface_1.cs)]  
  
 인터페이스는 네임스페이스 또는 클래스의 멤버가 될 수 있으며 다음 멤버의 시그니처를 포함할 수 있습니다.  
  
-   [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [속성](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [인덱서](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [이벤트](../../../csharp/language-reference/keywords/event.md)  
  
 인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.  
  
 기본 형식 목록에 기본 클래스와 인터페이스가 있는 경우 기본 클래스가 목록의 처음에 있어야 합니다.  
  
 인터페이스를 구현하는 클래스는 해당 인터페이스의 멤버를 명시적으로 구현할 수 있습니다.  명시적으로 구현된 멤버는 클래스 인스턴스를 통해 액세스할 수 없고 인터페이스의 인스턴스를 통해서만 액세스할 수 있습니다.  
  
 명시적 인터페이스 구현에 대한 자세한 내용과 코드 예제는 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 인터페이스 구현 방법을 보여 줍니다.  이 예제에서 인터페이스에는 속성 선언이 포함되고 클래스에는 구현이 포함됩니다.  `IPoint`를 구현하는 클래스 인스턴스에 정수 속성 `x` 및 `y`가 있습니다.  
  
 [!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/csharp/interface_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [인덱서 사용](../../../csharp/programming-guide/indexers/using-indexers.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)