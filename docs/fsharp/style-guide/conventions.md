---
title: 'F # 코딩 규칙'
description: 'F # 코드를 작성할 때는 일반적인 지침과 관용구를 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: f3d16f735ddc1901aeaa5ebb39e2fa2b70a3d836
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457984"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="430db-103">F # 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="430db-103">F# coding conventions</span></span>

<span data-ttu-id="430db-104">큰 F #을 사용한 작업 경험을 통해 다음과 같은 규칙이 공식화 됩니다 코드 베이스 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="430db-105">[좋은 F # 코드의 5 개 원칙](index.md#five-principles-of-good-f-code) 각 권장 사항은의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="430db-106">와 연결 되어는 [F # 구성 요소 디자인 지침](component-design-guidelines.md), F # 코드를 라이브러리와 같은 뿐 아니라 구성 요소에 적용할 수 있지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="430db-107">코드 구성</span><span class="sxs-lookup"><span data-stu-id="430db-107">Organizing code</span></span>

<span data-ttu-id="430db-108">F # 코드를 구성 하는 두 가지 기능: 모듈과 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="430db-109">이러한 유사 하지만, 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="430db-110">네임 스페이스는.NET 네임 스페이스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="430db-111">모듈은 정적 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="430db-112">네임 스페이스는 항상 최상위 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-112">Namespaces are always top level.</span></span> <span data-ttu-id="430db-113">모듈에는 최상위 및 다른 모듈 내에서 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="430db-114">네임 스페이스는 여러 파일을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="430db-115">모듈을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-115">Modules cannot.</span></span>
* <span data-ttu-id="430db-116">모듈으로 데코레이팅 될 수 `[<RequireQualifiedAccess>]` 및 `[<AutoOpen>]`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="430db-117">다음 지침을 하는 코드를 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="430db-118">최상위 수준에서 네임 스페이스를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="430db-119">공개적으로 사용 될 모든 코드에 대 한 네임 스페이스에는 최상위 수준에서 모듈에 최상의있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="430db-120">되기 때문에.NET 네임 스페이스도 컴파일된다는 문제 없이 C#에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="430db-121">최상위 모듈을 사용 하 여 나타날 수 없습니다. F # 에서만 호출 될 때 다른 하지만 C# 소비자에 호출자를 한정할 필요 하 여 달라진 수 `MyClass` 와 `MyCode` 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="430db-122">신중 하 게 적용 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="430db-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="430db-123">`[<AutoOpen>]` 구문 범위 호출자에 게 제공 되는 것을 오염 수와 항목에서 제공 된 위치에 대 한 대답은 "매직"입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="430db-124">이 일반적으로 좋은 일 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="430db-124">This is generally not a good thing.</span></span> <span data-ttu-id="430db-125">이 규칙에 예외가 발생 F # 핵심 라이브러리 자체 (경우에 이러한 사실이 약간 논쟁 이기도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="430db-126">그러나 이면 편의 위해 해당 공용 API에서 별도로 구성 하려는 공용 API에 대 한 도우미 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...


    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="430db-127">이렇게 하면 도우미 메서드를 호출할 때마다 정규화 하지 않고 공용 API 함수에서 별도 깨끗 하 게 구현 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="430db-128">또한 확장 메서드 및 네임 스페이스 수준에서 식 작성기 노출 깔끔하게으로 표현할 수 `[<AutoOpen>]`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="430db-129">사용 하 여 `[<RequireQualifiedAccess>]` 명명할 수 또는 가독성이 하는 데 도움이 생각 될 때마다</span><span class="sxs-lookup"><span data-stu-id="430db-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="430db-130">추가 `[<RequireQualifiedAccess>]` 특성을 모듈에 모듈을 열 수 있습니다 하며 액세스를 한정 된 모듈의 요소에 대 한 참조가 필요 명시적 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="430db-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="430db-131">예를 들어는 `Microsoft.FSharp.Collections.List` 모듈에는이 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="430db-132">함수 및 모듈의 값에는 이름이 다른 모듈의 있는 이름과 충돌 가능성이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="430db-133">정규화 된 액세스가 필요한 장기적인 유지 관리 및 라이브러리의 evolvability 크게 향상 시켜 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="430db-134">정렬 `open` 문을 토폴로지 방식으로</span><span class="sxs-lookup"><span data-stu-id="430db-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="430db-135">F #에서 선언의 중요를 비롯 한 `open` 문.</span><span class="sxs-lookup"><span data-stu-id="430db-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="430db-136">이 C#과 달리 여기서의 효과 `using` 및 `using static` 문 파일의 순서와 무관 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="430db-137">F #에서 요소 범위에 이미 있는 다른 사용자를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="430db-138">즉, 해당 순서 바꾸기 `open` 문을 코드의 의미를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="430db-139">결과적으로 모든 정렬 된 임의의 `open` 문 (예를 들어, 사전순으로)은 일반적으로 권장 되지가 예상 하는 다른 동작이 생성 받지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="430db-140">대신 좋습니다 정렬 하기 [토폴로지 방식으로](https://en.wikipedia.org/wiki/Topological_sorting); 순서 즉, 프로그램 `open` 순서는 경우에 문을 _레이어_ 정의 된 시스템의 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="430db-141">다양 한 토폴로지 계층 내에서 정렬 영숫자 수행 고려도 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="430db-142">예를 들어, 다음과 같습니다. F # 컴파일러 서비스 공개 API 파일에 대 한 토폴로지 정렬</span><span class="sxs-lookup"><span data-stu-id="430db-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="430db-143">참고 줄 바꿈을 나중에 사전순으로 정렬 하 고 각 레이어와 토폴로지 레이어를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="430db-144">이 값을 실수로 섀도잉 없이 코드를 완전히 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="430db-145">클래스를 사용 하 여 의도 하지 않은 값을 포함 하려면</span><span class="sxs-lookup"><span data-stu-id="430db-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="430db-146">많은 경우 초기화 값 수 의도 하지 않은 컨텍스트는 데이터베이스 또는 다른 원격 리소스를 인스턴스화 등.</span><span class="sxs-lookup"><span data-stu-id="430db-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="430db-147">모듈에서 등의 작업을 초기화 하 고 이후의 함수에서 사용 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="430db-148">이것은 자주 좋지 않습니다는 몇 가지 이유로:</span><span class="sxs-lookup"><span data-stu-id="430db-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="430db-149">응용 프로그램 구성 된 코드 베이스에 밀어 넣는 먼저 `dep1` 및 `dep2`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="430db-150">이 큰 코드 베이스에서 유지 관리 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="430db-151">둘째, 정적으로 초기화 된 데이터는 구성 요소 자체 다중 스레드 사용 하는 경우 스레드로부터 안전 하지 않은 값을 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="430db-152">이것은 명확 하 게에 위반 `dep3`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="430db-153">마지막으로 모듈을 초기화 전체 컴파일 단위에 대 한 정적 생성자로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="430db-154">으로 매니페스트에 해당 모듈의 let 바인딩 값 초기화에서 오류가 발생 한 `TypeInitializationException` 다음 응용 프로그램의 전체 수명 동안 캐시 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="430db-155">이 진단이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="430db-156">일반적으로 내부 예외에 대 한 이유를 시작할 수 있습니다 하지만 없는 경우, 다음이 근본 원인을 란 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="430db-157">대신, 방금를 사용 하 여 간단한 클래스 종속성:</span><span class="sxs-lookup"><span data-stu-id="430db-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="430db-158">이 통해 다음:</span><span class="sxs-lookup"><span data-stu-id="430db-158">This enables the following:</span></span>

