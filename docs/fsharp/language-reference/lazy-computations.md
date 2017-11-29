---
title: "지연 계산(F#)"
description: "F # 지연 계산 응용 프로그램 및 라이브러리의 성능이 향상 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="d924a-104">지연 계산</span><span class="sxs-lookup"><span data-stu-id="d924a-104">Lazy Computations</span></span>

<span data-ttu-id="d924a-105">*지연 계산* 에 즉시 평가 되지 않은 하지만 결과가 필요할 때 대신 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="d924a-106">이 코드의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="d924a-107">구문</span><span class="sxs-lookup"><span data-stu-id="d924a-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="d924a-108">설명</span><span class="sxs-lookup"><span data-stu-id="d924a-108">Remarks</span></span>

<span data-ttu-id="d924a-109">위 구문에서 *식* 는 결과가 필요한 경우에 평가 되는 코드 및 *식별자* 결과 저장 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="d924a-110">형식의 값은 [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)위치는 실제 형식은에 사용 되 `'T` 식의 결과에서 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="d924a-111">지연 계산을 사용 하 여 계산을 결과가 필요한 경우에만 실행 하도록 제한 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="d924a-112">메서드를 호출 하면 계산을 강제로 수행할, `Force`합니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="d924a-113">`Force`한 번만 수행 하 고 실행을 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="d924a-114">에 대 한 후속 호출 `Force` 동일한 결과 실행 하지는 않습니다 모든 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="d924a-115">다음 코드에서는 지연 계산의 사용 및 사용 `Force`합니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="d924a-116">이 코드의 형식 `result` 은 `Lazy<int>`, 및 `Force` 메서드가 반환 되는 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="d924a-117">지연 계산 하지 않고는 `Lazy` 입력, 시퀀스에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="d924a-118">자세한 내용은 참조 [시퀀스](sequences.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d924a-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d924a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d924a-119">See Also</span></span>

[<span data-ttu-id="d924a-120">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d924a-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d924a-121">LazyExtensions 모듈</span><span class="sxs-lookup"><span data-stu-id="d924a-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
