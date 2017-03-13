---
title: "속성 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "get 접근자[C#]"
  - "속성[C#], 속성 정보"
  - "set 접근자[C#]"
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 속성 사용(C# 프로그래밍 가이드)
속성은 필드 기능과 메서드 기능을 둘다 포함하고 있습니다.  개체의 사용자에게는 속성이 필드로 나타나며, 속성에 액세스하려면 동일한 구문이 필요합니다.  클래스의 구현자에게 있어 속성은 [get](../../../csharp/language-reference/keywords/get.md) 접근자 및\/또는 [set](../../../csharp/language-reference/keywords/set.md) 접근자를 나타내는 한 개 또는 두 개의 코드 블록입니다.  `get` 접근자의 코드 블록은 속성을 읽을 때 실행되고, `set` 접근자의 코드 블록은 속성에 새 값을 할당할 때 실행됩니다.  `set` 접근자가 없는 속성은 읽기 전용으로 간주됩니다.  `get` 접근자가 없는 속성은 쓰기 전용으로 간주됩니다.  두 접근자가 모두 있는 속성은 읽고 쓸 수 있습니다.  
  
 필드와 달리 속성은 변수로 분류되지 않습니다.  따라서 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수로 속성을 전달할 수 없습니다.  
  
 속성은 여러 가지로 사용할 수 있습니다. 속성을 사용하면 데이터 변경을 허용하기 전에 데이터의 유효성을 검사하거나, 데이터베이스 같은 다른 소스에서 해당 데이터가 실제로 검색된 클래스에 데이터를 투명하게 노출하거나, 이벤트 발생 또는 다른 필드의 값 변경 같이 데이터가 변경되는 경우에 작업을 수행할 수 있습니다.  
  
 클래스 블록에서 필드의 액세스 수준을 지정하고 속성의 형식, 속성의 이름을 차례로 지정한 다음 `get` 접근자 및\/또는 `set` 접근자를 선언하는 코드 블록을 추가하여 속성을 선언할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_1.cs)]  
  
 이 예제에서 `Month`는 속성으로 선언되며 `set` 접근자는 `Month` 값이 1에서 12 사이의 숫자로 설정되는지 확인할 수 있습니다.  `Month` 속성은 실제 값을 추적하기 위해 전용 필드를 사용합니다.  속성 데이터의 실제 위치를 일반적으로 속성의 "지원 저장소"라고 합니다. 속성의 지원 저장소로는 대개 전용 필드가 사용됩니다.  이 필드는 속성을 호출한 경우에만 변경할 수 있도록 전용으로 표시됩니다.  공용 및 전용 액세스 제한 사항에 대한 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 자동으로 구현된 속성을 사용하면 단순화된 구문으로 간단한 속성을 선언할 수 있습니다.  자세한 내용은 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하십시오.  
  