1. <span data-ttu-id="430db-159">API 자체는 외부 종속 된 모든 상태를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="430db-160">구성은 API 외부에서 이제 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="430db-161">종속 값에 대 한 초기화의 오류도 나타날 가능성이 없는 `TypeInitializationException`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="430db-162">API 테스트 이제 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="430db-163">오류 관리</span><span class="sxs-lookup"><span data-stu-id="430db-163">Error management</span></span>

<span data-ttu-id="430db-164">큰 시스템에서 오류 관리는 복잡 하 고 nuanced 노력 되며 시스템에 글머리 기호 결함 허용 및 잘 작동은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="430db-165">다음 지침 이동 어려운이 공간에 대 한 지침을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="430db-166">오류 사례 및 사용자의 도메인에 기본 형식에 잘못 된 상태를 나타냅니다</span><span class="sxs-lookup"><span data-stu-id="430db-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="430db-167">와 [구별 된 공용 구조체](../language-reference/discriminated-unions.md), F # 하면 형식 시스템에서 잘못 된 프로그램 상태를 나타낼 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="430db-168">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="430db-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="430db-169">이 경우에 은행 계좌에서 돈을 맡 실패할 수 있는 알려진된 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="430db-170">각 오류 사례는 형식에 표시 되 고 있으므로 처리할 수 있습니다 안전 하 게 프로그램 전체에서.</span><span class="sxs-lookup"><span data-stu-id="430db-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="430db-171">일반적으로 다른 방법으로 모델링할 수 없습니다. 했을 수 **실패** 에 도메인에 다음 오류 처리 코드는 더 이상으로 처리 정기 프로그램 흐름 외에도 처리 해야 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="430db-172">단순히 일반 프로그램 흐름의 일부 이며 간주 되지 **예외적인**합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="430db-173">이 두 가지 주요 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="430db-174">도메인 시간이 지남에 따라 변경 될 때 유지 관리 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="430db-175">오류 사례는 단위 테스트 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="430db-176">오류 형식으로 표현할 수 없는 경우 예외를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="430db-177">문제 도메인에 모든 오류를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="430db-178">이러한 종류의 오류는 *예외적인* 따라서 본질적으로 발생 하 고 F #에서 예외를 catch 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="430db-179">첫째, 것이 좋습니다 읽어는 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="430db-180">이러한 F #에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-180">These are also applicable to F#.</span></span>

