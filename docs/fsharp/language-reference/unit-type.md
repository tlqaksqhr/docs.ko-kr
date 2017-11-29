---
title: "단위 형식(F#)"
description: "값이 필요한 또는 원하는 경우 언어 구문을 사용 하 여 값을 필요한은 위치 하는 데 자주 사용 하는 F # 'unit' 형식이 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: eabbb6d7-80f3-4fa5-80b4-0f48982466a7
ms.openlocfilehash: 60ac08c0e3f8380a8f9dec7a083ede93c68bb0e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="unit-type"></a><span data-ttu-id="18861-104">단위 형식</span><span class="sxs-lookup"><span data-stu-id="18861-104">Unit Type</span></span>

<span data-ttu-id="18861-105">`unit` 형식이 특정 값이 없음을 나타내는 형식이 고 `unit` 형식에 다른 값이 없으며 존재 하지 않거나 필요한 경우 자리 표시자로 사용 하는 단일 값만 합니다.</span><span class="sxs-lookup"><span data-stu-id="18861-105">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="18861-106">구문</span><span class="sxs-lookup"><span data-stu-id="18861-106">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="18861-107">설명</span><span class="sxs-lookup"><span data-stu-id="18861-107">Remarks</span></span>
<span data-ttu-id="18861-108">모든 F # 식은 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18861-108">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="18861-109">값 관심 있는 형식의 값을 생성 하지 않는 식에 대 한 `unit` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18861-109">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="18861-110">`unit` 형식 유사한는 `void` C# 및 c + +와 같은 언어를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="18861-110">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="18861-111">`unit` 형식에는 단일 값 및 해당 값이 토큰으로 표시 됩니다 `()`합니다.</span><span class="sxs-lookup"><span data-stu-id="18861-111">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="18861-112">값은 `unit` 유형은 F # 프로그래밍 언어 구문을 사용 하 여 값이 필요한 경우 하지만 값은 필요한 또는 원하는 경우에서 자리를 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18861-112">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="18861-113">반환 값의 예로 들 수 있습니다는 `printf` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-113">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="18861-114">때문에 중요 한 동작을는 `printf` 작업만 함수에서 함수는 실제 값을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18861-114">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="18861-115">형식의 반환 값은 따라서 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="18861-115">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="18861-116">일부 구문은 예상 되는 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-116">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="18861-117">예를 들어 한 `do` 바인딩 또는 모듈의 최상위 수준에서 코드는로 계산 되어야 하는 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-117">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="18861-118">컴파일러 경고를 보고 때는 `do` 바인딩 또는 모듈의 최상위 수준에서 코드 결과 이외의 생성는 `unit` 다음 예제와 같이 사용 되지 않는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-118">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="18861-119">이 경고는 함수형 프로그래밍;의 특징 다른.NET 프로그래밍 언어에에서는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18861-119">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="18861-120">함수 없는 의도 하지 순수 하 게 기능 프로그램에서 함수 호출의 유일한 결과 최종 반환 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-120">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="18861-121">따라서 결과 무시할 경우 프로그래밍 가능한 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="18861-121">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="18861-122">F #은 순수 함수형 프로그래밍 언어, 이지만 함수형 프로그래밍 스타일 가능 하면 항상 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18861-122">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="18861-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18861-123">See Also</span></span>
[<span data-ttu-id="18861-124">기본</span><span class="sxs-lookup"><span data-stu-id="18861-124">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="18861-125">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="18861-125">F# Language Reference</span></span>](index.md)
