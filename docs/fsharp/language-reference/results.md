---
title: '결과 (F #)'
description: "오류 무시 코드를 작성할 수 있도록 F # '결과' 형식을 사용 하는 방법에 알아봅니다."
ms.date: 04/24/2017
ms.openlocfilehash: 432e420ba7c2005caa46250dde82c2c67c9d3ae3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="results"></a>결과

F # 4.1 부터는 `Result<'T,'TFailure>` 종류입니다. 오류 무시 코드를 구성할 수 있는 작성에 사용할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>설명

결과 형식이 참고는 [구조체 구분 된 공용 구조체](discriminated-unions.md#struct-discriminated-unions), F # 4.1에서 도입 된는 또 다른 기능은입니다.  구조적 같음 의미 체계가 여기에 적용 됩니다.

`Result` 유형은 monadic 오류 처리는 종종 라고 하는 일반적으로 사용은 [직접 지향 프로그래밍](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) F # 커뮤니티 내에서.  다음의 간단한 예제에서는이 방법을 보여 줍니다.

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

경우 강제로 모두 반환할 다양 한 유효성 검사 기능 함께 연결할 수 있는 쉬운 볼 수 있듯이 `Result`합니다.  구성 되도록 필요에 따라 가능성 있는 작은 조각으로 다음과 같은 기능을 중단할이 있습니다.  부가 가치에 *적용* 사용 [패턴 일치](pattern-matching.md) 더 높은 수준의 프로그램 정확성 적용 결과적으로 라운드 유효성 검사의 끝입니다.

## <a name="see-also"></a>참고 항목

[구별된 공용 구조체](discriminated-unions.md)

[패턴 일치](pattern-matching.md)