<span data-ttu-id="430db-181">다음 기본 설정 순서에 예외를 발생 시키기 위해 F #에서 사용할 수 있는 기본 생성을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="430db-182">기능</span><span class="sxs-lookup"><span data-stu-id="430db-182">Function</span></span> | <span data-ttu-id="430db-183">구문</span><span class="sxs-lookup"><span data-stu-id="430db-183">Syntax</span></span> | <span data-ttu-id="430db-184">용도</span><span class="sxs-lookup"><span data-stu-id="430db-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="430db-185">발생 한 `System.ArgumentNullException` 지정 된 인수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="430db-186">발생 한 `System.ArgumentException` 지정 된 인수 이름 및 메시지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="430db-187">발생 한 `System.InvalidOperationException` 지정 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="430db-188">예외를 throw 하는 범용 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="430db-189">발생 한 `System.Exception` 지정 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="430db-190">발생 한 `System.Exception` 형식 문자열 및 해당 입력에 따라 메시지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="430db-191">사용 하 여 `nullArg`, `invalidArg` 및 `invalidOp` 시키려면 메커니즘으로 `ArgumentNullException`, `ArgumentException` 및 `InvalidOperationException` 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="430db-192">`failwith` 및 `failwithf` 함수는 기본 발생 하므로 피해 야 일반적으로 `Exception` 특정 예외가 아닌를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="430db-193">기준으로 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)을 가능 하면 보다 구체적인 예외를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="430db-194">예외 처리 구문을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="430db-194">Using exception-handling syntax</span></span>

