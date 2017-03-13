---
title: "개체(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "개체[C#], 개체 정보"
  - "변수[C#]"
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# 개체(C# 프로그래밍 가이드)
클래스나 구조체의 정의는 해당 형식으로 수행할 수 있는 작업을 지정하는 청사진과 같습니다.  개체는 기본적으로 이 청사진에 따라 할당되고 구성된 메모리 블록입니다.  프로그램은 동일한 클래스의 개체를 많이 만들 수 있습니다.  개체는 인스턴스라고도 하며 명명된 변수나 배열 또는 컬렉션에 저장될 수 있습니다.  클라이언트 코드는 이러한 변수를 사용하여 메서드를 호출하고 개체의 공용 속성에 액세스하는 코드입니다.  C\#과 같은 개체 지향 언어에서 일반적인 프로그램은 동적으로 상호 작용하는 여러 개체로 구성되어 있습니다.  
  
> [!NOTE]
>  정적 형식은 여기에서 설명하는 내용과 다르게 동작합니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)을 참조하십시오.  
  
## 구조체 인스턴스 VS. 클래스 인스턴스  
 클래스는 참조 형식이므로 클래스 개체의 변수는 개체 주소에 대한 참조를 관리되는 힙에 유지합니다.  첫 번째 개체에 동일한 형식의 두 번째 개체가 할당되면 두 변수 모두 같은 주소에 있는 개체를 참조합니다.  이 내용에 대해서는 이 항목의 뒷부분에서 자세히 설명합니다.  
  
 클래스의 인스턴스는 [new 연산자](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 생성됩니다.  다음 예제에서 `Person`은 형식이고 `person1` 및 `person 2`는 해당 형식의 인스턴스 또는 개체입니다.  
  
 [!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]  
  
 구조체는 값 형식이므로 구조체 개체의 변수는 전체 개체의 복사본을 유지합니다.  다음 예제와 같이 `new` 연산자를 사용하여 구조체의 인스턴스를 만들 수 있지만 이 연산자가 반드시 필요한 것은 아닙니다.  
  
 [!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]  
  
 `p1` 및 `p2`에 대한 메모리는 스레드 스택에 할당됩니다.  이 메모리는 해당 구조체가 선언된 형식 또는 메서드와 함께 회수됩니다.  이것이 구조체가 할당 시 복사되는 이유 중 하나입니다.  이와 달리 클래스 인스턴스용으로 할당된 메모리는 개체에 대한 모든 참조가 범위를 벗어나면 공용 언어 런타임에 의해 자동으로 회수\(가비지 수집\)됩니다.  하지만 C\+\+에서와 같이 클래스 개체를 명확하게 삭제할 수는 없습니다.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 가비지 수집에 대한 자세한 내용은 [Garbage Collection](../Topic/Garbage%20Collection.md)을 참조하십시오.  
  
> [!NOTE]
>  공용 언어 런타임에서 관리되는 힙의 메모리 할당 및 할당 취소는 고도로 최적화되어 있습니다.  대부분의 경우 힙에 클래스 인스턴스를 할당하는 것과 스택에 구조체 인스턴스를 할당하는 것 간에 성능상의 차이는 거의 없습니다.  
  
## VS Identity 개체. 값이 같은지 확인  
 두 개체가 같은지 비교할 때에는 두 변수가 메모리의 동일한 개체를 나타내는지를 비교할 것인지 또는 개체 필드에 있는 하나 이상의 값이 같은지를 비교할 것인지를 구분해야 합니다.  값을 비교하려는 경우에는 개체가 값 형식의 인스턴스\(구조체\)인지 참조 형식의 인스턴스\(클래스, 대리자, 배열\)인지 고려해야 합니다.  
  
-   두 클래스 인스턴스가 메모리에서 동일한 위치를 참조하는지 확인하려면, 즉 동일한 *ID*를 갖는지 확인하려면 정적 <xref:System.Object.Equals%2A> 메서드를 사용합니다.  \(<xref:System.Object?displayProperty=fullName>는 사용자 정의 구조체 및 클래스를 비롯한 모든 값 형식 및 참조 형식에 대한 암시적 기본 클래스입니다.\)  
  
-   두 구조체 인스턴스의 인스턴스 필드가 동일한 값을 갖는지 확인하려면 <xref:System.ValueType.Equals%2A?displayProperty=fullName> 메서드를 사용합니다.  모든 구조체는 <xref:System.ValueType?displayProperty=fullName>에서 암시적으로 상속되므로 다음 예제와 같이 개체에서 직접 이 메서드를 호출합니다.  
  
 [!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]  
  
 구조체에서 필드의 내용을 확인할 수 있어야 하므로 `Equals`의 <xref:System.ValueType?displayProperty=fullName> 구현에서는 리플렉션을 사용합니다.  고유한 구조체를 만들 때 해당 형식과 관련된 효율적인 동일성 비교 알고리즘을 제공하려면 `Equals` 메서드를 재정의합니다.  
  
-   두 개의 클래스 인스턴스에서 필드의 값이 같은지 확인하려면 <xref:System.Object.Equals%2A> 메서드 또는 [\=\= 연산자](../../../csharp/language-reference/operators/equality-comparison-operator.md)를 사용할 수도 있습니다.  그러나 해당 형식의 개체에 대해 어떤 "품질"인지에 대한 사용자 지정 정의를 제공하기 위해 클래스가 오버로드된 경우에만 사용합니다.  이 클래스는 <xref:System.IEquatable%601> 인터페이스 또는 <xref:System.Collections.Generic.IEqualityComparer%601> 인터페이스를 구현할 수도 있습니다.  두 인터페이스 모두 값이 같은지 테스트하는 데 사용할 수 있는 메서드를 제공합니다.  `Equals`를 재지정하는 자체 클래스를 설계할 때 [방법: 형식의 값 일치 정의](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) 및 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>에 명시된 지침에 따라야 합니다.  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [이벤트](../../../csharp/programming-guide/events/index.md)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [클래스](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [new 연산자](../../../csharp/language-reference/keywords/new-operator.md)   
 [공용 형식 시스템](../../../standard/base-types/common-type-system.md)