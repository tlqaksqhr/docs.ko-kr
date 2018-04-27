---
title: '일치 식 (F #)'
description: 'F # 일치 식 패턴의 집합 식의 비교를 기반으로 하는 분기를 제어를 제공 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 04/19/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f843e6fde98eae8a10235dd5cae38ffc10a4fb9f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="match-expressions"></a>일치 식

`match` 식은 일련의 패턴으로 식의 비교를 기반으로 하는 분기를 제어를 제공 합니다.

## <a name="syntax"></a>구문

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>설명

일련의 패턴으로 테스트 식의 비교를 기반으로 복잡 한 분기에 대 한 패턴 일치 하는 식을 허용 합니다. 에 `match` 식은 *테스트 식* 차례로 일치 하는 항목이 발견 되 면 해당 각 패턴와 비교 됩니다 *결과 식* 평가 결과 값이 고 일치 식의 값으로 반환 합니다.

패턴 일치 위 구문에서 표시 된 함수에는 패턴 일치는 즉시 인수에 람다 식입니다. 패턴 일치 위 구문에서 표시 된 함수는 다음과 같습니다.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

람다 식에 대 한 자세한 내용은 참조 [람다 식:는 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md)합니다.

패턴의 전체 집합 입력 변수의 가능한 모든 일치 항목을 포함 해야 합니다. 와일드 카드 패턴을 사용 하는 자주 (`_`) 이전에 일치 하지 않는 입력된 값에 맞게 마지막 패턴으로 합니다.

다음 코드에서는 있는 방법 중 일부는 `match` 식이 사용 됩니다. 대 한 참조 및 사용할 수 있는 모든 패턴의 예제를 참조 하세요. [패턴 일치](pattern-matching.md)합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>패턴 가드

사용할 수 있습니다는 `when` 절 변수 패턴과 일치 하도록 만족 해야 하는 추가 조건을 지정할 수 있습니다. 이러한 절의 라고는 *가드*합니다. 식은 다음의 `when` 해당 가드와 관련 된 패턴에 일치 하는 항목이 있어야만 키워드는 평가 되지 않습니다.

다음 예제에서는 변수 패턴에 대 한 숫자 범위를 지정 하는 가드의 사용을 보여 줍니다. 참고 여러 조건은 부울 연산자를 사용 하 여 결합 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

패턴의 리터럴 이외의 값을 사용할 수 없으므로, 있습니다를 사용 해야는 `when` 절 값에 대해 입력의 일부 비교 해야 하는 경우. 이 다음 코드에 나와 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

공용 구조체 패턴을 가드에서 검사 하는 가드를 적용 **모든** 의 마지막 하나 뿐 아니라 패턴입니다. 예를 들어 다음 코드에서는 가드 `when a > 12` 모두에 적용 되지만 `A a` 및 `B a`:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>참고자료

[F# 언어 참조](index.md)  
[활성 패턴](active-patterns.md)  
[패턴 일치](pattern-matching.md)  
