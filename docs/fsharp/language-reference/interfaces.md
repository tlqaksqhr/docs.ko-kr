---
title: 인터페이스(F#)
description: 'F # 인터페이스에서 다른 클래스에서 구현 하는 관련된 멤버의 집합을 지정 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 54ae8a2840ce26814be25f08c3ed02e12df6b7c0
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="interfaces"></a>인터페이스

*인터페이스* 다른 클래스에서 구현 하는 관련된 멤버의 집합을 지정 합니다.

## <a name="syntax"></a>구문

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>설명
인터페이스 선언 없는 멤버가 구현 된 점을 제외 하 고 클래스 선언 유사 합니다. 대신, 모든 멤버는 키워드로 표시 된 대로 추상적 `abstract`합니다. 추상 메서드에 대 한 메서드 본문을 제공 하지 않습니다. 와 함께 방법으로 멤버의 별도 정의 포함 하 여 기본 구현을 제공할 수 있습니다는 `default` 키워드입니다. 이렇게 다른.NET 언어에서 기본 클래스의 가상 메서드를 작성 하는 것과 결과가 같습니다. 클래스에서 인터페이스를 구현 하는 가상 메서드를 재정의할 수 있습니다.

인터페이스에 대 한 기본 액세스 가능성은 `public`합니다.

필요에 따라 일반 F # 구문을 사용 하 여 이름을 각 메서드 매개 변수를 지정할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

위의 `ISprintable` 예제에서는 `Print` 메서드에 형식의 단일 매개 변수는 `string` 이름의 `format`합니다.

인터페이스를 구현 하는 방법은 두 가지가: 개체 식을 사용 하 고 클래스 형식을 사용 합니다. 두 경우 모두 클래스 형식이 나 개체 식은 인터페이스의 추상 메서드에 대 한 메서드 본문을 제공합니다. 구현 된 인터페이스를 구현 하는 각 형식에 적용 됩니다. 따라서 서로 다른 형식에 대 한 인터페이스 메서드를 서로 다를 수 있습니다.

키워드 `interface` 및 `end`, 시작 및 끝의 정의 표시 하는 간단한 구문을 사용 하는 경우 선택 사항입니다. 이러한 키워드를 사용 하지 않으면 컴파일러는 형식이 인지는 클래스 또는 인터페이스 사용 하는 구문 분석 하 여 유추 하려고 합니다. 멤버를 정의 하거나 다른 클래스 구문을 사용 하 여 형식은 클래스로 해석 됩니다.

대문자로 모든 인터페이스를 시작 하는 코딩 스타일.NET `I`합니다.


## <a name="implementing-interfaces-by-using-class-types"></a>클래스 형식을 사용 하 여 인터페이스를 구현 합니다.
클래스 형식에 사용 하 여 하나 이상의 인터페이스를 구현할 수는 `interface` 인터페이스의 이름, 키워드 및 `with` 키워드, 다음 코드에 표시 된 인터페이스 멤버 정의 다음 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

인터페이스 구현은 상속 되므로 모든 파생된 클래스에서는를 구현할 필요가 없습니다.


## <a name="calling-interface-methods"></a>인터페이스 메서드 호출
인터페이스를 구현 하는 형식의 모든 개체를 통해서가 아니라 인터페이스를 통해서만 인터페이스 메서드를 호출할 수 있습니다. 따라서 해야할 인터페이스 형식으로 업캐스팅을 사용 하 여는 `:>` 연산자 또는 `upcast` 이러한 메서드를 호출 하기 위해 연산자.

메서드를 호출 하는 인터페이스 형식의 개체가 있으면 `SomeClass`, 다음 코드에 나와 있는 것 처럼 개체를 인터페이스 형식으로 업캐스팅을 수행 해야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

대신 해당 업캐스팅 개체에서 메서드를 선언 하는 것 하 고 다음 예제와 같이 인터페이스 메서드를 호출 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>개체 식을 사용 하 여 인터페이스를 구현 합니다.
개체 식에는 인터페이스를 구현 하는 간단한 방법을 제공 합니다. 명명된 된 형식, 만들 필요가 없습니다 하 고 방금 추가 메서드 없이 인터페이스 메서드를 원하는 개체를 원하는 경우 유용 합니다. 다음 코드는 개체 식은 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>인터페이스 상속
인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[개체 식](object-expressions.md)

[클래스](classes.md)
