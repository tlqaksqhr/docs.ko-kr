---
title: "Fixed 키워드 (F #)"
description: "고정할 수 있는' ' 하는 방법으로 스택에 F #을 사용 하 여 컬렉션을 방지 하기 위해 로컬 'fixed' 키워드에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: 1605603bc35941e21c798600140036fb678869b5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="the-fixed-keyword"></a>Fixed 키워드

F # 4.1 소개는 `fixed` 키워드 "고정"을 수집 하거나 가비지 수집 중 이동 하기만 해도 스택으로 로컬 수 있습니다.  낮은 수준의 프로그래밍 시나리오에 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>설명

포인터를 추출 하 고 수집 또는 가비지 수집 중 이동 되지 못하게 하는 이름에 바인딩할 수 있도록 하는 식의 구문은 확장 합니다.  

식에서 포인터를 통해 고정 되어는 `fixed` 키워드는 식별자를 통해 바인딩되는 `use` 키워드.  리소스 관리를 통해 이것의 의미 체계가 비슷합니다는 `use` 키워드입니다.  포인터가 범위에가 범위에 속하지는 것은 더 이상 고정 되어 있기 동안 고정 됩니다.  `fixed`컨텍스트 외부에서 사용할 수 없습니다는 `use` 바인딩.  이름으로 포인터를 바인딩해야 `use`합니다.

사용 하 여 `fixed` 함수나 메서드는 식 내에서 발생 해야 합니다.  스크립트 수준 또는 모듈 수준 범위에서 사용할 수 없습니다.

모든 포인터 코드 처럼 안전 하지 않은 기능 이므로 사용 하면 경고를 생성 합니다.

## <a name="example"></a>예

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a>참고 항목

[NativePtr 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
