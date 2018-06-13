---
title: 'Fixed 키워드 (F #)'
description: "고정할 수 있는' ' 하는 방법으로 스택에 F #을 사용 하 여 컬렉션을 방지 하기 위해 로컬 'fixed' 키워드에 알아봅니다."
ms.date: 04/24/2017
ms.openlocfilehash: 913ee4d7b0f6b2437793d4788e53556d6be6c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563878"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="aad72-103">Fixed 키워드</span><span class="sxs-lookup"><span data-stu-id="aad72-103">The Fixed Keyword</span></span>

<span data-ttu-id="aad72-104">F # 4.1 소개는 `fixed` 키워드 "고정"을 수집 하거나 가비지 수집 중 이동 하기만 해도 스택으로 로컬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="aad72-105">낮은 수준의 프로그래밍 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="aad72-106">구문</span><span class="sxs-lookup"><span data-stu-id="aad72-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="aad72-107">설명</span><span class="sxs-lookup"><span data-stu-id="aad72-107">Remarks</span></span>

<span data-ttu-id="aad72-108">포인터를 추출 하 고 수집 또는 가비지 수집 중 이동 되지 못하게 하는 이름에 바인딩할 수 있도록 하는 식의 구문은 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="aad72-109">식에서 포인터를 통해 고정 되어는 `fixed` 키워드는 식별자를 통해 바인딩되는 `use` 키워드.</span><span class="sxs-lookup"><span data-stu-id="aad72-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="aad72-110">리소스 관리를 통해 이것의 의미 체계가 비슷합니다는 `use` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="aad72-111">포인터가 범위에가 범위에 속하지는 것은 더 이상 고정 되어 있기 동안 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="aad72-112">`fixed` 컨텍스트 외부에서 사용할 수 없습니다는 `use` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="aad72-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="aad72-113">이름으로 포인터를 바인딩해야 `use`합니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="aad72-114">사용 하 여 `fixed` 함수나 메서드는 식 내에서 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="aad72-115">스크립트 수준 또는 모듈 수준 범위에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="aad72-116">모든 포인터 코드 처럼 안전 하지 않은 기능 이므로 사용 하면 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad72-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="aad72-117">예제</span><span class="sxs-lookup"><span data-stu-id="aad72-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aad72-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aad72-118">See Also</span></span>

[<span data-ttu-id="aad72-119">NativePtr 모듈</span><span class="sxs-lookup"><span data-stu-id="aad72-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
