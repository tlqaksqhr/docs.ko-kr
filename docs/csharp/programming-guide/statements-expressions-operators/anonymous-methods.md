---
title: "무명 메서드(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96e78257c5aab84562cd8cdb336bb5a91ba59534
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="anonymous-methods-c-programming-guide"></a><span data-ttu-id="c43af-102">무명 메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c43af-102">Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="c43af-103">2.0 이전의 C# 버전에서 [delegate](../../../csharp/language-reference/keywords/delegate.md)를 선언하는 유일한 방법은 [명명된 메서드](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)를 사용하는 것이었습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-103">In versions of C# before 2.0, the only way to declare a [delegate](../../../csharp/language-reference/keywords/delegate.md) was to use [named methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md).</span></span> <span data-ttu-id="c43af-104">C# 2.0에서는 무명 메서드가 도입되었고, C# 3.0 이상에서는 람다 식이 인라인 코드를 작성하는 기본 방법으로 무명 메서드를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-104">C# 2.0 introduced anonymous methods and in C# 3.0 and later, lambda expressions supersede anonymous methods as the preferred way to write inline code.</span></span> <span data-ttu-id="c43af-105">그러나 이 항목의 무명 메서드 관련 정보는 람다 식에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-105">However, the information about anonymous methods in this topic also applies to lambda expressions.</span></span> <span data-ttu-id="c43af-106">무명 메서드가 람다 식에서 찾을 수 없는 기능을 제공하는 한 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-106">There is one case in which an anonymous method provides functionality not found in lambda expressions.</span></span> <span data-ttu-id="c43af-107">무명 메서드를 사용하여 매개 변수 목록을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-107">Anonymous methods enable you to omit the parameter list.</span></span> <span data-ttu-id="c43af-108">즉, 무명 메서드를 여러 시그니처를 가진 대리자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-108">This means that an anonymous method can be converted to delegates with a variety of signatures.</span></span> <span data-ttu-id="c43af-109">람다 식에서는 이 작업이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-109">This is not possible with lambda expressions.</span></span> <span data-ttu-id="c43af-110">람다 식에 대한 자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c43af-110">For more information specifically about lambda expressions, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="c43af-111">무명 메서드를 만드는 것은 기본적으로 코드 블록을 대리자 매개 변수로 전달하는 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-111">Creating anonymous methods is essentially a way to pass a code block as a delegate parameter.</span></span> <span data-ttu-id="c43af-112">다음 두 가지 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c43af-112">Here are two examples:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 <span data-ttu-id="c43af-113">무명 메서드를 사용하면 별도 메서드를 만들 필요가 없기 때문에 대리자를 인스턴스화하는 코딩 오버헤드가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-113">By using anonymous methods, you reduce the coding overhead in instantiating delegates because you do not have to create a separate method.</span></span>  
  
 <span data-ttu-id="c43af-114">예를 들어 메서드를 만드는 것이 불필요한 오버헤드처럼 보일 수도 있는 경우 대리자 대신 코드 블록을 지정하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-114">For example, specifying a code block instead of a delegate can be useful in a situation when having to create a method might seem an unnecessary overhead.</span></span> <span data-ttu-id="c43af-115">좋은 예로 새 스레드를 시작하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-115">A good example would be when you start a new thread.</span></span> <span data-ttu-id="c43af-116">이 클래스는 스레드를 만들며, 대리자에 대한 추가 메서드를 만들지 않고 스레드에서 실행하는 코드도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-116">This class creates a thread and also contains the code that the thread executes without creating an additional method for the delegate.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="c43af-117">설명</span><span class="sxs-lookup"><span data-stu-id="c43af-117">Remarks</span></span>  
 <span data-ttu-id="c43af-118">무명 메서드의 매개 변수 범위는 *무명 메서드 블록*입니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-118">The scope of the parameters of an anonymous method is the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="c43af-119">대상이 블록 외부에 있을 경우 [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md) 등의 점프 문을 무명 메서드 블록 내부에 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-119">It is an error to have a jump statement, such as [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md), or [continue](../../../csharp/language-reference/keywords/continue.md), inside the anonymous method block if the target is outside the block.</span></span> <span data-ttu-id="c43af-120">대상이 블록 내부에 있을 경우 `goto`, `break`, `continue` 등의 점프 문을 무명 메서드 블록 외부에 사용하는 것도 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-120">It is also an error to have a jump statement, such as `goto`, `break`, or `continue`, outside the anonymous method block if the target is inside the block.</span></span>  
  
 <span data-ttu-id="c43af-121">범위에 무명 메서드 선언이 포함된 지역 변수 및 매개 변수를 무명 메서드의 *외부* 변수라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-121">The local variables and parameters whose scope contains an anonymous method declaration are called *outer* variables of the anonymous method.</span></span> <span data-ttu-id="c43af-122">예를 들어 다음 코드 세그먼트에서 `n`은 외부 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-122">For example, in the following code segment, `n` is an outer variable:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 <span data-ttu-id="c43af-123">외부 변수 `n`에 대한 참조는 대리자를 만들 때 *캡처*됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-123">A reference to the outer variable `n` is said to be *captured* when the delegate is created.</span></span> <span data-ttu-id="c43af-124">지역 변수와 달리 캡처된 변수의 수명은 무명 메서드를 참조하는 대리자가 가비지 수집에 적격할 때까지 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-124">Unlike local variables, the lifetime of a captured variable extends until the delegates that reference the anonymous methods are eligible for garbage collection.</span></span>  
  
 <span data-ttu-id="c43af-125">무명 메서드는 외부 범위의 [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-125">An anonymous method cannot access the [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters of an outer scope.</span></span>  
  
 <span data-ttu-id="c43af-126">안전하지 않은 코드는 *무명 메서드 블록* 내에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-126">No unsafe code can be accessed within the *anonymous-method-block*.</span></span>  
  
 <span data-ttu-id="c43af-127">[is](../../../csharp/language-reference/keywords/is.md) 연산자의 왼쪽에는 무명 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-127">Anonymous methods are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c43af-128">예</span><span class="sxs-lookup"><span data-stu-id="c43af-128">Example</span></span>  
 <span data-ttu-id="c43af-129">다음 예제에서는 대리자를 인스턴스화하는 다음 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-129">The following example demonstrates two ways of instantiating a delegate:</span></span>  
  
-   <span data-ttu-id="c43af-130">무명 메서드에 대리자 연결</span><span class="sxs-lookup"><span data-stu-id="c43af-130">Associating the delegate with an anonymous method.</span></span>  
  
-   <span data-ttu-id="c43af-131">명명된 메서드(`DoWork`)에 대리자 연결</span><span class="sxs-lookup"><span data-stu-id="c43af-131">Associating the delegate with a named method (`DoWork`).</span></span>  
  
 <span data-ttu-id="c43af-132">각각의 경우 대리자를 호출할 때 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c43af-132">In each case, a message is displayed when the delegate is invoked.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c43af-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c43af-133">See Also</span></span>  
 [<span data-ttu-id="c43af-134">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c43af-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c43af-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c43af-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c43af-136">대리자</span><span class="sxs-lookup"><span data-stu-id="c43af-136">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="c43af-137">람다 식</span><span class="sxs-lookup"><span data-stu-id="c43af-137">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="c43af-138">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="c43af-138">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="c43af-139">메서드</span><span class="sxs-lookup"><span data-stu-id="c43af-139">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="c43af-140">명명된 메서드 및 무명 메서드가 있는 대리자</span><span class="sxs-lookup"><span data-stu-id="c43af-140">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
