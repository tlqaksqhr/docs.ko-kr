---
title: '조건식: if... then...else(F#)'
description: 'F # 코드의 다른 분기를 실행 하려면 조건부 식을 작성 하는 방법을 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="3a7b7-103">조건식: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="3a7b7-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="3a7b7-104">`if...then...else` 식 코드의 다른 분기를 실행 하 고 주어진 부울 식에 따라 다른 값으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="3a7b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a7b7-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="3a7b7-106">설명</span><span class="sxs-lookup"><span data-stu-id="3a7b7-106">Remarks</span></span>
<span data-ttu-id="3a7b7-107">위 구문에서 *expression1* 부울 식으로 평가 되 면 실행 `true`, 그렇지 않으면 *expression2* 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="3a7b7-108">와 달리 다른 언어로 `if...then...else` 구문은 문이 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="3a7b7-109">즉, 실행 되는 분기의 마지막 식의 값은 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="3a7b7-110">각 분기에서 얻은 값의 형식이 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="3a7b7-111">없으면 더 명시적 `else` 분기, 해당 형식이 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="3a7b7-112">따라서 경우 유형의 `then` 분기는 모든 형식 이외의 `unit`, 있어야는 `else` 동일한 반환 형식 갖는 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="3a7b7-113">연결 하는 경우 `if...then...else` 식을 키워드를 사용 하면 함께 `elif` 대신 `else if`; 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="3a7b7-114">예제</span><span class="sxs-lookup"><span data-stu-id="3a7b7-114">Example</span></span>
<span data-ttu-id="3a7b7-115">사용 하는 방법을 보여 주는 다음 예제는 `if...then...else` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a7b7-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="3a7b7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a7b7-116">See Also</span></span>
[<span data-ttu-id="3a7b7-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3a7b7-117">F# Language Reference</span></span>](index.md)

