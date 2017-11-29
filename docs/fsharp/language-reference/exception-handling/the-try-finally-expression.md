---
title: "예외: try...finally 식(F#)"
description: "자세한 내용은 어떻게 F # ' try … 마지막 ' 코드 블록에서 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="a2441-104">예외: try...finally 식</span><span class="sxs-lookup"><span data-stu-id="a2441-104">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="a2441-105">`try...finally` 코드 블록에서 예외가 발생 하는 경우에 정리 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-105">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>


## <a name="syntax"></a><span data-ttu-id="a2441-106">구문</span><span class="sxs-lookup"><span data-stu-id="a2441-106">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="a2441-107">설명</span><span class="sxs-lookup"><span data-stu-id="a2441-107">Remarks</span></span>
<span data-ttu-id="a2441-108">`try...finally` 에 코드를 실행 하는 식은 사용할 수 있습니다 *expression2* 실행 하는 동안 예외가 생성 되는지 여부에 관계 없이 위 구문에 *expression1*합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-108">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="a2441-109">유형의 *expression2* , 전체 식의 값에 영향을 주지 않습니다 예외가 발생 하지 않는 경우 반환 되는 형식에서 마지막 값은 *expression1*합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-109">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="a2441-110">예외가 발생 아무 값도 반환 하 고 제어 흐름이 호출 스택으로 다음 일치 하는 예외 처리기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-110">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="a2441-111">예외 처리기가 있으면 프로그램 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-111">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="a2441-112">일치 하는 처리기의 코드가 실행 되 고 프로그램이 종료 코드에 전에 `finally` 분기가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-112">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="a2441-113">다음 코드에서는 `try...finally` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-113">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="a2441-114">콘솔에 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-114">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="a2441-115">출력에서 볼 수 있듯이 외부 예외를 처리 하기 전에 스트림이 닫히고 및 파일 `test.txt` 텍스트 포함 `test1`, 버퍼 플러시 하 고 예외 전송 디스크에 기록 된 나타냅니다 외부 예외 처리기에 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-115">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="a2441-116">`try...with` 구문은 별도에서 `try...finally` 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-116">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="a2441-117">따라서 코드 둘 다 요구 하는 경우는 `with` 블록 및 `finally` 블록에서 두 구문이, 다음 코드 예제와 같이 중첩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-117">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="a2441-118">계산 식의 컨텍스트에서 시퀀스 식 및 비동기 워크플로 비롯 한 **try... 마지막** 식에는 사용자 지정 구현을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-118">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="a2441-119">자세한 내용은 참조 [계산 식](../computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2441-119">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="a2441-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2441-120">See Also</span></span>
[<span data-ttu-id="a2441-121">예외 처리</span><span class="sxs-lookup"><span data-stu-id="a2441-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="a2441-122">예외: `try...with` 식</span><span class="sxs-lookup"><span data-stu-id="a2441-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
