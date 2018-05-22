---
title: 'F # 코드 지침 서식 지정'
description: 'F # 코드의 서식을 지정 하기 위한 지침에 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 1433b6891a6a0ddcdc082c141365ae54fa40c27b
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="61741-103">F # 코드 지침 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-103">F# code formatting guidelines</span></span>

<span data-ttu-id="61741-104">이 문서에서는 코드의 서식을 지정 하 여 F # 코드는 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="61741-105">일반적으로 보다 쉽게 읽을로 표시</span><span class="sxs-lookup"><span data-stu-id="61741-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="61741-106">Visual Studio의 도구 및 다른 편집기를 지정 하 여 적용 하는 규칙을 따르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="61741-107">다른 온라인으로 코드와 유사한</span><span class="sxs-lookup"><span data-stu-id="61741-107">Similar to other code online</span></span>

<span data-ttu-id="61741-108">다음이 지침에 따라 [F # 형식 지정 규칙에 대 한 포괄적인 지침](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 여 [Anh 똥 Phan](https://github.com/dungpa)합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="61741-109">들여쓰기에 대 한 일반 규칙</span><span class="sxs-lookup"><span data-stu-id="61741-109">General rules for indentation</span></span>

<span data-ttu-id="61741-110">F # 유효한 공백 기본적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-110">F# uses significant whitespace by default.</span></span> <span data-ttu-id="61741-111">다음 지침은이 적용할 수는 몇 가지 과제 사용 해야 하는 방법에 대 한 지침을 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="61741-112">공간 사용</span><span class="sxs-lookup"><span data-stu-id="61741-112">Using spaces</span></span>

<span data-ttu-id="61741-113">들여쓰기 요구 되는 경우 탭이 아니라 공백을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="61741-114">하나 이상의 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-114">At least one space is required.</span></span> <span data-ttu-id="61741-115">조직은 들여쓰기;에 사용할 공백 수를 지정 하려면 코딩 표준을 만들 수 있습니다. 들여쓰기 들여쓰기가 필요한 경우 각 수준에 2, 3 또는 4 개의 공백을 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="61741-116">**들여쓰기 당 4 개의 공백을 사용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="61741-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="61741-117">즉, 프로그램의 들여쓰기는 주관적인 문제.</span><span class="sxs-lookup"><span data-stu-id="61741-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="61741-118">변형 [확인]을 있지만 따라야 하는 첫 번째 규칙은 *들여쓰기의 일관성*합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="61741-119">들여쓰기의 일반적으로 허용 되는 스타일을 선택 하면 코드 베이스에서 체계적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="61741-120">구별 된 공용 구조체 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-120">Formatting discriminated union declarations</span></span>

<span data-ttu-id="61741-121">들여쓰기 `|` 4 공백 사용 하 여 형식 정의에:</span><span class="sxs-lookup"><span data-stu-id="61741-121">Indent `|` in type definition by 4 spaces:</span></span>

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

<span data-ttu-id="61741-122">여러 줄에 의해 분할 되는 인스턴스화된 구별 된 공용 구조체 오목한 부분이 있는 새 범위를 포함 된 데이터를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-122">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="61741-123">새 줄에 닫는 괄호를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-123">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a><span data-ttu-id="61741-124">튜플 형식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-124">Formatting tuples</span></span>

<span data-ttu-id="61741-125">튜플 인스턴스화 괄호로 묶고 고 내에서 구분 쉼표 뒤에 야 단일 공백, 예: `(1, 2)`, `(x, y, z)`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-125">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="61741-126">일반적으로 허용 되는 예외는 튜플 패턴 일치에서 괄호를 생략 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-126">A commonly accepted exception is to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a><span data-ttu-id="61741-127">레코드 형식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-127">Formatting records</span></span>

<span data-ttu-id="61741-128">한 줄에 짧은 레코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-128">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="61741-129">오래 된 레코드는 레이블에 대 한 새 줄을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-129">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="61741-130">새 줄에 닫는 토큰과 같은 줄에 여 토큰을 배치 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-130">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

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

<span data-ttu-id="61741-131">목록 및 배열 요소에 대 한 동일한 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-131">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="61741-132">Lists와 arrays 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-132">Formatting lists and arrays</span></span>

<span data-ttu-id="61741-133">쓰기 `x :: l` 주위에 공백이 있는 `::` 연산자 (`::` 공간 따라서 둘러싸인 않은 중 위 연산자가) 및 `[1; 2; 3]` (`;` 따라서 뒤에 공백이 구분 기호가).</span><span class="sxs-lookup"><span data-stu-id="61741-133">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="61741-134">항상 두 명의 고유 중괄호와 비슷한 연산자 사이 하나 이상의 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-134">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="61741-135">예를 들어 사이 공백을 두고는 `[` 및 `{`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-135">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="61741-136">목록 및 여러 줄에 의해 분할 되는 배열 레코드와 마찬가지로 유사한 규칙을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="61741-136">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

## <a name="formatting-if-expressions"></a><span data-ttu-id="61741-137">경우에 형식 지정 식</span><span class="sxs-lookup"><span data-stu-id="61741-137">Formatting if expressions</span></span>

<span data-ttu-id="61741-138">조건문의 들여쓰기를 구성 하는 식의 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="61741-138">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="61741-139">경우 `cond`, `e1` 및 `e2` 은 작은 단순히 한 줄에 쓸지:</span><span class="sxs-lookup"><span data-stu-id="61741-139">If `cond`, `e1` and `e2` are small, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="61741-140">경우 `e1` 및 `cond` 은 작은 하지만 `e2` 큽니다.</span><span class="sxs-lookup"><span data-stu-id="61741-140">If `e1` and `cond` are small, but `e2` is large:</span></span>

```fsharp
if cond then e1
else
    e2
```

<span data-ttu-id="61741-141">경우 `e1` 및 `cond` 큰 및 `e2` 작습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-141">If `e1` and `cond` are large and `e2` is small:</span></span>

```fsharp
if cond then
    e1
else e2
```

<span data-ttu-id="61741-142">모든 식은 큰 경우:</span><span class="sxs-lookup"><span data-stu-id="61741-142">If all the expressions are large:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="61741-143">와 여러 가지 조건을 `elif` 및 `else` 와 동일한 범위에서 들여쓰기는 `if`:</span><span class="sxs-lookup"><span data-stu-id="61741-143">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="61741-144">패턴 일치 하는 구문</span><span class="sxs-lookup"><span data-stu-id="61741-144">Pattern matching constructs</span></span>

<span data-ttu-id="61741-145">사용 하 여 한 `|` 없는 오목한 부분이 있는 일치 항목의 각 절에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-145">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="61741-146">식이 짧은 경우에 한 줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-146">If the expression is short, you can use a single line.</span></span>

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

<span data-ttu-id="61741-147">패턴 일치 화살표 오른쪽의 식이 너무 클 경우 다음 줄에서 한 단계를 보다 한 수준된으로 이동 된 `match` / `|`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-147">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="61741-148">패턴 일치에서 시작 하는 익명 함수 `function`, 해야 일반적으로 들여쓰지 너무 멀리 떨어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-148">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="61741-149">예를 들어 한 범위를 다음과 같이 들여쓰기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-149">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="61741-150">패턴에 정의 된 함수에서 일치 `let` 또는 `let rec` 의 시작한 후 들여쓰기 된 4 개의 공백을 해야 `let`경우에 `function` 키워드를 사용:</span><span class="sxs-lookup"><span data-stu-id="61741-150">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="61741-151">화살표를 정렬 하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-151">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="61741-152">서식 지정 try / 식을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="61741-152">Formatting try/with expressions</span></span>

<span data-ttu-id="61741-153">예외 형식에 패턴 일치와 같은 수준에 써야 `with`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-153">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="61741-154">함수 매개 변수 응용 프로그램을 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-154">Formatting function parameter application</span></span>

<span data-ttu-id="61741-155">일반적으로 대부분의 함수 매개 변수 응용 프로그램 같은 줄에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-155">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="61741-156">새 줄에 함수에 매개 변수를 적용 하려는 경우 한 범위 하 여 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="61741-156">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="61741-157">익명 함수 인수는 다음 줄에서 또는 현 수와 가능 `fun` 인수 줄에:</span><span class="sxs-lookup"><span data-stu-id="61741-157">Anonymous function arguments can be either on next line or with a dangling `fun` on the argument line:</span></span>

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

### <a name="formatting-infix-operators"></a><span data-ttu-id="61741-158">서식 지정 중 위 연산자</span><span class="sxs-lookup"><span data-stu-id="61741-158">Formatting infix operators</span></span>

<span data-ttu-id="61741-159">공백 사용 하 여 별도 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-159">Separate operators by spaces.</span></span> <span data-ttu-id="61741-160">이 규칙에 대 한 확실 한 예외는는 `!` 및 `.` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-160">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="61741-161">중 위 식이란 확인에 동일한 열에는 목록:</span><span class="sxs-lookup"><span data-stu-id="61741-161">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="61741-162">파이프라인 연산자를 형식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-162">Formatting pipeline operators</span></span>

<span data-ttu-id="61741-163">파이프라인 `|>` 연산자에서 작동 하는 식 아래까지 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-163">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="61741-164">서식 지정 모듈</span><span class="sxs-lookup"><span data-stu-id="61741-164">Formatting modules</span></span>

<span data-ttu-id="61741-165">로컬 모듈의 코드 모듈을 기준으로 써야 있지만 최상위 모듈에 코드를 들여쓰지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-165">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="61741-166">Namespace 요소 들 여 쓰도록 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-166">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="61741-167">개체 식 및 인터페이스 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-167">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="61741-168">개체 식 및 인터페이스 정렬 하는 같은 방식으로 `member` 4 개의 공백을 후 들여쓰기 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-168">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a><span data-ttu-id="61741-169">식에는 공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-169">Formatting whitespace in expressions</span></span>

<span data-ttu-id="61741-170">F # 식에서 불필요 한 공백을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="61741-170">Avoid extraneous whitespace in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="61741-171">명명 된 인수도 없어야 공간 둘러싼는 `=`:</span><span class="sxs-lookup"><span data-stu-id="61741-171">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="61741-172">빈 줄에 서식 지정</span><span class="sxs-lookup"><span data-stu-id="61741-172">Formatting blank lines</span></span>

* <span data-ttu-id="61741-173">별도 최상위 함수 및 클래스 정의 두 개의 빈 줄만 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-173">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="61741-174">클래스 내의 메서드 정의 단일 줄으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61741-174">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="61741-175">빈 줄을 별도의 관련 된 기능 그룹 (드물게) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-175">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="61741-176">다양 한 관련된 one-liners (예를 들어 더미 구현 집합) 사이의 빈 줄을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-176">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="61741-177">논리적 섹션을 나타내기 위해 함수에서 빈 줄을 제한적으로 사용, 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-177">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="61741-178">서식 주석</span><span class="sxs-lookup"><span data-stu-id="61741-178">Formatting comments</span></span>

<span data-ttu-id="61741-179">일반적으로 ML 스타일 블록 주석을 통해 여러 이중 슬래시 의견을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-179">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

<span data-ttu-id="61741-180">인라인 주석 첫 번째 글자를 대문자로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-180">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="61741-181">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="61741-181">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="61741-182">CamelCase 클래스 바인딩, 바인딩 식 및 패턴 바인딩된 값 및 함수에 대 한 사용</span><span class="sxs-lookup"><span data-stu-id="61741-182">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="61741-183">일반적인 바인딩되고 camelCase 모든 이름에 대해 사용 하도록 허용 된 F # 스타일 또는 패턴 일치 및 함수 정의에 지역 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-183">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="61741-184">클래스의 바인딩된 로컬로 함수 camelCase 또한 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-184">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="61741-185">CamelCase를 사용 하 여 내부 및 개인 모듈 바인딩된 값 및 함수에 대 한</span><span class="sxs-lookup"><span data-stu-id="61741-185">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="61741-186">다음을 포함 하는 개인 모듈 바인딩된 값에 대 한 camelCase를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-186">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="61741-187">스크립트에서 임시 함수</span><span class="sxs-lookup"><span data-stu-id="61741-187">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="61741-188">형식 또는 모듈의 내부 구현을 구성 하는 값</span><span class="sxs-lookup"><span data-stu-id="61741-188">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="61741-189">매개 변수에 대 한 camelCase를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="61741-189">Use camelCase for parameters</span></span>

<span data-ttu-id="61741-190">모든 매개 변수는 camelCase.NET 명명 규칙에 따라 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-190">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="61741-191">모듈에 대 한 표시 방법이 PascalCase를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="61741-191">Use PascalCase for modules</span></span>

<span data-ttu-id="61741-192">모든 모듈 (예: 최상위, 내부, 개인, 중첩 된) 표시 방법이 PascalCase 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-192">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="61741-193">형식 선언, 멤버 및 레이블 표시 방법이 PascalCase 사용</span><span class="sxs-lookup"><span data-stu-id="61741-193">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="61741-194">클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구분 된 공용 구조체 모두 표시 방법이 PascalCase로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-194">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="61741-195">또한 형식 및 레코드 및 구분 된 공용 구조체에 대 한 레이블 내에서 멤버 표시 방법이 PascalCase를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-195">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="61741-196">.NET 내장 구문에 대 한 표시 방법이 PascalCase를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="61741-196">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="61741-197">네임 스페이스, 예외, 이벤트 및 프로젝트 /`.dll` 이름 표시 방법이 PascalCase에도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-197">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="61741-198">뿐만 아니라 소비자에 게 더 자연 스러운 생각 하는 다른.NET 언어에서 소비 되셨나요는 발생할 가능성이 있는.NET 명명 규칙과 일치 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-198">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="61741-199">이름에 밑줄이 방지</span><span class="sxs-lookup"><span data-stu-id="61741-199">Avoid underscores in names</span></span>

<span data-ttu-id="61741-200">지금까지 일부 F # 라이브러리 이름에 밑줄을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-200">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="61741-201">그러나이 더 이상 광범위 하 게 수락 거의.NET 명명 규칙와 충돌 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="61741-201">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="61741-202">즉, 일부 F # 프로그래머가 사용 밑줄 과도 하 게, 부분적으로 지금 및 내결함성 및 존중이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-202">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="61741-203">그러나 다른 사용 여부에 대 한 선택 옵션이 사용자 스타일은 종종 사이가 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-203">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="61741-204">일부 예외는 밑줄을 매우 자주 네이티브 구성 요소와의 상호 운용 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-204">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="61741-205">표준 F # 연산자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="61741-205">Use standard F# operators</span></span>

<span data-ttu-id="61741-206">다음과 같은 연산자 F # 표준 라이브러리에 정의 되 고 해당 항목을 정의 하는 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-206">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="61741-207">이러한 연산자를 사용 하 여 코드를 더 쉽게 읽고 관용구는 것으로 확인 하는 대로 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-207">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="61741-208">백그라운드 OCaml 또는 다른 함수형 프로그래밍 언어에서 개발자가 익숙한 다른 관용구 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-208">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="61741-209">다음 목록에는 권장 되는 F # 연산자 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61741-209">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="61741-210">제네릭에 대 한 접두사 구문을 사용 하 여 (`Foo<T>`) 후 위 구문 대신 (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="61741-210">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="61741-211">F # 제네릭 형식 명명의 두는 후 위 ML 스타일을 상속 합니다. (예를 들어 `int list`) 접두사.NET 스타일 뿐만 아니라 (예를 들어 `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="61741-211">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="61741-212">.NET 스타일 4 개의 특정 형식 제외 하 고 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-212">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="61741-213">후 위 형태를 사용 하 여 F # 목록에 대 한: `int list` 대신 `list<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-213">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="61741-214">F # 옵션에 대해 후 위 형태를 사용 하 여: `int option` 대신 `option<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-214">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="61741-215">F # 배열에 대해 구문 이름을 사용 하 여 `int[]` 대신 `int array` 또는 `array<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-215">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="61741-216">사용 하 여 참조 셀에 대 한 `int ref` 대신 `ref<int>` 또는 `Ref<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-216">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="61741-217">다른 모든 형식에 대 한 전위 형태를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61741-217">For all other types, use the prefix form.</span></span>
