---
title: "class(C# 참조)"
ms.date: 07/18/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ae4b019ee88b6f331a76c750ab94fc76a3343adb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="class-c-reference"></a>class(C# 참조)

클래스는 다음 예제와 같이 `class` 키워드를 사용하여 선언됩니다.

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates 
    // and nested classes go here.
}
```

## <a name="remarks"></a>주의
C#에서는 단일 상속만 허용됩니다. 즉, 한 클래스는 하나의 기본 클래스에서만 구현을 상속할 수 있습니다. 그러나 한 클래스는 두 개 이상의 인터페이스를 구현할 수 있습니다. 다음 표에는 클래스 상속 및 인터페이스 구현에 대한 예제가 나와 있습니다.

|상속|예제|
|-----------------|-------------|
|없음|`class ClassA { }`|
|Single|`class DerivedClass: BaseClass { }`|
|없음. 두 개의 인터페이스 구현|`class ImplClass: IFace1, IFace2 { }`|
|단일. 하나의 인터페이스 구현|`class ImplDerivedClass: BaseClass, IFace1 { }`|

다른 클래스 내에 중첩되는 것이 아니라 네임스페이스 내에서 직접 선언되는 클래스는 [public](../../../csharp/language-reference/keywords/public.md) 또는 [internal](../../../csharp/language-reference/keywords/internal.md)일 수 있습니다. 기본적으로 클래스는 `internal`입니다.

중첩된 클래스를 포함 하 여 클래스 멤버 수 [공용](../../../csharp/language-reference/keywords/public.md), `protected internal`, [보호](../../../csharp/language-reference/keywords/protected.md), [내부](../../../csharp/language-reference/keywords/internal.md), [개인](../../../csharp/language-reference/keywords/private.md), 또는 `private protected`. 기본적으로 멤버는 [private](../../../csharp/language-reference/keywords/private.md)입니다.

자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.

형식 매개 변수가 포함된 제네릭 클래스를 선언할 수 있습니다. 자세한 내용은 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)를 참조하세요.

클래스에는 다음 멤버의 선언이 포함될 수 있습니다.

- [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [필드](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [인덱서](../../../csharp/programming-guide/indexers/index.md)

- [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [이벤트](../../../csharp/programming-guide/events/index.md)

- [대리자](../../../csharp/programming-guide/delegates/index.md)

- [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [인터페이스](../../../csharp/programming-guide/interfaces/index.md)

- [구조체](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a>예제
다음 예제에서는 클래스 필드, 생성자 및 메서드를 선언하는 방법을 보여 줍니다. 또한 개체 인스턴스화 및 인스턴스 데이터 출력을 보여 줍니다. 이 예제에서는 두 개의 클래스가 선언됩니다. 첫 번째 클래스인 `Child`는 private 필드 2개(`name` 및 `age`), public 생성자 2개, public 메서드 1개를 포함합니다. 두 번째 클래스인 `StringTest`는 `Main`을 포함하는 데 사용됩니다.

[!code-csharp[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]

## <a name="comments"></a>설명
이전 예제에서 private 필드(`name` 및 `age`)는 `Child` 클래스의 public 메서드를 통해서만 액세스할 수 있습니다. 예를 들어 다음과 같은 문을 사용하여 `Main` 메서드에서 자식의 이름을 출력할 수 없습니다.

```csharp
Console.Write(child1.name);   // Error
```

`Main`이 클래스의 멤버인 경우에만 `Main`에서 `Child`의 private 멤버에 액세스할 수 있습니다.

액세스 한정자 없이 클래스 내부에 선언된 형식은 기본적으로 `private`로 설정되므로 키워드가 제거된 경우 이 예제의 데이터 멤버는 `private`입니다.

마지막으로 기본 생성자(`child3`)를 사용하여 만들어진 개체의 경우 연령 필드는 기본적으로 0으로 초기화되었습니다.

## <a name="c-language-specification"></a>C# 언어 사양
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)
