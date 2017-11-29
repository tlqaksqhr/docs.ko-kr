---
title: "측정 단위(F#)"
description: "자세한 방법을 부동 소수점 및 F #의 부호 있는 정수 값은 측정 단위를, 길이, 볼륨 및 mass 나타내기 위해 일반적으로 사용 되는 연결 될 수 있습니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: cb2eb658-df6c-422e-afad-97422609c773
ms.openlocfilehash: 2d0683e864c5684a78c02e177c296d3067295723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="units-of-measure"></a>측정 단위

F #에서 부동 소수점 및 부호 있는 정수 값 일반적으로 대량, 길이, 볼륨을 나타내는 데 사용 되는 측정 단위가 연결 될 수 있습니다. 수량 단위를 사용 하 여 사용 하도록 설정 하면 컴파일러 권한이 있는지 확인 하려면 산술 관계 올바른 단위를 사용 하면 방지할 수 있는 프로그래밍 오류입니다.


## <a name="syntax"></a>구문

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>설명
위 구문 정의 *단위 이름* 으로 측정 단위입니다. 선택적 요소는 이전에 정의 된 단위를 기준으로 새 측정값을 정의 하는 데 사용 됩니다. 다음 줄에서는 측정값을 정의 하는 예를 들어 `cm` (센티미터).

```fsharp
[<Measure>] type cm
```

