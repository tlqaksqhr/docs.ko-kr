---
title: "함수를 고급 값으로 상승(F#)"
description: "함수는 F # 프로그래밍 언어에 대 한 고급 상태로 승격 되는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6b76b93b-a141-40f4-976c-7f0c558d6d09
ms.openlocfilehash: bca0e09edbe0aa86f0db746282acd4f4b3237a03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="functions-as-first-class-values"></a>함수를 고급 값으로 상승

함수형 프로그래밍 언어의 특징은 함수를 고급 상태 상승입니다. 모든 다른 기본 제공 형식의 값을 사용 하 여 수행할 수 있고 상대적으로 적은 노력 이렇게 할 수는 함수를 사용 하 여 수행할 수 있습니다.

일반적인 측정값 고급 상태는 다음과 같습니다.

- 식별자에 함수를 바인딩할 수 있습니까? 즉, 사용자 이름을 지정할 수에?

- 저장할 수의 데이터 구조를 함수과 같은 목록에서?

- 함수는 함수 호출에서 인수로 전달할 수 있습니까?

- 함수 호출에서 함수를 반환할 수 있습니까?

마지막 두 개의 측정값 정의 일명 *고차 연산* 또는 *고차 함수*합니다. 고차 함수는 함수를 인수로 받아들이고 함수 호출 값으로 함수를 반환 합니다. 이러한 작업에는 매핑 함수 및 함수 컴퍼지션으로 함수형 프로그래밍의 핵심적 지원 합니다.


## <a name="give-the-value-a-name"></a>값에 이름을 지정합니다

함수는 첫 번째 클래스 값 이면 있습니다 수 있어야 이름을 것 처럼 정수, 문자열 및 다른 기본 제공 형식 이름을 지정할 수 있습니다. 이 식별자 값에 바인딩할으로 함수형 프로그래밍 연구에서 참조 됩니다. 사용 하 여 F # [ `let` 바인딩](../language-reference/functions/let-bindings.md) 이름 값에 바인딩할: `let <identifier> = <value>`합니다. 다음 코드는 두 가지 예를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

