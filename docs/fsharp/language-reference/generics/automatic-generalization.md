---
title: 자동 일반화(F#)
description: '어떻게 F # 자동으로 일반화 하 여 인수 및 함수 유형 가능 하면 여러 종류를 사용에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 858c8bab4a1a37f44a700744e70ebfa8a5abf12c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565077"
---
# <a name="automatic-generalization"></a><span data-ttu-id="858ca-103">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="858ca-103">Automatic Generalization</span></span>

<span data-ttu-id="858ca-104">F # 형식 유추 유형 함수 및 식의 평가를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="858ca-105">이 항목에서는 방법을 F # 자동으로 일반화 하 여 인수 및 함수 유형 가능한 경우 여러 유형으로 작업할 수 있도록 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>


## <a name="automatic-generalization"></a><span data-ttu-id="858ca-106">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="858ca-106">Automatic Generalization</span></span>
<span data-ttu-id="858ca-107">F # 컴파일러는 함수에서 형식 유추를 수행 하는 경우에 지정된 된 매개 변수가 제네릭 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="858ca-108">컴파일러가 각 매개 변수를 검사 하 고 함수는 해당 매개 변수의 특정 형식을에 종속 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="858ca-109">그렇지 않은 경우 제네릭 형식을 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="858ca-110">다음 코드 예제에서는 컴파일러가 제네릭인 것으로 유추 하는 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="858ca-111">형식 유추 됩니다 `'a -> 'a -> 'a`합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="858ca-112">형식을 알 수 없는 동일한 형식의 두 인수를 사용 하 고 동일한 형식의 값을 반환 하는 함수 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="858ca-113">이전 함수 일 수 있는 원인 중 하나로 일반은 큼-연산자 보다 (`>`)는 그 자체가 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="858ca-114">큼-서명이 연산자 보다 `'a -> 'a -> bool`합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="858ca-115">일부 연산자는 일반, 및 해당 매개 변수 형식을 함수에 코드에서 비 제네릭 함수 또는 연산자와 함께 매개 변수 형식에서 사용 하는 경우 일반화 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="858ca-116">때문에 `max` 은 일반, 사용할 수 있습니다 형식과 같은 `int`, `float`등의 다음 예제에 나와 있는 것 처럼, 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="858ca-117">그러나 두 개의 인수는 동일한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="858ca-118">서명이 `'a -> 'a -> 'a`이 아니라 `'a -> 'b -> 'a`합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="858ca-119">따라서 다음 코드 형식이 일치 하지 않기 때문에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="858ca-120">`max` 함수를 지 원하는 더 큰 종류와도 작동-than 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="858ca-121">따라서 있습니다 사용할 수도 것 문자열에서 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a><span data-ttu-id="858ca-122">값 제한 사항</span><span class="sxs-lookup"><span data-stu-id="858ca-122">Value Restriction</span></span>
<span data-ttu-id="858ca-123">컴파일러는 간단한 변경할 수 없는 값 및 명시적 인수가 포함 하는 완전 한 함수 정의에 자동 일반화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="858ca-124">즉, 충분히를 특정 형식으로 제한 되지 않은 뿐만 아니라 하지 일반화할 코드를 컴파일하려고 하면 컴파일러 오류가 발생 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="858ca-125">이 문제에 대 한 오류 메시지 값 형식에 대 한 자동 일반화에이 제한 사항을 가리키는 *제한 값*합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="858ca-126">일반적으로 값 제한 오류는 컴파일러에 계정을 일반화 정보가 부족 하지만 제네릭이 아니어야 하는 구문 않으려는 경우 또는 실수로 제네릭이 아닌 구문에 충분 한 정보를 입력 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="858ca-127">값 제한 오류를 해결 방법은 보다 완전 하 게 다음과 같은 방법 중 하나에서 형식 유추 문제를 제한 하려면 보다 명시적인 정보를 제공 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>


- <span data-ttu-id="858ca-128">명시적인 형식 주석 값 또는 매개 변수를 추가 하 여 제네릭이 아닌 형식을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="858ca-129">문제를 사용 하는 경우 함수 합성 또는 불완전 하 게 제네릭 함수 정의를 일반화할 수 없는 구문을 적용 된 변환된 함수 인수, 함수는 일반적인 함수 정의 다시 작성 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="858ca-130">문제는 너무 복잡해 서 이미지를 일반화 하는 식, 함수에는 추가 하 고 사용 하지 않는 매개 변수를 추가 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="858ca-131">명시적 제네릭 형식 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="858ca-132">이 옵션은 거의 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-132">This option is rarely used.</span></span>

- <span data-ttu-id="858ca-133">다음 코드 예제에서는 이러한 각 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="858ca-134">사례 1: 너무 복잡 한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="858ca-135">이 예제에서는 목록 `counter` 하려면 `int option ref`, 간단한 변경할 수 없는 값으로 정의 되어 있지 않지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="858ca-136">사례 2: 일반화할 수 없는 구문을 사용 하 여 제네릭 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="858ca-137">이 예제에서는 구문이 인지 함수 인수를 부분 적용을 포함 하기 때문에 일반화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="858ca-138">사례 3:는 추가 하 고 사용 하지 않는 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="858ca-139">이 식은 일반화 수 있을 만큼 간단 없기 때문에 컴파일러 값 제한 오류를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="858ca-140">사례 4: 형식 매개 변수 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="858ca-141">마지막 경우에서 값이 예를 들어 다음과 같이 서로 다른 여러 형식의 값을 만드는 데 사용할 수 있는 형식 함수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="858ca-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="858ca-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="858ca-142">See Also</span></span>
[<span data-ttu-id="858ca-143">형식 유추</span><span class="sxs-lookup"><span data-stu-id="858ca-143">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="858ca-144">제네릭</span><span class="sxs-lookup"><span data-stu-id="858ca-144">Generics</span></span>](index.md)

[<span data-ttu-id="858ca-145">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="858ca-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="858ca-146">제약 조건</span><span class="sxs-lookup"><span data-stu-id="858ca-146">Constraints</span></span>](constraints.md)