<span data-ttu-id="430db-195">F # 예외 패턴을 통해 지원는 `try...with` 구문:</span><span class="sxs-lookup"><span data-stu-id="430db-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="430db-196">패턴 일치와 함께 예외가 발생할 때 수행 하는 기능을 조정 하는 코드를 완전 하 게 하려는 경우에 약간 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="430db-197">이 문제를 처리 한 방법으로 사용 하는 것 [활성 패턴](../language-reference/active-patterns.md) 자체 예외와 함께 오류 사례는 주변 그룹 기능을 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="430db-198">예를 들어, 예외를 throw 하는 경우 예외 메타 데이터에 중요 한 정보를 포함 하는 API 사용해 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="430db-199">활성 패턴 내 캡처된 예외의 본문에 유용한 값을 래핑 해제 하 고 반환 값 일부 상황에서 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="430db-200">Monadic 오류 바꿀 예외 처리를 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="430db-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="430db-201">예외는 다소 taboo 함수형 프로그래밍에서으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="430db-202">실제로 예외가 not quite 기능 고려해 야 할 안전 하므로 순수한 정도 고을 위반 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="430db-203">그러나이 코드가 실행 해야 하 고 해당 런타임 오류가 발생할 수 있는 현실을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="430db-204">일반적으로 대부분 일은 순수 아니고 원하지 않는 상황을 최소화 하기 위해 총 가정 하에서 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="430db-205">다음 측면을 고려해 코어 장점/예외의 관련성 및.NET 런타임 및 언어 간 환경에서 전체적으로 적합성에 대해을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="430db-206">문제를 디버깅할 때 매우 유용 자세한 진단 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="430db-207">런타임 및 다른.NET 언어에서 잘 이해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430db-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="430db-208">중요 한 기본 구성 요소를 사용 되는 코드와 비교 했을 때를 줄일 수 *방지* 임시 별로 구문의 일부 하위 집합을 구현 하 여 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="430db-209">이 세 번째 점이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-209">This third point is critical.</span></span> <span data-ttu-id="430db-210">Nontrivial 복잡 한 작업에 대 한 예외를 사용 하도록 못하면이 같은 구조를 처리할 때의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="430db-211">오류 "형식의 stringly"에 패턴 일치와 같은 취약 한 코드를 쉽게 야기할 수 있는:</span><span class="sxs-lookup"><span data-stu-id="430db-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="430db-212">또한 "더 좋은" 형식을 반환 하는 "단순" 함수에 대 한 desire에서 모든 예외를 무시 하 고 싶어 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="430db-213">그러나 `tryReadAllText` 무수 한 파일 시스템에 발생할 수 있는 작업을 기반으로 하는 다양 한 예외를 throw 할 수 있습니다 및이 코드를 바로 삭제 수 실제로 될 무엇이 문제 환경에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="430db-214">이 코드는 결과 형식으로 교체 하면 다음 하는 경우 "형식의 stringly" 오류 메시지를 구문 분석 이동:</span><span class="sxs-lookup"><span data-stu-id="430db-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="430db-215">배치 하는 예외 개체 자체에 `Error` 생성자 방금 호출 사이트에서 아닌 함수에서 예외 형식을를 제대로 처리 하지 않아도 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="430db-216">이 작업을 효과적으로 수행 API의 호출자로 다루기가 매우 재미 나오지 않은 확인 된 예외를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="430db-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="430db-217">Catch 하는 위의 예에서는 대신 *특정* 예외와 해당 예외의 컨텍스트에서 의미 있는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="430db-218">수정 하는 경우는 `tryReadAllText` 다음과 같이 작동 `None` 자세한 의미가:</span><span class="sxs-lookup"><span data-stu-id="430db-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="430db-219">범용으로 작동 하는 대신이 함수는 이제 제대로 처리 경우 파일을 찾을 수 없습니다 고 return에 해당 의미를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="430db-220">반환 값이 하지 모든 컨텍스트 정보를 삭제 하거나 호출자가 코드에서 해당 시점에 관련 되지 않을 수 있는 경우를 처리 하도록을 강제 적용 하는 동안 해당 오류 사례에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="430db-221">와 같은 형식은 `Result<'Success, 'Error>` 여기서 중첩 되지 있습니다 하 고 F # 선택적 형식은 반송 없습니다 것 때 나타내기 위해 완벽 한 기본 작업에 적합 한 *문제가* 또는 *nothing*.</span><span class="sxs-lookup"><span data-stu-id="430db-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="430db-222">예외에 대 한 대체 하지는 하지만 하며 예외를 교체할 수에 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="430db-223">대신, 적용 해야 하 신중 하 게 주소 예외와 오류 관리 정책의 특정 측면을 대상으로 지정 된 방식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="430db-224">부분 응용 프로그램 및 지점 필요 없는 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="430db-224">Partial application and point-free programming</span></span>

