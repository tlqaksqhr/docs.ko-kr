---
title: 'F # 코드 서식 지정 지침'
description: 'F # 코드 서식 지정에 대 한 지침을 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 9c6e80509e9a5654e6514674d38c02e2a6b44e37
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935939"
---
# <a name="f-code-formatting-guidelines"></a>F # 코드 서식 지정 지침

이 문서는 F # 코드 되도록 프로그램 코드의 서식을 지정 하는 방법에 대 한 지침을 제공 합니다.

* 일반적으로 보다 쉽게 읽을 것으로 간주
* Visual Studio의 도구 및 다른 편집기를 지정 하 여 적용 되는 규칙에 따라는
* 다른 온라인으로 코드와 유사

다음이 지침에 기반한 [F # 서식 지정 규칙에 대 한 포괄적인 지침](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 하 여 [Anh 똥 Phan](https://github.com/dungpa)합니다.

## <a name="general-rules-for-indentation"></a>들여쓰기에 대 한 일반 규칙

F # 기본적으로 유효 공백 문자를 사용합니다. 다음 지침을 적용할 수이 하는 몇 가지 과제를 다루어야 하는 방법에 대 한 지침을 제공 하려는.

### <a name="using-spaces"></a>공간 사용

들여쓰기가 필요한 경우 공백, 탭 하지 사용 해야 합니다. 하나 이상의 공간이 필요 합니다. 조직에 들여쓰기;에 사용할 공백 수를 지정 하는 코딩 표준을 만들 수 있습니다. 2, 3 또는 4 개의 공백 들여쓰기 발생 하는 각 수준에서 들여쓰기 하는 것이 일반적입니다.

**들여쓰기 당 4 개의 공백을 사용 하는 것이 좋습니다.**

즉, 프로그램의 들여쓰기는 주관적입니다. 변형 좋은지 이지만 첫 번째 규칙을 따라야 *들여쓰기 일관성*합니다. 들여쓰기의 일반적으로 허용 되는 스타일을 선택 하 고 코드 베이스 전체에서 체계적으로 사용 합니다.

## <a name="formatting-blank-lines"></a>빈 줄을 서식 지정

* 별도 최상위 함수 및 클래스 정의 두 개의 빈 줄을 사용 하 여 합니다.
* 클래스 내의 메서드 정의 비어 있는 단일 선으로 구분 됩니다.
* 빈 줄을 별도의 관련 된 기능 그룹 (제한적) 사용할 수 있습니다. 다양 한 관련된 one-liner (예를 들어, 구현 집합을 더미) 사이의 빈 줄을 생략할 수 있습니다.
* 논리적 섹션을 나타내기 위해 함수에서 빈 줄을 제한적으로 사용 합니다.

## <a name="formatting-comments"></a>주석 형식

일반적으로 기계 학습 스타일 블록 주석 통해 여러 이중 슬래시 주석을 선호 합니다.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

인라인 주석을 첫 번째 글자를 대문자로 표시 해야 합니다.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>명명 규칙

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>CamelCase를 사용 하 여 클래스 바인딩, 바인딩 식 및 패턴 바인딩된 값 및 함수에 대 한

일반적인 되며 모든 이름에 대 한 camelCase를 사용 하도록 허용 된 F # 스타일 바인딩된 지역 변수 또는 패턴 일치에 함수 정의입니다.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

클래스에 바인딩된 로컬로 함수도 camelCase를 사용 해야 합니다.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>CamelCase를 사용 하 여 모듈 바인딩된 공용 함수에 대 한

모듈 바인딩된 함수는 공용 API의 일부 이면 camelCase 사용 해야 합니다.

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>CamelCase를 사용 하 여 내부 및 개인 모듈 바인딩된 값 및 함수에 대 한

다음을 포함 하 여 개인 모듈 바인딩된 값에 대 한 camelCase를 사용 합니다.

* 스크립트의 임시 함수

* 값 형식 또는 모듈의 내부 구현을 구성

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>CamelCase를 사용 하 여 매개 변수

모든 매개 변수는.NET 명명 규칙에 따라 camelCase를 사용 해야 합니다.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>PascalCase를 사용 하 여 모듈에 대 한

모든 모듈 (예: 최상위, 내부, 개인, 중첩 된) PascalCase를 사용 해야 합니다.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>형식 선언, 멤버 및 레이블을 사용 하 여 PascalCase

클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구분 된 공용 구조체 모든 PascalCase로 명명 해야 합니다. 형식 및 레코드 및 구분 된 공용 구조체에 대 한 레이블 내에서 멤버 PascalCase 사용 해야 합니다.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>PascalCase를 사용 하 여.NET으로 내장 되는 구문에 대 한

네임 스페이스, 예외, 이벤트 및 프로젝트 /`.dll` 이름을 PascalCase에도 사용 해야 합니다. 뿐만 아니라 소비자에 게 자연스럽 게 느낄 다른.NET 언어에서 소비 되셨나요, 그리고 발생할 가능성이 있는.NET 명명 규칙에 부합 합니다.

### <a name="avoid-underscores-in-names"></a>이름에 밑줄을 방지 합니다.

지금까지 일부 F # 라이브러리 이름에 밑줄을 사용 했습니다. 그러나이 더 이상 광범위 하 게 수락 되 면.NET 명명 규칙을 사용 하 여 충돌 하기 때문입니다. 즉, 일부 F # 프로그래머가 사용 하 여 밑줄 많이, 부분적으로 기록 상의 용도로 허용 오차 존경 하는 것이 중요 합니다. 그러나 사용할 것인지 선택할 수 있는 다른 사용자가 스타일은 종종 싫는 주의 합니다.

밑줄을 매우 자주 네이티브 구성 요소와의 상호 운용 하는 몇 가지 예외 포함 되어 있습니다.

### <a name="use-standard-f-operators"></a>표준 F # 연산자를 사용 합니다.

다음 연산자를 F # 표준 라이브러리에 정의 되어 있고 해당 항목을 정의 하는 대신 사용 해야 합니다. 더 읽기 쉽고 자연 스러운 코드를 확인 하는 경향이 있습니다 이러한 연산자를 사용 하 여 것이 좋습니다. OCaml 또는 다른 함수형 프로그래밍 언어에서 배경의 개발자가 익숙한 다른 관용구를 수 있습니다. 다음 목록에는 권장 되는 F # 연산자 요약 되어 있습니다.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>제네릭에 대 한 접두사 구문을 사용 하 여 (`Foo<T>`) 후 위 구문 보다 우선적으로 (`T Foo`)

F # 제네릭 형식 명명 모두는 후 위 ML 스타일을 상속 합니다. (예를 들어 `int list`)와.NET 스타일 접두사 (예를 들어, `list<int>`). 네 개의 특정 형식 제외 하 고.NET 스타일을 선호 합니다.

1. F # 목록에서는, 후 위 형식 사용: `int list` 대신 `list<int>`합니다.
2. F # 옵션에 대해 후 위 형식 사용: `int option` 대신 `option<int>`합니다.
3. F # 배열의 경우 구문 이름을 사용 하 여 `int[]` 대신 `int array` 또는 `array<int>`합니다.
4. 참조 셀에 대 한 사용 `int ref` 대신 `ref<int>` 또는 `Ref<int>`합니다.

다른 모든 형식에 대 한 접두사 형식을 사용 합니다.

## <a name="formatting-tuples"></a>튜플 형식

튜플 인스턴스화를 괄호로 묶고 고 내의 구분 쉼표 뒤에 야 공백, 예: `(1, 2)`, `(x, y, z)`합니다.

튜플 패턴 일치에서 괄호를 생략 하려면 일반적으로 허용 됩니다.

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a>구별 된 공용 구조체 선언 서식 지정

들여쓰기 `|` 4 개의 공백 사용 하 여 형식 정의에서:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>구별 된 공용 구조체 형식

여러 줄에 분할 된 인스턴스화된 구별 된 공용 구조체 들여쓰기를 사용 하 여 새 범위를 포함 된 데이터를 제공 해야 합니다.

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

닫는 괄호를 새 줄 수도 있습니다.

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>서식 레코드 선언

들여쓰기 `{` 형식에서 4로 정의 공백 및 필드 목록 같은 줄에서 시작 합니다.

```fsharp
// OK
type PostalAddress =
    { Address : string
      City : string
      Zip : string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address : string
    City : string
    Zip : string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
// Unusual in F#
type PostalAddress =
    { 
        Address : string
        City : string
        Zip : string
    }
```

열기 토큰을 새 줄에 닫는 토큰과 같은 줄 배치도 정상 이지만 사용 해야 합니다 [자세한 구문](../language-reference/verbose-syntax.md) 멤버를 정의 (의 `with` 키워드):

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address : string
    City : string
    Zip : string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a>레코드 형식

짧은 레코드는 한 줄에 작성할 수 있습니다.

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

오래 된 레코드는 레이블에 대 한 새 줄을 사용 해야 합니다.

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

새 줄에 닫는 토큰과 같은 줄에 여 토큰을 배치 해도 됩니다.

```fsharp
let rainbow = {
    Boss1 = "Jeffrey"
    Boss2 = "Jeffrey"
    Boss3 = "Jeffrey"
    Boss4 = "Jeffrey"
    Boss5 = "Jeffrey"
    Boss6 = "Jeffrey"
    Boss7 = "Jeffrey"
    Boss8 = "Jeffrey"
    Lackeys = ["Zippy"; "George"; "Bungle"]
}
```

목록 및 배열 요소에 대 한 동일한 규칙이 적용 됩니다.

## <a name="formatting-lists-and-arrays"></a>서식 지정 목록 및 배열

쓰기 `x :: l` 주위에 공백을 사용 하 여는 `::` 연산자 (`::` 는 공백으로 둘러싸인 따라서 중 위 연산자,) 및 `[1; 2; 3]` (`;` 는 구분 기호, 공백 뒤에 있으므로).

항상 두 명의 고유 중괄호 같은 연산자 사이 하나 이상의 공백을 사용 합니다. 예를 들어 사이 공백을 둡니다를 `[` 및 `{`합니다.

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

목록 및 여러 줄 분할 되는 배열 레코드와 마찬가지로 비슷한 규칙을 따릅니다.

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>경우에 형식 지정 식

조건문의 들여쓰기 구성 하는 식의 크기에 따라 달라 집니다. 하는 경우 `cond`, `e1` 및 `e2` 짧은, 한 줄에 작성 하면 됩니다.

```fsharp
if cond then e1 else e2
```

경우 `cond`, `e1` 또는 `e2` 더 있지만 여러 줄 없습니다.

```fsharp
if cond
then e1
else e2
```

식이 있는 경우 여러 줄:

```fsharp
if cond then
    e1
else
    e2
```

사용 하 여 여러 가지 조건을 `elif` 하 고 `else` 와 동일한 범위에서 들여쓰기가 적용 되는 `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>패턴 일치 하는 구문

사용 된 `|` 없습니다 들여쓰기를 사용 하 여 일치 하는 각 절에 대 한 합니다. 식 짧은 경우 각 하위 식에 간단한 이기도 한 경우는 단일 선을 사용을 고려할 수 있습니다.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

패턴 일치 화살표 오른쪽의 식이 너무 큰 경우 들여쓰기 한 단계에서 다음 줄으로 이동 합니다 `match` / `|`합니다.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

패턴 일치 익명 함수에 의해 시작 `function`을 해야 일반적으로 들여쓰지 멀리 합니다. 예를 들어, 한 범위를 다음과 같이 들여쓰기 괜찮습니다.

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

패턴에서 정의 된 함수에서 일치 `let` 또는 `let rec` 시작 후 들여쓰기 4 공간을 사용 해야 `let`경우에 `function` 키워드가 사용:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

화살표를 정렬 하는 것은 좋지 않습니다.

## <a name="formatting-trywith-expressions"></a>서식 지정 시도 / 식을 사용 하 여

예외 형식에 패턴 일치와 같은 수준에서 써야 `with`합니다.

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>서식 지정 함수에 대 한 매개 변수 응용 프로그램

일반적으로 대부분의 함수 매개 변수 응용 프로그램 같은 줄에서 수행 됩니다.

새 줄에 함수에 매개 변수를 적용 하려는 경우 하나의 범위로 들여씁니다.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

동일한 지침이 함수 인수로 람다 식에 적용 됩니다. 범위를 하나 만큼 들여씁니다 본문 람다 식의 본문에서 다른 줄에 넣을 수 있는 경우

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

그러나 둘 이상의 줄 람다 식의 본문을 사용 하는 경우 별도 함수에 팩터링 하는 것이 좋습니다 보다 단일 인수로 함수에 적용 하는 여러 줄 구문입니다.

### <a name="formatting-infix-operators"></a>서식 지정 중 위 연산자

공백 사용 하 여 별도 연산자입니다. 이 규칙에 확실 한 예외는 `!` 고 `.` 연산자.

중 위 식은 다음과 같습니다. 확인에 동일한 열 목록

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>파이프라인 연산자를 서식 지정

파이프라인 `|>` 연산자에서 작동 하는 식 아래에 있는 이동 해야 합니다.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>모듈을 서식 지정

로컬 모듈의 코드 모듈을 기준으로 써야 하지만 최상위 모듈에는 코드를 들여쓰지 해야 합니다. Namespace 요소 들여쓰기 될 필요가 없습니다.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>서식 개체 식 및 인터페이스

개체 식 및 인터페이스는 동일한 방식으로 정렬 해야 합니다 `member` 4 개의 공백을 후 들여쓰기 되 고 있습니다.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>식에서 공백 서식 지정

F # 식에 불필요 한 공백을 사용 하지 않습니다.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

명명 된 인수도 없어야 공간 관련 된 `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
