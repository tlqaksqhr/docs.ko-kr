---
title: '예외: raise 함수(F#)'
description: "오류 또는 예외 조건이 발생 했음을 알리는 데 F # 'raise' 함수를 사용 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564757"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="2fa54-103">예외: raise 함수</span><span class="sxs-lookup"><span data-stu-id="2fa54-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="2fa54-104">`raise` 함수는 오류 또는 예외 조건이 발생 했음을 알리는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="2fa54-105">오류에 대 한 정보는 예외 개체에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-105">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="2fa54-106">구문</span><span class="sxs-lookup"><span data-stu-id="2fa54-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="2fa54-107">설명</span><span class="sxs-lookup"><span data-stu-id="2fa54-107">Remarks</span></span>
<span data-ttu-id="2fa54-108">`raise` 함수는 예외 개체를 생성 하 고 스택 해제 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="2fa54-109">스택 해제 프로세스는이 프로세스의 동작이 다른 모든.NET 언어에 있는 것과 같은 공용 언어 런타임 (CLR)에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="2fa54-110">스택 해제 프로세스는 생성 된 예외와 일치 하는 예외 처리기에 대 한 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="2fa54-111">현재에서 검색 시작 `try...with` 식에 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="2fa54-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="2fa54-112">각 패턴에는 `with` 순서 대로 블록 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="2fa54-113">일치 하는 예외 처리기가 발견 되 면 예외 것으로 간주 됩니다; 처리 그렇지 않으면 스택의 스택이 해제 되 고 `with` 일치 하는 처리기를 찾을 때까지 호출 체인 블록을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="2fa54-114">모든 `finally` 스택이 해제 되므로 순서 대로 호출 체인에 있는 블록도 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="2fa54-115">`raise` 함수는 해당 하는 `throw` C# 또는 c + +입니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="2fa54-116">사용 하 여 `reraise` 에 catch 처리기 호출 체인 동일한 예외를 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="2fa54-117">다음 코드 예제는 사용법을 보여 줍니다.는 `raise` 함수에서 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="2fa54-118">`raise` 다음 예제와 같이 함수를.NET 예외를 발생 사용 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa54-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="2fa54-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fa54-119">See Also</span></span>
[<span data-ttu-id="2fa54-120">예외 처리</span><span class="sxs-lookup"><span data-stu-id="2fa54-120">Exception Handling</span></span>](index.md)

[<span data-ttu-id="2fa54-121">예외 형식</span><span class="sxs-lookup"><span data-stu-id="2fa54-121">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="2fa54-122">예외: `try...with` 식</span><span class="sxs-lookup"><span data-stu-id="2fa54-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="2fa54-123">예외: `try...finally` 식</span><span class="sxs-lookup"><span data-stu-id="2fa54-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="2fa54-124">예외: `failwith` 함수</span><span class="sxs-lookup"><span data-stu-id="2fa54-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="2fa54-125">예외: `invalidArg` 함수</span><span class="sxs-lookup"><span data-stu-id="2fa54-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
