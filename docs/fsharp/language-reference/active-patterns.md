---
title: 활성 패턴(F#)
description: 'F # 프로그래밍 언어의 입력된 데이터를 분할 하는 명명 된 파티션을 정의 하려면 활성 패턴을 사용 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: b8c3270b1efbeb3495ac69bf1217fddf8a5a73e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="active-patterns"></a>활성 패턴

*활성 패턴* 사용 패턴 일치 구별된 된 공용 구조체에 대 한 것 처럼 식에에서 이러한 이름을 사용할 수 있도록 입력된 데이터를 분할 하는 명명 된 파티션을 정의할 수 있습니다. 활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.


## <a name="syntax"></a>구문

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>설명
위 구문에는 식별자가 나타내는 입력된 데이터의 파티션에 대 한 이름 *인수*, 또는 즉, 인수의 모든 값의 집합의 하위 집합에 대 한 이름입니다. 활성 패턴 정의에 최대 7 개의 파티션이 있을 수 있습니다. *식* 데이터를 분해 하는 폼을 설명 합니다. 명명 된 파티션을에 속해 주어진 값을 확인 하기 위한 규칙을 정의 하는 활성 패턴 정의 사용할 수 있습니다. (| 및 |) 기호 이라고 *바나나 클립* let 바인딩의이 형식에 의해 생성 함수를 호출 하 고는 *활성 인식기*합니다.

예를 들어, 다음과 같은 활성 패턴을 인수가 지정 된 것이 좋습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

다음 예제와 같이 식과 일치 하는 패턴에서 활성 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

이 프로그램의 출력은 다음과 같습니다.

```
7 is odd
11 is odd
32 is even
```

활성 패턴의 또 다른 용도 동일한 기본 데이터 다양 한 가능한 표현 하는 경우와 같은 여러 가지 방법으로 데이터 형식을 분해 하는 합니다. 예를 들어 한 `Color` 개체 RGB 표현 또는 HSB 표현으로 분해할 수 없습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

위의 프로그램의 출력은 다음과 같습니다.

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

와 함께에서 활성 패턴의 두 가지 파티션 수 있게 해만 적절 한 형태의 데이터를 분해 및 계산에 대 한 가장 편리 하 게 폼의 적절 한 데이터에 적절 한 계산을 수행 합니다.

결과 패턴 일치 하는 식을 사용 데이터를 읽을 수 있는 매우를 크게 간소화 잠재적으로 복잡 한 분기 및 코드 분석 데이터를 편리 하 게 방식에서 작성할 수 있습니다.


## <a name="partial-active-patterns"></a>부분 활성 패턴
경우에 따라 입력 공간의 일부만 분할 해야 할 수도 있습니다. 이 경우에는 일부 입력 사항이 일치 하지만 다른 입력과 일치 하지 않게 부분 패턴 집합을 작성 합니다. 값을 생성 하지 않을 수 있는 활성 패턴 이라고 *부분 활성 패턴*; 옵션 형식으로 반환 값을 갖습니다. 부분 활성 패턴을 정의 하려면 바나나 클립 내에서 패턴 목록의 끝에 와일드 카드 문자 (_)를 사용 합니다. 다음 코드 부분 활성 패턴 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

이전 예의 출력은 다음과 같습니다.

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

부분 활성 패턴을 사용 하는 경우 때로는 개별 선택 비연속 또는 수 상호 배타적인 있지만 될 필요는 없습니다. 다음 예제에서는 패턴 제곱와 큐브 패턴 높지 않습니다이 일부 숫자는 사각형인 64와 같은 큐브 때문에 있습니다. 다음 프로그램은 사각형인 큐브 1000000 최대 모든 정수 인쇄 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

출력은 다음과 같습니다.

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a>매개 변수가 있는 활성 패턴
활성 패턴은 항상 일치 여부를 확인할 항목에 대 한 하나 이상의 인수를 사용 하지만 경우에 이름에 인수를 추가로 소요 될 수 있습니다 *매개 변수가 있는 활성 패턴* 적용 됩니다. 추가 인수는 특수화 된 것으로 되는 일반적인 패턴을 허용 합니다. 문자열을 구문 분석 종종 정규식을 사용 하 여 활성 패턴 또한 부분 활성 패턴을 사용 하 여 다음 코드 처럼 추가 매개 변수로 정규식을 포함 하는 예를 들어 `Integer` 이전 코드 예제에 정의 되어 있습니다. 이 예제에서는 다양 한 날짜 형식에 대 한 정규식을 사용 하는 문자열 일반 ParseRegex 활성 패턴에 맞게 지정 됩니다. 정수 활성 패턴은 DateTime 생성자에 전달 될 수 있는 정수에 일치 하는 문자열을 변환 하는 데 사용 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

이전 코드의 출력은 다음과 같습니다.

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

활성 패턴 일치 하는 식을 패턴에 제한 되지 않습니다., let 바인딩에 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

이전 코드의 출력은 다음과 같습니다.

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[일치 식](match-expressions.md)

