---
title: 패턴 일치(F#)
description: 'F #에서는 논리 구조를 사용 하 여 데이터를 비교, 데이터를 구성 부분으로 분해 하거나 데이터에서 정보를 추출할 패턴을 사용 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 31a5b321e5daecdc3add9a205d60b63b2c00ccd2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="pattern-matching"></a>패턴 일치

패턴은 입력된 데이터를 변환에 대 한 규칙입니다. 논리 구조 또는 구조를 사용 하 여 데이터를 비교 하 고, 데이터를 구성 부분으로 분해 또는 다양 한 방법으로 데이터에서 정보를 추출 하는 F # 언어에서 사용 됩니다.


## <a name="remarks"></a>설명
패턴와 같은 여러 가지 언어 구문에 사용 되는 `match` 식입니다. 함수에 대 한 인수를 처리 하는 경우 사용 하는 `let` 바인딩, 람다 식 및과 관련 된 예외 처리기에서는 `try...with` 식입니다. 자세한 내용은 참조 [일치 식](match-expressions.md), [let 바인딩](functions/let-bindings.md), [람다 식:는 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md), 및 [예외:는 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.

예를 들어는 `match` 식의 *패턴* 파이프 기호 뒤에 오는 합니다.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

각 패턴 특정 방식으로 입력 변환에 대 한 규칙으로 동작 합니다. 에 `match` 식에서는 각 패턴을를 차례로 입력된 데이터의 패턴와 호환 되는지 검사 합니다. 일치 하는 항목이 결과 식을 실행 됩니다. 일치 하는 항목이 없는 경우에 다음 패턴 규칙 테스트 됩니다. 선택적 when *조건* 부분에 대해서는 설명 [일치 식](match-expressions.md)합니다.

지원 되는 패턴은 다음 표에 표시 됩니다. 런타임 시 각 테이블에 나열 된 순서로 다음 패턴에 대해 테스트 되는 입력 및 패턴은 재귀적으로 적용된 먼저 마지막 코드에서와 왼쪽에서 오른쪽 패턴에 대 한 줄에 표시 된 대로 합니다.

|이름|설명|예제|
|----|-----------|-------|
|상수 패턴|모든 숫자, 문자 또는 문자열 리터럴, 열거형 상수, 또는 정의 된 리터럴 식별자|`1.0`, `"test"`, `30`, `Color.Red`|
|식별자 패턴|구별된 된 공용 구조체, 예외 레이블 또는 활성 패턴 케이스의 case 값|`Some(x)`<br /><br />`Failure(msg)`|
|가변 패턴|*identifier*|`a`|
|`as` 패턴|*패턴* 으로 *식별자*|`(a, b) as tuple1`|
|또는 패턴|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|및 패턴|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Cons 패턴|*식별자* :: *목록 id*|`h :: t`|
|목록 패턴|[ *pattern_1*;...; *pattern_n* ]|`[ a; b; c ]`|
|배열 패턴|[&#124; *pattern_1*;..; *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|괄호로 묶인 패턴|( *패턴* )|`( a )`|
|튜플 패턴|( *pattern_1*,..., *pattern_n* )|`( a, b )`|
|레코드 패턴|{ *identifier1* = *pattern_1*;...; *identifier_n* = *pattern_n* }|`{ Name = name; }`|
|와일드 카드 패턴|_|`_`|
|형식 주석 함께 패턴|*패턴* : *유형*|`a : int`|
|형식 테스트 패턴|:? *형식* [으로 *식별자* ]|`:? System.DateTime as dt`|
|Null 패턴|null|`null`|

## <a name="constant-patterns"></a>상수 패턴
상수 패턴은 숫자, 문자 및 문자열 리터럴, 열거형 상수 (열거형 형식 이름 포함). A `match` 상수 패턴만 식 다른 언어의 case 문과 비교할 수 있습니다. 입력은 리터럴 값 비교 하 고 패턴 일치의 값이 같으면 키를 누릅니다. 리터럴의 형식을 입력의 형식과 호환 되어야 합니다.

다음 예제에서는 리터럴 패턴의 사용법을 설명 하 고 또한 가변 패턴을 사용 하 여 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

리터럴 패턴의 또 다른 예로 열거 상수에 기반을 패턴입니다. 열거형 형식 이름 열거 상수를 사용 하는 경우 지정 해야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>식별자 패턴
유효한 식별자를 형성 하는 문자의 문자열 패턴을 사용 하는 경우 식별자의 형식 패턴은 일치 하는 방법을 결정 합니다. 식별자는 단일 문자 보다 긴 하 대문자로 시작 하는 경우 컴파일러는 식별자 패턴 일치 여부를 확인 하려고 합니다. 이 패턴에 대 한 식별자를 표시 된 리터럴 특성, 구별 된 공용 구조체 케이스, 예외 식별자 또는 활성 패턴 case 값 수 있습니다. 없는 일치 하는 식별자가 있으면 검색이 실패 하 고 패턴 규칙, 패턴은 변수를 입력으로 비교 됩니다.

구별 된 공용 구조체 패턴 간단한 명명 된 case 또는 수는 값 또는 여러 값이 포함 된 튜플이 있을 수 있습니다. 값 이면 값에 대 한 식별자를 지정 해야 합니다. 튜플의 튜플의 각 요소에 대 한 식별자 또는 하나에 필드 이름 포함 하는 식별자로 튜플 패턴을 제공 해야 합니다 또는 이상의 명명 된 공용 구조체 필드입니다. 예제를 보려면이 섹션의 코드 예제를 참조 하십시오.

`option` 이라는 두 case가 구별된 된 공용 구조체 형식이 `Some` 및 `None`합니다. 한 가지 경우 (`Some`)에 값을 있지만 다른 (`None`)는 명명 된 경우만 합니다. 따라서 `Some` 있어야 연관 된 값에 대 한 변수는 `Some` , 있지만 `None` 이 자동으로 표시 해야 합니다. 다음 코드에서는 변수 `var1` 를 비교 하 여 가져온 값이 지정 되는 `Some` 사례입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

다음 예제에서는 `PersonName` 구별 된 공용 구조체의 문자열 및 문자 이름을 나타내는 혼합 되어 포함 됩니다. 구별 된 공용 구조체의 경우는 `FirstOnly`, `LastOnly`, 및 `FirstLast`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

필드를 이라는 구별 된 공용 구조체, 등호 (=) 사용 하 여 명명된 된 필드의 값을 추출 합니다. 예를 들어 다음과 같은 선언으로 구분된 된 공용 구조체를 것이 좋습니다.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

패턴 일치 하는 식의 명명 된 필드를 다음과 같이 사용할 수 있습니다.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

지정된 된 필드의 사용은 선택 사항 이전 예에서 하므로 둘 다 `Circle(r)` 및 `Circle(radius = r)` 동일한 효과가 있습니다.

세미콜론 (;)를 사용 하 여 여러 필드를 지정 하면를 구분 합니다.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

활성 패턴을 사용 하 여 보다 복잡 한 사용자 지정 패턴 일치를 정의할 수 있습니다. 활성 패턴에 대 한 자세한 내용은 참조 [활성 패턴](active-patterns.md)합니다.

식별자가 예외가 있는 경우는 예외 처리기의 컨텍스트에서 일치 하는 패턴에 사용 됩니다. 예외 처리의 패턴 일치에 대 한 정보를 참조 하십시오. [예외:는 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.


## <a name="variable-patterns"></a>가변 패턴
가변 패턴은 다음의 오른쪽으로 실행 식에서 사용 하기 위해 사용할 수 있는 변수 이름에 일치 하는 값을 할당는 `->` 기호입니다. 가변 패턴 만으로도 모든 입력을 일치 하지만 따라서 튜플 및 배열 변수도 분해할 수를 같은 보다 복잡 한 구조를 사용 하도록 설정 하는 다른 패턴, 내 가변 패턴에 자주 나타납니다.

다음 예에서는 튜플 패턴 내 변수 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>패턴으로
`as` 패턴은 패턴을는 `as` 절을 추가 합니다. `as` 절의 실행 식에서 사용할 수 있는 이름에 일치 하는 값을 바인딩하는 `match` 식 또는에이 패턴은 사용 하는 경우에는 `let` 바인딩, 로컬 범위를 바인딩과 이름이 추가 됩니다.

다음 예제에서는 `as` 패턴입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>또는 패턴
OR 패턴에는 입력된 데이터는 여러 개의 패턴을 검색할 수 있으며 결과적으로 동일한 코드를 실행 하려는 경우 사용 됩니다. OR 패턴 양쪽의 형식이 호환 되어야 합니다.

다음 예제에서는 OR 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>및 패턴
AND 패턴 입력 두 개의 패턴 일치를 해야 합니다. AND 패턴 양쪽의 형식이 호환 되어야 합니다.

다음 예제와 비슷합니다 `detectZeroTuple` 에서처럼는 [튜플 패턴](https://msdn.microsoft.com/library/#tuple) 섹션의 뒷부분에 나오는이 항목에서는 하지만 여기서 `var1` 및 `var2` AND 패턴을 사용 하 여 가져온 값으로.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Cons 패턴
Cons 패턴은 첫 번째 요소로 분해 하는 데 사용 되는 *h e a d*, 나머지 요소를 포함 하는 목록과 *꼬리*합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>목록 패턴
목록 패턴을 사용 하면 목록을 수의 요소로 분해 합니다. 목록 패턴 자체에 특정 수의 요소를 목록만 일치할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>배열 패턴
배열 패턴 목록 패턴과 유사 하 고는 지정 된 길이의 배열을 분해 하는 데 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>괄호로 묶인 패턴
패턴을 원하는 대로 주위의 괄호를 그룹화 할 수 있습니다. 다음 예제에서는 AND 패턴 및 cons 패턴 간의 연관성을 제어 하는 괄호 사용 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>튜플 패턴
튜플 패턴 일치 형식의 입력 하 고 패턴 일치 튜플의 각 위치에 대 한 변수를 사용 하 여 구성 요소의으로 분해할 수에 튜플을 활성화 합니다.

다음 예에서는 튜플 패턴을 보여 주고 또한 리터럴 패턴, 가변 패턴 및 와일드 카드 패턴을 사용 하 여 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>레코드 패턴
레코드 패턴 필드의 값을 추출 하는 레코드를 분해 하기 위해 사용 됩니다. 패턴은 레코드;의 모든 필드를 참조할 필요가 없습니다. 생략 된 모든 필드는 방금 일치에 참여 하지 않는 및는 추출 되지 않습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>와일드 카드 패턴
와일드 카드 패턴 밑줄으로 표현 됩니다 (`_`) 및 문자 제외 하 고 대신 변수에 할당 하는 입력을 삭제 패턴은 변수 처럼 모든 입력을 일치 합니다. 와일드 카드 패턴은 대개 다른 패턴 내 자리 표시자로 오른쪽의 식에 필요 하지 않은 값에 대 한는 `->` 기호입니다. 와일드 카드 패턴은 자주도 일치 하지 않는 모든 입력과 일치 하도록 패턴 목록의 끝에 사용 됩니다. 이 항목의 많은 코드 예제에는 와일드 카드 패턴을 보여 줍니다. 앞의 코드에 대 한 예를 참조 하십시오.


## <a name="patterns-that-have-type-annotations"></a>형식 주석이 패턴
패턴 유형 주석이 있을 수 있습니다. 이러한 기타 형식 주석을 처럼 동작 및 기타 형식 주석 마찬가지로 유추 합니다. 패턴에 대 한 형식 주석 주위의 괄호는 필요 합니다. 다음 코드 형식 주석이 있는 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>형식 테스트 패턴
형식 테스트 패턴 유형에 대해 입력과 일치 하도록 사용 됩니다. 입력된 형식에 일치 하는 항목 (또는의 파생된 형식) 일치 하는 패턴에 지정 된 형식과 성공 합니다.

다음 예제에서는 형식 테스트 패턴을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Null 패턴
Null 패턴에는 null 값을 허용 하는 형식을 사용 하 여 작업할 때 나타날 수 있는 null 값과 일치 합니다. Null 패턴은.NET Framework 코드와 상호 작용할 때 자주 사용 됩니다. 예를 들어,.NET API의 반환 값에 대 한 입력 수 있습니다는 `match` 식입니다. 반환 값이 null 인지 그리고 반환된 된 값의 다른 특징에 따라 프로그램 흐름을 제어할 수 있습니다. 프로그램의 나머지 부분에 전달 될 null 값을 방지 하려면 null 패턴을 사용할 수 있습니다.

다음 예제에서는 null 패턴 및 가변 패턴을 사용합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>참고 항목
[일치 식](match-expressions.md)

[활성 패턴](active-patterns.md)

[F# 언어 참조](index.md)
