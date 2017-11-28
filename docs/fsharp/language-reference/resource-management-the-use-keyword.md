---
title: "리소스 관리: use 키워드(F#)"
description: "F # 키워드 'use'와 '사용' 함수를 초기화 및 리소스의 해제를 제어할 수 있는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="b85c8-104">리소스 관리: use 키워드</span><span class="sxs-lookup"><span data-stu-id="b85c8-104">Resource Management: The use Keyword</span></span>

<span data-ttu-id="b85c8-105">키워드에 설명 `use` 및 `using` 초기화 및 리소스의 해제를 제어할 수 있는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-105">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="b85c8-106">리소스</span><span class="sxs-lookup"><span data-stu-id="b85c8-106">Resources</span></span>
<span data-ttu-id="b85c8-107">용어 *리소스* 에 여러 가지 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-107">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="b85c8-108">예, 리소스 문자열, 그래픽, like, 같은 있지만이 컨텍스트에서 응용 프로그램을 사용 하는 데이터 수 *리소스* 그래픽 장치 컨텍스트, 파일 핸들, 네트워크 등의 소프트웨어 또는 운영 체제 리소스에 대 한 참조 와 데이터베이스 연결, 대기 핸들 등과 같은 동시성 개체.</span><span class="sxs-lookup"><span data-stu-id="b85c8-108">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="b85c8-109">응용 프로그램에서 이러한 리소스의 사용에 운영 체제 또는 다른 응용 프로그램에 제공 될 수 있도록 풀에 리소스의 이후 릴리스 후 다른 리소스 공급자에서 리소스를 확보를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-109">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="b85c8-110">문제는 응용 프로그램 일반적인 풀으로 리소스를 해제 하지 않는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-110">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="b85c8-111">리소스 관리</span><span class="sxs-lookup"><span data-stu-id="b85c8-111">Managing Resources</span></span>
<span data-ttu-id="b85c8-112">책임 지 고 효율적으로 응용 프로그램의 리소스를 관리 하려면 신속 하 게 하 고 예측 가능한 방식으로 리소스를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-112">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="b85c8-113">.NET Framework를 사용 하면 제공 하 여이 작업을 수행 된 `System.IDisposable` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-113">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="b85c8-114">구현 하는 형식은 `System.IDisposable` 에 `System.IDisposable.Dispose` 메서드를 올바르게 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-114">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="b85c8-115">잘 작성 된 응용 프로그램을 `System.IDisposable.Dispose` 제한 된 리소스를 보유 하는 모든 개체는 더 이상 필요 없는 신속 하 게 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-115">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="b85c8-116">다행히 대부분.NET 언어를 더 쉽게 확인을 지원 하 고 F #도 예외가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-116">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="b85c8-117">dispose 패턴을 지 원하는 두 개의 유용한 언어 구문이 있습니다:는 `use` 바인딩 및 `using` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-117">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="b85c8-118">바인딩을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b85c8-118">use Binding</span></span>
<span data-ttu-id="b85c8-119">`use` 키워드의 구문과 유사 합니다 하는 폼에는 `let` 바인딩:</span><span class="sxs-lookup"><span data-stu-id="b85c8-119">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="b85c8-120">사용 하 여 *값* = *식*</span><span class="sxs-lookup"><span data-stu-id="b85c8-120">use *value* = *expression*</span></span>

<span data-ttu-id="b85c8-121">와 동일한 기능을 제공는 `let` 바인딩 있지만 경우에 대 한 호출 추가 `Dispose` 값 범위를 벗어날 때 값에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-121">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="b85c8-122">컴파일러는 값에 대해 null 확인을 삽입 되는 경우 값은 참고 `null`에 대 한 호출 `Dispose` 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-122">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="b85c8-123">다음 예제를 사용 하 여 파일을 자동으로 종결 하는 방법을 보여 줍니다는 `use` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-123">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
<span data-ttu-id="b85c8-124">사용할 수 있습니다 `use` 계산 식에는 사용자 지정 된 버전의 경우는 `use` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-124">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="b85c8-125">자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-125">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="using-function"></a><span data-ttu-id="b85c8-126">함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b85c8-126">using Function</span></span>
<span data-ttu-id="b85c8-127">`using` 함수 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-127">The `using` function has the following form:</span></span>

<span data-ttu-id="b85c8-128">`using`(*expression1*) *람다 또는 함수*</span><span class="sxs-lookup"><span data-stu-id="b85c8-128">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="b85c8-129">에 `using` 식 *expression1* 삭제 해야 하는 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-129">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="b85c8-130">결과 *expression1* (삭제 해야 하는 개체)가 인수, *값*을 *람다 또는 함수*, 단일 필요한 함수 중 하나는 생성 되는 값과 일치 하는 형식의 인수를 남은 *expression1*, 또는 해당 형식의 인수를 예상 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-130">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="b85c8-131">함수 실행 끝날 때 런타임에서 호출 `Dispose` 리소스를 해제 하 고 (값이 `null`, Dispose에 대 한 호출 시도 하지는 경우).</span><span class="sxs-lookup"><span data-stu-id="b85c8-131">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="b85c8-132">다음 예제는 `using` 람다 식 사용 하 여 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-132">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="b85c8-133">에서는 다음 예제는 `using` 함수로 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-133">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="b85c8-134">다른 인수가 이미 적용 하는 함수 일 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-134">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="b85c8-135">다음 코드 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-135">The following code example demonstrates this.</span></span> <span data-ttu-id="b85c8-136">문자열이 포함 된 파일을 만듭니다 `XYZ`합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-136">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="b85c8-137">`using` 함수 및 `use` 바인딩은 거의 같은 방식으로 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-137">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="b85c8-138">`using` 키워드 좀 더 잘 제어할 때 `Dispose` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-138">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="b85c8-139">사용 하는 경우 `using`, `Dispose` 사용 하는 경우, 함수 또는 람다 식의 끝에서 호출 되는 `use` 키워드를 `Dispose` 포함 하는 코드 블록의 끝에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-139">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="b85c8-140">일반적으로 사용 하려면 해야 `use` 대신는 `using` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b85c8-140">In general, you should prefer to use `use` instead of the `using` function.</span></span>


## <a name="see-also"></a><span data-ttu-id="b85c8-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b85c8-141">See Also</span></span>
[<span data-ttu-id="b85c8-142">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b85c8-142">F# Language Reference</span></span>](index.md)
