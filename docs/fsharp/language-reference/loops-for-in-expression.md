---
title: '루프: for...in 식(F#)'
description: '참조 방식을 F # >for.. 식에 구문 반복 하는 데 열거 가능한 컬렉션 패턴 일치 하는 항목을 반복 합니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 926f0a9940021b3dc0deefc12ea158c35975e949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564076"
---
# <a name="loops-forin-expression"></a>루프: for...in 식

이 루프 구문은 열거 가능한 컬렉션 범위 식, 시퀀스, 목록, 배열 또는 열거형을 지 원하는 다른 생성자와 같은 패턴 일치 하는 항목을 반복 하는 데 사용 됩니다.


## <a name="syntax"></a>구문

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>설명
`for...in` 식과 비교할 수는 `for each` 다른.NET 언어의 문과 하는 값 열거 가능한 컬렉션을 반복 하는 데 사용 됩니다. 그러나 `for...in` 패턴 전체 컬렉션 단순히 반복 하는 대신 컬렉션에 대해 일치도 지원 합니다.

열거 가능한 컬렉션 또는 사용 하 여 열거 가능한 식을 지정할 수는 `..` 정수 계열 형식에 대 한 범위로 연산자. 열거 가능한 컬렉션 목록, 시퀀스, 배열, 집합, 지도, 및에 포함 됩니다. 구현 하는 형식 `System.Collections.IEnumerable` 사용할 수 있습니다.

사용 하 여 범위를 표현할는 `..` 연산자는 다음 구문을 사용할 수 있습니다.

*시작* ... *마침*

라는 증분을 포함 하는 버전을 사용할 수도 있습니다는 *건너뛸*, 다음 코드 에서처럼에서 합니다.

*시작* ... *건너뛸* ... *마침*

일반적인 동작은 카운터 변수 반복 될 때마다 1 씩 증가 하는 패턴으로 정수 범위와 단순 카운터 변수를 사용 하면 하지만 범위는 skip 값을 포함 하는 경우 카운터는 증가 된 건너뛰기 값으로 대신.

패턴에 일치 하는 값을 본문 식에 사용할 수도 있습니다.

다음 코드 예제는 사용법을 보여 줍니다.는 `for...in` 식입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

출력은 다음과 같습니다.

```
1
5
100
450
788
```

다음 예제에는 시퀀스에 대해 반복 하는 방법과 단순 변수 대신 튜플 패턴을 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

출력은 다음과 같습니다.

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

다음 예제에서는 단순한 정수 범위를 반복 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

Function1의 출력은 다음과 같습니다.

```
1 2 3 4 5 6 7 8 9 10
```

다음 예제에서는 범위에 있는 다른 모든 요소를 포함 하는 2, 건너뛰기로 범위를 반복 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

출력 `function2` 는 다음과 같습니다.

```
1 3 5 7 9
```

다음 예제에서는 문자 범위를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

출력 `function3` 는 다음과 같습니다.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

다음 예제에는 역방향 반복에 대 한 음수 건너뛰기 값을 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

출력 `function4` 는 다음과 같습니다.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

시작과 범위의 끝에 다음 코드 에서처럼 함수 등의 식을 수도 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

출력 `function5` 이 입력으로는 다음과 같습니다.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

다음 예제에서는 루프에서 요소가 필요 하지 않은 경우 와일드 카드 문자 (_) 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

출력은 다음과 같습니다.

```
Number of elements in list1: 5
```

`Note` 사용할 수 있습니다 `for...in` 시퀀스 식 및 다른 계산 식, 사용자 지정된 된 버전의 경우는 `for...in` 식이 사용 됩니다. 자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[루프: `for...to` 식](loops-for-to-expression.md)

[루프: `while...do` 식](loops-while-do-expression.md)
