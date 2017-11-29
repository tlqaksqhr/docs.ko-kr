---
title: "루프: for...to 식(F#)"
description: "참조 방식을 F # >for.. 식으로 하는 데 루프 변수 값의 범위에 대해 루프를 반복 합니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="06530-104">루프: for...to 식</span><span class="sxs-lookup"><span data-stu-id="06530-104">Loops: for...to Expression</span></span>

<span data-ttu-id="06530-105">`for...to` 식은 루프 변수 값의 범위에 대해 루프를 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06530-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="06530-106">구문</span><span class="sxs-lookup"><span data-stu-id="06530-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="06530-107">설명</span><span class="sxs-lookup"><span data-stu-id="06530-107">Remarks</span></span>
<span data-ttu-id="06530-108">식별자의 형식은 형식에서 유추 됩니다는 *시작* 및 *마침* 식입니다.</span><span class="sxs-lookup"><span data-stu-id="06530-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="06530-109">이러한 식에 대 한 형식에는 32 비트 정수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06530-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="06530-110">하지만 식을 기술적으로 `for...to` 는 더 일반적인 명령형 프로그래밍 언어의 문에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06530-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="06530-111">반환 형식에는 *본문 식* 해야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="06530-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="06530-112">다음 예제에서는 보여의 다양 한 용도 `for...to` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="06530-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="06530-113">위 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="06530-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="06530-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06530-114">See Also</span></span>
[<span data-ttu-id="06530-115">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="06530-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="06530-116">루프: `for...in` 식</span><span class="sxs-lookup"><span data-stu-id="06530-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="06530-117">루프: `while...do` 식</span><span class="sxs-lookup"><span data-stu-id="06530-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
