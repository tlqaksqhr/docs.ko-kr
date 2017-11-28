---
title: "조건식: if... then...else(F#)"
description: "F # 코드의 다른 분기를 실행 하려면 조건부 식을 작성 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 3531a112eb53657d5e9102d5e5f3be988360b76e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="0b6c8-104">조건식:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="0b6c8-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="0b6c8-105">`if...then...else` 식 코드의 다른 분기를 실행 하 고 주어진 부울 식에 따라 다른 값으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="0b6c8-106">구문</span><span class="sxs-lookup"><span data-stu-id="0b6c8-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="0b6c8-107">설명</span><span class="sxs-lookup"><span data-stu-id="0b6c8-107">Remarks</span></span>
<span data-ttu-id="0b6c8-108">위 구문에서 *expression1* 부울 식으로 평가 되 면 실행 `true`, 그렇지 않으면 *expression2* 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="0b6c8-109">와 달리 다른 언어로 `if...then...else` 구문은 문이 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="0b6c8-110">즉, 실행 되는 분기의 마지막 식의 값은 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="0b6c8-111">각 분기에서 얻은 값의 형식이 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="0b6c8-112">없으면 더 명시적 `else` 분기, 해당 형식이 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="0b6c8-113">따라서 경우 유형의 `then` 분기는 모든 형식 이외의 `unit`, 있어야는 `else` 동일한 반환 형식 갖는 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="0b6c8-114">연결 하는 경우 `if...then...else` 식을 키워드를 사용 하면 함께 `elif` 대신 `else if`; 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="0b6c8-115">예제</span><span class="sxs-lookup"><span data-stu-id="0b6c8-115">Example</span></span>
<span data-ttu-id="0b6c8-116">사용 하는 방법을 보여 주는 다음 예제는 `if...then...else` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b6c8-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
John
910 is less than 20
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="0b6c8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b6c8-117">See Also</span></span>
[<span data-ttu-id="0b6c8-118">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0b6c8-118">F# Language Reference</span></span>](index.md)

