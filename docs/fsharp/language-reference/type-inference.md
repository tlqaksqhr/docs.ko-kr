---
title: 형식 유추(F#)
description: 'F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b5f7861c0a638baebfe72c9b4cf7dca119339ae3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="type-inference"></a><span data-ttu-id="ffccc-103">형식 유추</span><span class="sxs-lookup"><span data-stu-id="ffccc-103">Type Inference</span></span>

<span data-ttu-id="ffccc-104">이 항목에서는 F # 컴파일러 값, 변수, 매개 변수 및 반환 값의 형식을 유추 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="ffccc-105">형식 유추를 일반 사항</span><span class="sxs-lookup"><span data-stu-id="ffccc-105">Type Inference in General</span></span>
<span data-ttu-id="ffccc-106">형식 유추 방법은 때 컴파일러 추론할 수 없습니다. 결정적 유형을 제외 하 고 F # 구문 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="ffccc-107">F #은 동적으로 형식화 된 언어 또는 F #의 값은 약하게 형식화 된 명시적 형식 정보를 생략 하는 것은 의미가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="ffccc-108">F # 컴파일러를 컴파일하는 동안 각 구문에 대 한 정확한 형식을 추론 하는 정적 형식의 언어인은입니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="ffccc-109">각 구문의 형식을 추론 하도록 컴파일러에 대 한 정보가 충분 하지 않으면, 코드에서 어딘가에 명시적인 형식 주석을 추가 하 여 추가 형식 정보를 일반적으로 제공 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="ffccc-110">매개 변수 및 반환 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ffccc-110">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="ffccc-111">매개 변수 목록에서 각 매개 변수의 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="ffccc-112">및 F #은 정적으로 형식화 된 언어 및 따라서 모든 값과 식의 형식이 정해 집니다 컴파일 타임에 아직 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="ffccc-113">명시적으로 지정 하지 않으면 해당 형식에 컴파일러는 컨텍스트를 기준으로 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="ffccc-114">형식에 별도로 지정 하지 않은 경우 제네릭인 것으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="ffccc-115">코드를 사용 하는 값 일관 되지 않게 하는 방식에 더 단일 임을 유추 컴파일러에서 오류를 보고 하는 값의 모든 사용을 충족 하.</span><span class="sxs-lookup"><span data-stu-id="ffccc-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="ffccc-116">함수의 반환 형식은 함수에서 마지막 식 유형에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="ffccc-117">예를 들어 다음 코드에서는 형식 매개 변수에서에서 `a` 및 `b` 반환 형식 모두로 유추 하 고 `int` 때문에 리터럴 `100` 유형의 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="ffccc-118">리터럴을 변경 하 여 형식 유추를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="ffccc-119">만들면는 `100` 는 `uint32` 접미사를 추가 하 여 `u`, 유형의 `a`, `b`, 반환 값으로 유추 되 고 `uint32`합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="ffccc-120">수도 내재 함수 및 특정 유형과 함께 작동 하는 메서드 같은 형식에 대 한 제한 된 다른 구문을 사용 하 여 형식 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="ffccc-121">또한 또는 적용할 수 있습니다 명시적 형식 주석을 함수 또는 메서드 매개 변수를 식에서 변수를 다음 예제에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="ffccc-122">오류가 다른 제약 조건 사이 충돌이 발생 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="ffccc-123">명시적으로 제공 하 여 형식 주석을 모든 매개 변수는 함수의 반환 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="ffccc-124">형식 주석이 매개 변수에 유용 일반적인 경우에도 매개 변수는 개체 유형 및 멤버를 사용 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="ffccc-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="ffccc-125">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="ffccc-125">Automatic Generalization</span></span>
<span data-ttu-id="ffccc-126">함수 코드 매개 변수의 형식에 종속 된 경우 컴파일러는 제네릭 매개 변수를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="ffccc-127">이 라고 *자동 일반화*, 복잡성 증가 하지 않고 제네릭 코드를 작성를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="ffccc-128">예를 들어 다음 함수에 모든 형식의 두 매개 변수를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="ffccc-129">형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="ffccc-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ffccc-130">Additional Information</span></span>
<span data-ttu-id="ffccc-131">형식 유추에서 F # 언어 사양에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffccc-131">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="ffccc-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffccc-132">See Also</span></span>
[<span data-ttu-id="ffccc-133">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="ffccc-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