<span data-ttu-id="430db-225">F # 지점 필요 없는 스타일 부분 응용 프로그램 이므로, 프로그램에 다양 한 방법으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="430db-226">이 모듈 또는 항목의 구현 내에서 코드 재사용에 게 도움이 될 수 있지만 이것은 일반적으로 공개적으로 노출 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="430db-227">일반적으로 프로그래밍 지점 필요 없는 자체로, 전문화 아니며 스타일에서 immersed 하지는 사용자를 위해 중요 한 cognitive 장벽을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="430db-228">부분 응용 프로그램 및 커리 공용 Api에서 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="430db-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="430db-229">거의 예외와 함께 공용 Api에서 부분 응용 프로그램의 사용을 소비자에 대 한 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="430db-230">일반적으로 `let`-F # 코드에 바인딩된 값은 **값**이 아니라 **함수 값**합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="430db-231">와 같은 연산자와 결합 하는 경우에 특히 많은 양의 cognitive 오버 헤드의 교환으로 코드의 줄 수가 적은 저장 하는 중 발생할 수 있습니다 값, 함수 값을 함께 혼합 `>>` 함수를 작성 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="430db-232">지점 필요 없는 프로그래밍에 대 한 도구 문제도 고려해</span><span class="sxs-lookup"><span data-stu-id="430db-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="430db-233">커리 된 함수 인수가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="430db-234">이 인해 tooling 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="430db-234">This has tooling implications.</span></span> <span data-ttu-id="430db-235">다음 두 가지 기능을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="430db-236">유효한 함수에 모두 있지만 `funcWithApplication` 커리 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="430db-237">편집기에서 해당 형식을 마우스로 가리키면이 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="430db-238">호출 사이트에서 Visual Studio와 같은 도구에서 도구 설명을 제공 되지 것입니다 기능에 대 한 의미 있는 정보는 `string` 및 `int` 입력된 형식은 실제로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="430db-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="430db-239">다음과 같은 코드 포인트 필요 없는 발생 하는 경우 `funcWithApplication` 즉 공개적으로 사용 될 것이 좋습니다 도구 수 사항에 인수에 대 한 의미 있는 이름을 하도록 전체 η 확장을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="430db-240">또한 지점 필요 없는 코드를 디버깅할 수 매우 어려울 수 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="430db-241">이름에 바인딩된 값에 의존 하는 디버깅 도구 (예를 들어 `let` 바인딩) 실행을 통해 중간에 있는 중간 값을 검사할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="430db-242">코드를 검사 하 값이 없는 때 디버깅 하는 일은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="430db-243">나중에 이전에 실행된 경로에 따라 이러한 값을 만드는 진화 할 수 디버깅 도구에서 사용자 선택 hedge 하는 것이 좋습니다 것만 *잠재적인* 디버깅 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="430db-244">기술로 부분 응용 프로그램을을 내부 상용구를 줄이는 것이 좋습니다</span><span class="sxs-lookup"><span data-stu-id="430db-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="430db-245">이전 시점 달리 부분 응용 프로그램에는 응용 프로그램 또는 API의 깊은 내부 내부 상용구 줄이기 위한 매우 유용한 도구는입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="430db-246">단위 테스트, 여기서 상용구는 종종 처리 하는 과정을 어렵게 더 복잡 한 Api의 구현에 대 한 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="430db-247">예를 들어 다음 코드와 수행 하는 방법은 어떤 가장 모의 프레임 워크를 제공 이러한 프레임 워크에는 외부 종속성을 수행 하지 않고 고 API 맞춤식를 관련 배울 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="430db-248">예를 들어 다음 솔루션 토폴로지:</span><span class="sxs-lookup"><span data-stu-id="430db-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="430db-249">`ImplementationLogic.fsproj` 와 같은 코드를 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="430db-250">단위 테스트 `Transactions.doTransaction` 에 `ImplementationLogic.Tests.fspoj` 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="430db-251">부분적으로 적용 `doTransaction` 모의 개체 컨텍스트의 개체 때마다 모의 컨텍스트를 생성 하지 않고도 모든 단위 테스트에서 함수를 호출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="430db-252">이 방법은 전체 코드 베이스에 전체적으로 적용 하지 해야 하지만 복잡 한 내부 및 단위 테스트 해당 내부 구조에 대 한 기본 구성 요소를 줄이기 위해 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="430db-253">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="430db-253">Access control</span></span>

<span data-ttu-id="430db-254">F #에 여러 옵션이 [액세스 제어](../language-reference/access-control.md),.NET 런타임에서 사용할 수 있는에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="430db-255">형식에만 사용할 수 없는-도 사용할 수 있습니다 이러한 함수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="430db-256">비-선호`public` 형식 및 공개적으로 사용할 수 있으려면 필요할 때까지 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="430db-257">이 또한에 어떤 소비자 몇을 최소화</span><span class="sxs-lookup"><span data-stu-id="430db-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="430db-258">모든 도우미 기능을 유지 하기 위해 노력 `private`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="430db-259">사용 하 여 `[<AutoOpen>]` 도우미 함수 수많은 하 게 하는 경우 개인 모듈에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="430db-260">형식 유추 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="430db-260">Type inference and generics</span></span>

