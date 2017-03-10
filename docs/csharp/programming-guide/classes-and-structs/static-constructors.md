---
title: "정적 생성자(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "생성자[C#], static"
  - "정적 생성자[C#]"
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# 정적 생성자(C# 프로그래밍 가이드)
정적 생성자는 [정적](../../../csharp/language-reference/keywords/static.md) 데이터를 초기화하거나 한 번만 수행하면 되는 특정 작업을 수행하는 데 사용됩니다.  이 생성자는 첫 번째 인스턴스가 만들어지기 전이나 정적 멤버가 참조되기 전에 자동으로 호출됩니다.  
  
 [!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-constructors_1.cs)]  
  
 정적 생성자에는 다음과 같은 속성이 있습니다.  
  
-   정적 생성자는 액세스 한정자를 사용하지 않고 매개 변수를 갖지 않습니다.  
  
-   정적 생성자는 첫 번째 인스턴스가 만들어지기 전이나 정적 멤버가 참조되기 전에 [클래스](../../../csharp/language-reference/keywords/class.md)를 초기화하기 위해 자동으로 호출됩니다.  
  
-   정적 생성자는 직접 호출할 수 없습니다.  
  
-   사용자는 프로그램에서 정적 생성자가 실행되는 시기를 제어할 수 없습니다.  
  
-   정적 생성자는 일반적으로 클래스에서 로그 파일을 사용할 때 이 파일에 항목을 쓰기 위해 사용됩니다.  
  
-   정적 생성자는 생성자에서 `LoadLibrary` 메서드를 호출할 수 있는 경우 비관리 코드에 대한 래퍼 클래스를 만들 때도 유용합니다.  
  
-   정적 생성자에서 예외를 throw하면 런타임은 다시 이 생성자를 호출하지 않으므로 해당 형식은 프로그램이 실행되는 응용 프로그램 도메인의 수명 동안 초기화되지 않은 상태로 남아 있게 됩니다.  
  
## 예제  
 이 예제에서 `Bus` 클래스에는 정적 생성자가 있습니다.  `Bus`의 첫 번째 인스턴스를 만들면\(`bus1`\) 정적 생성자가 호출되어 클래스를 초기화합니다.  샘플 출력에서는 `Bus`의 두 인스턴스를 만들어도 정적 생성자가 한 번만 실행되며, 인스턴스 생성자가 실행되기 전에 정적 생성자가 실행되는지 확인합니다.  
  
 [!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/static-constructors_2.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)