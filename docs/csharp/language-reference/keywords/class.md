---
title: "class(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "class_CSharpKeyword"
  - "class"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "class 키워드[C#]"
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# class(C# 참조)
클래스는 다음 예제와 같이 `class` 키워드를 사용하여 선언합니다.  
  
```  
  
      class TestClass  
{  
    // Methods, properties, fields, events, delegates   
    // and nested classes go here.  
}  
```  
  
## 설명  
 C\# 단일 상속만 허용 됩니다.  즉, 클래스는 하나의 기본 클래스에서만 구현을 상속할 수 있습니다.  그러나 클래스는 인터페이스를 두 개 이상 구현할 수 있습니다.  다음 표에는 클래스 상속 및 인터페이스 구현 예제가 나와 있습니다.  
  
|상속|예제|  
|--------|--------|  
|없음|`class ClassA { }`|  
|Single|`class DerivedClass: BaseClass { }`|  
|없음, 두 개의 인터페이스 구현|`class ImplClass: IFace1, IFace2 { }`|  
|단일, 한 개의 인터페이스 구현|`class ImplDerivedClass: BaseClass, IFace1 { }`|  
  
 다른 클래스 내에 중첩 없습니다 직접는 네임 스페이스를 선언 하는 클래스 일 수 있습니다  [공용](../../../csharp/language-reference/keywords/public.md) 또는  [내부](../../../csharp/language-reference/keywords/internal.md).  클래스는 `internal` 기본적으로.  
  
 중첩 된 클래스를 포함 하는 클래스 멤버를 사용할 수 있습니다  [공용](../../../csharp/language-reference/keywords/public.md), `protected internal`,  [보호](../../../csharp/language-reference/keywords/protected.md),  [내부](../../../csharp/language-reference/keywords/internal.md), 또는  [개인](../../../csharp/language-reference/keywords/private.md).  구성원 인  [개인](../../../csharp/language-reference/keywords/private.md) 기본적으로.  
  
 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)을 참조하십시오.  
  
 형식 매개 변수가 있는 제네릭 클래스를 선언할 수 있습니다.  자세한 내용은  [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md).  
  
 클래스에는 다음과 같은 멤버 선언이 포함될 수 있습니다.  
  
-   [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)  
  
-   [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)  
  
-   [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [인덱서](../../../csharp/programming-guide/indexers/index.md)  
  
-   [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [이벤트](../../../csharp/programming-guide/events/index.md)  
  
-   [대리자](../../../csharp/programming-guide/delegates/index.md)  
  
-   [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [인터페이스](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
## 예제  
 다음 예제에서는 클래스의 필드, 생성자 및 메서드 선언을 보여 줍니다.  또한 개체를 인스턴스화하는 것과 인스턴스 데이터를 출력하는 것을 보여 줍니다.  이 예제에서는 두 개의 클래스를 선언합니다. 첫째 클래스인 `Child` 클래스에는 두 개의 private 필드\(`name` 및 `age`\)와 두 개의 public 메서드가 있습니다.  두 번째 클래스인 `StringTest`는 `Main`을 포함하는 데 사용됩니다.  
  
 [!code-cs[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]  
  
## 설명  
 앞의 예제에서 private 필드\(`name` 및 `age`\)는 `Child` 클래스의 public 메서드를 통해서만 액세스할 수 있습니다.  예를 들어 다음과 같은 문을 사용하면 `Main` 메서드에서 자식의 이름을 출력할 수 없습니다.  
  
```  
Console.Write(child1.name);   // Error  
```  
  
 `Main`에서 `Child`의 private 멤버에 액세스하려면 `Main`이 이 클래스의 멤버여야 합니다.  
  
 액세스 한정자 기본값으로 사용 하지 않고 클래스 내에서 선언한 형식은 `private`,이 예제에서 데이터 멤버는 여전히 수 `private` 키워드 제거 되었으면 합니다.  
  
 또한 기본 생성자를 사용하여 생성한 개체\(`child3`\)의 age 필드는 기본적으로 0으로 초기화됩니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)