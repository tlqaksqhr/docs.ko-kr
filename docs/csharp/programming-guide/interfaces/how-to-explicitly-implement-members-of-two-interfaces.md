---
title: "방법: 두 인터페이스의 멤버를 명시적으로 구현(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "상속[C#], 명시적으로 인터페이스 멤버 구현"
  - "인터페이스[C#], 명시적으로 상속 구현"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# 방법: 두 인터페이스의 멤버를 명시적으로 구현(C# 프로그래밍 가이드)
명시적으로 [인터페이스](../../../csharp/language-reference/keywords/interface.md)를 구현하면 멤버 이름이 동일한 두 개의 인터페이스를 구현하여 각 인터페이스 멤버에 별도의 구현을 제공할 수 있습니다.  다음 예제에서는 상자의 크기를 미터와 인치 단위로 표시합니다.  Box [클래스](../../../csharp/language-reference/keywords/class.md)는 서로 다른 단위를 나타내는 두 인터페이스인 IEnglishDimensions 및 IMetricDimensions를 구현합니다.  두 인터페이스에는 모두 동일한 멤버 이름 Length와 Width가 있습니다.  
  
## 예제  
 [!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## 강력한 프로그래밍  
 인치를 기본 단위로 하려면 메서드 Length와 Width를 정상적으로 구현하고 IMetricDimensions 인터페이스에서 Length와 Width 메서드를 명시적으로 구현해야 합니다.  
  
 [!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 이런 경우 인치 단위는 클래스 인스턴스에서 액세스하고 미터 단위는 인터페이스 인스턴스에서 액세스할 수 있습니다.  
  
 [!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [방법: 인터페이스 멤버를 명시적으로 구현](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)