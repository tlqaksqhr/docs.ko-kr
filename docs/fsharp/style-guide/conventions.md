---
title: 'F # 코딩 규칙'
description: 'F # 코드를 작성할 때는 일반적인 지침과 관용구를 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 4db1e2b4fef97fc060f717a080cd762f9fe08ee0
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="f-coding-conventions"></a>F # 코딩 규칙

큰 F #을 사용한 작업 경험을 통해 다음과 같은 규칙이 공식화 됩니다 코드 베이스 합니다. [좋은 F # 코드의 5 개 원칙](index.md#five-principles-of-good-f-code) 각 권장 사항은의 기반이 됩니다. 와 연결 되어는 [F # 구성 요소 디자인 지침](component-design-guidelines.md), F # 코드를 라이브러리와 같은 뿐 아니라 구성 요소에 적용할 수 있지만 합니다.

## <a name="organizing-code"></a>코드 구성

F # 코드를 구성 하는 두 가지 기능: 모듈과 네임 스페이스입니다. 이러한 유사 하지만, 다음과 같은 차이가 있습니다.

* 네임 스페이스는.NET 네임 스페이스로 컴파일됩니다. 모듈은 정적 클래스로 컴파일됩니다.
* 네임 스페이스는 항상 최상위 수준입니다. 모듈에는 최상위 및 다른 모듈 내에서 중첩 될 수 있습니다.
* 네임 스페이스는 여러 파일을 확장할 수 있습니다. 모듈을 할 수 없습니다.
* 모듈으로 데코레이팅 될 수 `[<RequireQualifiedAccess>]` 및 `[<AutoOpen>]`합니다.

다음 지침을 하는 코드를 구성 하는 데 사용할 수 있습니다.

### <a name="prefer-namespaces-at-the-top-level"></a>최상위 수준에서 네임 스페이스를 선호 합니다.

공개적으로 사용 될 모든 코드에 대 한 네임 스페이스에는 최상위 수준에서 모듈에 최상의있지 않습니다. 되기 때문에.NET 네임 스페이스도 컴파일된다는 문제 없이 C#에서 사용 가능 합니다.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

최상위 모듈을 사용 하 여 나타날 수 없습니다. F # 에서만 호출 될 때 다른 하지만 C# 소비자에 호출자를 한정할 필요 하 여 달라진 수 `MyClass` 와 `MyCode` 모듈입니다.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>신중 하 게 적용 `[<AutoOpen>]`

`[<AutoOpen>]` 구문 범위 호출자에 게 제공 되는 것을 오염 수와 항목에서 제공 된 위치에 대 한 대답은 "매직"입니다. 이 일반적으로 좋은 일 아닙니다. 이 규칙에 예외가 발생 F # 핵심 라이브러리 자체 (경우에 이러한 사실이 약간 논쟁 이기도 함)입니다.

그러나 이면 편의 위해 해당 공용 API에서 별도로 구성 하려는 공용 API에 대 한 도우미 기능을 사용할 수 있습니다.

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

이렇게 하면 도우미 메서드를 호출할 때마다 정규화 하지 않고 공용 API 함수에서 별도 깨끗 하 게 구현 정보가 있습니다.

또한 확장 메서드 및 네임 스페이스 수준에서 식 작성기 노출 깔끔하게으로 표현할 수 `[<AutoOpen>]`합니다.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>사용 하 여 `[<RequireQualifiedAccess>]` 명명할 수 또는 가독성이 하는 데 도움이 생각 될 때마다

추가 `[<RequireQualifiedAccess>]` 특성을 모듈에 모듈을 열 수 있습니다 하며 액세스를 한정 된 모듈의 요소에 대 한 참조가 필요 명시적 나타냅니다. 예를 들어는 `Microsoft.FSharp.Collections.List` 모듈에는이 특성입니다.

함수 및 모듈의 값에는 이름이 다른 모듈의 있는 이름과 충돌 가능성이 있는 경우에 유용 합니다. 정규화 된 액세스가 필요한 장기적인 유지 관리 및 라이브러리의 evolvability 크게 향상 시켜 합니다.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>정렬 `open` 문을 토폴로지 방식으로