<span data-ttu-id="430db-261">형식 유추 상용구 많은 입력에서 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="430db-262">및 사용자의 추가 작업 없이 거의 보다 일반적인 코드를 작성할 F # 컴파일러에서 자동 일반화 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="430db-263">그러나 이러한 기능은 일반적으로 좋은있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="430db-264">공용 Api에서 명시적 형식 인수 이름에 레이블을 지정 하 고이 대 한 형식 유추에 의존 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="430db-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="430db-265">이 대 한 이유는 **있습니다** 컴파일러가 아닌 해당 API의 모양 제어에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="430db-266">컴파일러가 있습니다에 대 한 형식 유추에서 세밀 하 게 작업을 수행할 수, 이지만에 의존 하는 내부 형식 변경 되 면 API 변경의 모양이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="430db-267">원하는 수도 있지만 대부분 다운스트림 소비자가 처리 하는 주요 API 변경 균형이 깨어 집니다.</span><span class="sxs-lookup"><span data-stu-id="430db-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="430db-268">대신, 공용 API의 모양의 명시적으로 제어 하는 경우 이러한 주요 변경 사항 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="430db-269">DDD 측면에서이 생각할 수 있습니다 바이러스 손상 계층으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="430db-270">제네릭 인수에 의미 있는 이름을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="430db-271">특정 도메인에만 적용 되는 진정한 일반 코드를 작성 하는 경우가 아니면에서 작업 하는 도메인 이해 프로그래머에 의미 있는 이름을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="430db-272">예를 들어, 형식 매개 변수 라는 `'Document` 문서와 상호 작용의 컨텍스트에서 데이터베이스 사용 하면 명확 하 게 제네릭 문서 형식을 함수 또는 멤버를 사용 하는 허용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="430db-273">제네릭 형식 매개 변수 표시 방법이 PascalCase와 이름을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="430db-274">이것이 하므로 snake_case 또는 camelCase 표시 방법이 PascalCase 대신를 사용 하는 것이 좋습니다..net에서는 작업을 수행 하는 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="430db-275">마지막으로, 자동 일반화는 F # 또는 큰 코드 베이스를 처음 접하는 사용자를 위해 유용 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="430db-276">일반적인 구성 요소를 사용 하 여 cognitive 오버 헤드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="430db-277">또한 자동으로 일반화 함수 (let 단독으로 사용 해서도 하려는 경우) 여러 입력된 형식으로 사용 되지 않는 경우 시간 해당 시점에 제네릭를 실질적인 이점은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="430db-278">작성 중인 코드 실제로 제네릭에서 이익을 얻을 경우 항상 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="430db-279">성능</span><span class="sxs-lookup"><span data-stu-id="430db-279">Performance</span></span>

