---
title: "상속(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "추상 클래스(C#)"
  - "추상 메서드[C#]"
  - "C# 언어, 상속"
  - "파생 클래스[C#]"
  - "상속[C#]"
  - "가상 메서드[C#]"
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
caps.latest.revision: 38
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# 상속(C# 프로그래밍 가이드)
상속은 캡슐화 및 다형성과 함께 개체 지향 프로그래밍의 세 가지 주요 특징 또는 *기둥* 중 하나입니다.  상속을 사용하면 다른 클래스에 정의된 동작을 다시 사용, 확장 및 수정하는 새 클래스를 만들 수 있습니다.  멤버가 상속되는 클래스를 *기본 클래스*라고 하고 해당 멤버를 상속하는 클래스를 *파생 클래스*라고 합니다.  파생 클래스는 직접 기본 클래스를 하나만 가질 수 있습니다.  그러나, 상속은 전이적입니다.  ClassC가 ClassB에서 파생되고 ClassB가 ClassA에서 파생되는 경우 ClassC는 ClassB 및 ClassA에서 선언된 멤버를 상속합니다.  
  
> [!NOTE]
>  구조체는 상속을 지원하지 않지만 인터페이스는 구현할 수 있습니다.  자세한 내용은 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)를 참조하십시오.  
  
 개념적으로 파생 클래스는 기본 클래스를 구체화한 것입니다.  예를 들어 기본 클래스 `Animal`이 있으면 `Mammal`이라는 하나의 파생 클래스와 `Reptile`이라는 또 다른 파생 클래스를 만들 수 있습니다.  `Mammal`은 `Animal`이고 `Reptile`도 `Animal`이지만 각 파생 클래스는 기본 클래스의 서로 다른 특징을 나타냅니다.  
  
 다른 클래스를 상속하여 파생 클래스를 정의하는 경우 이 클래스는 암시적으로 생성자와 소멸자를 제외한 기본 클래스의 모든 멤버를 얻습니다.  따라서 파생 클래스는 기본 클래스의 코드를 다시 구현하지 않고 재사용할 수 있습니다.  파생 클래스에서는 멤버를 추가하여  기본 클래스의 기능을 확장할 수 있습니다.  
  
 다음 그림에서는 특정 비즈니스 프로세스에서 작업 항목을 나타내는 `WorkItem` 클래스를 보여 줍니다.  모든 클래스처럼 <xref:System.Object?displayProperty=fullName>에서 파생되고 모든 해당 메서드를 상속합니다.  `WorkItem`은 자신의 다섯 멤버를 추가합니다.  생성자는 상속되지 않으므로 생성자를 포함합니다.  클래스 `ChangeRequest`는 `WorkItem`에서 상속하며, 특정 종류의 작업 항목을 나타냅니다.  `ChangeRequest`는 `WorkItem` 및 <xref:System.Object>에서 상속되는 멤버에 둘 이상의 멤버를 추가합니다.  자체 생성자를 추가해야 하며 `originalItemID`도 추가합니다.  속성 `originalItemID`를 통해 `ChangeRequest` 인스턴스를 변경 요청이 적용되는 원본 `WorkItem`과 연결할 수 있습니다.  
  
 ![클래스 상속](../../../csharp/programming-guide/classes-and-structs/media/class-inheritance.png "Class\_Inheritance")  