F #에서 선언의 중요를 비롯 한 `open` 문. 이 C#과 달리 여기서의 효과 `using` 및 `using static` 문 파일의 순서와 무관 합니다.

F #에서 요소 범위에 이미 다른 섀도잉할 수 때문에 제공 합니다. 즉, 해당 순서 바꾸기 `open` 문을 코드의 의미를 변경할 수 있습니다. 결과적으로, 정렬 알파벳순 (또는 pseudorandomly)은 일반적으로 좋지가 예상 하는 다른 동작이 생성 받지 않도록 합니다.

대신 좋습니다 정렬 하기 [토폴로지 방식으로](https://en.wikipedia.org/wiki/Topological_sorting); 순서 즉, 프로그램 `open` 순서는 경우에 문을 _레이어_ 정의 된 시스템의 합니다. 다양 한 토폴로지 계층 내에서 정렬 영숫자 수행 고려도 수 있습니다.

예를 들어, 다음과 같습니다. F # 컴파일러 서비스 공개 API 파일에 대 한 토폴로지 정렬

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Core.Printf
open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
open Microsoft.FSharp.Compiler.Layout.TaggedTextOps
```

참고 줄 바꿈을 나중에 사전순으로 정렬 하 고 각 레이어와 토폴로지 레이어를 구분 합니다. 이 값을 실수로 섀도잉 없이 코드를 완전히 구성 합니다.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>클래스를 사용 하 여 의도 하지 않은 값을 포함 하려면

많은 경우 초기화 값 수 의도 하지 않은 컨텍스트는 데이터베이스 또는 다른 원격 리소스를 인스턴스화 등. 모듈에서 등의 작업을 초기화 하 고 이후의 함수에서 사용 하기 쉽습니다.

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"
    let dep3 = Random().Next() // Random is not thread-safe

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

이것은 자주 좋지 않습니다는 몇 가지 이유로:

첫째, 이렇게 하면 API 자체는 공유 상태에 기반한 있습니다. 예를 들어 여러 호출 스레드 수를 액세스 하려고는 `dep3` 값 (및 스레드로부터 안전 하지 않습니다). 둘째, 자체에서 코드 베이스로 응용 프로그램 구성을 푸시합니다. 이 큰 코드 베이스에 대 한 유지 관리 하기가 어렵습니다.

마지막으로 모듈을 초기화 전체 컴파일 단위에 대 한 정적 생성자로 컴파일합니다. 으로 매니페스트에 해당 모듈의 let 바인딩 값 초기화에서 오류가 발생 한 `TypeInitializationException` 다음 응용 프로그램의 전체 수명 동안 캐시 된 합니다. 이 진단이 어려울 수 있습니다. 일반적으로 내부 예외에 대 한 이유를 시작할 수 있습니다 하지만 없는 경우, 다음이 근본 원인을 란 합니다.

대신, 방금를 사용 하 여 간단한 클래스 종속성:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

이 통해 다음:

1. API 자체는 외부 종속 된 모든 상태를 푸시합니다.
2. 구성은 API 외부에서 이제 수행할 수 있습니다.
3. 종속 값에 대 한 초기화의 오류도 나타날 가능성이 없는 `TypeInitializationException`합니다.
4. API 테스트 이제 쉽습니다.

## <a name="error-management"></a>오류 관리

큰 시스템에서 오류 관리는 복잡 하 고 nuanced 노력 되며 시스템에 글머리 기호 결함 허용 및 잘 작동은 없습니다. 다음 지침 이동 어려운이 공간에 대 한 지침을 제공 해야 합니다.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>오류 사례 및 사용자의 도메인에 기본 형식에 잘못 된 상태를 나타냅니다

와 [구별 된 공용 구조체](../language-reference/discriminated-unions.md), F # 하면 형식 시스템에서 잘못 된 프로그램 상태를 나타낼 수 있는 기능입니다. 예를 들어:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

이 경우에 은행 계좌에서 돈을 맡 실패할 수 있는 알려진된 세 가지가 있습니다. 각 오류 사례는 형식에 표시 되 고 있으므로 처리할 수 있습니다 안전 하 게 프로그램 전체에서.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

일반적으로 다른 방법으로 모델링할 수 없습니다. 했을 수 **실패** 에 도메인에 다음 오류 처리 코드는 더 이상으로 처리 정기 프로그램 흐름 외에도 처리 해야 하는 것입니다. 단순히 일반 프로그램 흐름의 일부 이며 간주 되지 **예외적인**합니다. 이 두 가지 주요 이점이 있습니다.

1. 도메인 시간이 지남에 따라 변경 될 때 유지 관리 하는 것이 쉽습니다.
2. 오류 사례는 단위 테스트 하기 쉽습니다.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>오류 형식으로 표현할 수 없는 경우 예외를 사용 합니다.

문제 도메인에 모든 오류를 나타낼 수 있습니다. 이러한 종류의 오류는 *예외적인* 따라서 본질적으로 발생 하 고 F #에서 예외를 catch 하는 기능입니다.

첫째, 것이 좋습니다 읽어는 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)합니다. 이러한 F #에 적용 됩니다.

다음 기본 설정 순서에 예외를 발생 시키기 위해 F #에서 사용할 수 있는 기본 생성을 고려해 야 합니다.

| 함수 | 구문 | 용도 |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | 발생 한 `System.ArgumentNullException` 지정 된 인수 이름을 사용 합니다. |
| `invalidArg` | `invalidArg "argumentName" "message"` | 발생 한 `System.ArgumentException` 지정 된 인수 이름 및 메시지를 사용 합니다. |
| `invalidOp` | `invalidOp "message"` | 발생 한 `System.InvalidOperationException` 지정 된 메시지입니다. |
|`raise`| `raise (ExceptionType("message"))` | 예외를 throw 하는 범용 메커니즘입니다. |
| `failwith` | `failwith "message"` | 발생 한 `System.Exception` 지정 된 메시지입니다. |
| `failwithf` | `failwithf "format string" argForFormatString` | 발생 한 `System.Exception` 형식 문자열 및 해당 입력에 따라 메시지를 사용 합니다. |

사용 하 여 `nullArg`, `invalidArg` 및 `invalidOp` 시키려면 메커니즘으로 `ArgumentNullException`, `ArgumentException` 및 `InvalidOperationException` 적절 합니다.

`failwith` 및 `failwithf` 함수는 기본 발생 하므로 피해 야 일반적으로 `Exception` 특정 예외가 아닌를 입력 합니다. 기준으로 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)을 가능 하면 보다 구체적인 예외를 발생 합니다.

### <a name="using-exception-handling-syntax"></a>예외 처리 구문을 사용 하 여

F # 예외 패턴을 통해 지원는 `try...with` 구문:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

패턴 일치와 함께 예외가 발생할 때 수행 하는 기능을 조정 하는 코드를 완전 하 게 하려는 경우에 약간 까다로울 수 있습니다. 이 문제를 처리 한 방법으로 사용 하는 것 [활성 패턴](../language-reference/active-patterns.md) 자체 예외와 함께 오류 사례는 주변 그룹 기능을 하는 것입니다. 예를 들어, 예외를 throw 하는 경우 예외 메타 데이터에 중요 한 정보를 포함 하는 API 사용해 수 있습니다. 활성 패턴 내 캡처된 예외의 본문에 유용한 값을 래핑 해제 하 고 반환 값 일부 상황에서 도움이 될 수 있습니다.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Monadic 오류 바꿀 예외 처리를 사용 하지 마십시오

예외는 다소 taboo 함수형 프로그래밍에서으로 표시 됩니다. 실제로 예외가 not quite 기능 고려해 야 할 안전 하므로 순수한 정도 고을 위반 합니다. 그러나이 코드가 실행 해야 하 고 해당 런타임 오류가 발생할 수 있는 현실을 무시 합니다. 일반적으로 대부분 일은 순수 아니고 원하지 않는 상황을 최소화 하기 위해 총 가정 하에서 코드를 작성 합니다.

다음 측면을 고려해 코어 장점/예외의 관련성 및.NET 런타임 및 언어 간 환경에서 전체적으로 적합성에 대해을 고려해 야 합니다.

1. 문제를 디버깅할 때 매우 유용 자세한 진단 정보를 포함 합니다.
2. 런타임 및 다른.NET 언어에서 잘 이해 됩니다.
3. 중요 한 기본 구성 요소를 사용 되는 코드와 비교 했을 때를 줄일 수 *방지* 임시 별로 구문의 일부 하위 집합을 구현 하 여 예외입니다.

이 세 번째 점이 중요 합니다. Nontrivial 복잡 한 작업에 대 한 예외를 사용 하도록 못하면이 같은 구조를 처리할 때의 될 수 있습니다.

```fsharp
Result<Result<MyType, string>, string list>
```

오류 "형식의 stringly"에 패턴 일치와 같은 취약 한 코드를 쉽게 야기할 수 있는:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

또한 "더 좋은" 형식을 반환 하는 "단순" 함수에 대 한 desire에서 모든 예외를 무시 하 고 싶어 수 있습니다.

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

그러나 `tryReadAllText` 무수 한 파일 시스템에 발생할 수 있는 작업을 기반으로 하는 다양 한 예외를 throw 할 수 있습니다 및이 코드를 바로 삭제 수 실제로 될 무엇이 문제 환경에 대 한 정보입니다. 이 코드는 결과 형식으로 교체 하면 다음 하는 경우 "형식의 stringly" 오류 메시지를 구문 분석 이동:

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

배치 하는 예외 개체 자체에 `Error` 생성자 방금 호출 사이트에서 아닌 함수에서 예외 형식을를 제대로 처리 하지 않아도 되도록 합니다. 이 작업을 효과적으로 수행 API의 호출자로 다루기가 매우 재미 나오지 않은 확인 된 예외를 만듭니다.

Catch 하는 위의 예에서는 대신 *특정* 예외와 해당 예외의 컨텍스트에서 의미 있는 값을 반환 합니다. 수정 하는 경우는 `tryReadAllText` 다음과 같이 작동 `None` 자세한 의미가:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

범용으로 작동 하는 대신이 함수는 이제 제대로 처리 경우 파일을 찾을 수 없습니다 고 return에 해당 의미를 할당 합니다. 반환 값이 하지 모든 컨텍스트 정보를 삭제 하거나 호출자가 코드에서 해당 시점에 관련 되지 않을 수 있는 경우를 처리 하도록을 강제 적용 하는 동안 해당 오류 사례에 매핑할 수 있습니다.

와 같은 형식은 `Result<'Success, 'Error>` 여기서 중첩 되지 있습니다 하 고 F # 선택적 형식은 반송 없습니다 것 때 나타내기 위해 완벽 한 기본 작업에 적합 한 *문제가* 또는 *nothing*. 예외에 대 한 대체 하지는 하지만 하며 예외를 교체할 수에 사용할 해야 합니다. 대신, 적용 해야 하 신중 하 게 주소 예외와 오류 관리 정책의 특정 측면을 대상으로 지정 된 방식에서입니다.

## <a name="partial-application-and-point-free-programming"></a>부분 응용 프로그램 및 지점 필요 없는 프로그래밍

F # 지점 필요 없는 스타일 부분 응용 프로그램 이므로, 프로그램에 다양 한 방법으로 지원합니다. 이 모듈 또는 항목의 구현 내에서 코드 재사용에 게 도움이 될 수 있지만 이것은 일반적으로 공개적으로 노출 하도록 합니다. 일반적으로 프로그래밍 지점 필요 없는 자체로, 전문화 아니며 스타일에서 immersed 하지는 사용자를 위해 중요 한 cognitive 장벽을 추가할 수 있습니다. F #에서 프로그래밍 지점 필요 없는 숙련 된 수학적에 대 한 기본 이지만 람다 미적분 법에 익숙하지 않은 사용자를 위해 어려울 수 있습니다.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>부분 응용 프로그램 및 커리 공용 Api에서 사용 하지 마십시오

거의 예외와 함께 공용 Api에서 부분 응용 프로그램의 사용을 소비자에 대 한 혼동 될 수 있습니다. 일반적으로 `let`-F # 코드에 바인딩된 값은 **값**이 아니라 **함수 값**합니다. 와 같은 연산자와 결합 하는 경우에 특히 많은 양의 cognitive 오버 헤드의 교환으로 코드의 줄 수가 적은 저장 하는 중 발생할 수 있습니다 값, 함수 값을 함께 혼합 `>>` 함수를 작성 하 합니다.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>지점 필요 없는 프로그래밍에 대 한 도구 문제도 고려해

커리 된 함수 인수가 표시 되지 않습니다. 이 인해 tooling 영향을 줍니다. 다음 두 가지 기능을 고려 합니다.

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

유효한 함수에 모두 있지만 `funcWithApplication` 커리 된 함수입니다. 편집기에서 해당 형식을 마우스로 가리키면이 볼 수 있습니다.

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

호출 사이트에서 Visual Studio와 같은 도구에서 도구 설명을 제공 되지 것입니다 기능에 대 한 의미 있는 정보는 `string` 및 `int` 입력된 형식은 실제로 나타냅니다.

다음과 같은 코드 포인트 필요 없는 발생 하는 경우 `funcWithApplication` 즉 공개적으로 사용 될 것이 좋습니다 도구 수 사항에 인수에 대 한 의미 있는 이름을 하도록 전체 η 확장을 수행 합니다.

또한 지점 필요 없는 코드를 디버깅할 수 매우 어려울 수 거의 불가능 합니다. 이름에 바인딩된 값에 의존 하는 디버깅 도구 (예를 들어 `let` 바인딩) 실행을 통해 중간에 있는 중간 값을 검사할 수 있도록 합니다. 코드를 검사 하 값이 없는 때 디버깅 하는 일은 없습니다. 나중에 이전에 실행된 경로에 따라 이러한 값을 만드는 진화 할 수 디버깅 도구에서 사용자 선택 hedge 하는 것이 좋습니다 것만 *잠재적인* 디버깅 기능입니다.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>기술로 부분 응용 프로그램을을 내부 상용구를 줄이는 것이 좋습니다

이전 시점 달리 부분 응용 프로그램에는 응용 프로그램 또는 API의 깊은 내부 내부 상용구 줄이기 위한 매우 유용한 도구는입니다. 단위 테스트, 여기서 상용구는 종종 처리 하는 과정을 어렵게 더 복잡 한 Api의 구현에 대 한 유용할 수 있습니다. 예를 들어 다음 코드와 수행 하는 방법은 어떤 가장 모의 프레임 워크를 제공 이러한 프레임 워크에는 외부 종속성을 수행 하지 않고 고 API 맞춤식를 관련 배울 필요 합니다.

예를 들어 다음 솔루션 토폴로지:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` 와 같은 코드를 노출 될 수 있습니다.

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

단위 테스트 `Transactions.doTransaction` 에 `ImplementationLogic.Tests.fspoj` 쉽습니다.

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

부분적으로 적용 `doTransaction` 모의 개체 컨텍스트의 개체 때마다 모의 컨텍스트를 생성 하지 않고도 모든 단위 테스트에서 함수를 호출 수 있습니다.

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

이 방법은 전체 코드 베이스에 전체적으로 적용 하지 해야 하지만 복잡 한 내부 및 단위 테스트 해당 내부 구조에 대 한 기본 구성 요소를 줄이기 위해 좋은 방법입니다.

## <a name="access-control"></a>액세스 제어

F #에 여러 옵션이 [액세스 제어](../language-reference/access-control.md),.NET 런타임에서 사용할 수 있는에서 상속 합니다. 형식에만 사용할 수 없는-도 사용할 수 있습니다 이러한 함수에 대 한 합니다.

* 비-선호`public` 형식 및 공개적으로 사용할 수 있으려면 필요할 때까지 멤버입니다. 이 또한에 어떤 소비자 몇을 최소화
* 모든 도우미 기능을 유지 하기 위해 노력 `private`합니다.
* 사용 하 여 `[<AutoOpen>]` 도우미 함수 수많은 하 게 하는 경우 개인 모듈에 저장 합니다.

## <a name="type-inference-and-generics"></a>형식 유추 및 제네릭

형식 유추 상용구 많은 입력에서 저장할 수 있습니다. 및 사용자의 추가 작업 없이 거의 보다 일반적인 코드를 작성할 F # 컴파일러에서 자동 일반화 수 있습니다. 그러나 이러한 기능은 일반적으로 좋은있지 않습니다.

* 공용 Api에서 명시적 형식 인수 이름에 레이블을 지정 하 고이 대 한 형식 유추에 의존 하지 마십시오.

    이 대 한 이유는 **있습니다** 컴파일러가 아닌 해당 API의 모양 제어에 있어야 합니다. 컴파일러가 있습니다에 대 한 형식 유추에서 세밀 하 게 작업을 수행할 수, 이지만에 의존 하는 내부 형식 변경 되 면 API 변경의 모양이 있을 수 있습니다. 원하는 수도 있지만 대부분 다운스트림 소비자가 처리 하는 주요 API 변경 균형이 깨어 집니다. 대신, 공용 API의 모양의 명시적으로 제어 하는 경우 이러한 주요 변경 사항 제어할 수 있습니다. DDD 측면에서이 생각할 수 있습니다 바이러스 손상 계층으로 합니다.

* 제네릭 인수에 의미 있는 이름을 지정 하는 것이 좋습니다.

    특정 도메인에만 적용 되는 진정한 일반 코드를 작성 하는 경우가 아니면에서 작업 하는 도메인 이해 프로그래머에 의미 있는 이름을 수 있습니다. 예를 들어, 형식 매개 변수 라는 `'Document` 문서와 상호 작용의 컨텍스트에서 데이터베이스 사용 하면 명확 하 게 제네릭 문서 형식을 함수 또는 멤버를 사용 하는 허용 될 수 있습니다.

* 제네릭 형식 매개 변수 표시 방법이 PascalCase와 이름을 지정 하는 것이 좋습니다.

    이것이 하므로 snake_case 또는 camelCase 표시 방법이 PascalCase 대신를 사용 하는 것이 좋습니다..net에서는 작업을 수행 하는 일반적인 방법입니다.

마지막으로, 자동 일반화는 F # 또는 큰 코드 베이스를 처음 접하는 사용자를 위해 유용 하 게 합니다. 일반적인 구성 요소를 사용 하 여 cognitive 오버 헤드가 있습니다. 또한 자동으로 일반화 함수 (let 단독으로 사용 해서도 하려는 경우) 여러 입력된 형식으로 사용 되지 않는 경우 시간 해당 시점에 제네릭를 실질적인 이점은 없습니다. 작성 중인 코드 실제로 제네릭에서 이익을 얻을 경우 항상 고려 합니다.

## <a name="performance"></a>성능

F # 값은 특정 클래스 (특히 해당 관련 된 동시성 및 병렬 처리 수준) 버그의 수는 기본적으로 변경할 수 없습니다. 그러나 경우에 따라 실행 시간 또는 메모리 할당의 최적 (또는 심지어 합리적인) 효율성을 얻기 위해 작업의 범위 가장 잘 구현 될 수 있습니다 내부 변경 했습니다. 상태를 사용 하 여 합니다. F #으로 옵트인 방식에서 가능는 `mutable` 키워드입니다.

그러나 사용 `mutable` F #에서 기능 순도 되었는데 느낄 수 있습니다. 순도 하 게 조정 하는 경우에 문제가 [참조 투명도](https://en.wikipedia.org/wiki/Referential_transparency)합니다. 참조 투명도-순도-F # 함수를 작성할 때 최종 목표는 합니다. 이 옵션을 사용 하면 성능에 중요 코드에 대 한 변환이 기반 구현을 통해 기능 인터페이스를 작성 수 있습니다.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>변경할 수 없는 인터페이스에서 변경할 수 있는 코드 줄 바꿈

이 목표를으로 참조 투명 성능이 중요 한 기능 변경 가능한 언더 벨 리를 노출 하지 않는 코드를 작성 하려면 중요 합니다. 예를 들어 다음 코드 구현 하는 `Array.contains` 함수에는 F # 핵심 라이브러리:

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

이 함수를 여러 번 호출 원본으로 사용 하 여 배열에는 변경 되지 않습니다 요구 하지도 않습니다 사용에서 변경할 수 있는 모든 상태를 유지 관리할 수 있습니다. 내 코드의 거의 모든 줄 변환이 사용 하는 경우에 것 참조가 투명 합니다.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>변경할 수 있는 클래스의에서 데이터를 캡슐화 하는 것이 좋습니다.

변경할 수 있는 데이터를 사용 하 여 작업을 캡슐화 하는 단일 함수를 사용 하는 앞의 예제. 항상 더 복잡 한 데이터 집합에 대 한 충분 한 있는 이것은 아닙니다. 다음 함수 집합을 고려 합니다.

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

이 코드는 성능이 나 하지만 호출자가 유지 관리 해야 남겨지고 기반 데이터 구조를 표시 하기. 이 변경 될 수 있는 기본 멤버 없이 클래스 내부 줄 바꿈할 수 있습니다.

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

`Closure1Table` 활용 하지 않는 기본 데이터 구조를 유지 하기 위해 호출자가 강제 적용 하면 기본 남겨지고 기반 데이터 구조를 캡슐화 합니다. 클래스는 데이터와 호출자에 게 세부 정보를 노출 하지 않고 남겨지고 기반 되는 루틴을 캡슐화 하는 강력한 방법을입니다.

### <a name="prefer-let-mutable-to-reference-cells"></a>원하는 `let mutable` 참조 셀

참조 셀은 자체의 값이 아닌 값에 대 한 참조를 나타낼 수 있습니다. 성능에 중요 코드에 대해 사용할 수 있습니다, 있지만 일반적으로 권장 되지 않습니다. 다음 예제를 참조하세요.

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

이제는 참조 셀 사용 "오염" 모든 후속 코드를 역참조 하 고 기본 데이터를 다시 참조 해야 합니다. 대신, `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

람다 식 중간에 남겨지고 단일 지점 외에도 다른 모든 코드를 건드리면 `acc` 더 일반적인의 사용량을 다른 방식으로 그렇게 할 수 `let`-바인딩된 변경할 수 없는 값입니다. 이 쉽게 바뀔 수 있습니다.

## <a name="object-programming"></a>개체 프로그래밍

F # 개체 및 개체 지향 (개체 지향) 개념에 대 한 완전 한 지원을 제공 합니다. 여러 개체 지향 개념 강력 하 고 유용 하지만, 그 중 일부만 사용 하기에 적합 합니다. 다음 목록에서는 상위 수준 개체 지향 기능 범주에 대 한 지침을 제공합니다.

**다양 한 상황에서 이러한 기능을 사용 하는 것이 좋습니다.**

* 점 표기법 (`x.Length`)
* 인스턴스 멤버
* 암시적 생성자
* 정적 멤버
* 인덱서 표기법 (`arr.[x]`)
* 명명 된 인수와 선택적 인수
* 인터페이스 및 인터페이스 구현

**이러한 기능에 대해 먼저 도달 하지 않는 있지만 문제를 해결 하기 편리 하 게 될 때 적용할 주의 해 서 수행:**

* 메서드 오버로드
* 변경할 수 있는 데이터를 캡슐화합니다.
* 형식에 연산자
* 자동 속성
* 구현 `IDisposable` 및 `IEnumerable`
* 형식 확장명
* 이벤트
* 구조체
* 대리자
* 열거형

**일반적으로 사용 해야 하지 않는 한 이러한 기능을 하지 말아야 합니다.**

* 구현 상속 및 상속 기반 형식 계층 구조
* Null 및 `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>컴퍼지션 상속 보다 선호

[상속을 통해 컴퍼지션](https://en.wikipedia.org/wiki/Composition_over_inheritance) 좋은 F # 코드 수를 준수 하는 오래 된 관용구가 있습니다. 기본 원칙은 해야 하지는 기본 클래스를 노출 하는 기능을 활용 하려면의 기본 클래스에서 상속 하는 호출자를 강제로 것입니다.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>개체 식을 사용 하 여 클래스를 필요 하지 않으면 인터페이스를 구현 합니다.

[개체 식](../language-reference/object-expressions.md) 클래스 내부 작업을 수행 하지 않고도 값에 구현 된 인터페이스를 바인딩할 즉석에서 인터페이스를 구현할 수 있습니다. 이 편리 하 고 경우에 특히 있습니다 _만_ 전체 클래스에 대 한 필요 없는 인터페이스를 구현 해야 합니다.

예를 들어 다음은에서 실행 되는 코드 [Ionide](http://ionide.io/) 지원 하지 않는 기호를 추가한 경우 코드 수정 동작을 제공 하는 `open` 에 대 한 문:

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

개체 식 필요는 없습니다 클래스에 대 한 Visual Studio 코드 API와 상호 작용할 때, 되므로이 이상적인 도구입니다. 단위 테스트, 테스트 루틴을 사용 하 여 인터페이스에서 특별 한 방식으로 추출할 하려는 경우 유용할 수도 있습니다.

## <a name="type-abbreviations"></a>형식 약어

[형식 약어](../language-reference/type-abbreviations.md) 함수 서명 또는 더 복잡 한 형식 등의 다른 형식에 레이블을 지정 하는 편리한 방법입니다. 별칭은 레이블을 계산을 정의 하는 데 필요한 항목을 할당 하는 예를 들어 [CNTK](https://www.microsoft.com/cognitive-toolkit/), 라이브러리 학습 깊습니다.

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

`Computation` 이름은 시그니처와 일치 하는 것이 별칭을 지정 하는 모든 함수를 표시 하는 편리한 방법입니다. 다음과 같은 형식 약어를 사용 하 여 편리 하 고 불필요 한 코드 허용 합니다.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>도메인을 나타내기 위해 형식 약어를 사용 하지 마십시오

형식 약어를 함수 서명에 이름을 지정 하는 데 편리 하지만은 혼동 될 수 있습니다 다른 종류를 단축 하는 경우. 이 약어를 고려 합니다.

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

여러 가지 방법으로 혼동 될 수 있습니다.

* `BufferSize` 추상화; 않습니다. 정수에 대 한 또 다른 이름입니다.
* 경우 `BufferSize` 노출 되는 공용 API에서 것 쉽게 잘못 해석 될 수을 보다 더 의미 `int`합니다. 일반적으로 도메인에 있는 특성이 여러 개 있을 형식과 같은 기본 형식이 아닌 `int`합니다. 이 약어 아니라고를 위반합니다.
* 대/소문자 `BufferSize` (표시 방법이 PascalCase) 의미이 이와 같은 더 많은 데이터를 보유 합니다.
* 이 별칭 비교 함수에 대 한 명명 된 인수를 제공 하는 증가 선명도 제공 하지 않습니다.
* 약어 컴파일된 IL;에서 매니페스트 되지 않습니다. 정수 이므로이 별칭은 컴파일 타임 구문.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

요약 하자면, 형식 약어와 문제는 이들이 **하지** 이니셜는 형식에 대 한 추상화입니다. 이전 예에서 `BufferSize` 단지는 `int` 없는 추가 데이터 또는 기능 외에도 유형 시스템 으로부터 장점으로 내부적으로 `int` 에 이미 있습니다.