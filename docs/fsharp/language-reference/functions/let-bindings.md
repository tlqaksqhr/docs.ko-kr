---
title: let 바인딩(F#)
description: "F # 식별자 값 또는 함수를 연결 하는 바인딩 ' let'를 사용 하는 방법에 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: bcdf01747c2a1d0ba9a894188dae1d42acdf9104
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="let-bindings"></a>let 바인딩

A *바인딩* 식별자는 값 또는 함수를 연결 합니다. 사용 하면는 `let` 값 또는 함수에는 이름을 바인딩하는 키워드입니다.

## <a name="syntax"></a>구문

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>설명

`let` 키워드 또는 하나 이상의 이름에 대 한 함수 값을 정의 하는 바인딩 식에 사용 됩니다. 가장 간단한 형태는 `let` 식은 간단한 값에 다음과 같이 이름의 바인딩합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

새 줄을 사용 하 여 식에서 식별자를 구분 하면 각 줄에 다음 코드 처럼 식에 써야 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

단순한 이름 대신 이름을 포함 하는 패턴을 지정할 수 있습니다, 예를 들어, 튜플, 다음 코드에 나와 있는 것 처럼 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

*본문 식* 이름이 사용 되는 식입니다. 본문 식의 첫 번째 문자로 정확히 위로 줄 들여쓰기 자체 줄에 표시 되는 `let` 키워드:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

A `let` 바인딩은 될 수 있습니다는 클래스 형식의 정의에서 나 로컬 범위에서 모듈 수준 등에 함수 정의 합니다. A `let` 최상위에는 모듈 또는 클래스 형식에 바인딩 본문 식이 필요 하지는 않지만 다른 범위 수준에서 본문 식이 필요 합니다. 하지만 먼저에 없는 정의의 지점 이후에 바인딩된 이름은 사용할 수는 `let` 다음 코드 에서처럼 바인딩 나타납니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a>함수 바인딩이

다음 코드에 표시 된 함수 이름과 매개 변수를 함수 바인딩을 포함 하는 점을 제외 하 고 함수 바인딩이 값 바인딩에 대 한 규칙을 따릅니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

일반적으로 매개 변수는 튜플 패턴 같은 패턴.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

A `let` 마지막 식의 값으로 계산 바인딩 식입니다. 따라서 다음 코드 예제에서는 값에서에서 `result` 에서 계산 `100 * function3 (1, 2)`를 반환 하 `300`합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

자세한 내용은 [함수](index.md)를 참조하세요.

## <a name="type-annotations"></a>형식 주석

괄호 안에 포함 된 모든 형식 이름 뒤에 오는 콜론 (:)를 포함 하 여 매개 변수를 형식에 지정할 수 있습니다. 또한 마지막 매개 변수 뒤에 콜론과 형식을 추가 하 여 반환 값의 형식을 지정할 수 있습니다. 에 대 한 전체 형식 주석을 `function1`, 매개 변수 형식으로 정수를 사용할 때 다음과 같습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

명시적 형식 매개 변수가 없는 경우 형식 유추를 함수 매개 변수의 형식을 결정 사용 됩니다. 이 형식의 제네릭 매개 변수를 자동으로 일반화 포함할 수 있습니다.

자세한 내용은 참조 [자동 일반화](../generics/automatic-generalization.md) 및 [형식 유추](../type-inference.md)합니다.

## <a name="let-bindings-in-classes"></a>클래스의 let 바인딩

A `let` 바인딩 구조 또는 레코드 종류는 있지만 클래스 형식에 표시 될 수 있습니다. 클래스 형식에 바인딩 수를 사용 하려면 기본 생성자를 클래스에 있어야 합니다. 생성자 매개 변수는 클래스 정의에 형식 이름 뒤에 나타나야 합니다. A `let` 전용 필드 및 멤버 해당 클래스 형식에 대 한와 함께 클래스 형식에 바인딩 정의 `do` 형식에서 바인딩 유형에 대 한 기본 생성자에 대 한 코드를 형성 합니다. 다음 코드 예제에서는 클래스를 보여 줍니다 `MyClass` 전용 필드와 `field1` 및 `field2`합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

범위 `field1` 및 `field2` 선언 된 형식으로 제한 됩니다. 자세한 내용은 참조 [ `let` 클래스에서](../members/let-bindings-in-classes.md) 및 [클래스](../classes.md)합니다.

## <a name="type-parameters-in-let-bindings"></a>형식 매개 변수에 let 바인딩

A `let` 형식에서 또는 계산 식에서 모듈 수준에서 바인딩 명시적 형식 매개 변수를 사용할 수 있습니다. Let 함수 정의 내에서 같은 식에서 바인딩을 형식 매개 변수를 가질 수 없습니다. 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.

## <a name="attributes-on-let-bindings"></a>특성을 let 바인딩

특성은 최상위에 적용할 수 `let` 모듈에서는 다음 코드에 나와 있는 것 처럼 바인딩.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a>범위 및 액세스 가능성의 Let 바인딩

Let 바인딩을 사용 하 여 선언 엔터티의 범위를 포함 하는 영역 제한 됩니다 바인딩에 표시 된 후 범위 (예: 함수, 모듈, 파일 또는 클래스). 따라서이 방식이 적용 됩니다 let 바인딩 범위에는 이름을 새로 추가 합니다. 모듈에서는 let 바인딩 값 또는 함수의 모듈의 클라이언트에서 액세스할 수 한 모듈은 모듈의 let 바인딩 모듈의 공용 함수로 컴파일되는 때문에 액세스할 수 있습니다. 반면, 클래스의 let 바인딩은 private 클래스입니다.

일반적으로 모듈의 함수는 클라이언트 코드에서 사용 하는 경우 모듈의 이름으로 한정 되어야 합니다. 예를 들어 모듈 `Module1` 함수 `function1`, 사용자 지정 `Module1.function1` 에 함수를 참조 합니다.

사용자가 모듈의 모듈 이름으로 한정 되지 않고 해당 모듈 내에서 함수를 사용 하기 위해 사용할 수 있도록 하는 가져오기 선언을 사용할 수 있습니다. 위에서 언급 한 예에서 사용자가 모듈의 경우 열 수 모듈 가져오기 선언 열기를 사용 하 여 `Module1` 이후에 참조할 `function1` 직접 합니다.

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

일부 모듈 특성이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), 즉, 제공 하는 함수 모듈의 이름으로 한정 되어야 합니다. 예를 들어 F # List 모듈에는이 특성이 있습니다.

모듈 및 액세스 제어에 대 한 자세한 내용은 참조 하십시오. [모듈](../modules.md) 및 [액세스 제어](../access-control.md)합니다.

## <a name="see-also"></a>참고 항목

[함수](index.md)

[클래스의 `let` 바인딩](../members/let-bindings-in-classes.md)