## get 접근자  
 `get` 접근자의 본문은 메서드의 본문과 비슷하며  속성 형식의 값을 반환해야 합니다.  `get` 접근자를 실행하는 것은 필드 값을 읽는 것과 같습니다.  예를 들어, 최적화 기능을 활성화한 상태로 `get` 접근자에서 private 변수를 반환하는 경우 메서드 호출 오버헤드가 발생하지 않도록 `get` 접근자 메서드에 대한 호출이 컴파일러에서 인라인됩니다.  그러나 가상 `get` 접근자 메서드는 인라인될 수 없습니다. 런타임에 실제로 호출할 수 있는 메서드에 대한 정보가 컴파일 단계에서 컴파일러에 제공되지 않기 때문입니다.  다음은 전용 필드인 `name`의 값을 반환하는 `get` 접근자입니다.  
  
 [!code-cs[csProgGuideProperties#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_2.cs)]  
  
 할당 대상인 경우를 제외하고 속성을 참조하면 속성 값을 읽기 위해 `get` 접근자가 호출됩니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_3.cs)]  
  
 `get` 접근자는 [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 끝나야 합니다. 제어는 접근자 본문에서 끝날 수 없습니다.  
  
 `get` 접근자를 사용하여 개체의 상태를 변경하는 것은 잘못된 프로그래밍 습관입니다.  예를 들어, 다음 접근자에서는 `number` 필드에 액세스할 때마다 개체의 상태가 바뀌는 의도하지 않은 동작이 발생합니다.  
  
 [!code-cs[csProgGuideProperties#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_4.cs)]  
  
 `get` 접근자는 필드 값을 반환하거나 필드 값을 계산하여 그 결과를 반환하는 데 사용됩니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_5.cs)]  
  
 위 코드 세그먼트에서 `Name` 속성에 값을 할당하지 않으면 NA 값이 반환됩니다.  
  
## set 접근자  
 `set` 접근자는 반환 형식이 [void](../../../csharp/language-reference/keywords/void.md)인 메서드와 비슷합니다.  이 접근자는 해당 형식이 속성의 형식과 같은 `value`라는 암시적 매개 변수를 사용합니다.  다음 예제에서는 `Name` 속성에 `set` 접근자를 추가합니다.  
  
 [!code-cs[csProgGuideProperties#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_6.cs)]  
  
 속성에 값을 할당하면 새 값을 제공하는 인수를 사용하여 `set` 접근자가 호출됩니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideProperties#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_7.cs)]  
  
 `set` 접근자의 지역 변수 선언에서 암시적 매개 변수 이름\(`value`\)을 사용하면 오류가 발생합니다.  
  
## 설명  
 속성은 `public`, `private`, `protected`, `internal` 또는 `protected internal`로 표시할 수 있습니다.  이러한 액세스 한정자는 클래스 사용자가 속성에 액세스할 수 있는 방식을 정의합니다.  동일한 속성에 대한 `get` 및 `set` 접근자에 서로 다른 액세스 한정자가 있을 수 있습니다.  예를 들어, `get`은 형식 외부에서 읽기 전용으로 액세스할 수 있도록 `public`으로 지정하고 `set`은 `private` 또는 `protected`로 지정할 수 있습니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 `static` 키워드를 사용하면 속성을 정적 속성으로 선언할 수 있습니다.  이렇게 하면 클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 속성을 사용할 수 있습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하십시오.  
  
 [virtual](../../../csharp/language-reference/keywords/virtual.md) 키워드를 사용하면 속성을 가상 속성으로 선언할 수 있습니다.  이렇게 하면 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 파생 클래스에서 속성 동작을 재정의할 수 있습니다.  이러한 옵션에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하십시오.  
  
 가상 속성을 재정의하는 속성은 파생 클래스에 대해 이 속성이 가상이 아님을 지정하는 [sealed](../../../csharp/language-reference/keywords/sealed.md)가 될 수도 있습니다.  마지막으로 속성을 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있습니다.  이렇게 하면 클래스에 구현이 없으므로 파생 클래스에서 자체 구현을 작성해야 합니다.  이러한 옵션에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)을 참조하십시오.  
  
> [!NOTE]
>  [정적](../../../csharp/language-reference/keywords/static.md) 속성의 접근자에 [virtual](../../../csharp/language-reference/keywords/virtual.md), [abstract](../../../csharp/language-reference/keywords/abstract.md) 또는 [override](../../../csharp/language-reference/keywords/override.md) 한정자를 사용하면 오류가 발생합니다.  
  
## 예제  
 다음 예제에서는 인스턴스, 정적 및 읽기 전용 속성을 보여 줍니다.  키보드에서 직원 이름을 입력 받고, `NumberOfEmployees` 변수의 값을 1만큼 증가시킨 다음 직원 이름과 번호를 표시합니다.  
  
 [!code-cs[csProgGuideProperties#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_8.cs)]  
  
## 예제  
 다음 예제에서는 파생 클래스에 기본 클래스의 속성과 동일한 이름의 속성이 있어서 숨겨진 기본 클래스의 속성에 액세스하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideProperties#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_9.cs)]  
  
 위 예제의 주요 사항은 다음과 같습니다.  
  
-   파생 클래스의 `Name` 속성은 기본 클래스의 `Name` 속성을 숨깁니다.  이 경우 다음과 같이 `new` 한정자가 파생 클래스의 속성 선언에 사용됩니다.  
  
     [!code-cs[csProgGuideProperties#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_10.cs)]  
  
-   `(Employee)` 캐스팅은 기본 클래스의 숨겨진 속성에 액세스하는 데 사용됩니다.  
  
     [!code-cs[csProgGuideProperties#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_11.cs)]  
  
     멤버 숨기기에 대한 자세한 내용은 [new 한정자](../../../csharp/language-reference/keywords/new-modifier.md)를 참조하십시오.  
  
## 예제  
 다음 예제의 `Cube` 클래스와 `Square`는 `Shape` 추상 클래스를 구현하고 `Area` 추상 속성을 재정의합니다.  속성에서 [override](../../../csharp/language-reference/keywords/override.md) 한정자를 사용한 방법에 주의하십시오.  프로그램에서는 측면 길이 값을 입력 받아 정사각형과 입방체의 면적을 계산합니다.  또한 면적을 입력 받아 그에 대응하는 정사각형과 입방체의 측면 길이 값을 계산합니다.  
  
 [!code-cs[csProgGuideProperties#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_12.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [인터페이스 속성](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)   
 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)