<span data-ttu-id="430db-280">F # 값은 특정 클래스 (특히 해당 관련 된 동시성 및 병렬 처리 수준) 버그의 수는 기본적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="430db-281">그러나 경우에 따라 실행 시간 또는 메모리 할당의 최적 (또는 심지어 합리적인) 효율성을 얻기 위해 작업의 범위 가장 잘 구현 될 수 있습니다 내부 변경 했습니다. 상태를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="430db-282">F #으로 옵트인 방식에서 가능는 `mutable` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="430db-283">그러나 사용 `mutable` F #에서 기능 순도 되었는데 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="430db-284">순도 하 게 조정 하는 경우에 문제가 [참조 투명도](https://en.wikipedia.org/wiki/Referential_transparency)합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="430db-285">참조 투명도-순도-F # 함수를 작성할 때 최종 목표는 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="430db-286">이 옵션을 사용 하면 성능에 중요 코드에 대 한 변환이 기반 구현을 통해 기능 인터페이스를 작성 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="430db-287">변경할 수 없는 인터페이스에서 변경할 수 있는 코드 줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="430db-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="430db-288">이 목표를으로 참조 투명 성능이 중요 한 기능 변경 가능한 언더 벨 리를 노출 하지 않는 코드를 작성 하려면 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="430db-289">예를 들어 다음 코드 구현 하는 `Array.contains` 함수에는 F # 핵심 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="430db-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="430db-290">이 함수를 여러 번 호출 원본으로 사용 하 여 배열에는 변경 되지 않습니다 요구 하지도 않습니다 사용에서 변경할 수 있는 모든 상태를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="430db-291">내 코드의 거의 모든 줄 변환이 사용 하는 경우에 것 참조가 투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="430db-292">변경할 수 있는 클래스의에서 데이터를 캡슐화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="430db-293">변경할 수 있는 데이터를 사용 하 여 작업을 캡슐화 하는 단일 함수를 사용 하는 앞의 예제.</span><span class="sxs-lookup"><span data-stu-id="430db-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="430db-294">항상 더 복잡 한 데이터 집합에 대 한 충분 한 있는 이것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="430db-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="430db-295">다음 함수 집합을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-295">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="430db-296">이 코드는 성능이 나 하지만 호출자가 유지 관리 해야 남겨지고 기반 데이터 구조를 표시 하기.</span><span class="sxs-lookup"><span data-stu-id="430db-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="430db-297">이 변경 될 수 있는 기본 멤버 없이 클래스 내부 줄 바꿈할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="430db-298">`Closure1Table` 활용 하지 않는 기본 데이터 구조를 유지 하기 위해 호출자가 강제 적용 하면 기본 남겨지고 기반 데이터 구조를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="430db-299">클래스는 데이터와 호출자에 게 세부 정보를 노출 하지 않고 남겨지고 기반 되는 루틴을 캡슐화 하는 강력한 방법을입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="430db-300">원하는 `let mutable` 참조 셀</span><span class="sxs-lookup"><span data-stu-id="430db-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="430db-301">참조 셀은 자체의 값이 아닌 값에 대 한 참조를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="430db-302">성능에 중요 코드에 대해 사용할 수 있습니다, 있지만 일반적으로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="430db-303">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430db-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="430db-304">이제는 참조 셀 사용 "오염" 모든 후속 코드를 역참조 하 고 기본 데이터를 다시 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="430db-305">대신, `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="430db-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="430db-306">람다 식 중간에 남겨지고 단일 지점 외에도 다른 모든 코드를 건드리면 `acc` 더 일반적인의 사용량을 다른 방식으로 그렇게 할 수 `let`-바인딩된 변경할 수 없는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="430db-307">이 쉽게 바뀔 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="430db-308">개체 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="430db-308">Object programming</span></span>

