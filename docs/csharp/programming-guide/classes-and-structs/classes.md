---
title: "클래스(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "클래스[C#]"
  - "C# 언어, 클래스"
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: 40
caps.handback.revision: 40
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 클래스(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

*클래스*는 다른 형식의 변수, 메서드 및 이벤트를 그룹화하여 사용자 지정 형식을 만들 수 있는 구문입니다.  클래스는 청사진과 같습니다.  클래스는 형식의 데이터 및 동작을 정의합니다.  클래스가 static으로 선언되지 않은 경우 클라이언트 코드에서는 변수에 할당되는 *개체* 또는 *인스턴스*를 만들어 클래스를 사용할 수 있습니다.  변수는 해당 변수에 대한 모든 참조가 범위를 벗어날 때까지 메모리에 유지됩니다.  모든 참조가 범위를 벗어나면 CLR에서 해당 변수를 가비지 수집 대상으로 표시합니다.  클래스가 [static](../../../csharp/language-reference/keywords/static.md)으로 선언되면 하나의 복사본만 메모리에 존재하며 클라이언트 코드에서는 *인스턴스 변수*를 통해서가 아니라 클래스 자체를 통해서만 클래스에 액세스할 수 있습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)을 참조하십시오.  
  
 구조체와 달리 클래스는 개체 지향 프로그래밍의 근본 특징인 *상속*을 지원합니다.  자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하십시오.  
  
## 클래스 선언  
 다음 예제와 같이 클래스는 [class](../../../csharp/language-reference/keywords/class.md) 키워드를 사용하여 선언합니다.  
  
 [!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]  
  
 `class` 키워드는 액세스 수준 뒤에 사용합니다.  이 경우에는 [public](../../../csharp/language-reference/keywords/public.md)을 사용했기 때문에 모든 사용자가 이 클래스에서 개체를 만들 수 있습니다.  클래스의 이름은 `class` 키워드 뒤에 사용합니다.  정의의 나머지 부분인 클래스 본문에서는 동작과 데이터를 정의합니다.  클래스의 필드, 속성, 메서드 및 이벤트를 통칭하여 *클래스 멤버*라고 합니다.  
  
## 개체 만들기  
 클래스와 개체는 서로 바꿔 사용되기도 하지만 근본적으로 이 둘은 서로 다릅니다.  클래스는 개체의 형식을 정의할 뿐 개체 자체는 아닙니다.  개체는 클래스를 기반으로 하는 구체적인 엔터티이며 클래스의 인스턴스라고도 합니다.  
  
 개체는 다음과 같이 [new](../../../csharp/language-reference/keywords/new.md) 키워드 뒤에 개체의 기반으로 사용할 클래스의 이름을 추가하여 만들 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]  
  
 클래스의 인스턴스가 만들어지면 개체에 대한 참조가 프로그래머에게 다시 전달됩니다.  위의 예제에서 `object1`은 `Customer`를 기반으로 하는 개체에 대한 참조입니다.  이 참조는 새 개체를 가리키지만 개체 데이터 자체를 포함하지는 않습니다.  사실 개체를 전혀 만들지 않고도 개체 참조를 만들 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]  
  
 이와 같이 개체를 참조하지 않는 개체 참조는 만들지 않는 것이 좋습니다. 이러한 참조를 통해 개체에 액세스하려고 하면 런타임에 오류가 발생하기 때문입니다.  그러나 다음과 같이 새 개체를 만들거나 이러한 참조를 기존 개체에 할당하여 참조가 개체를 가리키도록 할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]  
  
 이 코드에서는 모두 동일한 개체를 가리키는 두 개의 개체 참조를 만듭니다.  따라서 `object3`을 통해 개체에 대해 변경한 내용은 모두 이후에 `object4`를 사용할 때 반영됩니다.  클래스를 기반으로 하는 개체는 참조를 통해 참조되기 때문에 클래스를 참조 형식이라고 합니다.  
  
## 클래스 상속  
 상속은 *파생*을 통해 이루어집니다. 즉, 클래스는 데이터와 동작을 상속할 *기본 클래스*를 사용하여 선언합니다.  기본 클래스는 다음과 같이 파생 클래스 이름 뒤에 콜론과 기본 클래스의 이름을 추가하여 지정합니다.  
  
 [!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]  
  
 클래스에서 기본 클래스를 선언하면 생성자를 제외한 기본 클래스의 모든 멤버가 상속됩니다.  
  
 C\+\+와 달리 C\#의 클래스는 하나의 기본 클래스만 직접 상속할 수 있습니다.  그러나 기본 클래스 자체도 다른 클래스를 상속할 수 있기 때문에 클래스는 여러 개의 기본 클래스를 간접적으로 상속할 수 있습니다.  또한 클래스는 인터페이스를 두 개 이상 직접 구현할 수 있습니다.  자세한 내용은 [인터페이스](../../../visual-basic/reference/command-line-compiler/index.md)을 참조하십시오.  
  
 클래스를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있습니다.  추상 클래스는 시그니처 정의가 있지만 구현은 없는 추상 메서드를 포함합니다.  추상 클래스는 인스턴스화할 수 없습니다.  추상 클래스는 추상 메서드를 구현하는 파생 클래스를 통해서만 사용할 수 있습니다.  이와 반대로 [sealed](../../../csharp/language-reference/keywords/sealed.md) 클래스는 다른 클래스에서 상속할 수 없습니다.  자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)을 참조하십시오.  
  
 클래스 정의는 여러 소스 파일로 분할할 수 있습니다.  자세한 내용은 [Partial 클래스 및 메서드](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)을 참조하십시오.  
  
## 설명  
 다음 예제에서는 단일 필드, 메서드 및 생성자라는 특별한 메서드가 포함된 공용 클래스를 정의합니다.  자세한 내용은 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)을 참조하십시오.  그런 다음 `new` 키워드를 사용하여 클래스를 인스턴스화합니다.  
  
## 예제  
 [!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [개체 지향 프로그래밍](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)   
 [멤버](../../../csharp/programming-guide/classes-and-structs/members.md)   
 [메서드](../../../fsharp/language-reference/members/methods.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [개체](../../../csharp/programming-guide/classes-and-structs/objects.md)