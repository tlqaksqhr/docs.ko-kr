---
title: "명시적 인터페이스 구현(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "명시적 인터페이스[C#]"
  - "인터페이스[C#], 명시적"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 명시적 인터페이스 구현(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[클래스](../../../csharp/language-reference/keywords/class.md)에서 시그니처가 동일한 멤버가 들어 있는 두 인터페이스를 구현하는 경우 클래스에서 이 멤버를 구현하면 두 인터페이스 모두에서 이 멤버를 해당 구현으로 사용하게 됩니다.  다음 예제에서 모든 호출을 `Paint` 같은 메서드를 호출 합니다.  
  
 [!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 그러나 두 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 멤버가 동일한 기능을 수행하지 않는 경우에는 인터페이스 하나 또는 모두의 구현이 잘못될 수 있습니다.  인터페이스를 통해서만 호출되고 특정 인터페이스에만 관련되는 클래스 멤버를 만드는 방식으로 인터페이스 멤버를 명시적으로 구현할 수 있습니다.  이렇게 하려면 인터페이스 이름과 마침표를 사용하여 클래스 멤버의 이름을 지정해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 클래스 멤버 `IControl.Paint`는 `IControl` 인터페이스를 통해서만 사용할 수 있고 `ISurface.Paint`는 `ISurface`를 통해서만 사용할 수 있습니다.  두 메서드 구현은 서로 별개이며 어느 쪽도 클래스에 대해 직접 사용할 수 없습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 두 인터페이스에서 각각 이름이 동일하지만 서로 다른 속성 및 메서드 등의 멤버를 선언할 때 발생하는 문제의 해결에도 명시적 구현이 사용됩니다.  
  
 [!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 두 인터페이스를 모두 구현하려는 경우에는 클래스에서 P 속성이나 P 메서드 또는 둘 모두에 대해 명시적 구현을 사용해야 컴파일러 오류를 방지할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [인터페이스](../../../visual-basic/reference/command-line-compiler/index.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)