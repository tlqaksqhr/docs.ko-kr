---
title: "루프: while...do 식(F#)"
description: "참조 방식을... 하는 동안 수행 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (루프)을 수행 하는데 사용 됩니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="340dc-104">루프: while...do 식</span><span class="sxs-lookup"><span data-stu-id="340dc-104">Loops: while...do Expression</span></span>

<span data-ttu-id="340dc-105">`while...do` 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (루프)을 수행 하는데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="340dc-106">구문</span><span class="sxs-lookup"><span data-stu-id="340dc-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="340dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="340dc-107">Remarks</span></span>
<span data-ttu-id="340dc-108">*테스트 식* 를 평가 합니다;이 경우 `true`, *본문 식* 실행 될 테스트 식이 다시 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="340dc-109">*본문 식* 형식이 있어야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="340dc-110">테스트 식이 `false`, 반복이 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="340dc-111">다음 예제에서는 `while...do` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="340dc-112">이전 코드의 출력은 1에서 20 사이의 난수 이루어진은 10 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="340dc-113">사용할 수 있습니다 `while...do` 시퀀스 식 및 다른 계산 식, 사용자 지정된 된 버전의 경우는 `while...do` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="340dc-114">자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="340dc-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="340dc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340dc-115">See Also</span></span>
[<span data-ttu-id="340dc-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="340dc-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="340dc-117">루프: `for...in` 식</span><span class="sxs-lookup"><span data-stu-id="340dc-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="340dc-118">루프: `for...to` 식</span><span class="sxs-lookup"><span data-stu-id="340dc-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
