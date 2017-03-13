---
title: "접근자 액세스 가능성 제한(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "접근자[C#]"
  - "비대칭 접근자 액세스 가능성[C#]"
  - "인덱서[C#], 읽기 전용"
  - "속성[C#], 읽기 전용"
  - "읽기 전용 인덱서[C#]"
  - "읽기 전용 속성[C#]"
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# 접근자 액세스 가능성 제한(C# 프로그래밍 가이드)
속성이나 인덱서의 [get](../../../csharp/language-reference/keywords/get.md) 및 [set](../../../csharp/language-reference/keywords/set.md) 부분을 *접근자*라고 합니다.  기본적으로 이러한 접근자의 표시 여부\(액세스 수준\)는 이 접근자가 속한 속성이나 인덱서의 경우와 동일합니다.  자세한 내용은 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하십시오.  그러나 때로는 이러한 접근자 중 하나에 대한 액세스를 제한해야 할 수도 있습니다.  일반적인 예로는 `set` 접근자의 액세스 가능성을 제한한 채 `get` 접근자를 계속 공용으로 액세스할 수 있도록 유지하는 경우를 들 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]  
  
 이 예제에서 `Name`이라는 속성은 `get` 및 `set` 접근자를 정의합니다.  `get` 접근자는 속성 자체와 동일한 수준\(이 경우 `public`\)으로 액세스 가능성이 설정되는 반면, `set` 접근자는 이 접근자 자체에 [protected](../../../csharp/language-reference/keywords/protected.md) 액세스 한정자를 적용하여 액세스가 명시적으로 제한됩니다.  
  
## 접근자에 대한 액세스 한정자의 제한  
 속성이나 인덱서에 대한 접근자 한정자를 사용하려면 다음과 같은 조건을 준수해야 합니다.  
  
-   인터페이스나 명시적 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 멤버 구현에는 접근자 한정자를 사용할 수 없습니다.  
  
-   접근자 한정자는 속성이나 인덱서에 `set` 및 `get` 접근자가 모두 있는 경우에만 사용할 수 있습니다.  이 경우 한정자는 두 접근자 중 하나에 대해서만 허용됩니다.  
  
-   속성이나 인덱서에 [재정의](../../../csharp/language-reference/keywords/override.md) 한정자가 있는 경우 재정의된 접근자의 접근자가 있으면 접근자 한정자가 이와 일치해야 합니다.  
  
-   접근자에 대한 액세스 수준은 속성이나 인덱서 자체에 대한 액세스 수준보다 더 제한적이어야 합니다.  
  
## 재정의 접근자에 대한 액세스 한정자  
 속성이나 인덱서를 재정의하는 경우 재정의 코드에서는 재정의된 접근자에 액세스할 수 있어야 합니다.  또한 속성과 인덱서 모두의 액세스 수준 및 접근자의 액세스 수준은 상응하는 재정의된 속성과 인덱서 및 접근자의 액세스 수준과 일치해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]  
  
## 인터페이스 구현  
 접근자를 사용하여 인터페이스를 구현하는 경우 접근자에는 액세스 한정자가 없을 수 있습니다.  그러나 `get` 같은 접근자 하나를 사용하여 인터페이스를 구현하는 경우에는 다음 예제에서와 같이 다른 접근자에 액세스 한정자가 있을 수 있습니다.  
  
 [!code-cs[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]  
  
## 접근자 액세스 가능 도메인  
 접근자에 대해 액세스 한정자를 사용하는 경우 접근자의 [액세스 가능 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)은 이 한정자를 통해 결정됩니다.  
  
 접근자에 대해 액세스 한정자를 사용하지 않는 경우 접근자의 액세스 가능 도메인은 속성이나 인덱서의 액세스 수준에 따라 결정됩니다.  
  
## 예제  
 다음 예제에는 `BaseClass`, `DerivedClass` 및 `MainClass`라는 세 가지 클래스가 들어 있습니다.  `BaseClass`에 대한 속성 두 개가 있고 나머지 두 클래스에 모두 `Name` 및 `Id`가 있습니다.  이 예제에서는 [protected](../../../csharp/language-reference/keywords/protected.md) 또는 [private](../../../csharp/language-reference/keywords/private.md) 같은 제한된 액세스 한정자를 사용할 때 `DerivedClass`의 `Id` 속성을 `BaseClass`의 `Id` 속성으로 숨기는 방법을 보여 줍니다.  따라서 이 속성에 값을 할당하면 `BaseClass` 클래스의 속성이 대신 호출됩니다.  액세스 한정자를 [public](../../../csharp/language-reference/keywords/public.md)으로 바꾸면 속성에 액세스할 수 있습니다.  
  
 이 예제에서는 `DerivedClass`에서 `Name` 속성의 `set` 접근자에 대한 `private` 또는 `protected` 같은 제한적 액세스 한정자로 접근자에 대한 액세스를 막고 여기에 할당하는 경우 오류를 생성하는 방법도 보여 줍니다.  
  
 [!code-cs[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]  
  
## 설명  
 `new private string Id` 선언을 `new public string Id`로 바꾸는 경우 출력은 다음과 같습니다.  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)