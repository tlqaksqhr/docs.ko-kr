---
title: "자동 일반화(F#)"
description: "어떻게 F # 자동으로 일반화 하 여 인수 및 함수 유형 가능 하면 여러 종류를 사용에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a>자동 일반화

F # 형식 유추 유형 함수 및 식의 평가를 사용 합니다. 이 항목에서는 방법을 F # 자동으로 일반화 하 여 인수 및 함수 유형 가능한 경우 여러 유형으로 작업할 수 있도록 설명 합니다.


## <a name="automatic-generalization"></a>자동 일반화
F # 컴파일러는 함수에서 형식 유추를 수행 하는 경우에 지정된 된 매개 변수가 제네릭 수 있는지 여부를 결정 합니다. 컴파일러가 각 매개 변수를 검사 하 고 함수는 해당 매개 변수의 특정 형식을에 종속 여부를 결정 합니다. 그렇지 않은 경우 제네릭 형식을 유추 됩니다.

다음 코드 예제에서는 컴파일러가 제네릭인 것으로 유추 하는 함수를 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

형식 유추 됩니다 `'a -> 'a -> 'a`합니다.

형식을 알 수 없는 동일한 형식의 두 인수를 사용 하 고 동일한 형식의 값을 반환 하는 함수 임을 나타냅니다. 이전 함수 일 수 있는 원인 중 하나로 일반은 큼-연산자 보다 (`>`)는 그 자체가 제네릭입니다. 큼-서명이 연산자 보다 `'a -> 'a -> bool`합니다. 일부 연산자는 일반, 및 해당 매개 변수 형식을 함수에 코드에서 비 제네릭 함수 또는 연산자와 함께 매개 변수 형식에서 사용 하는 경우 일반화 될 수 없습니다.

때문에 `max` 은 일반, 사용할 수 있습니다 형식과 같은 `int`, `float`등의 다음 예제에 나와 있는 것 처럼, 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

그러나 두 개의 인수는 동일한 형식 이어야 합니다. 서명이 `'a -> 'a -> 'a`이 아니라 `'a -> 'b -> 'a`합니다. 따라서 다음 코드 형식이 일치 하지 않기 때문에 오류가 발생 합니다.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

`max` 함수를 지 원하는 더 큰 종류와도 작동-than 연산자입니다. 따라서 있습니다 사용할 수도 것 문자열에서 다음 코드에 나와 있는 것 처럼 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a>값 제한 사항
컴파일러는 간단한 변경할 수 없는 값 및 명시적 인수가 포함 하는 완전 한 함수 정의에 자동 일반화를 수행 합니다.

즉, 충분히를 특정 형식으로 제한 되지 않은 뿐만 아니라 하지 일반화할 코드를 컴파일하려고 하면 컴파일러 오류가 발생 하는 것을 의미 합니다. 이 문제에 대 한 오류 메시지 값 형식에 대 한 자동 일반화에이 제한 사항을 가리키는 *제한 값*합니다.

일반적으로 값 제한 오류는 컴파일러에 계정을 일반화 정보가 부족 하지만 제네릭이 아니어야 하는 구문 않으려는 경우 또는 실수로 제네릭이 아닌 구문에 충분 한 정보를 입력 하는 경우에 발생 합니다. 값 제한 오류를 해결 방법은 보다 완전 하 게 다음과 같은 방법 중 하나에서 형식 유추 문제를 제한 하려면 보다 명시적인 정보를 제공 하는입니다.


- 명시적인 형식 주석 값 또는 매개 변수를 추가 하 여 제네릭이 아닌 형식을 제한 합니다.

- 문제를 사용 하는 경우 함수 합성 또는 불완전 하 게 제네릭 함수 정의를 일반화할 수 없는 구문을 적용 된 변환된 함수 인수, 함수는 일반적인 함수 정의 다시 작성 하려고 합니다.

- 문제는 너무 복잡해 서 이미지를 일반화 하는 식, 함수에는 추가 하 고 사용 하지 않는 매개 변수를 추가 하 여 확인 합니다.

- 명시적 제네릭 형식 매개 변수를 추가 합니다. 이 옵션은 거의 사용 되었습니다.

- 다음 코드 예제에서는 이러한 각 시나리오를 보여 줍니다.

사례 1: 너무 복잡 한 식입니다. 이 예제에서는 목록 `counter` 하려면 `int option ref`, 간단한 변경할 수 없는 값으로 정의 되어 있지 않지만 합니다.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

사례 2: 일반화할 수 없는 구문을 사용 하 여 제네릭 함수를 정의 합니다. 이 예제에서는 구문이 인지 함수 인수를 부분 적용을 포함 하기 때문에 일반화할 수 없습니다.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

사례 3:는 추가 하 고 사용 하지 않는 매개 변수를 추가 합니다. 이 식은 일반화 수 있을 만큼 간단 없기 때문에 컴파일러 값 제한 오류를 발생 합니다.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

사례 4: 형식 매개 변수 추가 합니다.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

마지막 경우에서 값이 예를 들어 다음과 같이 서로 다른 여러 형식의 값을 만드는 데 사용할 수 있는 형식 함수가 됩니다.

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>참고 항목
[형식 유추](../type-inference.md)

[제네릭](index.md)

[정적으로 확인된 형식 매개 변수](statically-resolved-type-parameters.md)

[제약 조건](constraints.md)

