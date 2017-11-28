---
title: "로컬 함수(C# 프로그래밍 가이드)"
ms.date: 06/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: local functions [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b4e95d48e451038f0f7004d0901f329b2c57fe5
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="a4926-102">로컬 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a4926-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="a4926-103">C# 7부터 C#에서는 *로컬 함수*를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-103">Starting with C# 7, C# supports *local functions*.</span></span> <span data-ttu-id="a4926-104">로컬 함수는 다른 멤버에 중첩된 형식의 private 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="a4926-105">포함하는 멤버에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-105">They can only be called from their containing member.</span></span> <span data-ttu-id="a4926-106">로컬 함수는 다음에서 선언하고 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="a4926-107">메서드, 특히 반복기 메서드 및 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="a4926-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="a4926-108">생성자</span><span class="sxs-lookup"><span data-stu-id="a4926-108">Constructors</span></span>
- <span data-ttu-id="a4926-109">속성 접근자</span><span class="sxs-lookup"><span data-stu-id="a4926-109">Property accessors</span></span>
- <span data-ttu-id="a4926-110">이벤트 접근자</span><span class="sxs-lookup"><span data-stu-id="a4926-110">Event accessors</span></span>
- <span data-ttu-id="a4926-111">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="a4926-111">Anonymous methods</span></span>
- <span data-ttu-id="a4926-112">람다 식</span><span class="sxs-lookup"><span data-stu-id="a4926-112">Lambda expressions</span></span>
- <span data-ttu-id="a4926-113">종료자</span><span class="sxs-lookup"><span data-stu-id="a4926-113">Finalizers</span></span>
- <span data-ttu-id="a4926-114">다른 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="a4926-114">Other local functions</span></span>

<span data-ttu-id="a4926-115">그러나 식 본문 멤버 내에서는 로컬 함수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="a4926-116">로컬 함수에서도 지원하는 기능을 람다 식으로 구현할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="a4926-117">비교를 보려면 [로컬 함수 및 람다 식 비교](../../local-functions-vs-lambdas.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4926-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="a4926-118">로컬 함수는 코드의 의도를 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="a4926-119">코드를 읽는 모든 사용자가 포함하는 메서드를 통해서만 메서드를 호출할 수 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-119">Anyone reading you code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="a4926-120">팀 프로젝트의 경우 로컬 함수를 사용하면 다른 개발자가 실수로 클래스 또는 구조체의 다른 곳에서 직접 메서드를 호출하는 경우를 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or stuct.</span></span>
 
## <a name="local-function-syntax"></a><span data-ttu-id="a4926-121">로컬 함수 구문</span><span class="sxs-lookup"><span data-stu-id="a4926-121">Local function syntax</span></span>

<span data-ttu-id="a4926-122">로컬 함수는 포함하는 멤버 내의 중첩 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="a4926-123">해당 정의는 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-123">Its definition has the following syntax:</span></span>

```txt
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="a4926-124">로컬 함수는 [async](../../language-reference/keywords/async.md) 및 [unsafe](../../language-reference/keywords/unsafe.md) 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span> 

<span data-ttu-id="a4926-125">해당 메서드 매개 변수를 비롯하여 포함하는 멤버에 정의된 모든 지역 변수는 로컬 함수에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span> 

<span data-ttu-id="a4926-126">메서드 정의와 달리 로컬 함수 정의에는 다음 요소를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-126">Unlike a method definition, a local function definition cannot include the following elements:</span></span>

- <span data-ttu-id="a4926-127">멤버 액세스 한정자.</span><span class="sxs-lookup"><span data-stu-id="a4926-127">The member access modifier.</span></span> <span data-ttu-id="a4926-128">모든 로컬 함수는 private이므로 `private` 키워드 등의 액세스 한정자를 포함하면 컴파일러 오류 CS0106,“이 항목의 ‘private’ 한정자가 유효하지 않습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-128">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>
 
- <span data-ttu-id="a4926-129">[static](../../language-reference/keywords/static.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-129">The [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="a4926-130">`static` 키워드를 포함하면 컴파일러 오류 CS0106, “이 항목의 ‘static’ 한정자가 유효하지 않습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-130">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="a4926-131">또한 로컬 함수나 해당 매개 변수 및 형식 매개 변수에는 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-131">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span> 
 
<span data-ttu-id="a4926-132">다음 예제에서는 `GetText` 메서드에 대해 private인 로컬 함수 `AppendPathSeparator`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-132">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>
   
[!code-csharp[LocalFunctionExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a><span data-ttu-id="a4926-133">로컬 함수 및 예외</span><span class="sxs-lookup"><span data-stu-id="a4926-133">Local functions and exceptions</span></span>

<span data-ttu-id="a4926-134">로컬 함수의 유용한 기능 중 하나는 예외가 즉시 나타나도록 할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-134">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="a4926-135">메서드 반복기의 경우 반환된 시퀀스가 열거된 경우에만 예외가 나타나고 반복기를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-135">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="a4926-136">비동기 메서드의 경우 비동기 메서드에서 throw된 예외는 반환된 작업을 대기할 때 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-136">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span> 

<span data-ttu-id="a4926-137">다음 예제에서는 지정된 범위 사이의 홀수를 열거하는 `OddSequence` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-137">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="a4926-138">100보다 큰 숫자를 `OddSequence` 열거자 메서드에 전달하기 때문에 메서드가 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-138">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="a4926-139">예제의 출력에서 볼 수 있듯이 예외는 숫자를 반복하는 경우에만 나타나고 열거자를 검색할 때는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-139">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

<span data-ttu-id="a4926-140">대신, 다음 예제와 같이 로컬 함수에서 반복기를 반환하여 유효성 검사를 수행할 때, 반복기를 검색하기 전에 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-140">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="a4926-141">유사한 방식으로 로컬 함수를 사용하여 비동기 작업 외부에서 예외를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-141">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="a4926-142">일반적으로 비동기 메서드에서 throw된 예외의 경우 <xref:System.AggregateException>의 내부 예외를 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-142">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="a4926-143">로컬 함수를 사용하면 코드가 빨리 실패하여 예외가 throw되는 동시에 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-143">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="a4926-144">다음 예제에서는 `GetMultipleAsync`라는 비동기 메서드를 사용하여 지정된 시간(초) 동안 일시 중지하고 해당 시간(초)의 임의 배수인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-144">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="a4926-145">최대 지연 시간은 5초입니다. 값이 5보다 크면 <xref:System.ArgumentOutOfRangeException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-145">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="a4926-146">다음 예제와 같이 값 6이 `GetMultipleAsync` 메서드에 전달될 때 throw되는 예외는 `GetMultipleAsync` 메서드 실행이 시작된 후에 <xref:System.AggregateException>에 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-146">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

<span data-ttu-id="a4926-147">메서드 반복기와 마찬가지로, 이 예제의 코드를 리팩터링하여 비동기 메서드를 호출하기 전에 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-147">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="a4926-148">다음 예제의 출력에서 볼 수 있듯이, <xref:System.ArgumentOutOfRangeException>이 <x:System.AggregateException>에 래핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4926-148">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <x:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a><span data-ttu-id="a4926-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4926-149">See also</span></span>
[<span data-ttu-id="a4926-150">메서드</span><span class="sxs-lookup"><span data-stu-id="a4926-150">Methods</span></span>](methods.md)