다음 줄에서는 측정값을 정의 `ml` (밀리 리터) 입방 센티미터도 (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

위 구문에서 *측정값* 은 단위와 관련 된 수식입니다. 단위와 관련 된 수식에 정수 거듭제곱에 (양수 및 음수) 지원 되는 경우 단위 사이의 공백을 나타내는 제품 두 명의 단위입니다. `*` 나타내기도 단위, 제품 및 `/` 단위의 몫을 나타냅니다. 역 단위에 대 한 음의 정수 power를 사용 하거나 또는 `/` 분자와 분모 단위 수식의 구분을 나타내는입니다. 분모에 여러 단위 괄호로 묶어야 합니다. 후 공백으로 분리 되어 단위는 `/` 의 일부는 분모 이지만 오는 모든 단위 것으로 해석 한 `*` 분자의 일부로 해석 됩니다.

분자와 같이 다른 단위와 함께 또는 단독으로 수량을 나타내거나 단위 식에 1을 사용할 수 있습니다. 으로 속도 대 한 단위를 작성 하는 예를 들어 `1/s`여기서 `s` 초를 의미 합니다. 괄호 단위 수식에 사용 되지 않습니다. 숫자 변환 상수 단위 수식;에 지정 하지 않으면 그러나 별도로 단위와 변환 상수를 정의 하 고 단위 검사 계산에서 사용할 수 있습니다.

해당 하는 다양 한 방법으로 동일한 것을 의미할 단위 수식은 작성할 수 있습니다. 따라서 컴파일러 단위 수식 음수 거듭제곱 단일 분자와 분모의 경우 평균은, 그룹 단위를 변환 하 고 분자와 분모에서 단위를 사전순으로 정렬 되는 일관 된 형식에 변환 합니다.

예를 들어 단위 수식 `kg m s^-2` 및 `m /s s * kg` 둘 다로 변환할지 `kg m/s^2`합니다.

부동 소수점 식을 측정 단위를 사용합니다. 측정값의 연결 된 단위와 함께 부동 소수점 숫자를 사용 하 여 다른 수준의 형식 안전성 더하고 약한 형식의 부동 소수점 숫자를 사용 하는 경우 수식에서 발생할 수 있는 단위 불일치 오류를 방지할 수 합니다. 부동을 작성 하는 경우 단위를 사용 하는 소수점 식을 식의 단위가 일치 해야 합니다.

다음 예제에 나와 있는 것 처럼 꺾쇠 괄호에 단위 수식 사용 하 여 리터럴 주석을 달 수 있습니다.

```fsharp
1.0<cm>
55.0<miles/hour>
```

꺾쇠 괄호; 수 사이 공백을 삽입 하지 마십시오 그러나와 같은 리터럴 접미사를 포함할 수는 `f`다음 예제와 같이, 합니다.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

해당 기본 형식에서 리터럴 형식을 변경 하는 그러한 주석을 (같은 `float`) 크기가 지정 된 형식으로와 같은 `float<cm>` 또는,이 경우 `float<miles/hour>`합니다. 단위 주석 `<1>` 하다 고 수량을 나타내거나 및 해당 형식이 단위 매개 변수 없이 기본 형식과 동일 합니다.

측정 단위는 부동 소수점 형식 또는 부호 있는 정수 계열 형식 대괄호로 표시 된 추가 단위 주석 함께 합니다. 따라서 작성 하는 경우에서 변환 형식을 `g` (그램)를 `kg` 다음과 같이 형식을 설명 (킬로그램).

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

측정 단위를 확인 하는 컴파일 시간 단위에 대해 사용 되지만 런타임 환경에서 유지 되지 않습니다. 따라서 성능을 적용 되지 않습니다.

측정 단위를 뿐 아니라 부동 소수점 형식; 모든 형식에 적용할 수 있습니다. 그러나만 부동 소수점 형식 정수 계열 형식 및 소수 형식 지원 차원이 구분 된 수량에 서명 합니다. 따라서 하면 이러한 기본 형식을 포함 하는 집계 및 기본 형식에서 측정 단위를 사용 하도록 합니다.

다음 예제에는 측정 단위를 사용 하 여를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
다음 코드 예제에는 값을 가지는 부동 소수점 숫자에서 크기가 지정 된 부동 소수점 값으로 변환 하는 방법을 보여 줍니다. 곱하기만 1.0에서 크기를 1.0에 적용 합니다. 와 같은 함수에이 추상화할 수 `degreesFahrenheit`합니다.

또한 부동 소수점 숫자 값을 가지는 함수에 크기가 지정 된 값을 전달할 때의 단위를 취소 하거나 해야 캐스팅 `float` 를 사용 하 여는 `float` 연산자입니다. 이 예제에서는로 나누면 `1.0<degC>` 에 대 한 인수에 대 한 `printf` 때문에 `printf` 차원이 수량을 예상 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

다음 예제에서는 세션에는이 코드에 입력과 출력에서 보여 줍니다.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>제네릭 단위를 사용 하 여
데이터에서 연결 된 단위에 대해 실행 되는 제네릭 함수를 작성할 수 있습니다. 이렇게 하면 제네릭 단위 삼아 형식을 형식 매개 변수로 지정 하 여 다음 코드 예제와 같이 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a>집합체 형식은 제네릭 단위를 사용 하 여 만들기
다음 코드에는 일반적인 단위가 포함 된 개별 부동 소수점 값으로 구성 된 집계 형식을 만드는 방법을 보여 줍니다. 이렇게 하면 다양 한 단위를 사용 하는 단일 형식을 만들 수 있습니다. 또한 제네릭 단위를 단위 집합이 하나를 가진 제네릭 형식을 같은 제네릭 형식 다른 집합의 단위는 다른 형식 인지 확인 하 여 형식 안전성을 유지 합니다. 이 기술의 기반은 하는 `Measure` 특성에 형식 매개 변수에 적용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a>런타임 시 단위
측정 단위는 정적 형식 확인에 사용 됩니다. 부동 소수점 값을 컴파일하면 측정 단위를 제거 실행 시 단위는 손실 됩니다. 따라서 실행 시의 단위를 확인 하는 중에 의존 하는 기능을 구현 하려고 수는 없습니다. 예를 들어, 구현 하는 `ToString` 단위를 출력 하는 함수 수는 없습니다.


## <a name="conversions"></a>변환
단위는 형식을 변환 하려면 (예를 들어 `float<'u>`) 단위 하지 않은 형식으로 표준 변환 함수를 사용할 수 있습니다. 사용할 수는 예를 들어 `float` 변환할는 `float` 하지 않은 단위, 다음 코드에 나와 있는 것 처럼 값입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

단위 없는 값 단위를가지고 있는 값으로 변환 하려면 해당 단위로 주석을 처리 하는 1 또는 1.0 값을 곱합니다 수 있습니다. 그러나 상호 운용성 계층을 쓰기 위해 있습니다 값 단위와 단위 값으로 변환 하는 데 사용할 수 있는 일부 explicit 함수. 이러한 데이터베이스는 [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) 모듈입니다. 예를 들어, 단위는 변환할 `float` 에 `float<cm>`를 사용 하 여 [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)다음 코드에 나온 것 처럼 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a>F # Power Pack의 측정 단위
단위 라이브러리에서 F # PowerPack ´ ù. 단위 라이브러리 SI 단위 및 실제 상수를 포함합니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
