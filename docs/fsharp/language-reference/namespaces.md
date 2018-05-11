---
title: 네임스페이스(F#)
description: 'F # 네임 스페이스는 프로그램 요소의 그룹화에 이름을 연결 하 여 코드의 기능 관련된 영역으로 구성할 수 있습니다 어떻게에 대해 알아봅니다.'
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="namespaces"></a>네임스페이스

네임스페이스를 통해 프로그램 요소의 그룹에 이름을 연결하여 관련 기능 영역으로 코드를 체계화할 수 있습니다.


## <a name="syntax"></a>구문

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>설명
네임 스페이스에 코드를 입력 하려는 경우 파일의 첫 번째 선언 네임 스페이스를 선언 해야 합니다. 전체 파일의 내용을 네임 스페이스의 일부가 됩니다.

네임 스페이스 값 및 함수에 직접 포함할 수 없습니다. 대신, 값 및 함수 모듈에 포함 되어야 하며 모듈이 네임 스페이스에 포함 됩니다. 네임 스페이스는 형식, 모듈을 포함할 수 있습니다.

네임 스페이스 선언할 수 있습니다 명시적으로 네임 스페이스 키워드를 사용 하거나 암시적으로 모듈을 선언 하는 경우. 네임 스페이스를 명시적으로 선언 하려면 뒤 네임 스페이스 이름을 네임 스페이스 키워드를 사용 합니다. 다음 예제에서는 형식과 해당 네임 스페이스에 포함 된 모듈을 사용 하 여 위젯을 네임 스페이스를 선언 하는 코드 파일을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

파일의 전체 내용을 한 모듈에 있는 경우 선언할 수도 있습니다 네임 스페이스 암시적으로 사용 하 여는 `module` 키워드와 정규화 된 모듈 이름에 새 네임 스페이스 이름을 제공 합니다. 다음 예제에서는 네임 스페이스를 선언 하는 코드 파일 `Widgets` 및 모듈 `WidgetsModule`, 함수를 포함 하 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

다음 코드는 앞의 코드에서와 동일 하지만 모듈은 로컬 모듈 선언 합니다. 이 경우 네임 스페이스는 별도 줄에 나타나야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

하나 이상의 네임 스페이스에 있는 동일한 파일에 둘 이상의 모듈에 필요한 경우 로컬 모듈 선언 사용 해야 합니다. 로컬 모듈 선언을 사용 하는 경우에 모듈 선언에 정규화 된 네임 스페이스를 사용할 수 없습니다. 다음 코드에는 네임 스페이스 선언 및 두 개의 로컬 모듈 선언에 있는 파일을 보여 줍니다. 네임 스페이스;에 직접 모듈은 포함 하는 경우에 파일 이름이 같은 암시적으로 생성된 된 모듈이 없는 경우 다른 모든 코드가 파일에서와 같은 한 `do` 되므로 모듈 멤버를 한정할 필요가 내부 모듈 있지만 네임 스페이스에는 바인딩, `widgetFunction` 모듈 이름을 사용 하 여 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

이 예제의 출력은 다음과 같습니다.

```fsharp
Module1 10 20
Module2 5 6
```

자세한 내용은 참조 [모듈](modules.md)합니다.

## <a name="nested-namespaces"></a>중첩 된 네임 스페이스
중첩 된 네임 스페이스를 만들 때 완전 하 게 정규화 해야 있습니다. 그렇지 않으면 새 최상위 네임 스페이스를 만들 있습니다. 들여쓰기는 네임 스페이스 선언에는 무시 됩니다.

다음 예에서는 중첩된 된 네임 스페이스를 선언 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>파일 및 어셈블리의 네임 스페이스
네임 스페이스는 단일 프로젝트 또는 컴파일에서 여러 파일을 확장할 수 있습니다. 용어 *네임 스페이스 조각* 하나의 파일에 포함 된 네임 스페이스의 일부를 설명 합니다. 네임 스페이스에서 여러 어셈블리를 걸쳐 있을 수 있습니다. 예를 들어는 `System` 네임 스페이스에 걸쳐 여러 어셈블리를 여러 개의 중첩 된 네임 스페이스를 포함 합니다. 전체.NET Framework를 포함 합니다.


## <a name="global-namespace"></a>전역 Namespace
미리 정의 된 네임 스페이스를 사용 하 여 `global` 이름을.NET 최상위 네임 스페이스에 넣을 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

사용할 수도 있습니다 전역 예를 들어 최상위.NET 네임 스페이스를 참조 하려면, 다른 네임 스페이스와 이름 충돌을 해결 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>재귀 네임 스페이스

F # 4.1 상호는 재귀적일 수에 포함 된 모든 코드를 허용 하는 네임 스페이스의 개념을 소개 합니다.  통해 이렇게 `namespace rec`합니다.  사용 하 여 `namespace rec` 의 형식 및 모듈 간에 상호 참조 코드를 작성할 수 없는 일부 그리고를 완화할 수 있습니다.  다음은 이러한 예입니다.

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.  또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로를 참조할 수도 있습니다.  F #에서 express를 제거한 경우 가능 하지 않습니다이 `rec` 에서 키워드는 `MutualReferences` 네임 스페이스입니다.

이 기능에 대 한 제공 됩니다. 최상위 [모듈](modules.md) F # 4.1 또는 그 이상입니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[모듈](modules.md)

[F # RFC FS 1009 파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
