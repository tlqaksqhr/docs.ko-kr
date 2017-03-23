---
title: "속성(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.properties"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 속성"
  - "속성[C#]"
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# 속성(C# 프로그래밍 가이드)
속성은 전용 필드의 값을 읽거나 쓰거나 계산하는 유연한 메커니즘을 제공하는 멤버입니다.  공용 데이터 멤버인 것처럼 속성을 사용할 수 있지만, 실제로 *접근자*라는 특수 메서드입니다.  이렇게 하면 데이터에 쉽게 액세스할 수 있으며 메서드의 안전성과 유연성 수준을 올리는 데에도 도움이 됩니다.  
  
 이 예제에서 `TimePeriod` 클래스는 기간을 저장합니다.  내부적으로 이 클래스는 초 단위로 시간을 저장하지만, `Hours`라는 속성을 사용하여 클라이언트에서 시간 단위로 시간을 지정할 수 있습니다.  `Hours` 속성에 대한 접근자는 시간과 초 사이의 변환을 수행합니다.  
  
## 예제  
 [!code-cs[csProgGuideProperties#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/properties_1.cs)]  
  
## 식 본문 정의  
 일반적으로 식의 결과와 함께 바로 반환되는 속성이 있습니다.  `=>`를 사용하여 이러한 속성을 정의하기 위한 구문 바로 가기는 다음과 같습니다.  
  
```c#  
public string Name => First + " " + Last;   
```  
  
 속성은 읽기 전용이어야 하며, `get` 접근자 키워드를 사용하지 않습니다.  
  
## 속성 개요  
  
-   속성을 사용하면 클래스가 구현 또는 검증 코드를 숨기는 동시에 값을 가져오고 설정하는 방법을 공개적으로 노출할 수 있습니다.  
  
-   [get](../../../csharp/language-reference/keywords/get.md) 속성 접근자는 속성 값을 반환하는 데 사용되고 [set](../../../csharp/language-reference/keywords/set.md) 접근자는 새 값을 할당하는 데 사용됩니다.  이러한 접근자는 각기 다른 액세스 수준을 가질 수 있습니다.  자세한 내용은 [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.  
  
-   [value](../../../csharp/language-reference/keywords/value.md) 키워드는 `set` 접근자가 할당하는 값을 정의하는 데 사용됩니다.  
  
-   `set` 접근자를 구현하지 않는 속성은 읽기 전용입니다.  
  
-   사용자 지정 접근자 코드가 필요 없는 단순 속성의 경우 자동 구현 속성을 사용하는 것이 좋습니다.  자세한 내용은 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.  
  
## 관련 단원  
  
-   [속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [인터페이스 속성](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [속성 및 인덱서 비교](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성 사용](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)