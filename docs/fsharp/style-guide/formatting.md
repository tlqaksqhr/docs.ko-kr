---
title: 'F # 코드 formattin 지침'
description: 'F # 코드의 서식을 지정 하기 위한 지침에 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: e5c700ca9ae3968243f11c1237b9e4b26e580dcf
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="f-code-formatting-guidelines"></a>F # 코드 지침 서식 지정

이 문서에서는 코드의 서식을 지정 하 여 F # 코드는 하는 방법에 대 한 지침을 제공 합니다.

* 일반적으로 보다 쉽게 읽을로 표시
* Visual Studio의 도구 및 다른 편집기를 지정 하 여 적용 하는 규칙을 따르는 것입니다.
* 다른 온라인으로 코드와 유사한

다음이 지침에 따라 [F # 형식 지정 규칙에 대 한 포괄적인 지침](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 여 [Anh 똥 Phan](https://github.com/dungpa)합니다.

## <a name="general-rules-for-indentation"></a>들여쓰기에 대 한 일반 규칙

F # 유효한 공백 기본적으로 사용합니다. 다음 지침은이 적용할 수는 몇 가지 과제 사용 해야 하는 방법에 대 한 지침을 제공 하는 데 사용 됩니다.

### <a name="using-spaces"></a>공간 사용

들여쓰기 요구 되는 경우 탭이 아니라 공백을 사용 해야 합니다. 하나 이상의 공간이 필요 합니다. 조직은 들여쓰기;에 사용할 공백 수를 지정 하려면 코딩 표준을 만들 수 있습니다. 들여쓰기 들여쓰기가 필요한 경우 각 수준에 2, 3 또는 4 개의 공백을 일반적입니다.

**들여쓰기 당 4 개의 공백을 사용 하는 것이 좋습니다.**

즉, 프로그램의 들여쓰기는 주관적인 문제. 변형 [확인]을 있지만 따라야 하는 첫 번째 규칙은 *들여쓰기의 일관성*합니다. 들여쓰기의 일반적으로 허용 되는 스타일을 선택 하면 코드 베이스에서 체계적으로 사용 합니다.

## <a name="formatting-discriminated-union-declarations"></a>구별 된 공용 구조체 선언 서식 지정

들여쓰기 `|` 4 공백 사용 하 여 형식 정의에:

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

여러 줄에 의해 분할 되는 인스턴스화된 구별 된 공용 구조체 오목한 부분이 있는 새 범위를 포함 된 데이터를 제공 해야 합니다.

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

새 줄에 닫는 괄호를 실행할 수도 있습니다.

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a>튜플 형식 지정

튜플 인스턴스화 괄호로 묶고 고 내에서 구분 쉼표 뒤에 야 단일 공백, 예: `(1, 2)`, `(x, y, z)`합니다.

일반적으로 허용 되는 예외는 튜플 패턴 일치에서 괄호를 생략 하는 것입니다.

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>레코드 형식 지정

한 줄에 짧은 레코드를 작성할 수 있습니다.

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

## <a name="formatting-lists-and-arrays"></a>Lists와 arrays 서식 지정

쓰기 `x :: l` 주위에 공백이 있는 `::` 연산자 (`::` 공간 따라서 둘러싸인 않은 중 위 연산자가) 및 `[1; 2; 3]` (`;` 따라서 뒤에 공백이 구분 기호가).

항상 두 명의 고유 중괄호와 비슷한 연산자 사이 하나 이상의 공백을 사용 합니다. 예를 들어 사이 공백을 두고는 `[` 및 `{`합니다.

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

목록 및 여러 줄에 의해 분할 되는 배열 레코드와 마찬가지로 유사한 규칙을 따르십시오.

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

조건문의 들여쓰기를 구성 하는 식의 크기에 따라 달라 집니다. 경우 `cond`, `e1` 및 `e2` 은 작은 단순히 한 줄에 쓸지:

```fsharp
if cond then e1 else e2
```

경우 `e1` 및 `cond` 은 작은 하지만 `e2` 큽니다.

```fsharp
if cond then e1
else
    e2
```

경우 `e1` 및 `cond` 큰 및 `e2` 작습니다.

```fsharp
if cond then
    e1
else e2
```

모든 식은 큰 경우:

```fsharp
if cond then
    e1
else
    e2
```

와 여러 가지 조건을 `elif` 및 `else` 와 동일한 범위에서 들여쓰기는 `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>패턴 일치 하는 구문

사용 하 여 한 `|` 없는 오목한 부분이 있는 일치 항목의 각 절에 대 한 합니다. 식이 짧은 경우에 한 줄을 사용할 수 있습니다.

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

// OK
match l with [] -> false | _ :: _ -> true
```

패턴 일치 화살표 오른쪽의 식이 너무 클 경우 다음 줄에서 한 단계를 보다 한 수준된으로 이동 된 `match` / `|`합니다.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

패턴 일치에서 시작 하는 익명 함수 `function`, 해야 일반적으로 들여쓰지 너무 멀리 떨어져 있습니다. 예를 들어 한 범위를 다음과 같이 들여쓰기 됩니다.

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

패턴에 정의 된 함수에서 일치 `let` 또는 `let rec` 의 시작한 후 들여쓰기 된 4 개의 공백을 해야 `let`경우에 `function` 키워드를 사용:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

화살표를 정렬 하는 것은 좋지 않습니다.

## <a name="formatting-trywith-expressions"></a>서식 지정 try / 식을 사용 하 여

예외 형식에 패턴 일치와 같은 수준에 써야 `with`합니다.

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

## <a name="formatting-function-parameter-application"></a>함수 매개 변수 응용 프로그램을 서식 지정

일반적으로 대부분의 함수 매개 변수 응용 프로그램 같은 줄에서 수행 됩니다.

새 줄에 함수에 매개 변수를 적용 하려는 경우 한 범위 하 여 들여씁니다.

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

익명 함수 인수는 다음 줄에서 또는 현 수와 가능 `fun` 인수 줄에:

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a>서식 지정 중 위 연산자

공백 사용 하 여 별도 연산자입니다. 이 규칙에 대 한 확실 한 예외는는 `!` 및 `.` 연산자입니다.

중 위 식이란 확인에 동일한 열에는 목록:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>파이프라인 연산자를 형식 지정

파이프라인 `|>` 에 작업 중인 식 바로 아래 줄의 시작 될 때까지 유지 되어야 합니다.

```fsharp
// OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
               |> List.ofArray
               |> List.map (fun assm -> assm.GetTypes())
               |> Array.concat
               |> List.ofArray
               |> List.map (fun t -> t.GetMethods())
               |> Array.concat

// OK, but prefer previous
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

### <a name="formatting-modules"></a>서식 지정 모듈

로컬 모듈의 코드 모듈을 기준으로 써야 있지만 최상위 모듈에 코드를 들여쓰지 해야 합니다. Namespace 요소 들 여 쓰도록 필요가 없습니다.

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

### <a name="formatting-object-expressions-and-interfaces"></a>개체 식 및 인터페이스 서식 지정

개체 식 및 인터페이스 정렬 하는 같은 방식으로 `member` 4 개의 공백을 후 들여쓰기 되 고 있습니다.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>식에는 공백 서식 지정

F # 식에서 불필요 한 공백을 사용 하지 마십시오.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

명명 된 인수도 없어야 공간 둘러싼는 `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a>빈 줄에 서식 지정

* 별도 최상위 함수 및 클래스 정의 두 개의 빈 줄만 작성 합니다.
* 클래스 내의 메서드 정의 단일 줄으로 구분 됩니다.
* 빈 줄을 별도의 관련 된 기능 그룹 (드물게) 사용할 수 있습니다. 다양 한 관련된 one-liners (예를 들어 더미 구현 집합) 사이의 빈 줄을 생략할 수 있습니다.
* 논리적 섹션을 나타내기 위해 함수에서 빈 줄을 제한적으로 사용, 사용 합니다.

## <a name="formatting-comments"></a>서식 주석

일반적으로 ML 스타일 블록 주석을 통해 여러 이중 슬래시 의견을 선호 합니다.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

인라인 주석 첫 번째 글자를 대문자로 지정 해야 합니다.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>명명 규칙

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>CamelCase 클래스 바인딩, 바인딩 식 및 패턴 바인딩된 값 및 함수에 대 한 사용

일반적인 바인딩되고 camelCase 모든 이름에 대해 사용 하도록 허용 된 F # 스타일 또는 패턴 일치 및 함수 정의에 지역 변수입니다.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

클래스의 바인딩된 로컬로 함수 camelCase 또한 사용 해야 합니다.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>CamelCase를 사용 하 여 내부 및 개인 모듈 바인딩된 값 및 함수에 대 한

다음을 포함 하는 개인 모듈 바인딩된 값에 대 한 camelCase를 사용 합니다.

* 스크립트에서 임시 함수

* 형식 또는 모듈의 내부 구현을 구성 하는 값

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="avoid-underscores-in-names"></a>이름에 밑줄이 방지

지금까지 일부 F # 라이브러리 이름에 밑줄을 사용 했습니다. 그러나이 더 이상 광범위 하 게 수락 거의.NET 명명 규칙와 충돌 하기 때문입니다. 즉, 일부 F # 프로그래머가 사용 밑줄 과도 하 게, 부분적으로 지금 및 내결함성 및 존중이 중요 합니다. 그러나 다른 사용 여부에 대 한 선택 옵션이 사용자 스타일은 종종 사이가 있는지 알아야 합니다.

일부 예외는 밑줄을 매우 자주 네이티브 구성 요소와의 상호 운용 포함 되어 있습니다.

### <a name="use-standard-f-operators"></a>표준 F # 연산자를 사용 하 여

다음과 같은 연산자 F # 표준 라이브러리에 정의 되 고 해당 항목을 정의 하는 대신 사용 해야 합니다. 이러한 연산자를 사용 하 여 코드를 더 쉽게 읽고 관용구는 것으로 확인 하는 대로 좋습니다. 백그라운드 OCaml 또는 다른 함수형 프로그래밍 언어에서 개발자가 익숙한 다른 관용구 수 있습니다. 다음 목록에는 권장 되는 F # 연산자 요약 되어 있습니다.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>제네릭에 대 한 접두사 구문을 사용 하 여 (`Foo<T>`) 후 위 구문 대신 (`T Foo`)

F # 제네릭 형식 명명의 두는 후 위 ML 스타일을 상속 합니다. (예를 들어 `int list`) 접두사.NET 스타일 뿐만 아니라 (예를 들어 `list<int>`). .NET 스타일 4 개의 특정 형식 제외 하 고 선호 합니다.

1. 후 위 형태를 사용 하 여 F # 목록에 대 한: `int list` 대신 `list<int>`합니다.
2. F # 옵션에 대해 후 위 형태를 사용 하 여: `int option` 대신 `option<int>`합니다.
3. F # 배열에 대해 구문 이름을 사용 하 여 `int[]` 대신 `int array` 또는 `array<int>`합니다.
4. 사용 하 여 참조 셀에 대 한 `int ref` 대신 `ref<int>` 또는 `Ref<int>`합니다.

다른 모든 형식에 대 한 전위 형태를 사용 합니다.