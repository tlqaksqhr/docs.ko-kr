---
title: "인터페이스 속성(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인터페이스[C#], 속성"
  - "속성[C#], 인터페이스의"
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 인터페이스 속성(C# 프로그래밍 가이드)
[interface](../../../csharp/language-reference/keywords/interface.md)에서 속성을 선언할 수 있습니다.  다음은 인터페이스 인덱서 접근자의 예제입니다.  
  
 [!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_1.cs)]  
  
 인터페이스 속성의 접근자에는 본문이 없습니다.  접근자를 사용하는 목적은 속성이 읽기\/쓰기, 읽기 전용 또는 쓰기 전용인지 여부를 나타내는 것입니다.  
  
## 예제  
 다음 예제의 `IEmployee` 인터페이스에는 읽기\/쓰기 속성인 `Name`과 읽기 전용 속성인 `Counter`가 있습니다.  `Employee` 클래스는 `IEmployee` 인터페이스를 구현하고 이 두 속성을 사용합니다.  프로그램에서는 새 직원 이름과 현재 번호를 읽어 들이고 직원 이름과 계산된 직원 번호를 표시합니다.  
  
 멤버가 선언된 인터페이스를 참조하는 속성의 정규화된 이름을 사용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 이를 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)이라고 합니다.  예를 들어, `Employee` 클래스가`ICitizen` 및 `IEmployee`라는 두 개의 인터페이스를 구현하며 두 인터페이스 모두에 `Name` 속성이 있는 경우 해당 인터페이스 멤버를 명시적으로 구현해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 위 선언에서는 `IEmployee` 인터페이스의 `Name` 속성을 구현합니다.  
  
 [!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_3.cs)]  
  
 그러나 이와 같이 선언하면 `ICitizen` 인터페이스의 `Name` 속성을 구현합니다.  
  
 [!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## 샘플 출력  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [속성 및 인덱서 비교](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)