클래스 상속  
  
 다음 예제에서는 이전 그림에서 설명한 클래스 관계가 C\#에서 어떻게 표현되는지 보여 줍니다.  이 예제에서는 `WorkItem`이 가상 메서드 <xref:System.Object.ToString%2A?displayProperty=fullName>을 재정의하는 방법 및 `ChangeRequest` 클래스가 해당 메서드의 `WorkItem` 구현을 상속하는 방법도 보여 줍니다.  
  
 [!code-cs[csProgGuideInheritance#49](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/inheritance_1.cs)]  
  
## 추상 및 가상 메서드  
 기본 클래스가 메서드를 [virtual](../../../csharp/language-reference/keywords/virtual.md)로 선언하면 파생 클래스는 자체 구현으로 이 메서드를 [override](../../../csharp/language-reference/keywords/override.md)할 수 있습니다.  기본 클래스가 멤버를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언하는 경우 해당 클래스를 직접 상속하는 비추상 클래스는 이 메서드를 재정의해야 합니다.  파생 클래스가 추상 클래스이면 추상 멤버를 구현하지 않고 상속합니다.  추상 및 가상 멤버는 개체 지향 프로그래밍의 두 번째 주요 특징인 다형성의 기반이 됩니다.  자세한 내용은 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)를 참조하십시오.  
  
## 추상 기본 클래스  
 [new](../../../csharp/language-reference/keywords/new.md) 키워드를 사용하여 직접 인스턴스화하지 않으려는 클래스는 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있습니다.  이렇게 하면 이 클래스는 새 클래스가 자신에게서 파생되는 경우에만 사용될 수 있습니다.  추상 클래스는 추상으로 선언된 하나 이상의 메서드 시그니처를 포함할 수 있습니다.  이러한 시그니처는 매개 변수와 반환 값을 지정하지만 구현\(메서드 본문\)은 포함하고 있지 않습니다.  추상 클래스가 추상 멤버를 포함할 필요는 없지만 클래스에 추상 멤버가 있는 경우 해당 클래스는 반드시 추상으로 선언되어야 합니다.  추상 클래스가 아닌 파생 클래스는 추상 기본 클래스의 모든 추상 멤버에 대한 구현을 제공해야 합니다.  자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하십시오.  
  
## 인터페이스  
 *인터페이스*는 추상 멤버로만 구성된 추상 기본 클래스와 어느 정도 유사한 참조 형식입니다.  클래스가 인터페이스를 구현하는 경우 해당 인터페이스의 모든 멤버에 대한 구현을 제공해야 합니다.  클래스는 하나의 직접 기본 클래스에서 파생되지만 여러 개의 인터페이스를 구현할 수 있습니다.  
  
 인터페이스를 사용하여 "is a" 관계가 없을 수도 있는 클래스를 위한 특정 기능을 정의할 수 있습니다.  예를 들어 <xref:System.IEquatable%601?displayProperty=fullName> 인터페이스는 클라이언트 코드에서 해당 형식의 같음에 대한 정의에 따라 두 개체가 같은지 여부를 결정할 수 있어야 하는 클래스 또는 구조체에서 구현할 수 있습니다.  <xref:System.IEquatable%601>은 기본 클래스 및 파생 클래스 사이에 존재하는 같은 종류의 "is a" 관계를 의미하는 것이 아닙니다\(예: `Mammal`은 `Animal`\).  자세한 내용은 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)를 참조하십시오.  
  
## 기본 클래스 멤버에 대한 파생 클래스 액세스  
 파생 클래스는 기본 클래스의 public, protected, internal 및 protected internal 멤버에 액세스할 수 있습니다.  파생 클래스는 기본 클래스의 private 멤버를 상속함에도 불구하고 해당 멤버에 액세스할 수 없습니다.  하지만 모든 private 멤버는 파생 클래스에 존재하면서 기본 클래스에서 수행하는 작업과 동일한 작업을 수행할 수 있습니다.  예를 들어 protected 기본 클래스 메서드가 private 필드에 액세스한다고 가정합니다.  상속된 기본 클래스 메서드가 올바르게 작동하려면 파생 클래스에 해당 필드가 있어야 합니다.  
  
## 추가 파생 방지  
 클래스는 자신 또는 멤버를 [sealed](../../../csharp/language-reference/keywords/sealed.md)로 선언하여 다른 클래스가 상속하는 것을 막을 수 있습니다.  자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하십시오.  
  
## 파생 클래스에서 기본 클래스 멤버 숨기기  
 파생 클래스는 기본 클래스와 동일한 이름과 시그니처를 가진 멤버를 선언하여 기본 클래스 멤버를 숨길 수 있습니다.  [new](../../../csharp/language-reference/keywords/new.md) 한정자를 사용하면 멤버가 기본 클래스의 재정의가 아니라는 것을 명시적으로 나타낼 수 있습니다.  [new](../../../csharp/language-reference/keywords/new.md)를 반드시 사용할 필요는 없지만 [new](../../../csharp/language-reference/keywords/new.md)를 사용하지 않으면 컴파일러에서 경고를 생성합니다.  자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)