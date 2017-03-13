---
title: "필드(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "필드[C#]"
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# 필드(C# 프로그래밍 가이드)
*필드*는 [클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md) 내부에 직접 선언되는 임의 형식의 변수입니다.  필드는 포함하는 형식의 *멤버* 입니다.  
  
 클래스 또는 구조체는 인스턴스 필드 또는 정적 필드를 가지거나 둘 모두를 가질 수 있습니다.  인스턴스 필드는 특정 형식의 인스턴스에 고유합니다.  인스턴스 필드 F를 포함하는 클래스 T가 있을 때 T 형식의 개체 두 개를 만드는 경우 다른 개체의 값에 영향을 주지 않고 각 개체의 F 값을 수정할 수 있습니다.  이와 달리 정적 필드는 클래스 자체에 속해 있으며 해당 클래스의 모든 인스턴스에서 공유됩니다.  인스턴스 A에서 정적 필드를 변경하는 경우 인스턴스 B와 C에서 이 필드에 액세스할 때 즉시 이 변경 내용을 볼 수 있습니다.  
  
 일반적으로 액세스 가능성이 private 또는 protected인 변수에 대해서만 필드를 사용해야 합니다.  클래스에서 클라이언트 코드에 노출하는 데이터는 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../../csharp/programming-guide/indexers/index.md)를 통해 제공해야 합니다.  내부 필드에 간접적으로 액세스하기 위해 이러한 구문을 사용함으로써 잘못된 입력 값으로부터 보호할 수 있습니다.  public 속성에 의해 노출되는 데이터를 저장하는 private 필드를 *지원 저장소* 또는 *지원 필드*라고 합니다.  
  
 대개 필드에는 여러 클래스 메서드에서 액세스해야 하고 단일 메서드의 수명보다 오래 저장되어야 하는 데이터가 저장됩니다.  예를 들어 달력 데이터를 나타내는 클래스에는 각각 일, 월, 년을 나타내는 세 개의 정수 필드가 포함될 수 있습니다.  단일 메서드 범위 밖에서 사용하지 않는 변수는 메서드 본문의 내부에서 *지역 변수*로 선언해야 합니다.  
  
 필드는 필드의 액세스 수준을 지정하고 필드의 형식과 필드의 이름을 차례로 사용하여 클래스 블록에서 선언됩니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 개체의 필드에 액세스하려면 `objectname.fieldname`과 같이 개체 이름 뒤에 마침표와 필드 이름을 추가합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 필드를 선언할 때 대입 연산자를 사용하여 필드의 초기 값을 지정할 수 있습니다.  예를 들어 `day` 필드에 `"Monday"`을 자동으로 할당하려면 다음 예제와 같이 `day`를 선언합니다.  
  
 [!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 필드는 개체 인스턴스의 생성자를 호출하기 직전에 초기화됩니다.  생성자가 필드의 값을 할당하는 경우 필드 선언 도중 지정된 모든 값을 덮어씁니다.  자세한 내용은 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)를 참조하십시오.  
  
> [!NOTE]
>  필드 이니셜라이저는 다른 인스턴스 필드를 참조할 수 없습니다.  
  
 필드는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected internal`로 표시할 수 있습니다.  이러한 액세스 한정자는 클래스 사용자가 필드에 액세스하는 방식을 정의합니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 추가적으로 필드를 [static](../../../csharp/language-reference/keywords/static.md)으로 선언할 수도 있습니다.  이렇게 하면 클래스의 인스턴스가 없어도 언제든지 호출자가 필드를 사용할 수 있습니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하십시오.  
  
 [readonly](../../../csharp/language-reference/keywords/readonly.md)를 사용하여 필드를 선언할 수 있습니다.  읽기 전용 필드에는 초기화 도중이나 생성자에서만 값을 할당할 수 있습니다.  `static` `readonly` 필드는 상수와 매우 비슷하지만 C\# 컴파일러가 컴파일 타임이 아닌 런타임에만 정적 읽기 전용 필드의 값에 액세스할 수 있다는 점에서 차이가 있습니다.  자세한 내용은 [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)