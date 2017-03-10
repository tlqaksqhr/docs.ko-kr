---
title: "클래스 및 구조체(C# 프로그래밍 가이드) | Microsoft Docs"
description: Describes the use of classes and structures (structs) in C#.
ms.date: "2016-01-17"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 클래스"
  - "C# 언어, 개체"
  - "C# 언어, 구조체"
  - "클래스[C#], 개요"
  - "개체[C#]"
  - "구조체[C#], 구조체 정보"
ms.assetid: cc39dbda-8754-423e-b5b1-16a1db0734c0
caps.latest.revision: 48
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 48
---
# 클래스 및 구조체(C# 프로그래밍 가이드)
클래스 및 구조체는 .NET Framework 공용 형식 시스템의 두 가지 기본 구문입니다.  클래스 및 구조체는 본질적으로 하나의 논리 단위에 속하는 일련의 데이터와 동작을 캡슐화하는 데이터 구조입니다.  데이터 및 동작은 클래스 또는 구조체의 *멤버*로 이 항목의 뒷부분에서 설명하는 메서드, 속성, 이벤트 등이 여기에 해당합니다.  
  
 클래스 또는 구조체 선언은 런타임에 인스턴스 또는 개체를 만드는 데 사용되는 청사진과 같습니다.  `Person`이라는 클래스 또는 구조체를 정의하는 경우 `Person`은 해당 형식의 이름이 됩니다.  `Person` 형식의 변수 `p`를 선언하고 초기화하는 경우 `p`를 `Person`의 개체 또는 인스턴스라고 합니다.  동일한 `Person` 형식의 인스턴스를 여러 개 만들 수 있으며 각 인스턴스의 속성 및 필드는 서로 다른 값을 가질 수 있습니다.  
  
 클래스는 참조 형식입니다.  클래스의 개체를 만드는 경우 개체가 할당된 변수에는 해당 메모리에 대한 참조만 포함됩니다.  개체 참조가 다른 변수에 할당되면 새 변수는 원래 개체를 참조합니다.  두 변수는 동일한 데이터를 참조하므로 한 변수를 통해 변경된 내용은 다른 변수에도 적용됩니다.  
  
 구조체는 값 형식입니다.  구조체를 만드는 경우 구조체가 할당된 변수에는 구조체의 실제 데이터가 포함됩니다.  구조체를 새 변수에 할당하면 해당 구조체가 복사되므로  새 변수와 원래 변수는 동일한 데이터의 별도 복사본을 보유하게 됩니다.  한 복사본이 변경되어도 다른 복사본은 영향을 받지 않습니다.  
  
 일반적으로 클래스는 클래스 개체를 생성한 후 수정하려고 하는 데이터나 더 복잡한 동작을 모델링하는 데 사용됩니다.  구조체는 구조체를 생성한 후 수정하지 않을 데이터를 주로 포함하는 작은 데이터 구조에 더 적합합니다.  
  
 자세한 내용은 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md), [개체](../../../csharp/programming-guide/classes-and-structs/objects.md) 및 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `ProgrammingGuide` 네임스페이스의 최상위에 세 가지 멤버가 있는 `MyCustomClass`를 정의합니다.  `MyCustomClass`의 인스턴스\(개체\)는 `Program` 클래스의 `Main` 메서드에서 생성되고 개체의 메서드와 속성은 점 표기를 사용하여 액세스됩니다.  
  
 [!code-cs[csProgGuideObjects#88](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/index_1.cs)]  
  
## 캡슐화  
 *캡슐화*는 개체 지향 프로그래밍의 첫 번째 기둥 또는 원칙으로도 불립니다.  캡슐화 원칙에 따르면 클래스 또는 구조체에서는 클래스 또는 구조체 외부 코드에서 각 멤버로의 액세스 가능성을 지정할 수 있습니다.  클래스 또는 어셈블리 외부에서 사용할 목적이 아닌 메서드 및 변수는 코딩 오류 또는 악의적인 이용의 가능성을 방지하기 위해 숨길 수 있습니다.  
  
 클래스에 대한 자세한 내용은 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md) 및 [개체](../../../csharp/programming-guide/classes-and-structs/objects.md)를 참조하십시오.  
  
### Members  
 모든 메서드, 필드, 상수, 속성 및 이벤트는 형식 내에서 선언되어야 하는데 이들을 형식의 *멤버*라고 합니다.  C\#에는 일부 다른 언어와 달리 전역 변수 또는 메서드가 없습니다.  프로그램의 진입점인 `Main` 메서드까지도 클래스 또는 구조체 내부에서 선언해야 합니다.  다음 목록에서는 클래스나 구조체에서 선언할 수 있는 다양한 종류의 멤버를 모두 보여 줍니다.  
  
-   [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [이벤트](../../../csharp/programming-guide/events/index.md)  
  
-   [인덱서](../../../csharp/programming-guide/indexers/index.md)  
  
-   [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)  
  
### 내게 필요한 옵션  
 일부 메서드 및 속성은 클래스 또는 구조체 외부 코드\(*클라이언트 코드*\)에서 호출하거나 액세스하기 위한 것입니다. .  다른 메서드 및 속성은 클래스 또는 구조체 자체에서 사용하기 위한 것입니다.  의도된 클라이언트 코드에서만 접근할 수 있도록 코드의 액세스 가능성을 제한해야 합니다.  액세스 한정자인 [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal` 및 [private](../../../csharp/language-reference/keywords/private.md)을 사용하여 클라이언트 코드에서 형식 및 해당 멤버로의 액세스 가능성을 지정할 수 있습니다.  기본 액세스 가능성은 `private`입니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)을\(를\) 참조하십시오.  
  
### 상속  
 구조체와 달리 클래스는 상속 개념을 지원합니다.  다른 클래스\(*기본 클래스*\)를 상속하는 클래스에는 생성자와 소멸자를 제외한 기본 클래스의 모든 public, protected 및 internal 멤버가 자동으로 포함됩니다.  자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md) 및 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)을 참조하십시오.  
  
 클래스를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수도 있습니다. 이것은 해당 클래스에서 하나 이상의 메서드가 구현되지 않았다는 의미입니다.  추상 클래스는 직접 인스턴스화할 수 없지만 다른 클래스의 기본 클래스로 사용하여 누락된 구현을 제공할 수 있습니다.  클래스를 [sealed](../../../csharp/language-reference/keywords/sealed.md)로 선언할 수도 있습니다. 그러면 다른 클래스에서 해당 클래스를 상속할 수 없습니다.  자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)을\(를\) 참조하십시오.  
  
### 인터페이스  
 클래스와 구조체는 여러 인터페이스를 상속할 수 있습니다.  인터페이스를 상속하는 것은 형식에서 해당 인터페이스에 정의된 모든 메서드를 구현한다는 의미입니다.  자세한 내용은 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)을\(를\) 참조하십시오.  
  
### 제네릭 형식  
 클래스와 구조체를 하나 이상의 형식 매개 변수와 함께 정의할 수 있습니다.  클라이언트 코드에서는 형식의 인스턴스를 생성할 때 형식을 지정합니다.  예를 들어 <xref:System.Collections.Generic> 네임스페이스의 <xref:System.Collections.Generic.List%601> 클래스에는 형식 매개 변수 하나가 정의되어 있습니다.  클라이언트 코드에서는 `List<string>` 또는 `List<int>` 인스턴스를 생성하여 목록에 유지되는 형식을 지정합니다.  자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을\(를\) 참조하십시오.  
  
### 정적 형식  
 클래스\(구조체는 안 됨\)를 [static](../../../csharp/language-reference/keywords/static.md)으로 선언할 수 있습니다.   정적 클래스는 정적 멤버만 포함할 수 있으며 new 키워드를 사용하여 인스턴스화할 수 없습니다.  따라서 프로그램이 로드될 때 클래스 복사본 하나가 로드되고 클래스 이름을 통해 해당 멤버에 액세스합니다.  클래스 및 구조체는 모두 정적 멤버를 포함할 수 있습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)을\(를\) 참조하십시오.  
  
### 중첩 형식  
 클래스 또는 구조체는 다른 클래스 또는 구조체 내에 중첩될 수 있습니다.  자세한 내용은 [중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md)을 참조하십시오.  
  
### 부분 형식\(Partial type\)  
 한 코드 파일에서 클래스, 구조체 또는 메서드의 일부를 정의하고 다른 코드 파일에서 나머지 부분을 정의할 수 있습니다.  자세한 내용은 [Partial 클래스 및 메서드](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)를 참조하십시오.  
  
### 개체 이니셜라이저  
 생성자를 명시적으로 호출하지 않고도 클래스 또는 구조체 개체와 개체 컬렉션을 인스턴스화하고 초기화할 수 있습니다.  자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하십시오.  
  
### 익명 형식  
 목록을 데이터 구조로 채우지만 해당 목록을 유지하거나 다른 메서드로 전달할 필요가 없는 경우와 같이, 명명된 클래스를 만드는 것이 불편하거나 만들 필요가 없는 경우에는 익명 형식을 사용합니다.  자세한 내용은 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하십시오.  
  
### 확장 메서드  
 원래 형식에서 마치 해당 형식에 속한 것처럼 호출할 수 있는 메서드가 있는 별도의 형식을 만들면 파생 클래스를 만들지 않고도 클래스를 "확장"할 수 있습니다.  자세한 내용은 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하십시오.  
  
### 암시적으로 형식화한 지역 변수  
 클래스 또는 구조체 메서드 내에서 암시적 형식 지정을 사용하여 컴파일러가 컴파일 타임에 올바른 형식을 결정하게 만들 수 있습니다.  자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)