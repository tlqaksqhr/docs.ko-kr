---
title: "대리자(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c78b06b23805082251db8bbd7b377ffd36c6ef03
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="638d5-102">대리자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="638d5-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="638d5-103">[대리자](../../../csharp/language-reference/keywords/delegate.md)는 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="638d5-104">대리자를 인스턴스화하면 모든 메서드가 있는 인스턴스를 호환되는 시그니처 및 반환 형식에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="638d5-105">대리자 인스턴스를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="638d5-106">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="638d5-107">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="638d5-108">사용자 지정 메서드를 만들면 Windows 컨트롤 같은 클래스가 특정 이벤트가 발생했을 때 해당 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="638d5-109">다음 예제에서는 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="638d5-110">액세스 가능한 클래스 또는 대리자 형식과 일치하는 구조의 모든 메서드는 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="638d5-111">메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="638d5-112">메서드를 대리자에 할당하면 프로그래밍 방식으로 메서드 호출을 변경하고 기존 클래스에 새 코드를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="638d5-113">메서드 오버로드의 컨텍스트에서는 메서드 시그니처에 반환 값이 포함되지 않지만</span><span class="sxs-lookup"><span data-stu-id="638d5-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="638d5-114">대리자 컨텍스트에서는 시그니처에 반환 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="638d5-115">즉 메서드의 반환 형식이 대리자의 반환 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="638d5-116">대리자에서는 이와 같이 메서드를 매개 변수로 취급할 수 있으므로 대리자는 콜백 메서드 정의에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="638d5-117">예를 들어, 두 개체를 비교하는 메서드에 대한 참조를 정렬 알고리즘에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="638d5-118">비교 코드는 별도의 절차이기 때문에 정렬 알고리즘을 보다 일반적인 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="638d5-119">대리자 개요</span><span class="sxs-lookup"><span data-stu-id="638d5-119">Delegates Overview</span></span>  
 <span data-ttu-id="638d5-120">대리자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="638d5-121">대리자는 C++의 함수 포인터와 유사하지만 형식이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-121">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="638d5-122">대리자를 통해 메서드를 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="638d5-123">대리자를 사용하여 콜백 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="638d5-124">여러 대리자를 연결할 수 있습니다. 예를 들어 단일 이벤트에 대해 여러 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="638d5-125">메서드와 대리자 형식이 정확히 일치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="638d5-126">자세한 내용은 [대리자의 가변성 사용](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="638d5-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="638d5-127">C# 버전 2.0에는 별도로 정의된 메서드 대신 코드 블록을 매개 변수로 전달할 수 있도록 하는 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)라는 개념이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="638d5-128">C# 3.0에는 인라인 코드 블록을 더 간단하게 작성할 수 있는 람다 식이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="638d5-129">특정 컨텍스트에서는 무명 메서드와 람다 식 모두 대리자 형식으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="638d5-130">이 두 기능을 익명 함수라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="638d5-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="638d5-131">람다 식에 대한 자세한 내용은 [익명 함수](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="638d5-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="638d5-132">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="638d5-132">In This Section</span></span>  
  
-   [<span data-ttu-id="638d5-133">대리자 사용</span><span class="sxs-lookup"><span data-stu-id="638d5-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="638d5-134">인터페이스(C# 프로그래밍 가이드) 대신 대리자를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="638d5-134">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/library/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="638d5-135">명명된 메서드 및 무명 메서드가 있는 대리자</span><span class="sxs-lookup"><span data-stu-id="638d5-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="638d5-136">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="638d5-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="638d5-137">대리자의 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="638d5-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="638d5-138">방법: 대리자 조합(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="638d5-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="638d5-139">방법: 대리자 선언, 인스턴스화 및 사용</span><span class="sxs-lookup"><span data-stu-id="638d5-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="638d5-140">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="638d5-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="638d5-141">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="638d5-141">Featured Book Chapters</span></span>  
 <span data-ttu-id="638d5-142">[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195395) 의 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="638d5-142">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="638d5-143">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="638d5-143">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638d5-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="638d5-144">See Also</span></span>  
 <xref:System.Delegate>  
 [<span data-ttu-id="638d5-145">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="638d5-145">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="638d5-146">이벤트</span><span class="sxs-lookup"><span data-stu-id="638d5-146">Events</span></span>](../../../csharp/programming-guide/events/index.md)
