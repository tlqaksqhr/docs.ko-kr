---
title: "예외 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96fc082d135d38f521429de7b4e9a668773982ea
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-exceptions-c-programming-guide"></a><span data-ttu-id="e3f2d-102">예외 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e3f2d-102">Using Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="e3f2d-103">C#에서는 런타임 시 프로그램의 오류가 예외라는 메커니즘을 사용하여 프로그램 전체에 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-103">In C#, errors in the program at run time are propagated through the program by using a mechanism called exceptions.</span></span> <span data-ttu-id="e3f2d-104">오류가 발생하는 코드에서 예외를 throw하고, 오류를 수정할 수 있는 코드에서 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-104">Exceptions are thrown by code that encounters an error and caught by code that can correct the error.</span></span> <span data-ttu-id="e3f2d-105">.NET Framework CLR(공용 언어 런타임) 또는 프로그램의 코드에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-105">Exceptions can be thrown by the .NET Framework common language runtime (CLR) or by code in a program.</span></span> <span data-ttu-id="e3f2d-106">예외가 throw되면 예외에 대한 `catch` 문이 발견될 때까지 호출 스택이 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-106">Once an exception is thrown, it propagates up the call stack until a `catch` statement for the exception is found.</span></span> <span data-ttu-id="e3f2d-107">Catch되지 않은 예외는 대화 상자를 표시하는 시스템에서 제공하는 제네릭 예외 처리기에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-107">Uncaught exceptions are handled by a generic exception handler provided by the system that displays a dialog box.</span></span>  
  
 <span data-ttu-id="e3f2d-108">예외는 <xref:System.Exception>에서 파생된 클래스로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-108">Exceptions are represented by classes derived from <xref:System.Exception>.</span></span> <span data-ttu-id="e3f2d-109">이 클래스는 예외의 형식을 식별하며 예외에 대한 세부 정보가 들어 있는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-109">This class identifies the type of exception and contains properties that have details about the exception.</span></span> <span data-ttu-id="e3f2d-110">예외를 throw하는 것에는 예외에서 파생된 클래스의 인스턴스를 만드는 것, 선택적으로 예외의 속성을 구성하는 것, 그리고 `throw` 키워드를 사용하여 개체를 throw하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-110">Throwing an exception involves creating an instance of an exception-derived class, optionally configuring properties of the exception, and then throwing the object by using the `throw` keyword.</span></span> <span data-ttu-id="e3f2d-111">예:</span><span class="sxs-lookup"><span data-stu-id="e3f2d-111">For example:</span></span>  
  
 <span data-ttu-id="e3f2d-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3f2d-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span></span>  
  
 <span data-ttu-id="e3f2d-113">예외가 throw되면 런타임은 현재 문을 확인하여 `try` 블록 내에 있는지 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-113">After an exception is thrown, the runtime checks the current statement to see whether it is within a `try` block.</span></span> <span data-ttu-id="e3f2d-114">있는 경우, `try` 블록과 연결된 `catch` 블록을 확인하여 예외를 catch할 수 있는지 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-114">If it is, any `catch` blocks associated with the `try` block are checked to see whether they can catch the exception.</span></span> <span data-ttu-id="e3f2d-115">`Catch` 블록은 일반적으로 예외 형식을 지정합니다. `catch` 블록의 형식이 예외와 동일한 형식이거나 예외의 기본 클래스인 경우 `catch` 블록이 메서드를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-115">`Catch` blocks typically specify exception types; if the type of the `catch` block is the same type as the exception, or a base class of the exception, the `catch` block can handle the method.</span></span> <span data-ttu-id="e3f2d-116">예:</span><span class="sxs-lookup"><span data-stu-id="e3f2d-116">For example:</span></span>  
  
 <span data-ttu-id="e3f2d-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3f2d-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span></span>  
  
 <span data-ttu-id="e3f2d-118">예외를 throw하는 문이 `try` 블록 내에 없거나 이를 감싸는 `try` 블록에 일치하는 `catch` 블록이 없는 경우 런타임은 호출 메서드에서 `try` 문과 `catch` 블록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-118">If the statement that throws an exception is not within a `try` block or if the `try` block that encloses it has no matching `catch` block, the runtime checks the calling method for a `try` statement and `catch` blocks.</span></span> <span data-ttu-id="e3f2d-119">런타임은 호출 스택까지 계속 확인하여 호환되는 `catch` 블록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-119">The runtime continues up the calling stack, searching for a compatible `catch` block.</span></span> <span data-ttu-id="e3f2d-120">`catch` 블록을 찾아서 실행한 후에는 해당 `catch` 블록 다음의 문으로 제어가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-120">After the `catch` block is found and executed, control is passed to the next statement after that `catch` block.</span></span>  
  
 <span data-ttu-id="e3f2d-121">`try` 문은 `catch` 블록을 둘 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-121">A `try` statement can contain more than one `catch` block.</span></span> <span data-ttu-id="e3f2d-122">예외를 처리할 수 있는 첫 번째 `catch` 문이 실행됩니다. 그 뒤의 `catch` 문은 호환되더라도 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-122">The first `catch` statement that can handle the exception is executed; any following `catch` statements, even if they are compatible, are ignored.</span></span> <span data-ttu-id="e3f2d-123">따라서 catch 블록은 가장 구체적인 것(또는 가장 많이 파생된 것)에서 가장 덜 구체적인 것 순으로 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-123">Therefore, catch blocks should always be ordered from most specific (or most-derived) to least specific.</span></span> <span data-ttu-id="e3f2d-124">예:</span><span class="sxs-lookup"><span data-stu-id="e3f2d-124">For example:</span></span>  
  
 <span data-ttu-id="e3f2d-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3f2d-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="e3f2d-126">`catch` 블록이 실행되기 전에 런타임은 `finally` 블록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-126">Before the `catch` block is executed, the runtime checks for `finally` blocks.</span></span> <span data-ttu-id="e3f2d-127">프로그래머는 `Finally` 블록을 사용해 중단된 `try` 블록으로부터 남겨질 수 있는 모호한 상태를 정리하거나, 런타임 시 가비지 수집기를 기다리지 않은 채 외부 리소스(예: 그래픽 핸들, 데이터베이스 연결 또는 파일 스트림)를 해제하여 개체를 마무리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-127">`Finally` blocks enable the programmer to clean up any ambiguous state that could be left over from an aborted `try` block, or to release any external resources (such as graphics handles, database connections or file streams) without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="e3f2d-128">예:</span><span class="sxs-lookup"><span data-stu-id="e3f2d-128">For example:</span></span>  
  
 <span data-ttu-id="e3f2d-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3f2d-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="e3f2d-130">`WriteByte()`에서 예외를 throw한 경우, `file.Close()`가 호출되지 않으면 파일을 다시 열려고 시도하는 두 번째 `try` 블록이 실패하고 파일이 잠금 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-130">If `WriteByte()` threw an exception, the code in the second `try` block that tries to reopen the file would fail if `file.Close()` is not called, and the file would remain locked.</span></span> <span data-ttu-id="e3f2d-131">`finally` 블록은 예외가 throw되도 실행되므로, 이전 예제의 `finally` 블록을 통해 파일을 정확히 닫고 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-131">Because `finally` blocks are executed even if an exception is thrown, the `finally` block in the previous example allows for the file to be closed correctly and helps avoid an error.</span></span>  
  
 <span data-ttu-id="e3f2d-132">예외가 throw된 후 호출 스택에서 호환되는 `catch` 블록을 찾지 못하면 다음 세 가지 중 하나가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-132">If no compatible `catch` block is found on the call stack after an exception is thrown, one of three things occurs:</span></span>  
  
-   <span data-ttu-id="e3f2d-133">예외가 종료자 내부에 있으면 종료자가 중단되고 기본 종료자(있는 경우)가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-133">If the exception is within a finalizer, the finalizer is aborted and the base finalizer, if any, is called.</span></span>  
  
-   <span data-ttu-id="e3f2d-134">호출 스택에 정적 생성자 또는 정적 필드 이니셜라이저가 포함된 경우 새 예외의 <xref:System.Exception.InnerException%2A> 속성에 할당된 원래 예외와 함께 <xref:System.TypeInitializationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-134">If the call stack contains a static constructor, or a static field initializer, a <xref:System.TypeInitializationException> is thrown, with the original exception assigned to the <xref:System.Exception.InnerException%2A> property of the new exception.</span></span>  
  
-   <span data-ttu-id="e3f2d-135">스레드의 시작에 도달하면 스레드가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f2d-135">If the start of the thread is reached, the thread is terminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f2d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3f2d-136">See Also</span></span>  
 <span data-ttu-id="e3f2d-137">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e3f2d-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e3f2d-138">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="e3f2d-138">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

