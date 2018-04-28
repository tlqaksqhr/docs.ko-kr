---
title: '재귀 함수: rec 키워드(F#)'
description: "F # 'rec' 키워드를 하는 방법을 'let' 키워드와 함께 재귀 함수 정의 알아봅니다."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="3be01-103">재귀 함수: rec 키워드</span><span class="sxs-lookup"><span data-stu-id="3be01-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="3be01-104">`rec` 키워드와 함께 사용 되는 `let` 재귀 함수를 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="3be01-105">구문</span><span class="sxs-lookup"><span data-stu-id="3be01-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="3be01-106">설명</span><span class="sxs-lookup"><span data-stu-id="3be01-106">Remarks</span></span>
<span data-ttu-id="3be01-107">재귀 함수는 자기 자신을 호출 하는 함수는 F # 언어에서 명시적으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="3be01-108">이렇게 하면 함수 범위에서 사용할 수 정의 되는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="3be01-109">다음 코드에서는 재귀 함수를 계산 하는 *n*번째 피보나치 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-109">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="3be01-110">실제로 그렇게 위의 코드는 이전에 계산 된 값의 다시 계산 기능을 포함 하기 때문에 메모리 및 프로세서 시간을 낭비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="3be01-111">메서드는 암시적으로; 형식 내에서 재귀 추가할 필요가 없습니다는 `rec` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="3be01-112">Let 바인딩 클래스 내에서 암시적으로 재귀 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-112">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="3be01-113">상호 재귀 함수</span><span class="sxs-lookup"><span data-stu-id="3be01-113">Mutually Recursive Functions</span></span>
<span data-ttu-id="3be01-114">함수는 경우에 따라 *상호 재귀*, 즉 호출 원, 하나의 함수 호출 하는 경우 호출 하는 첫 번째 개수에 관계 없이 호출 된 다른 사이를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="3be01-115">번째에서 함께 이러한 함수를 정의 해야 `let` 바인딩을 사용 하는 `and` 키워드를 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3be01-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="3be01-116">다음 예제에서는 두 번호를 표시 상호 재귀 함수.</span><span class="sxs-lookup"><span data-stu-id="3be01-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="3be01-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3be01-117">See Also</span></span>
[<span data-ttu-id="3be01-118">함수</span><span class="sxs-lookup"><span data-stu-id="3be01-118">Functions</span></span>](index.md)
