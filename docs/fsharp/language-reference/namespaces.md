---
title: 네임스페이스(F#)
description: 'F # 네임 스페이스는 프로그램 요소의 그룹화에 이름을 연결 하 여 코드의 기능 관련된 영역으로 구성할 수 있습니다 어떻게에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 695de3b58b8567da60c8ef86900f8e78ea563e0e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="namespaces"></a><span data-ttu-id="ea579-103">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ea579-103">Namespaces</span></span>

<span data-ttu-id="ea579-104">네임스페이스를 통해 프로그램 요소의 그룹에 이름을 연결하여 관련 기능 영역으로 코드를 체계화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>


## <a name="syntax"></a><span data-ttu-id="ea579-105">구문</span><span class="sxs-lookup"><span data-stu-id="ea579-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="ea579-106">설명</span><span class="sxs-lookup"><span data-stu-id="ea579-106">Remarks</span></span>
<span data-ttu-id="ea579-107">네임 스페이스에 코드를 입력 하려는 경우 파일의 첫 번째 선언 네임 스페이스를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="ea579-108">전체 파일의 내용을 네임 스페이스의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="ea579-109">네임 스페이스 값 및 함수에 직접 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="ea579-110">대신, 값 및 함수 모듈에 포함 되어야 하며 모듈이 네임 스페이스에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="ea579-111">네임 스페이스는 형식, 모듈을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="ea579-112">네임 스페이스 선언할 수 있습니다 명시적으로 네임 스페이스 키워드를 사용 하거나 암시적으로 모듈을 선언 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ea579-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="ea579-113">네임 스페이스를 명시적으로 선언 하려면 뒤 네임 스페이스 이름을 네임 스페이스 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="ea579-114">다음 예제에서는 형식과 해당 네임 스페이스에 포함 된 모듈을 사용 하 여 위젯을 네임 스페이스를 선언 하는 코드 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="ea579-115">파일의 전체 내용을 한 모듈에 있는 경우 선언할 수도 있습니다 네임 스페이스 암시적으로 사용 하 여는 `module` 키워드와 정규화 된 모듈 이름에 새 네임 스페이스 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="ea579-116">다음 예제에서는 네임 스페이스를 선언 하는 코드 파일 `Widgets` 및 모듈 `WidgetsModule`, 함수를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="ea579-117">다음 코드는 앞의 코드에서와 동일 하지만 모듈은 로컬 모듈 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="ea579-118">이 경우 네임 스페이스는 별도 줄에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="ea579-119">하나 이상의 네임 스페이스에 있는 동일한 파일에 둘 이상의 모듈에 필요한 경우 로컬 모듈 선언 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="ea579-120">로컬 모듈 선언을 사용 하는 경우에 모듈 선언에 정규화 된 네임 스페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="ea579-121">다음 코드에는 네임 스페이스 선언 및 두 개의 로컬 모듈 선언에 있는 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="ea579-122">네임 스페이스;에 직접 모듈은 포함 하는 경우에 파일 이름이 같은 암시적으로 생성된 된 모듈이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="ea579-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="ea579-123">다른 모든 코드가 파일에서와 같은 한 `do` 되므로 모듈 멤버를 한정할 필요가 내부 모듈 있지만 네임 스페이스에는 바인딩, `widgetFunction` 모듈 이름을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="ea579-124">이 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="ea579-125">자세한 내용은 참조 [모듈](modules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="ea579-126">중첩 된 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="ea579-126">Nested Namespaces</span></span>
<span data-ttu-id="ea579-127">중첩 된 네임 스페이스를 만들 때 완전 하 게 정규화 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="ea579-128">그렇지 않으면 새 최상위 네임 스페이스를 만들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="ea579-129">들여쓰기는 네임 스페이스 선언에는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="ea579-130">다음 예에서는 중첩된 된 네임 스페이스를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="ea579-131">파일 및 어셈블리의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="ea579-131">Namespaces in Files and Assemblies</span></span>
<span data-ttu-id="ea579-132">네임 스페이스는 단일 프로젝트 또는 컴파일에서 여러 파일을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="ea579-133">용어 *네임 스페이스 조각* 하나의 파일에 포함 된 네임 스페이스의 일부를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="ea579-134">네임 스페이스에서 여러 어셈블리를 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="ea579-135">예를 들어는 `System` 네임 스페이스에 걸쳐 여러 어셈블리를 여러 개의 중첩 된 네임 스페이스를 포함 합니다. 전체.NET Framework를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>


## <a name="global-namespace"></a><span data-ttu-id="ea579-136">전역 Namespace</span><span class="sxs-lookup"><span data-stu-id="ea579-136">Global Namespace</span></span>
<span data-ttu-id="ea579-137">미리 정의 된 네임 스페이스를 사용 하 여 `global` 이름을.NET 최상위 네임 스페이스에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="ea579-138">사용할 수도 있습니다 전역 예를 들어 최상위.NET 네임 스페이스를 참조 하려면, 다른 네임 스페이스와 이름 충돌을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="ea579-139">재귀 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="ea579-139">Recursive namespaces</span></span>

<span data-ttu-id="ea579-140">F # 4.1 상호는 재귀적일 수에 포함 된 모든 코드를 허용 하는 네임 스페이스의 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="ea579-141">통해 이렇게 `namespace rec`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="ea579-142">사용 하 여 `namespace rec` 의 형식 및 모듈 간에 상호 참조 코드를 작성할 수 없는 일부 그리고를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="ea579-143">다음은 이러한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-143">The following is an example of this:</span></span>

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
    let peel (b : Banana) =
        let flip banana =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides banana =
            for side in banana.Sides do
                if side = Unpeeled then
                    side <- Peeled

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="ea579-144">예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="ea579-145">또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="ea579-146">F #에서 express를 제거한 경우 가능 하지 않습니다이 `rec` 에서 키워드는 `MutualReferences` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="ea579-147">이 기능에 대 한 제공 됩니다. 최상위 [모듈](modules.md) F # 4.1 또는 그 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="ea579-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea579-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea579-148">See Also</span></span>
[<span data-ttu-id="ea579-149">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ea579-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ea579-150">모듈</span><span class="sxs-lookup"><span data-stu-id="ea579-150">Modules</span></span>](modules.md)

[<span data-ttu-id="ea579-151">F # RFC FS 1009 파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용</span><span class="sxs-lookup"><span data-stu-id="ea579-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
