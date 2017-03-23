---
title: "생성자 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "생성자[C#], 생성자 정보"
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# 생성자 사용(C# 프로그래밍 가이드)
경우는  [클래스](../../../csharp/language-reference/keywords/class.md) 또는  [구조체](../../../csharp/language-reference/keywords/struct.md) 는 만들어지면 해당 생성자가 호출 됩니다.  생성자는 클래스 또는 구조체와 같은 이름을 하 고 일반적으로 새 개체의 데이터 멤버를 초기화 합니다.  
  
 다음 예제에서는 간단한 생성자를 사용하여 `Taxi`라는 클래스를 정의합니다.  그런 다음 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 이 클래스를 인스턴스화합니다.  새 개체에 대한 메모리를 할당한 직후에 `new` 연산자에 의해 `Taxi` 생성자가 호출됩니다.  
  
 [!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 매개 변수를 사용하지 않는 생성자를 *기본 생성자*라고 합니다.  기본 생성자는 `new` 연산자에 아무런 인수도 전달하지 않은 채 `new` 연산자를 사용하여 개체를 인스턴스화할 때마다 호출됩니다.  자세한 내용은 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)을 참조하십시오.  
  
 클래스가 [정적](../../../csharp/language-reference/keywords/static.md) 클래스가 아닌 경우 생성자가 없는 클래스에는 클래스 인스턴스화에 필요한 공용 기본 생성자가 C\# 컴파일러에 의해 제공됩니다.  자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)을 참조하십시오.  
  
 다음과 같이 생성자를 전용 생성자로 만들면 클래스가 인스턴스화되지 않도록 방지할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 자세한 내용은 [전용 생성자](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)을 참조하십시오.  
  
 [구조체](../../../csharp/language-reference/keywords/struct.md) 형식에 대한 생성자는 클래스 생성자와 비슷하지만 `structs`에는 컴파일러를 통해 생성자가 자동으로 제공되므로 명시적 기본 생성자가 포함될 수 없습니다.  이 생성자는 `struct`의 각 필드를 기본값으로 초기화합니다.  자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)을 참조하십시오.  그러나 이 기본 생성자는 `new`를 사용하여 `struct`를 인스턴스화한 경우에만 호출됩니다.  예를 들어 다음 코드에서는 <xref:System.Int32>의 기본 생성자를 사용하므로 정수가 초기화됩니다.  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 그러나 다음 코드에서는 `new`를 사용하지 않으며 초기화되지 않은 개체를 사용하려고 하기 때문에 컴파일러 오류가 발생합니다.  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 또는 다음 예제와 같이 `structs`를 기반으로 하는 개체\(모든 기본 제공 숫자 형식 포함\)를 초기화하거나 할당한 후에 사용할 수 있습니다.  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 따라서 값 형식에 대한 기본 생성자를 호출할 필요가 없습니다.  
  
 클래스와 `structs` 모두 매개 변수를 사용하는 생성자를 정의할 수 있습니다.  매개 변수를 사용하는 생성자는 `new` 문이나 [base](../../../csharp/language-reference/keywords/base.md) 문을 통해 호출해야 합니다.  클래스와 `structs`는 여러 생성자를 정의할 수도 있으며, 둘 모두 기본 생성자를 정의할 필요가 없습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 다음 문 중 하나를 사용하여 이 클래스를 만들 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 생성자에서는 `base` 키워드를 사용하여 기본 클래스의 생성자를 호출할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 이 예제에서 기본 클래스의 생성자는 생성자의 블록이 실행되기 전에 호출됩니다.  `base` 키워드는 매개 변수와 함께 사용하거나 매개 변수 없이 사용할 수 있습니다.  생성자에 대한 모든 매개 변수는 `base`에 대한 매개 변수로 사용하거나 식의 일부로 사용할 수 있습니다.  자세한 내용은 [base](../../../csharp/language-reference/keywords/base.md)을 참조하십시오.  
  
 파생 클래스에서 `base` 키워드를 사용하여 기본 클래스 생성자를 명시적으로 호출하지 않은 경우 기본 생성자가 있으면 이 생성자가 암시적으로 호출됩니다.  즉, 다음과 같은 생성자 선언도 동일한 결과를 낳습니다.  
  
 [!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 기본 클래스에서 기본 생성자를 제공하지 않으면 파생 클래스에서 `base`를 사용하여 기본 생성자를 명시적으로 호출해야 합니다.  
  
 생성자에서 [this](../../../csharp/language-reference/keywords/this.md) 키워드를 사용하여 동일한 개체의 다른 생성자를 호출할 수 있습니다.  `base`와 마찬가지로 `this`는 매개 변수와 함께 사용하거나 매개 변수 없이 사용할 수 있으며, 생성자의 임의의 매개 변수를 `this`에 대한 매개 변수로 사용하거나 식의 일부로 사용할 수 있습니다.  예를 들어, 위 예제의 두 번째 생성자는 `this`를 사용하여 다시 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 위의 예제에서 `this` 키워드를 사용하면 이 생성자가 호출됩니다.  
  
 [!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 생성자는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected` `internal`로 표시할 수 있습니다.  이러한 액세스 한정자는 클래스 사용자가 클래스를 생성하는 방식을 정의합니다.  자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 [static](../../../csharp/language-reference/keywords/static.md) 키워드를 사용하여 생성자를 정적으로 선언할 수 있습니다.  정적 생성자는 정적 필드에 액세스하기 직전에 자동으로 호출되며 일반적으로 정적 클래스 멤버를 초기화하는 데 사용됩니다.  자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)