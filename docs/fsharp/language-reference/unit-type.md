---
title: 단위 형식(F#)
description: "값이 필요한 또는 원하는 경우 언어 구문을 사용 하 여 값을 필요한은 위치 하는 데 자주 사용 하는 F # 'unit' 형식이 방법에 대해 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: fdd6b62f9d5c6d73407d5326c7d1f66d55780682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564422"
---
# <a name="unit-type"></a><span data-ttu-id="0a07e-103">단위 형식</span><span class="sxs-lookup"><span data-stu-id="0a07e-103">Unit Type</span></span>

<span data-ttu-id="0a07e-104">`unit` 형식이 특정 값이 없음을 나타내는 형식이 고 `unit` 형식에 다른 값이 없으며 존재 하지 않거나 필요한 경우 자리 표시자로 사용 하는 단일 값만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>


## <a name="syntax"></a><span data-ttu-id="0a07e-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a07e-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="0a07e-106">설명</span><span class="sxs-lookup"><span data-stu-id="0a07e-106">Remarks</span></span>
<span data-ttu-id="0a07e-107">모든 F # 식은 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="0a07e-108">값 관심 있는 형식의 값을 생성 하지 않는 식에 대 한 `unit` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="0a07e-109">`unit` 형식 유사한는 `void` C# 및 c + +와 같은 언어를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="0a07e-110">`unit` 형식에는 단일 값 및 해당 값이 토큰으로 표시 됩니다 `()`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="0a07e-111">값은 `unit` 유형은 F # 프로그래밍 언어 구문을 사용 하 여 값이 필요한 경우 하지만 값은 필요한 또는 원하는 경우에서 자리를 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="0a07e-112">반환 값의 예로 들 수 있습니다는 `printf` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="0a07e-113">때문에 중요 한 동작을는 `printf` 작업만 함수에서 함수는 실제 값을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="0a07e-114">형식의 반환 값은 따라서 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="0a07e-115">일부 구문은 예상 되는 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="0a07e-116">예를 들어 한 `do` 바인딩 또는 모듈의 최상위 수준에서 코드는로 계산 되어야 하는 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="0a07e-117">컴파일러 경고를 보고 때는 `do` 바인딩 또는 모듈의 최상위 수준에서 코드 결과 이외의 생성는 `unit` 다음 예제와 같이 사용 되지 않는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="0a07e-118">이 경고는 함수형 프로그래밍;의 특징 다른.NET 프로그래밍 언어에에서는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="0a07e-119">함수 없는 의도 하지 순수 하 게 기능 프로그램에서 함수 호출의 유일한 결과 최종 반환 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="0a07e-120">따라서 결과 무시할 경우 프로그래밍 가능한 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="0a07e-121">F #은 순수 함수형 프로그래밍 언어, 이지만 함수형 프로그래밍 스타일 가능 하면 항상 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0a07e-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a07e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a07e-122">See Also</span></span>
[<span data-ttu-id="0a07e-123">기본</span><span class="sxs-lookup"><span data-stu-id="0a07e-123">Primitive</span></span>](primitive-types.md)

[<span data-ttu-id="0a07e-124">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0a07e-124">F# Language Reference</span></span>](index.md)
