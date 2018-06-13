---
title: Discriminated Unions(F#)
description: 'F #을 사용 하는 방법을 알아봅니다 구별 된 공용 구조체입니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 617c659e26df52819a98294bcbfa081ab82fed03
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149077"
---
# <a name="discriminated-unions"></a>구별된 공용 구조체

구분 된 공용 구조체는 여러 명명 된 사례의 다양 한 값과 형식 중 하나일 수 있는 값에 대 한 지원을 제공 합니다. 구분 된 공용 구조체는 다른 유형의 데이터는 데 유용 특별 한 경우를 포함 하 여 유효한 및 오류의 경우; 가질 수 있는 데이터 한 인스턴스에서 다른; 형식에 따라 다른 데이터 작은 개체 계층 구조에 대 한 대신으로 합니다. 또한 재귀 구별 된 공용 구조체 트리 데이터 구조를 나타내는 데 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a>설명
구분 된 공용 구조체 다른 언어의 공용 구조체 형식과 유사 하지만 차이점이 있습니다. 으로 c + +에서 공용 구조체 형식 또는 Visual Basic의 variant 형식과 함께 값에 저장 된 데이터를 수정 하지 않으면; 여러 가지 옵션 중 하나일 수 있습니다. 그러나 구조체와 달리 이러한 다른 언어로, 각각의 가능한 옵션은 부여는 *케이스 식별자*합니다. 케이스 식별자에 가능한 다양 한 유형의 값이 유형의 개체 수; 이름에는 값은 선택적입니다. 값이 대/소문자는 열거형 케이스와 동일 합니다. 값이 더 있는 경우 각 값 단일 값에 지정된 된 형식 또는 동일한 또는 다른 형식의 여러 필드를 집계 하는 튜플이 일 수 있습니다. 이름을, 개별 필드를 지정할 수 있지만 이름이 선택 사항 대/소문자 그대로의 다른 필드에 이름이 지정 된 경우에 합니다.

기본 구분 된 공용 구조체에 대 한 액세스 권한은 `public`합니다.

예를 들어 셰이프 형식의 다음 선언을 생각해 보세요.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

위의 코드의 세 가지 경우 중 하나는 값을 가질 수 있는 모양 구별된 된 공용 구조체 선언: 사각형, 원, 및 프리즘 합니다. 각각의 경우에는 다른 필드 집합이 있습니다. 형식의 두 사례에서 두 개의 명명 된 사각형 필드 `float`, 하거나 이름 너비와 길이입니다. 원 사례에서 한 명명 된 필드 반지름입니다. 프리즘 케이스에 세 개의 필드가 있는 (너비 및 높이)의 두 필드 라고 합니다. 명명 되지 않은 필드는 익명 필드 라고 합니다.

다음 예제에 따라 명명 된 형식과 익명 필드에 대 한 값을 제공 하 여 개체를 구성 합니다.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

이 코드에서는 명명된 된 필드를 초기화 하는를 사용 하거나 또는 선언에서 필드의 순서에 의존 하 고 차례로 각 필드에 대 한 값을 방금 제공 수를 보여 줍니다. 에 대 한 생성자 호출 `rect` 이전 코드에서 명명 된 필드는 않지만,에 대 한 생성자 호출을 사용 하 여 `circ` 순서를 사용 합니다. 순서가 지정 된 필드를 혼합할 수와 이름이 같은 필드의 구조와 같이 `prism`합니다.

`option` F # 핵심 라이브러리의 간단한 공용된 구조체로 형식입니다. `option` 유형을 다음과 같이 선언 됩니다.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

앞의 코드를 지정 하는 형식을 `Option` 이라는 두 case가 구별 된 공용 구조체 `Some` 및 `None`합니다. `Some` 사례에서 해당 형식을 형식 매개 변수에 의해 표현 되는 하나의 익명 필드로 구성 된 연관된 된 값 `'a`합니다. `None` 사례에서 관련된 값이 없습니다. 따라서는 `option` 형식은 일부 형식이 나 값이 없는 제네릭 형식을 지정 합니다. 형식 `Option` 소문자 형식 별칭을 역시 `option`, 즉 더 일반적으로 사용 합니다.

케이스 식별자 구별 된 공용 구조체 형식에 대 한 생성자로 사용할 수 있습니다. 예를 들어 다음 코드는의 값을 만드는 데는 `option` 유형입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

일치 식 패턴에서 케이스 식별자도 사용 됩니다. 패턴 일치 식에서에서 식별자는 개별 사례와 관련 된 값에 대 한 제공 됩니다. 예를 들어, 다음 코드에서에서 `x` 식별자와 연결 된 값이 지정 되는 `Some` 의 사례는 `option` 유형입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

패턴 일치 식에서 구별 된 공용 구조체 일치 항목을 지정 하려면 명명 된 필드를 사용할 수 있습니다. 이전에 선언 된 셰이프 형식 필드의 값을 추출 하려면 다음 코드와 같이 명명된 된 필드를 사용할 수 있습니다.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

일반적으로 공용 구조체의 이름으로 정규화 하지 않고 케이스 식별자를 사용할 수 있습니다. 항상 공용 구조체의 이름으로 한정 되어야 하는 이름, 원하는 경우 적용할 수 있습니다는 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성을 공용 구조체 형식 정의 합니다.

### <a name="unwrapping-discriminated-unions"></a>래핑 해제 구별 된 공용 구조체

F # 구별 된 공용 구조체에는 보통에 사용 도메인 모델링은 하나로 줄 바꿈 합니다. 패턴 일치도 통해 기본 값을 추출 하는 것이 쉽습니다. 단일 사례에 대 한 일치 하는 식을 사용할 필요가 없습니다.
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

다음은 이에 대한 예입니다.

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a>구조체 구별 된 공용 구조체

F # 4.1 부터는 구조체로 구별 된 공용 구조체를 또한 나타낼 수 있습니다.  이러한 용도로 `[<Struct>]` 특성입니다.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

없기 때문에 이러한는 값 형식 및 형식을 참조 하지를 추가로 구별 된 공용 구조체 참조와 비교 하는 고려 사항:

1. 프로필은 값 형식으로 복사 하며 값 형식 의미 체계를 포함 합니다.
2. 구별 된 공용 구조체에 multicase 구조체 재귀 형식 정의 사용할 수 없습니다.
3. Multicase 구조체 구별 된 공용 구조체에 대 한 고유한 사례 이름을 제공 해야 합니다.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>구분 된 공용 구조체를 사용 하 여 개체 계층 구조 대신
흔히 소형 개체 계층에 더 간단한 방법으로 구별된 된 공용 구조체를 사용할 수 있습니다. 대신 다음 구별 된 공용 구조체를 사용할 수 예를 들어 한 `Shape` 기본 클래스에 대 한 파생 형식이 원, 사각형, 등입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

대신 영역이 나 경계를 계산 하는 가상 메서드로 사용 되는 개체 지향 구현에서 적절 한 수식으로 분기에 패턴 일치를 사용 하 여 이러한 수량을 계산 합니다. 다음 예제에서는 서로 다른 수식은 모양에 따라 영역을 계산 하는 데 사용 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

출력은 다음과 같습니다.

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>트리 데이터 구조에 대 한 구별 된 공용 구조체를 사용 하 여
구분 된 공용 구조체에는 재귀 공용 구조체 자체의 경우 하나 이상의 형식에 포함 될 수 수 있습니다. 재귀 구별 된 공용 구조체는 프로그래밍 언어에서 식을 모델링 하는 데 사용 되는 트리 구조를 만드는 데 사용할 수 있습니다. 다음 코드에서는 재귀 구별 된 공용 구조체는 이진 트리 데이터 구조를 만드는 데 사용 됩니다. 합집합의 두 가지 경우 구성 `Node`는 정수 값과 왼쪽 및 오른쪽 하위 트리 노드인 및 `Tip`, 트리를 종료 하는 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

이전 코드에서 `resultSumTree` 10 값을 갖습니다. 다음 그림에 대 한 트리 구조를 보여 줍니다. `myTree`합니다.

![Mytree 트리 구조](../media/TreeStructureDiagram.png)

구별 된 공용 구조체의 트리 노드는 다른 유형의 경우 잘 작동 합니다. 다음 코드 형식에서에서 `Expression` 숫자와 변수는 곱하기 및 지 원하는 추가 간단한 프로그래밍 언어에 있는 식의 추상 구문 트리를 나타냅니다. 일부 공용 구조체 케이스의 재귀를 없거나 두 숫자를 나타냅니다 (`Number`) 또는 변수 (`Variable`). 다른 경우 재귀 하 고 작업을 나타냅니다 (`Add` 및 `Multiply`)는 또한 식, 합니다. `Evaluate` 함수는 일치 하는 식 구문 트리를 재귀적으로 프로세스를 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

이 코드를 실행 하면,의 가치 `result` 은 5입니다.

## <a name="common-attributes"></a>공통 특성

다음 특성은 일반적으로 구분 된 공용 구조체에 표시 됩니다.

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]` (F # 4.1)

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
