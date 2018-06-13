---
title: '결과 (F #)'
description: "오류 무시 코드를 작성할 수 있도록 F # '결과' 형식을 사용 하는 방법에 알아봅니다."
ms.date: 04/24/2017
ms.openlocfilehash: 432e420ba7c2005caa46250dde82c2c67c9d3ae3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563010"
---
# <a name="results"></a><span data-ttu-id="91cea-103">결과</span><span class="sxs-lookup"><span data-stu-id="91cea-103">Results</span></span>

<span data-ttu-id="91cea-104">F # 4.1 부터는 `Result<'T,'TFailure>` 종류입니다. 오류 무시 코드를 구성할 수 있는 작성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="91cea-105">구문</span><span class="sxs-lookup"><span data-stu-id="91cea-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="91cea-106">설명</span><span class="sxs-lookup"><span data-stu-id="91cea-106">Remarks</span></span>

<span data-ttu-id="91cea-107">결과 형식이 참고는 [구조체 구분 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions), F # 4.1에서 도입 된는 또 다른 기능은입니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="91cea-108">구조적 같음 의미 체계가 여기에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="91cea-109">`Result` 유형은 monadic 오류 처리는 종종 라고 하는 일반적으로 사용은 [직접 지향 프로그래밍](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) F # 커뮤니티 내에서.</span><span class="sxs-lookup"><span data-stu-id="91cea-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="91cea-110">다음의 간단한 예제에서는이 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-110">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request = 
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="91cea-111">경우 강제로 모두 반환할 다양 한 유효성 검사 기능 함께 연결할 수 있는 쉬운 볼 수 있듯이 `Result`합니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="91cea-112">구성 되도록 필요에 따라 가능성 있는 작은 조각으로 다음과 같은 기능을 중단할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="91cea-113">부가 가치에 *적용* 사용 [패턴 일치](pattern-matching.md) 더 높은 수준의 프로그램 정확성 적용 결과적으로 라운드 유효성 검사의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="91cea-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="91cea-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91cea-114">See Also</span></span>

[<span data-ttu-id="91cea-115">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="91cea-115">Discriminated Unions</span></span>](discriminated-unions.md)

[<span data-ttu-id="91cea-116">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="91cea-116">Pattern Matching</span></span>](pattern-matching.md)
