---
title: "제네릭 소개(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "제네릭[C#], 제네릭 정보"
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# 제네릭 소개(C# 프로그래밍 가이드)
제네릭 클래스 및 메서드를 사용하면 제네릭이 아닌 형식에서는 불가능한 방식으로 재사용성, 형식 안전성 및 효율성을 동시에 달성할 수 있습니다.  제네릭은 컬렉션 및 컬렉션을 다루는 메서드에서 가장 자주 사용됩니다.  .NET Framework 클래스 라이브러리 버전 2.0에서는 <xref:System.Collections.Generic>이라는 새로운 네임스페이스를 제공하며, 이 네임스페이스에는 새로운 제네릭 기반 컬렉션 클래스가 여러 개 있습니다.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 2.0 이상을 대상으로 하는 모든 응용 프로그램에서는 이전의 <xref:System.Collections.ArrayList> 같은 제네릭이 아닌 형식 대신 새로운 제네릭 컬렉션 클래스를 사용하는 것이 좋습니다.  자세한 내용은 [.NET Framework 클래스 라이브러리의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)를 참조하십시오.  
  
 물론 사용자 고유의 형식이 안전하고 효율적인 일반화 솔루션 및 디자인 패턴을 제공하기 위해 사용자 지정 제네릭 형식 및 메서드를 만들 수도 있습니다.  다음 코드 예제에서는 이해를 돕기 위해 간단한 제네릭 연결 리스트 클래스를 보여 줍니다.  대부분의 경우에는 사용자가 이러한 클래스를 직접 만드는 대신 .NET Framework 클래스 라이브러리에서 제공하는 <xref:System.Collections.Generic.List%601> 클래스를 사용해야 합니다. 목록에 저장되는 항목의 형식을 지정하기 위해 일반적으로는 구체적인 형식이 사용될 여러 위치에 형식 매개 변수 `T`가 사용되고 있습니다.  구체적으로는 다음과 같이 사용되고 있습니다.  
  
-   `AddHead` 메서드의 메서드 매개 변수 형식  
  
-   공용 메서드인 `GetNext`의 반환 형식 및 중첩 `Node` 클래스의 `Data` 속성  
  
-   중첩 클래스에 있는 전용 멤버 데이터의 형식  
  
 중첩 `Node` 클래스에서도 T를 사용할 수 있습니다.  `GenericList<int>`와 같이 `GenericList<T>`를 구체적 형식을 사용하여 인스턴스화하면 모든 `T`가 `int`로 대체됩니다.  
  
 [!code-cs[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/csharp/introduction-to-generics_1.cs)]  
  
 다음 코드 예제에서는 클라이언트 코드에서 제네릭 `GenericList<T>` 클래스를 사용하여 정수 목록을 만드는 방법을 보여 줍니다.  형식 매개 변수를 변경하는 간단한 방법으로 다음 코드를 문자열이나 기타 사용자 지정 형식의 목록을 만들도록 쉽게 변경할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/csharp/introduction-to-generics_2.cs)]  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)