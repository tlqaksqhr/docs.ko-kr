---
title: "인터페이스의 인덱서(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "접근자[C#], 인덱서"
  - "인덱서[C#], 인터페이스의"
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# 인터페이스의 인덱서(C# 프로그래밍 가이드)
[interface](../../../csharp/language-reference/keywords/interface.md)에서 인덱서를 선언할 수 있습니다.  인터페이스 인덱서의 접근자와 [클래스](../../../csharp/language-reference/keywords/class.md) 인덱서의 접근자는 다음과 같은 차이점이 있습니다.  
  
-   인터페이스 접근자는 한정자를 사용하지 않습니다.  
  
-   인터페이스 접근자에는 본문이 없습니다.  
  
 따라서 접근자의 목적은 인덱서가 읽기\/쓰기, 읽기 전용 또는 쓰기 전용인지 여부를 나타내는 것입니다.  
  
 다음은 인터페이스 인덱서 접근자의 예제입니다.  
  
 [!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 인덱서의 시그니처는 같은 인터페이스에 선언된 다른 모든 인덱서의 시그니처와 달라야 합니다.  
  
## 예제  
 다음 예제는 인터페이스 인덱서의 구현 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 위 예제에서 인터페이스 멤버의 정규화된 이름을 사용하여 명시적 인터페이스 멤버를 구현할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 그러나 정규화된 이름은 클래스에서 인덱서 시그니처가 같은 두 개 이상의 인터페이스를 구현하는 경우에 모호성을 피하고자 할 때 필요합니다.  예를 들어,  `Employee` 클래스가 `ICitizen` 및 `IEmployee`라는 두 개의 인터페이스를 구현하고 두 인터페이스에 동일한 인덱서 시그니처가 있는 경우 해당 인터페이스 멤버를 명시적으로 구현해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 위의 선언은 `IEmployee` 인터페이스에서 인덱서를 구현합니다.  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 그러나 위의 선언은 `ICitizen` 인터페이스에서 인덱서를 구현합니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)