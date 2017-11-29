---
title: "형식 유추(F#)"
description: "F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2d5fa4b1-732a-4d71-a62d-07f7ee79fe06
ms.openlocfilehash: c23954c0a0828cc7d2aae0553d37d5ee1dfbe152
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="type-inference"></a><span data-ttu-id="01d55-104">형식 유추</span><span class="sxs-lookup"><span data-stu-id="01d55-104">Type Inference</span></span>

<span data-ttu-id="01d55-105">이 항목에서는 F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-105">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="01d55-106">형식 유추를 일반 사항</span><span class="sxs-lookup"><span data-stu-id="01d55-106">Type Inference in General</span></span>
<span data-ttu-id="01d55-107">형식 유추 방법은 때 컴파일러 추론할 수 없습니다. 결정적 유형을 제외 하 고 F # 구문 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-107">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="01d55-108">F #은 동적으로 형식화 된 언어 또는 F #의 값은 약하게 형식화 된 명시적 형식 정보를 생략 하는 것은 의미가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-108">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="01d55-109">F # 컴파일러를 컴파일하는 동안 각 구문에 대 한 정확한 형식을 추론 하는 정적 형식의 언어인은입니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-109">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="01d55-110">각 구문의 형식을 추론 하도록 컴파일러에 대 한 정보가 충분 하지 않으면, 코드에서 어딘가에 명시적인 형식 주석을 추가 하 여 추가 형식 정보를 일반적으로 제공 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-110">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="01d55-111">매개 변수 및 반환 형식 유추</span><span class="sxs-lookup"><span data-stu-id="01d55-111">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="01d55-112">매개 변수 목록에서 각 매개 변수의 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-112">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="01d55-113">및 F #은 정적으로 형식화 된 언어 및 따라서 모든 값과 식의 형식이 정해 집니다 컴파일 타임에 아직 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-113">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="01d55-114">명시적으로 지정 하지 않으면 해당 형식에 컴파일러는 컨텍스트를 기준으로 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-114">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="01d55-115">형식에 별도로 지정 하지 않은 경우 제네릭인 것으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-115">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="01d55-116">코드를 사용 하는 값 일관 되지 않게 하는 방식에 더 단일 임을 유추 컴파일러에서 오류를 보고 하는 값의 모든 사용을 충족 하.</span><span class="sxs-lookup"><span data-stu-id="01d55-116">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="01d55-117">함수의 반환 형식은 함수에서 마지막 식 유형에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-117">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="01d55-118">예를 들어 다음 코드에서는 형식 매개 변수에서에서 `a` 및 `b` 반환 형식 모두로 유추 하 고 `int` 때문에 리터럴 `100` 유형의 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-118">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="01d55-119">리터럴을 변경 하 여 형식 유추를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-119">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="01d55-120">만들면는 `100` 는 `uint32` 접미사를 추가 하 여 `u`, 유형의 `a`, `b`, 반환 값으로 유추 되 고 `uint32`합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-120">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="01d55-121">수도 내재 함수 및 특정 유형과 함께 작동 하는 메서드 같은 형식에 대 한 제한 된 다른 구문을 사용 하 여 형식 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-121">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="01d55-122">또한 또는 적용할 수 있습니다 명시적 형식 주석을 함수 또는 메서드 매개 변수를 식에서 변수를 다음 예제에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-122">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="01d55-123">오류가 다른 제약 조건 사이 충돌이 발생 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-123">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="01d55-124">명시적으로 제공 하 여 형식 주석을 모든 매개 변수는 함수의 반환 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-124">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="01d55-125">형식 주석이 매개 변수에 유용 일반적인 경우에도 매개 변수는 개체 유형 및 멤버를 사용 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="01d55-125">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="01d55-126">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="01d55-126">Automatic Generalization</span></span>
<span data-ttu-id="01d55-127">함수 코드 매개 변수의 형식에 종속 된 경우 컴파일러는 제네릭 매개 변수를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-127">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="01d55-128">이 라고 *자동 일반화*, 복잡성 증가 하지 않고 제네릭 코드를 작성를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-128">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="01d55-129">예를 들어 다음 함수에 모든 형식의 두 매개 변수를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-129">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="01d55-130">형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-130">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="01d55-131">추가 정보</span><span class="sxs-lookup"><span data-stu-id="01d55-131">Additional Information</span></span>
<span data-ttu-id="01d55-132">형식 유추에서 F # 언어 사양에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01d55-132">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="01d55-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01d55-133">See Also</span></span>
[<span data-ttu-id="01d55-134">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="01d55-134">Automatic Generalization</span></span>](generics/automatic-generalization.md)
