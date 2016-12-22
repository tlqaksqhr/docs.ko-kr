---
title: "제네릭 클래스(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "C# 언어, 제네릭 클래스"
  - "제네릭[C#], 클래스"
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 제네릭 클래스(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

제네릭 클래스는 특정 데이터 형식에 고유하지 않은 작업을 캡슐화합니다.  제네릭 클래스는 연결된 목록, 해시 테이블, 스택, 큐, 트리 등의 컬렉션에 가장 일반적으로 사용됩니다.  컬렉션에서 항목을 추가하고 제거하는 등의 작업은 저장되는 데이터의 형식에 관계없이 기본적으로 동일한 방식으로 수행됩니다.  
  
 컬렉션 클래스가 필요한 대부분의 시나리오에서는 .NET Framework 클래스 라이브러리에서 제공하는 컬렉션 클래스를 사용하는 것이 좋습니다.  이러한 클래스 사용에 대한 자세한 내용은 [.NET Framework 클래스 라이브러리의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)을 참조하십시오.  
  
 일반적으로 기존의 구체적인 클래스로 시작하여 일반성과 편의성의 균형이 맞을 때까지 형식을 하나씩 형식 매개 변수로 바꾸는 방법으로 제네릭 클래스를 만듭니다.  사용자 고유의 제네릭 클래스를 만들 때는 다음과 같은 사항을 고려해야 합니다.  
  
-   형식 매개 변수로 일반화할 형식.  
  
     일반적으로는 매개 변수화할 수 있는 형식이 많을수록 코드의 융통성과 재사용 가능성이 향상됩니다.  그러나 코드를 지나치게 일반화하면 다른 개발자가 읽거나 이해하기가 어려워집니다.  
  
-   형식 매개 변수에 적용할 제약 조건\([형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md) 참조\).  
  
     필요한 형식을 처리할 수 있는 범위 내에서 최대한 많은 제약 조건을 적용하는 것이 좋습니다.  예를 들어 사용자 제네릭 클래스를 참조 형식으로만 사용하려는 경우에는 클래스 제약 조건을 적용합니다.  이렇게 하면 클래스를 값 형식으로 잘못 사용하는 것을 막을 수 있고, `T`에 `as` 연산자를 사용하여 null 값 여부를 확인할 수 있습니다.  
  
-   제네릭 동작을 기본 클래스와 서브클래스로 분할할지 여부.  
  
     제네릭 클래스는 기본 클래스가 될 수 있으므로 제네릭이 아닌 클래스에 적용되는 디자인 고려 사항이 동일하게 적용됩니다.  자세한 내용은 이 항목의 뒷부분에서 설명하는 제네릭 기본 클래스에서 상속하는 데 대한 규칙을 참조하십시오.  
  
-   제네릭 인터페이스를 하나 이상 구현할지 여부  
  
     예를 들어 제네릭 기반 컬렉션의 항목을 만드는 데 사용될 클래스를 디자인하는 경우 <xref:System.IComparable%601>\(`T`는 사용자 클래스 형식\)과 같은 인터페이스를 구현해야 할 수 있습니다.  
  
 간단한 제네릭 클래스의 예제를 보려면 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하십시오.  
  
 형식 매개 변수와 제약 조건에 대한 규칙은 제네릭 클래스 동작에서 특히 상속과 멤버 액세스 가능성에 대해 몇 가지 영향을 줍니다.  계속하려면 몇 가지 용어를 이해하고 있어야 합니다.  `Node<T>,` 제네릭 클래스의 경우 클라이언트 코드에서는 형식 인수를 지정하여 폐쇄형 생성 형식\(`Node<int>`\)을 만드는 방법으로 클래스를 참조하거나,  제네릭 기본 클래스를 지정하는 경우와 같이 형식 매개 변수를 지정하지 않고 개방형 생성 형식\(`Node<T>`\)을 만드는 방법으로 클래스를 참조할 수 있습니다.  제네릭 클래스는 구체적인 클래스, 폐쇄형 구성 클래스 또는 개방형 구성 기본 클래스에서 상속할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]  
  
 제네릭이 아닌 구체적인 클래스는 폐쇄형 생성 기본 클래스에서는 상속할 수 있지만 개방형 생성 클래스 또는 형식 매개 변수에서는 상속할 수 없습니다. 이는 런타임에 클라이언트 코드에서 기본 클래스를 인스턴스화할 때 필요한 형식 인수를 제공할 수 없기 때문입니다.  
  
 [!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]  
  
 개방형 생성 형식에서 상속하는 제네릭 클래스에서는 다음 코드와 같이 상속하는 클래스에서 공유하지 않는 모든 기본 클래스 형식 매개 변수에 대해 형식 인수를 제공해야 합니다.  
  
 [!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]  
  
 개방형 생성 형식에서 상속하는 제네릭 클래스에서는 기본 형식에 대한 제약 조건을 포함하거나 암시하는 제약 조건을 지정해야 합니다.  
  
 [!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]  
  
 제네릭 형식은 다음과 같이 여러 형식 매개 변수 및 제약 조건을 사용할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]  
  
 개방형 생성 형식 및 폐쇄형 생성 형식은 메서드 매개 변수로 사용될 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]  
  
 제네릭 클래스에서 인터페이스를 구현하면 이 클래스의 모든 인스턴스를 해당 인터페이스에 캐스팅할 수 있습니다.  
  
 제네릭 클래스는 비가변적입니다.  즉, 입력 매개 변수에서 `List<BaseClass>`를 지정하면 `List<DerivedClass>`를 제공하려고 할 때 컴파일 타임 오류가 발생합니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390)   
 [An Inheritance Puzzle, Part One](http://go.microsoft.com/fwlink/?LinkId=112380)