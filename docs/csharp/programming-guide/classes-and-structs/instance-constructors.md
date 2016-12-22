---
title: "인스턴스 생성자(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "생성자[C#], 인스턴스 생성자"
  - "인스턴스 생성자[C#]"
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 인스턴스 생성자(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[new](../../../csharp/language-reference/keywords/new.md) 식을 사용하여 [클래스](../../../csharp/language-reference/keywords/class.md)의 개체를 만드는 경우 인스턴스 생성자를 사용하여 인스턴스 멤버 변수를 만들고 초기화합니다.  [정적](../../../csharp/language-reference/keywords/static.md) 클래스나 비정적 클래스의 정적 변수를 초기화하려면 정적 생성자를 정의해야 합니다.  자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하십시오.  
  
 다음 예제에서는 인스턴스 생성자를 보여 줍니다.  
  
 [!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  명확한 이해를 돕기 위해 이 클래스에는 public 필드가 포함되어 있습니다.  public 필드를 사용하면 프로그램의 모든 메서드가 위치에 관계없이 개체의 내부 작업에 확인을 거치지 않은 채 무제한으로 액세스할 수 있으므로 이 방법은 실제로 사용하지 않는 것이 좋습니다.  데이터 멤버는 일반적으로 전용이어야 하며 클래스 메서드 및 속성을 통해서만 액세스할 수 있어야 합니다.  
  
 이 인스턴스 생성자는 `CoOrds` 클래스를 기반으로 개체가 만들어질 때마다 호출됩니다.  이와 같이 인수를 사용하지 않는 생성자를 *기본 생성자*라고 합니다.  그러나 일반적으로는 다른 생성자를 추가로 제공하는 것이 유용합니다.  예를 들어, 데이터 멤버에 대한 초기 값을 지정할 수 있도록 `CoOrds` 클래스에 생성자를 추가할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 이렇게 하면 다음과 같이 특정 초기 값이나 기본값으로 `CoOrd` 개체를 만들 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 클래스에 생성자가 없는 경우 기본 생성자가 자동으로 생성되며, 기본값을 사용하여 개체 필드가 초기화됩니다.  예를 들어, [int](../../../csharp/language-reference/keywords/int.md)는 0으로 초기화됩니다.  기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하십시오.  따라서, `CoOrds` 클래스 기본 생성자가 모든 데이터 멤버를 0으로 초기화하므로 클래스의 작동 방식을 변경하지 않고도 이를 완전히 제거할 수 있습니다.  여러 생성자를 사용하는 전체 예제는 이 항목의 뒷부분에 있는 예제 1을 참조하고, 자동으로 생성된 생성자의 예제는 예제 2를 참조하십시오.  
  
 인스턴스 생성자를 사용하여 기본 클래스의 인스턴스 생성자를 호출할 수도 있습니다.  클래스 생성자는 다음과 같이 이니셜라이저를 통해 기본 클래스의 생성자를 호출할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 이 예제에서 `Circle` 클래스는 `Circle`을 파생하는 데 사용되는 `Shape`에서 제공하는 생성자에 반지름과 높이를 나타내는 값을 전달합니다.  `Shape` 및 `Circle`을 사용하는 전체 예제는 이 항목의 예제 3을 참조하십시오.  
  
## 예제 1  
 다음 예제에서는 인수 없는 클래스 생성자와 두 개의 인수가 있는 클래스 생성자라는 2개의 클래스 생성자를 가진 클래스에 대해 설명합니다.  
  
 [!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## 예제 2  
 이 예제에서 `Person` 클래스는 생성자를 갖지 않는데, 이 경우 기본 생성자가 자동으로 생성되며 필드는 기본값으로 초기화됩니다.  
  
 [!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 `age`의 기본값은 `0`이고 `name`의 기본값은 `null`입니다.  기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하십시오.  
  
## 예제 3  
 다음 예제에서는 기본 클래스 이니셜라이저를 사용하여 설명합니다.  `Circle` 클래스는 일반 클래스 `Shape`에서 파생되며 `Cylinder` 클래스는 `Circle` 클래스에서 파생됩니다.  파생된 각 클래스의 생성자는 자체의 기본 클래스 이니셜라이저를 사용합니다.  
  
 [!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 기본 클래스 생성자 호출에 대한 자세한 예제는 [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) 및 [base](../../../csharp/language-reference/keywords/base.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)