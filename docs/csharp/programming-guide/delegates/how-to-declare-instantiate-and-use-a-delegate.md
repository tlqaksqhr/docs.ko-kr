---
title: '방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 19e5883135d65a648bb6afb74a475b761f572a95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333975"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="dc0e8-102">방법: 대리자 선언, 인스턴스화 및 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="dc0e8-102">How to: Declare, Instantiate, and Use a Delegate (C# Programming Guide)</span></span>
<span data-ttu-id="dc0e8-103">C# 1.0 이상 버전에서는 다음 예제와 같이 대리자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-103">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_2.cs)]  
  
 <span data-ttu-id="dc0e8-104">C# 2.0에서는 다음 예제와 같이 더욱 간단한 방법으로 이전 선언을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-104">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_3.cs)]  
  
 <span data-ttu-id="dc0e8-105">C# 2.0 이상 버전에서는 다음 예제와 같이 익명 메서드를 사용하여 [delegate](../../../csharp/language-reference/keywords/delegate.md)를 선언하고 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-105">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../../csharp/language-reference/keywords/delegate.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_4.cs)]  
  
 <span data-ttu-id="dc0e8-106">C# 3.0 이상에서는 다음 예제와 같이 람다 식을 사용하여 대리자를 선언하고 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-106">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_5.cs)]  
  
 <span data-ttu-id="dc0e8-107">자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-107">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="dc0e8-108">다음 예제에서는 대리자를 선언, 인스턴스화 및 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-108">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="dc0e8-109">`BookDB` 클래스는 책 데이터베이스를 유지 관리하는 서점 데이터베이스를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-109">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="dc0e8-110">그리고 데이터베이스의 모든 문고판 책을 찾아 각 책에 대해 대리자를 호출하는 `ProcessPaperbackBooks` 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-110">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="dc0e8-111">이때 사용되는 `delegate` 형식의 이름은 `ProcessBookDelegate`입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-111">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="dc0e8-112">`Test` 클래스는 이 클래스를 사용하여 문고판 책의 제목과 평균 가격을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-112">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="dc0e8-113">대리자를 사용하면 서점 데이터베이스와 클라이언트 코드 간에 기능을 효율적으로 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-113">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="dc0e8-114">클라이언트 코드는 책이 저장되는 방식이나 서점 코드가 문고판 책을 찾는 방식을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-114">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="dc0e8-115">서점 코드는 발견된 문고판 책에 대해 수행되는 처리를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-115">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc0e8-116">예</span><span class="sxs-lookup"><span data-stu-id="dc0e8-116">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_6.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="dc0e8-117">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dc0e8-117">Robust Programming</span></span>  
  
-   <span data-ttu-id="dc0e8-118">대리자 선언</span><span class="sxs-lookup"><span data-stu-id="dc0e8-118">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="dc0e8-119">다음 문은 새 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-119">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_7.cs)]  
  
     <span data-ttu-id="dc0e8-120">각 대리자 형식은 인수의 수와 형식 및 캡슐화 가능한 메서드의 형식과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-120">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="dc0e8-121">새 인수 형식 또는 반환 값 형식 집합이 필요할 때마다 새 대리자 형식을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-121">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
-   <span data-ttu-id="dc0e8-122">대리자 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="dc0e8-122">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="dc0e8-123">대리자 형식을 선언한 후에는 대리자 개체를 생성하여 특정 메서드와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-123">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="dc0e8-124">이전 예제의 경우 다음 예제와 같이 `PrintTitle` 메서드를 `ProcessPaperbackBooks` 메서드에 전달하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-124">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_8.cs)]  
  
     <span data-ttu-id="dc0e8-125">이렇게 하면 [정적](../../../csharp/language-reference/keywords/static.md) 메서드 `Test.PrintTitle`에 연결된 새 대리자 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-125">This creates a new delegate object associated with the [static](../../../csharp/language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="dc0e8-126">마찬가지로 개체 `totaller`의 비정적 메서드 `AddBookToTotal`도 다음 예제와 같이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-126">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_9.cs)]  
  
     <span data-ttu-id="dc0e8-127">두 경우 모두 새 대리자 개체가 `ProcessPaperbackBooks` 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-127">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="dc0e8-128">대리자를 만든 후에도 대리자가 연결된 메서드는 변경되지 않습니다. 대리자 개체는 변경이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-128">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
-   <span data-ttu-id="dc0e8-129">대리자 호출</span><span class="sxs-lookup"><span data-stu-id="dc0e8-129">Calling a delegate.</span></span>  
  
     <span data-ttu-id="dc0e8-130">생성된 대리자 개체는 대개 대리자를 호출하는 다른 코드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-130">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="dc0e8-131">대리자 개체의 이름 뒤에 대리자로 전달할 인수를 괄호로 묶어 추가한 형식을 사용하여 대리자 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-131">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="dc0e8-132">아래에 대리자 호출의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-132">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-declare-instantiate-and-use-a-delegate_10.cs)]  
  
     <span data-ttu-id="dc0e8-133">대리자는 이 예제와 같이 동기적으로 호출할 수도 있고 `BeginInvoke` 및 `EndInvoke` 메서드를 사용하여 비동기적으로 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc0e8-133">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0e8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc0e8-134">See Also</span></span>  
 [<span data-ttu-id="dc0e8-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dc0e8-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dc0e8-136">이벤트</span><span class="sxs-lookup"><span data-stu-id="dc0e8-136">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="dc0e8-137">대리자</span><span class="sxs-lookup"><span data-stu-id="dc0e8-137">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
