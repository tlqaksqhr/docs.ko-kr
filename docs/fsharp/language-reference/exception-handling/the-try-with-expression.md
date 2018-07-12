---
title: '예외: try...with 식(F#)'
description: "예외 처리에 대 한 F # 'try...with' 식을 사용 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565290"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="c4ff9-103">예외: try...with 식</span><span class="sxs-lookup"><span data-stu-id="c4ff9-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="c4ff9-104">이 항목에서는 설명는 `try...with` 식, F # 언어의 예외 처리에 사용 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="c4ff9-105">구문</span><span class="sxs-lookup"><span data-stu-id="c4ff9-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="c4ff9-106">설명</span><span class="sxs-lookup"><span data-stu-id="c4ff9-106">Remarks</span></span>
<span data-ttu-id="c4ff9-107">`try...with` 식은 F #에서 예외를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="c4ff9-108">비슷합니다는 `try...catch` C# 문.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="c4ff9-109">위 구문에 코드에서 *expression1* 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="c4ff9-110">`try...with` 식이 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="c4ff9-111">예외가 throw 되 면 전체 식의 값을 반환 *expression1*합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="c4ff9-112">예외가 throw 되 면 각 *패턴* 는 경우를 제외 하 고 해당 첫 번째 일치 하는 패턴에 대 한 다시 비교 *식*으로 알려진는 *예외처리기*해당 분기 실행 되 고 해당 예외 처리기에서 식의 값을 반환 하는 전체 식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="c4ff9-113">패턴 일치 하는 경우 일치 하는 처리기를 찾을 때까지 호출 스택으로 예외 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="c4ff9-114">예외 처리기에 각 식에서 반환 된 값의 형식이 일치 해야 하는 식에서 반환 되는 형식에서 `try` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="c4ff9-115">대부분의 경우 또한 오류가 발생 했다는 사실을 각 예외 핸들러에서의 식에서 반환 될 수 있는 유효한 값 임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="c4ff9-116">자주 패턴은 옵션 형식 이어야 하는 식의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="c4ff9-117">다음 코드 예제에서는이 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="c4ff9-118">예외는.NET 예외 수 또는 F # 예외 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="c4ff9-119">사용 하 여 F # 예외를 정의할 수는 `exception` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="c4ff9-120">예외 유형 및 기타 조건;에 대해 필터링 하는 다양 한 패턴을 사용할 수 있습니다. 옵션은 다음 표에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="c4ff9-121">무늬</span><span class="sxs-lookup"><span data-stu-id="c4ff9-121">Pattern</span></span>|<span data-ttu-id="c4ff9-122">설명</span><span class="sxs-lookup"><span data-stu-id="c4ff9-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="c4ff9-123">:?</span><span class="sxs-lookup"><span data-stu-id="c4ff9-123">:?</span></span> <span data-ttu-id="c4ff9-124">*예외 형식*</span><span class="sxs-lookup"><span data-stu-id="c4ff9-124">*exception-type*</span></span>|<span data-ttu-id="c4ff9-125">지정된 된.NET 예외 형식과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="c4ff9-126">:?</span><span class="sxs-lookup"><span data-stu-id="c4ff9-126">:?</span></span> <span data-ttu-id="c4ff9-127">*예외 형식* 으로 *식별자*</span><span class="sxs-lookup"><span data-stu-id="c4ff9-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="c4ff9-128">지정된 된.NET 예외 형식과 일치 하지만 예외 명명된 된 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="c4ff9-129">*예외 이름을*(*인수*)</span><span class="sxs-lookup"><span data-stu-id="c4ff9-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="c4ff9-130">F # 예외 형식과 일치 하 고 인수를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="c4ff9-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="c4ff9-131">*identifier*</span></span>|<span data-ttu-id="c4ff9-132">모든 예외에 일치 하 고 예외 개체에 이름을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="c4ff9-133">에 해당 하는 **:? System.Exception으로 * * * 식별자*</span><span class="sxs-lookup"><span data-stu-id="c4ff9-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="c4ff9-134">*식별자* 때 *조건*</span><span class="sxs-lookup"><span data-stu-id="c4ff9-134">*identifier* when *condition*</span></span>|<span data-ttu-id="c4ff9-135">조건이 true 인 경우 모든 예외를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="c4ff9-136">예제</span><span class="sxs-lookup"><span data-stu-id="c4ff9-136">Examples</span></span>
<span data-ttu-id="c4ff9-137">다음 코드 예제에서는 다양 한 예외 처리기 패턴 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="c4ff9-138">`try...with` 구문은에서 별도 식을 고 `try...finally` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="c4ff9-139">따라서 코드 둘 다 요구 하는 경우는 `with` 블록 및 `finally` 블록 두 식을 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="c4ff9-140">사용할 수 있습니다 `try...with` 비동기 워크플로 및 기타 계산 식, 있는 경우 사용자 지정 된 버전의는 `try...with` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="c4ff9-141">자세한 내용은 참조 [비동기 워크플로](../asynchronous-workflows.md), 및 [계산 식](../computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ff9-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c4ff9-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4ff9-142">See Also</span></span>
[<span data-ttu-id="c4ff9-143">예외 처리</span><span class="sxs-lookup"><span data-stu-id="c4ff9-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="c4ff9-144">예외 형식</span><span class="sxs-lookup"><span data-stu-id="c4ff9-144">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="c4ff9-145">예외: `try...finally` 식</span><span class="sxs-lookup"><span data-stu-id="c4ff9-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
