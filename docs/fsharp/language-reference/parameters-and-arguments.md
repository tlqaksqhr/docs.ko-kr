---
title: 매개 변수 및 인수(F#)
description: 'F # 언어 지원과 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하기 위한 방법을 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566222"
---
# <a name="parameters-and-arguments"></a>매개 변수 및 인수

이 항목에서는 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수 전달에 대 한 언어 지원에 설명 합니다. 참조로 전달 하는 방법 및 정의 하 고 가변 개수의 인수를 사용할 수 있는 메서드를 사용 하는 방법에 대 한 정보가 포함 됩니다.


## <a name="parameters-and-arguments"></a>매개 변수 및 인수
용어 *매개 변수* 제공 해야 하는 값의 이름을 설명 하는 데 사용 됩니다. 용어 *인수* 각 매개 변수에 대해 제공 된 값에 사용 됩니다.

튜플 또는 변환된 형식으로 또는 둘 중 일부 조합 매개 변수를 지정할 수 있습니다. 명시적 매개 변수 이름을 사용 하 여 인수를 전달할 수 있습니다. 메서드의 매개 변수 수 선택적으로 지정 되며 기본 값이 지정 되었습니다.


## <a name="parameter-patterns"></a>매개 변수 패턴
함수 및 메서드를 제공 된 매개 변수가 일반적으로 공백으로 구분 되는 패턴입니다. 즉, 즉, 원칙적으로 된 패턴에 설명 된 [일치 식](match-expressions.md) 함수 또는 멤버에 대 한 매개 변수 목록에서 사용할 수 있습니다.

메서드는 일반적으로 인수 전달의 튜플 형식을 사용합니다. 튜플 형식 인수는.NET 메서드에 전달 하는 방식과 일치 하기 때문에 다른.NET 언어의 관점에서 더 명확한 결과 얻을 수 있습니다.

사용 하 여 만든 함수 가장 자주 사용 되는 커리 된 형태의 `let` 바인딩.

다음 의사 코드 튜플 및 커리 된 인수가 예를 보여 줍니다.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

일부 인수 튜플을 있고 일부 없는 결합 된 형식을 사용할 수 있습니다.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

다른 패턴 매개 변수 목록에도 사용할 수 있습니다 하지만 매개 변수 패턴 가능한 모든 입력이 일치 하지 않습니다 있을 수 있습니다 불완전 한 일치 하는 런타임 시. 예외 `MatchFailureException` 인수 값 매개 변수 목록에 지정 된 패턴과 일치 하지 않을 때 생성 됩니다. 불완전 한 일치 항목에 대 한 매개 변수 패턴을 허용 하는 경우 컴파일러는 경고가 발생 합니다. 다른 하나 이상 패턴은 일반적으로 매개 변수 목록에 대 한 유용 있고 와일드 카드 패턴입니다. 제공 된 인수를 무시 하려면 단순히 매개 변수 목록에 와일드 카드 패턴을 사용 합니다. 다음 코드를 인수 목록에는 와일드 카드 패턴의 사용을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

와일드 카드 패턴은 일반적으로 다음 코드 에서처럼 문자열 배열로 제공 되는 명령줄 인수에 관심이 없는 경우 전달 된 인수를 불필요 때마다 유용 하 고 프로그램에 기본 요소와 같이 해당 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

인수에 자주 사용 되는 다른 패턴은 `as` 패턴과 관련 된 구별 된 공용 구조체 및 활성 패턴 식별자 패턴입니다. 다음과 같이 단일 대/소문자 구별 된 공용 구조체 패턴을 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

출력은 다음과 같습니다.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

인수는 다음 예제 에서처럼를 원하는 형식으로 변형 하는 경우 활성 패턴은 예를 들어 매개 변수로 유용할 수 있습니다.

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

사용할 수는 `as` 다음 코드 줄에 표시 된 대로 로컬 값으로 일치 하는 값을 저장 하는 패턴입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

다른 가끔씩 사용 되는 방법은 마지막 인수는 함수 본문으로 제공 하 여 명명 되지 않은 상태로 유지 하는 함수, 즉시 암시적 인수에 대해 패턴 일치를 수행 하는 람다 식입니다. 이 예제는 코드의 다음 줄입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

이 코드에서는 제네릭 목록을 사용 하 고 반환 하는 함수를 정의 `true` 목록이 비어 있으면 및 `false` 그렇지 않은 경우. 이와 같은 기술을 사용 하 여 사용 코드를 읽을 더 어렵게 만들 수 있습니다.

경우에 따라서는 불완전 한 일치 항목을 포함 하는 패턴은 유용를 예를 들어 프로그램의 목록에 세 개의 요소만 있는 있는지 알고 있는 경우 수 사용 다음과 같은 패턴 매개 변수 목록에서.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

불완전 한 일치 하는 패턴을 사용 하 여 빠른 프로토타입 및 임시 다른 사용에 가장 잘 예약 되어 있습니다. 컴파일러에서 해당 코드에 대 한 경고를 발생 합니다. 이러한 패턴은 일반적인 경우의 가능한 모든 입력을 처리할 수 없으므로 및 Api 구성 요소에 대해 적합 하지 않습니다.

## <a name="named-arguments"></a>명명된 인수
메서드에 대 한 인수는 쉼표로 구분 된 인수 목록에서 위치에 따라 지정할 수 있습니다 또는 전달할 수도 있습니다는 메서드를 명시적으로 뒤에 등호와 값에 전달 되도록 하는 이름을 제공 하 여 합니다. 이름을 제공 하 여 지정 하는 경우에 선언에 사용 되는 다른 순서로 나타날 수 있습니다.

명명 된 인수에 수행할 수 코드 더 쉽게 읽을 수 및 보다 융통성 있는 특정 형식의 메서드 매개 변수 다시 정렬 등의 API의 변경 내용.

명명 된 인수를 사용할 수 방법에 대해서만 아니라 `let`-바인딩된 함수, 함수 값 또는 람다 식입니다.

다음 코드 예제에서는 명명 된 인수를 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

클래스 생성자에 대 한 호출에서 명명 된 인수에서와 유사한 구문을 사용 하 여 클래스의 속성 값을 설정할 수 있습니다. 다음 예제에서는이 구문을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

자세한 내용은 참조 [생성자 (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)합니다.

## <a name="optional-parameters"></a>선택적 매개 변수
매개 변수 이름 앞에 매개 변수를 사용 하 여는 방법에 대 한 선택적 매개 변수를 지정할 수 있습니다. 선택적 매개 변수를 사용 하 여 옵션 종류를 쿼리 하는 일반적인 방법에서 쿼리할 수 있습니다는 F # 옵션 형식으로 해석 되므로 `match` 식 `Some` 및 `None`합니다. 선택적 매개 변수를 사용 하 여 만든 함수에 없는 멤버에 대해서만 허용 됩니다 `let` 바인딩.

함수를 사용할 수도 `defaultArg`, 선택적 인수는 기본 값을 설정 하는 합니다. `defaultArg` 함수는 첫 번째 인수는 선택적 매개 변수 및 기본값을 두 번째 인수로 사용 합니다.

다음 예에서는 선택적 매개 변수 사용을 예를 보여줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

출력은 다음과 같습니다.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>참조로 전달
F #에서는 `byref` 키워드는 매개 변수 참조로 전달 되도록 지정 합니다. 즉, 모든 값을 변경 하는 함수를 실행 한 후 유지 됩니다. 에 제공 된 값을 `byref` 매개 변수를 변경할 수 있어야 합니다. 또는 적절 한 형식의 참조 셀을 전달할 수 있습니다.

함수에서 둘 이상의 값을 반환 하는 방법으로 발전 하 고.NET 언어에서는 참조로 전달 합니다. F #에서이 위해 튜플을 반환 수도 있고 변경 가능한 참조 셀을 매개 변수로 사용할 수 있습니다. `byref` .NET 라이브러리와의 상호 운용성에 대 한 매개 변수는 주로 합니다.

다음 예에서는 사용을 보여 주기는 `byref` 키워드입니다. 매개 변수로 참조 셀을 사용 하는 경우 있습니다 해야 명명된 된 값으로 참조 셀을 만들 및 매개 변수로 사용 하는, 뿐 아니라 추가 `ref` 연산자에 대 한 첫 번째 호출에서와 같이 `Increment` 다음 코드에 있습니다. 참조 셀을 만드는 기본 값의 복사본을 만들기 때문에 첫 번째 호출에만 임시 값을 증가 시킵니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

저장을 튜플을 반환 값으로 사용할 수 있습니다 `out` .NET 라이브러리 메서드의 매개 변수입니다. 처리할 수 있습니다는 `out` 로 매개 변수는 `byref` 매개 변수입니다. 다음 코드 예제에서는 두 가지 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>매개 변수 배열
임의 개수의 유형이 다른 형식의 매개 변수를 사용 하는 함수를 정의 해야 하는 경우도 있습니다. 사용할 수 있는 모든 형식에 대 한 설명 하기 위해 가능한 모든 오버 로드 된 메서드를 만드는 유용한 됩니다. 매개 변수 배열 기능을 통해 이러한 메서드에 대 한 지원을 제공 하는.NET 구현 합니다. 시그니처에 매개 변수 배열을 사용 하는 메서드는 임의 개수의 매개 변수를 제공할 수 있습니다. 매개 변수를 배열에 배치 됩니다. 배열 요소의 형식에는 함수에 전달 될 수 있는 매개 변수 형식이 결정 합니다. 매개 변수 배열을 정의 하는 경우 `System.Object` 요소 유형으로 다음 클라이언트 코드 전달할 수 형식의 값입니다.

매개 변수 배열 F #에서 메서드에서만에서 정의할 수만 있습니다. 독립 실행형 함수나 모듈에 정의 된 함수를 사용할 수 없습니다.

매개 변수 배열을 사용 하 여 정의 된 `ParamArray` 특성입니다. `ParamArray` 특성은 마지막 매개 변수에 적용할 수 있습니다.

다음 코드에 나와 있는 매개 변수 배열을 사용 하는 메서드가 있는 F #에 매개 변수 배열 및 형식 정의 사용 하는.NET 메서드를 호출 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

프로젝트를 실행 하는 경우 앞의 코드 출력은 다음과 같습니다.

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>참고 항목
[멤버](members/index.md)
