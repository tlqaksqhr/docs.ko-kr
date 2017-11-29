---
title: "재귀 함수: rec 키워드(F#)"
description: "F # 'rec' 키워드를 하는 방법을 'let' 키워드와 함께 재귀 함수 정의 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="058dc-104">재귀 함수: rec 키워드</span><span class="sxs-lookup"><span data-stu-id="058dc-104">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="058dc-105">`rec` 키워드와 함께 사용 되는 `let` 재귀 함수를 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-105">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="058dc-106">구문</span><span class="sxs-lookup"><span data-stu-id="058dc-106">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="058dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="058dc-107">Remarks</span></span>
<span data-ttu-id="058dc-108">재귀 함수는 자기 자신을 호출 하는 함수는 F # 언어에서 명시적으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-108">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="058dc-109">이렇게 하면 함수 범위에서 사용할 수 정의 되는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-109">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="058dc-110">다음 코드에서는 재귀 함수를 계산 하는  *n* 번째 피보나치 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-110">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="058dc-111">실제로 그렇게 위의 코드는 이전에 계산 된 값의 다시 계산 기능을 포함 하기 때문에 메모리 및 프로세서 시간을 낭비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-111">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="058dc-112">메서드는 암시적으로; 형식 내에서 재귀 추가할 필요가 없습니다는 `rec` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="058dc-113">Let 바인딩 클래스 내에서 암시적으로 재귀 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-113">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="058dc-114">상호 재귀 함수</span><span class="sxs-lookup"><span data-stu-id="058dc-114">Mutually Recursive Functions</span></span>
<span data-ttu-id="058dc-115">함수는 경우에 따라 *상호 재귀*, 즉 호출 원, 하나의 함수 호출 하는 경우 호출 하는 첫 번째 개수에 관계 없이 호출 된 다른 사이를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-115">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="058dc-116">번째에서 함께 이러한 함수를 정의 해야 `let` 바인딩을 사용 하는 `and` 키워드를 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="058dc-116">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="058dc-117">다음 예제에서는 두 번호를 표시 상호 재귀 함수.</span><span class="sxs-lookup"><span data-stu-id="058dc-117">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="058dc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="058dc-118">See Also</span></span>
[<span data-ttu-id="058dc-119">함수</span><span class="sxs-lookup"><span data-stu-id="058dc-119">Functions</span></span>](index.md)