쉽게 함수를 이름을 지정할 수 있습니다. 다음 예제에서는 라는 함수를 정의 `squareIt` 식별자를 바인딩하여 `squareIt` 에 [람다 식을](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`합니다. 함수 `squareIt` 하나의 매개 변수가 `n`, 해당 매개 변수에 대 한 제곱을 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

F #는 다음과 같은 장점이 더 간결한 구문을 입력으로 동일한 결과 얻을 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

첫 번째 스타일을 사용 하 여이 예제에서는 주로 `let <function-name> = <lambda-expression>`, 함수 선언과 다른 유형의 값 사이의 유사성을 강조 하기. 그러나 모든 명명 된 함수 간결한 구문을 사용 하 여 작성할 수도 있습니다. 일부 예제는 두 가지 방식으로 작성 됩니다.


## <a name="store-the-value-in-a-data-structure"></a>데이터 구조에서 값을 저장 합니다.

데이터 구조에는 첫 번째 클래스 값을 저장할 수 있습니다. 다음 코드는 목록 및 튜플 값을 저장 하는 예제를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

함수에 튜플을 저장 된 함수 이름이 계산 실제로 않습니다를 확인 하려면 다음 예제에서는 `fst` 및 `snd` 튜플 로부터 첫 번째 및 두 번째 요소를 추출 하는 연산자 `funAndArgTuple`합니다. 튜플의 첫 번째 요소는 `squareIt` 두 번째 요소는 `num`합니다. 식별자 `num` 정수, 10에 대 한 유효한 인수에는 앞의 예에서 바인딩되는 `squareIt` 함수입니다. 두 번째 식은 튜플의 첫 번째 요소 튜플의 두 번째 요소에 적용: `squareIt num`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

마찬가지로, 식별자로 `num` 정수 10 일 수 있습니다 및 식별자를 수 있으므로 서로 교대로 사용 `squareIt` 람다 식과 `fun n -> n * n`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a>값을 인수로 전달 합니다.

값에 있는 경우 고급 상태는 언어에서를 함수에 인수로 전달할 수 있습니다. 예를 들어 일반적으로 정수 및 문자열 인수로 전달 됩니다. 다음 코드에서는 정수 및 F #에 인수로 전달 된 문자열을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

함수의 첫 번째 클래스 상태가 있으면 같은 방식으로 인수로 전달할 수 있어야 합니다. 고차 함수의 첫 번째 특성 임을 기억 합니다.

다음 예제에서에서 함수 `applyIt` 2 개의 매개 변수가 `op` 및 `arg`합니다. 에 대 한 1 개의 매개 변수가 있는 함수에서 보낼 `op` 및 적절 한 인수를 함수에 대 한 `arg`, 함수를 적용 한 결과 반환 `op` 를 `arg`합니다. 다음 예제에서는 함수 인수 및 정수 인수를 모두는 동일한 방식으로 전송 됩니다는 이름을 사용 하 여.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

다른 함수에 대 한 인수로 함수를 보낼 수 있는 기능에는 일반적인 추상화 맵 또는 필터 작업과 같은 함수형 프로그래밍 언어에서의 기초가 합니다. 예를 들어 맵 작업 목록을 단계별로 각 요소에 작업을 수행 하 고 다음 결과의 목록을 반환 하는 함수에서 공유 하는 계산을 캡처하는 고차 함수를입니다. 정수, 목록의 각 요소를 늘리거나 각 요소를 제곱 또는 문자열의 목록에서 각 요소를 대문자로 변경 할 수 있습니다. 계산의 오류가 발생 하기 쉬운 부분은 재귀 프로세스를 단계별로 실행 목록 및 반환 하도록 결과 목록을 작성 합니다. 해당 파트는 매핑 함수에 캡처됩니다. 특정 응용 프로그램에 대 한 작성 해야 할 모든는 개별적으로 목록의 각 요소에 적용 하려는 되는 함수 (추가, 제곱 대/소문자 변경). 함수를 보내 인수로 하도록 매핑 함수 처럼 `squareIt` 보내집니다 `applyIt` 이전 예에서 합니다.

F # 같은 대부분의 컬렉션 형식에 대 한 지도 메서드를 제공 합니다. [나열](../language-reference/lists.md), [배열](../language-reference/arrays.md), 및 [시퀀스](../language-reference/sequences.md)합니다. 다음 예에서는 목록을 사용합니다. 구문은 `List.map <the function> <the list>`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

자세한 내용은 참조 [나열](../language-reference/lists.md)합니다.

## <a name="return-the-value-from-a-function-call"></a>함수 호출에서 값을 반환 합니다.

마지막으로, 함수 언어의 고급 상태 있으면 있어야 함수 호출의 값으로 반환 하려면 정수 및 문자열과 같은 다른 형식을 반환 하는 것 처럼 합니다.

다음 함수 호출에서는 정수를 반환 하 고 주석이 표시.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

다음 함수 호출은 문자열을 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

를 인라인으로 선언한 다음 함수 호출에는 부울 값을 반환 합니다. 표시 되는 값은 `True`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

함수 호출의 값으로 함수를 반환 하는 기능이 더 높은 순서 함수의 두 번째 특성입니다. 다음 예에서 `checkFor` 하나의 인수를 사용 하는 함수 정의 됩니다. `item`, 해당 값으로 새 함수를 반환 합니다. 반환 된 함수에서는 인수로 목록과 `lst`, 검색 및 `item` 에서 `lst`합니다. 경우 `item` 가 있으면 반환 하 고 `true`합니다. 경우 `item` 없으면, 함수 반환 `false`합니다. 이전 단원에서와 마찬가지로 다음 코드에서는 제공 된 목록 함수 [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), 목록을 검색 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

다음 코드에서는 `checkFor` 목록에서 하나의 인수, 목록 및 7에 대 한 검색을 사용 하는 새 함수를 만들려고 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

다음 예제를 사용 하 여 함수의 고급 상태 F #에 함수 선언 `compose`, 두 개의 함수 인수 컴퍼지션을 반환 하는 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
더 짧게 버전을 다음 섹션인 "Curried 함수입니다."를 참조 하십시오.


다음 코드에 대 한 인수도 두 개의 함수를 보냅니다 `compose`모두의 동일한 형식의 단일 인수입니다. 반환 값은 새 함수 두 함수 인수의 조합입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
F #-두 연산자를 제공 하는 중 `<<` 및 `>>`, 함수를 작성 하는 합니다. 예를 들어 `let squareAndDouble2 = doubleIt << squareIt` 같습니다 `let squareAndDouble = compose doubleIt squareIt` 이전 예에서 합니다.

함수 호출의 값으로 함수를 반환의 다음 예제에서는 간단한 추측 게임을 만듭니다. 게임을 만들려면 호출 `makeGame` 값을 사용 해야 할지 추측 하기가 사용자 하려는 전달 `target`합니다. 함수에서 반환 값 `makeGame` (추측) 인수를 하나만 사용 하 여 추측이 올바른지 여부를 보고 하는 함수입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

다음 호출 코드 `makeGame`, 값 보내는 `7` 에 대 한 `target`합니다. 식별자 `playGame` 반환 된 람다 식에 바인딩되어 있습니다. 따라서 `playGame` 에 대 한 값을 하나의 인수로 사용 하는 함수는 `guess`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a>커리 된 함수

암시적의 이용 하 여 더 간결 하 게 쓸 수의 많은 예제에서는 이전 단원의 *커리* F # 함수 선언에 있습니다. 커리 둘 이상의 매개 변수는 각각 단일 매개 변수를 갖는 일련의 포함 된 함수에 포함 된 함수를 변환 하는 프로세스입니다. F #에서 둘 이상의 매개 변수는 함수를 기본적으로 변환 됩니다. 예를 들어 `compose` 이전 섹션에서로 작성할 수 있는 세 개의 매개 변수가 있는 다음 간결한 스타일에 표시 된 것입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

그러나 결과 함수에 나와 있는 것 처럼 하나의 매개 변수는 다른 함수를 반환 하는 하나의 매개 변수는 함수를 반환 하는 하나의 매개의 `compose4curried`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

여러 가지 방법으로이 함수에 액세스할 수 있습니다. 다음 예에서는 각 반환 하 고 18를 표시 합니다. 바꿀 수 `compose4` 와 `compose4curried` 예 중 하나입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

이전 처럼 함수 여전히 작동 하는지 확인 하려면 원래 테스트 사례를 다시 시도 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
튜플에 매개 변수를 포함 하 여 커리 제한할 수 있습니다. 자세한 내용은 "매개 변수 패턴"에서 참조 [매개 변수 및 인수](../language-reference/parameters-and-arguments.md)합니다.

다음 예제에서는 암시적 커리의 짧은 버전을 작성 `makeGame`합니다. 방법 자세히 `makeGame` 생성 및 반환 된 `game` 함수는이 형식으로 명시적 덜 않지만 결과 동일는 원래 테스트 사례를 사용 하 여 확인할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

변환 하는 방법에 대 한 자세한 내용은의 "인수 부분 응용 프로그램" 참조 [함수](../language-reference/functions/index.md)합니다.


## <a name="identifier-and-function-definition-are-interchangeable"></a>식별자 및 함수는 서로 전환이 가능
변수 이름 `num` 이전 예에서는 정수를 10으로 계산 되 고이 올바르기 때문 된 `num` 은 유효 10도를 사용할 수 있습니다. 기능 식별자 및 해당 값의 경우도 마찬가지: 함수의 이름을 사용할 수 원하는 위치에 연결 된 람다 식을 사용할 수 있습니다.

다음 예제에서는 정의 `Boolean` 함수를 호출 `isNegative`, 다음 함수의 이름과 함수 정의 같은 의미로 사용 됩니다. 다음 세 가지 예제 모두 반환 하 고 표시 `False`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

한 단계 더, 값을 대체 하는 `applyIt` for에 바인딩된 `applyIt`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>함수는 F # 고급 값 #

이전 섹션의 예제에서는 F #에서 F # 고급 값 되기 위한 조건을 충족 하는지 보여 줍니다.

- 함수 정의에 식별자를 바인딩할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- 데이터 구조에는 함수를 저장할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- 함수를 인수로 전달할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- 함수는 함수 호출 값으로 반환할 수 있습니다.
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

F #에 대 한 자세한 내용은 참조는 [F # 언어 참조](../language-reference/index.md)합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 코드는이 항목의 모든 예제를 포함합니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a>참고 항목

[목록](../language-reference/lists.md)

[튜플](../language-reference/tuples.md)

[함수](../language-reference/functions/index.md)

[`let`바인딩](../language-reference/functions/let-bindings.md)

[람다 식:는 `fun` 키워드](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