<span data-ttu-id="430db-309">F # 개체 및 개체 지향 (개체 지향) 개념에 대 한 완전 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="430db-310">여러 개체 지향 개념 강력 하 고 유용 하지만, 그 중 일부만 사용 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="430db-311">다음 목록에서는 상위 수준 개체 지향 기능 범주에 대 한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="430db-312">**다양 한 상황에서 이러한 기능을 사용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="430db-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="430db-313">점 표기법 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="430db-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="430db-314">인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="430db-314">Instance members</span></span>
* <span data-ttu-id="430db-315">암시적 생성자</span><span class="sxs-lookup"><span data-stu-id="430db-315">Implicit constructors</span></span>
* <span data-ttu-id="430db-316">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="430db-316">Static members</span></span>
* <span data-ttu-id="430db-317">인덱서 표기법 (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="430db-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="430db-318">명명 된 인수와 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="430db-318">Named and Optional arguments</span></span>
* <span data-ttu-id="430db-319">인터페이스 및 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="430db-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="430db-320">**이러한 기능에 대해 먼저 도달 하지 않는 있지만 문제를 해결 하기 편리 하 게 될 때 적용할 주의 해 서 수행:**</span><span class="sxs-lookup"><span data-stu-id="430db-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="430db-321">메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="430db-321">Method overloading</span></span>
* <span data-ttu-id="430db-322">변경할 수 있는 데이터를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="430db-323">형식에 연산자</span><span class="sxs-lookup"><span data-stu-id="430db-323">Operators on types</span></span>
* <span data-ttu-id="430db-324">자동 속성</span><span class="sxs-lookup"><span data-stu-id="430db-324">Auto properties</span></span>
* <span data-ttu-id="430db-325">구현 `IDisposable` 및 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="430db-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="430db-326">형식 확장명</span><span class="sxs-lookup"><span data-stu-id="430db-326">Type extensions</span></span>
* <span data-ttu-id="430db-327">이벤트</span><span class="sxs-lookup"><span data-stu-id="430db-327">Events</span></span>
* <span data-ttu-id="430db-328">구조체</span><span class="sxs-lookup"><span data-stu-id="430db-328">Structs</span></span>
* <span data-ttu-id="430db-329">대리자</span><span class="sxs-lookup"><span data-stu-id="430db-329">Delegates</span></span>
* <span data-ttu-id="430db-330">열거형</span><span class="sxs-lookup"><span data-stu-id="430db-330">Enums</span></span>

<span data-ttu-id="430db-331">**일반적으로 사용 해야 하지 않는 한 이러한 기능을 하지 말아야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="430db-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="430db-332">구현 상속 및 상속 기반 형식 계층 구조</span><span class="sxs-lookup"><span data-stu-id="430db-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="430db-333">Null 및 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="430db-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="430db-334">컴퍼지션 상속 보다 선호</span><span class="sxs-lookup"><span data-stu-id="430db-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="430db-335">[상속을 통해 컴퍼지션](https://en.wikipedia.org/wiki/Composition_over_inheritance) 좋은 F # 코드 수를 준수 하는 오래 된 관용구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="430db-336">기본 원칙은 해야 하지는 기본 클래스를 노출 하는 기능을 활용 하려면의 기본 클래스에서 상속 하는 호출자를 강제로 것입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="430db-337">개체 식을 사용 하 여 클래스를 필요 하지 않으면 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="430db-338">[개체 식](../language-reference/object-expressions.md) 클래스 내부 작업을 수행 하지 않고도 값에 구현 된 인터페이스를 바인딩할 즉석에서 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="430db-339">이 편리 하 고 경우에 특히 있습니다 _만_ 전체 클래스에 대 한 필요 없는 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="430db-340">예를 들어 다음은에서 실행 되는 코드 [Ionide](http://ionide.io/) 지원 하지 않는 기호를 추가한 경우 코드 수정 동작을 제공 하는 `open` 에 대 한 문:</span><span class="sxs-lookup"><span data-stu-id="430db-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="430db-341">개체 식 필요는 없습니다 클래스에 대 한 Visual Studio 코드 API와 상호 작용할 때, 되므로이 이상적인 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="430db-342">단위 테스트, 테스트 루틴을 사용 하 여 인터페이스에서 특별 한 방식으로 추출할 하려는 경우 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="430db-343">형식 약어</span><span class="sxs-lookup"><span data-stu-id="430db-343">Type Abbreviations</span></span>

<span data-ttu-id="430db-344">[형식 약어](../language-reference/type-abbreviations.md) 함수 서명 또는 더 복잡 한 형식 등의 다른 형식에 레이블을 지정 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="430db-345">별칭은 레이블을 계산을 정의 하는 데 필요한 항목을 할당 하는 예를 들어 [CNTK](https://www.microsoft.com/cognitive-toolkit/), 라이브러리 학습 깊습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="430db-346">`Computation` 이름은 시그니처와 일치 하는 것이 별칭을 지정 하는 모든 함수를 표시 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="430db-347">다음과 같은 형식 약어를 사용 하 여 편리 하 고 불필요 한 코드 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="430db-348">도메인을 나타내기 위해 형식 약어를 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="430db-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="430db-349">형식 약어를 함수 서명에 이름을 지정 하는 데 편리 하지만은 혼동 될 수 있습니다 다른 종류를 단축 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="430db-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="430db-350">이 약어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="430db-351">여러 가지 방법으로 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="430db-352">`BufferSize` 추상화; 않습니다. 정수에 대 한 또 다른 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="430db-353">경우 `BufferSize` 노출 되는 공용 API에서 것 쉽게 잘못 해석 될 수을 보다 더 의미 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="430db-354">일반적으로 도메인에 있는 특성이 여러 개 있을 형식과 같은 기본 형식이 아닌 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="430db-355">이 약어 아니라고를 위반합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="430db-356">대/소문자 `BufferSize` (표시 방법이 PascalCase) 의미이 이와 같은 더 많은 데이터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="430db-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="430db-357">이 별칭 비교 함수에 대 한 명명 된 인수를 제공 하는 증가 선명도 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="430db-358">약어 컴파일된 IL;에서 매니페스트 되지 않습니다. 정수 이므로이 별칭은 컴파일 타임 구문.</span><span class="sxs-lookup"><span data-stu-id="430db-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="430db-359">요약 하자면, 형식 약어와 문제는 이들이 **하지** 이니셜는 형식에 대 한 추상화입니다.</span><span class="sxs-lookup"><span data-stu-id="430db-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="430db-360">이전 예에서 `BufferSize` 단지는 `int` 없는 추가 데이터 또는 기능 외에도 유형 시스템 으로부터 장점으로 내부적으로 `int` 에 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430db-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
