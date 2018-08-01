---
title: readonly 키워드(C# 참조)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 96607f1dd7f019169446e29a08496fb54e1ed493
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961185"
---
# <a name="readonly-c-reference"></a>readonly(C# 참조)

`readonly` 키워드는 세 가지 컨텍스트에서 사용할 수 있는 한정자입니다.

- [필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다.
- [`readonly struct` 정의](#readonly-struct-example)에서 `readonly`는 `struct`가 불변임을 나타냅니다.
- [`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 해당 메서드가 참조를 반환하고 해당 참조에 쓰기를 허용하지 않음을 나타냅니다.

마지막 두 컨텍스트가 C# 7.2에 추가되었습니다.

## <a name="readonly-field-example"></a>읽기 전용 필드 예제  

이 예제에서는 클래스 생성자에서 값이 할당되지만, `year` 필드의 값을 `ChangeYear` 메서드에서 변경할 수 없습니다.  
  
[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]  
  
다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.  
  
- 변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.  

```csharp
public readonly int y = 5;  
```

- 인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.
- 정적 필드 선언을 포함하는 클래스의 정적 생성자.

이러한 생성자 컨텍스트는 또한 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효한 유일한 컨텍스트입니다.  
  
> [!NOTE]
> `readonly` 키워드와 [const](const.md) 키워드와 다릅니다. `const` 필드는 필드 선언에서만 초기화될 수 있습니다. `readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다. 따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다. 또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.  

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]  
  
위 예제에서 다음 예제와 같은 명령문을 사용하는 경우  
  
`p2.y = 66;        // Error`  
  
컴파일러 오류 메시지가 표시됩니다.  
  
`The left-hand side of an assignment must be an l-value`  
  
상수에 값을 할당하려고 할 때 표시되는 것과 같은 오류입니다.  

## <a name="readonly-struct-example"></a>읽기 전용 구조체 예제

`struct` 정의의 `readonly` 한정자는 구조체가 **불변**임을 선언합니다. 다음 예제와 같이 `struct`의 모든 인스턴스 필드를 `readonly`로 표시해야 합니다.

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]  

앞의 예제는 [읽기 전용 자동 속성](../../properties.md#read-only)을 사용하여 저장소를 선언합니다. 이는 컴파일러가 해당 속성의 `readonly` 백킹 필드를 만들도록 지시합니다. `readonly` 필드를 직접 선언할 수도 있습니다.

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

`readonly`로 표시되지 않은 필드를 추가하면 컴파일러 오류 `CS8340`: "읽기 전용 구조체의 인스턴스 필드는 읽기 전용이어야 합니다."가 발생합니다.

## <a name="ref-readonly-return-example"></a>참조 읽기 전용 반환 예

`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다. 다음 예제는 원점에 대한 참조를 반환합니다. 호출자가 원본을 수정할 수 없음을 나타내기 위해 `readonly` 한정자를 사용합니다.

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]  
반환된 유형은 `readonly struct`일 필요는 없습니다. `ref`에 의해 반환될 수 있는 모든 유형은 `ref readonly`에 의해 반환될 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
[C# 참조](../../../csharp/language-reference/index.md)  
[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
[C# 키워드](../../../csharp/language-reference/keywords/index.md)  
[한정자](../../../csharp/language-reference/keywords/modifiers.md)  
[const](../../../csharp/language-reference/keywords/const.md)  
[필드](../../../csharp/programming-guide/classes-and-structs/fields.md)
