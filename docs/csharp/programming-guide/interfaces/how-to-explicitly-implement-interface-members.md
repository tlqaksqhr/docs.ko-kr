---
title: "방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인터페이스[C#], 명시적으로 구현"
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# 방법: 인터페이스 멤버를 명시적으로 구현(C# 프로그래밍 가이드)
다음 예제에서는 `IDimensions` [인터페이스](../../../csharp/language-reference/keywords/interface.md)를 선언한 다음 인터페이스 멤버인 `getLength`와 `getWidth`를 명시적으로 구현하는 `Box` 클래스를 선언합니다.  멤버는 인터페이스 인스턴스 `dimensions`을 통해 액세스할 수 있습니다.  
  
## 예제  
 [!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## 강력한 프로그래밍  
  
-   `Main` 메서드에서 다음 줄은 컴파일 오류를 발생시키므로 주석 처리합니다.  명시적으로 구현된 인터페이스 멤버는 [클래스](../../../csharp/language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.  
  
     [!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   또한, 메서드는 인터페이스의 인스턴스에서 호출되므로 `Main` 메서드에서 다음 줄은 상자의 크기를 성공적으로 출력합니다.  
  
     [!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)   
 [방법: 두 인터페이스의 멤버를 명시적으로 구현](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)