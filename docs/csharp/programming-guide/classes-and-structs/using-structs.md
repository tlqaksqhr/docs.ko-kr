---
title: "구조체 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "구조체[C#], 사용"
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# 구조체 사용(C# 프로그래밍 가이드)
`struct` 형식은 `Point`, `Rectangle`, `Color` 등의 간단한 개체를 나타내는 데 적합합니다. 점을 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)이 있는 [클래스](../../../csharp/language-reference/keywords/class.md)로 표현할 수도 있지만 일부 시나리오에서는 [구조체](../../../csharp/language-reference/keywords/struct.md)를 사용하는 것이 더 효율적일 수 있습니다. 예를 들어 1000개의 `Point` 개체가 있는 배열을 선언하는 경우에는 각 개체를 참조하기 위해 추가 메모리를 할당하게 되며, 이러한 경우 구조체가 보다 효율적입니다.[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]에 <xref:System.Drawing.Point>라는 개체가 포함되어 있으므로 이 예제의 구조체 이름은 "CoOrds"로 지정되었습니다.  
  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 구조체에 대해 기본 생성자\(매개 변수 없음\)를 정의하면 오류가 발생합니다. 구조체 본문에서 인스턴스 필드를 초기화해도 오류가 발생합니다. 구조체의 멤버는 매개 변수가 있는 생성자를 사용하거나 구조체가 선언된 후 멤버에 개별적으로 액세스하는 방법으로만 초기화할 수 있습니다. 전용 멤버 또는 다른 방법으로 액세스할 수 없는 멤버는 생성자 내부에서만 초기화할 수 있습니다.  
  
 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 구조체 개체를 생성할 경우 구조체 개체가 생성된 후에 적절한 생성자가 호출됩니다. 클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다. 이런 경우에는 생성자를 호출하지 않으므로 할당이 더 효율적으로 이루어집니다. 하지만 필드가 할당되지 않은 상태로 남아 있게 되며 개체를 사용하려면 모든 필드를 초기화해야 합니다.  
  
 구조체에 참조 형식인 멤버가 있는 경우 멤버의 기본 생성자가 명시적으로 호출되어야 합니다. 그렇지 않으면 멤버가 할당되지 않은 상태로 남아 있게 되므로 구조체를 사용할 수 없습니다. 이 경우 컴파일러 오류 CS0171이 발생합니다.  
  
 클래스의 경우와는 달리 구조체에 대한 상속은 없습니다. 구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다. 그러나 구조체는 기본 클래스 <xref:System.Object>에서 상속할 수 있습니다. 구조체는 클래스에서 인터페이스를 구현하는 것과 동일한 방식으로 인터페이스를 구현할 수 있습니다.  
  
 `struct` 키워드를 사용하여 클래스를 선언할 수 없습니다. C\#에서 클래스와 구조체는 구문적으로 다릅니다. 구조체는 값 형식인 반면 클래스는 참조 형식입니다. 자세한 내용은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)을 참조하세요.  
  
 참조 형식 구문이 필요한 경우가 아니라면 작은 클래스는 구조체로 대신 선언하면 시스템에서 보다 효율적으로 처리할 수 있습니다.  
  
## 예제 1  
  
### 설명  
 이 예제에서는 기본 생성자와 매개 변수가 있는 생성자 둘 다를 사용하여 `struct`를 초기화하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## 예제 2  
  
### 설명  
 이 예제에서는 구조체의 특징에 대해 설명합니다. 여기서는 `new` 연산자를 사용하지 않고 CoOrds 개체를 만듭니다.`struct`를 `class`로 바꾸면 프로그램이 컴파일되지 않습니다.  
  
### 코드  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)