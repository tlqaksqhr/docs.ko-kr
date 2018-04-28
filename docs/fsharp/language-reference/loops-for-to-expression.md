---
title: '루프: for...to 식(F#)'
description: '참조 방식을 F # >for.. 식으로 하는 데 루프 변수 값의 범위에 대해 루프를 반복 합니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a><span data-ttu-id="f91f8-103">루프: for...to 식</span><span class="sxs-lookup"><span data-stu-id="f91f8-103">Loops: for...to Expression</span></span>

<span data-ttu-id="f91f8-104">`for...to` 식은 루프 변수 값의 범위에 대해 루프를 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="f91f8-105">구문</span><span class="sxs-lookup"><span data-stu-id="f91f8-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="f91f8-106">설명</span><span class="sxs-lookup"><span data-stu-id="f91f8-106">Remarks</span></span>
<span data-ttu-id="f91f8-107">식별자의 형식은 형식에서 유추 됩니다는 *시작* 및 *마침* 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="f91f8-108">이러한 식에 대 한 형식에는 32 비트 정수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="f91f8-109">하지만 식을 기술적으로 `for...to` 는 더 일반적인 명령형 프로그래밍 언어의 문에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="f91f8-110">반환 형식에는 *본문 식* 해야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="f91f8-111">다음 예제에서는 보여의 다양 한 용도 `for...to` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="f91f8-112">위 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91f8-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="f91f8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f91f8-113">See Also</span></span>
[<span data-ttu-id="f91f8-114">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f91f8-114">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f91f8-115">루프: `for...in` 식</span><span class="sxs-lookup"><span data-stu-id="f91f8-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="f91f8-116">루프: `while...do` 식</span><span class="sxs-lookup"><span data-stu-id="f91f8-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
