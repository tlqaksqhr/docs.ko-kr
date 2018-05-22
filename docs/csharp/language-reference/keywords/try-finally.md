---
title: try-finally(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 696eb531fe3e340f7fe0ae12483648119cf5a7eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="d1370-102">try-finally(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d1370-102">try-finally (C# Reference)</span></span>
<span data-ttu-id="d1370-103">`finally` 블록을 사용하면 [try](../../../csharp/language-reference/keywords/try-catch.md) 블록에서 할당된 리소스를 정리할 수 있으며, `try` 블록에서 예외가 발생하는 경우에도 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](../../../csharp/language-reference/keywords/try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="d1370-104">일반적으로 `finally` 블록의 문은 제어가 `try` 문을 벗어날 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="d1370-105">제어 전송은 정상적인 실행 결과, `break`, `continue`, `goto` 또는 `return` 문의 실행 결과 또는 `try` 문에서 예외 전파의 결과로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>  
  
 <span data-ttu-id="d1370-106">처리된 예외 내에서는 연결된 `finally` 블록이 항상 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="d1370-107">그러나 예외가 처리되지 않은 경우 `finally` 블록의 실행 여부는 예외 해제 작업의 트리거 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="d1370-108">트리거 방법은 다시 사용자 컴퓨터의 설정 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-108">That, in turn, is dependent on how your computer is set up.</span></span>
  
 <span data-ttu-id="d1370-109">일반적으로 처리되지 않은 예외로 응용 프로그램이 종료되는 경우 `finally` 블록의 실행 여부는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-109">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="d1370-110">그러나 해당 상황에서도 실행해야 하는 문이 `finally` 블록에 있는 경우 한 가지 솔루션은 `catch` 블록을 `try`-`finally` 문에 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-110">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="d1370-111">또는 호출 스택에서 상위 `try`-`finally` 문의 `try` 블록에 throw될 수 있는 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-111">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="d1370-112">즉, `try`-`finally` 문을 포함하는 메서드를 호출하는 메서드, 해당 메서드를 호출하는 메서드 또는 호출 스택의 임의 메서드에 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-112">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="d1370-113">예외가 catch되지 않는 경우 `finally`의 실행은 운영 체제에서 예외 해제 작업 트리거를 선택하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-113">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1370-114">예</span><span class="sxs-lookup"><span data-stu-id="d1370-114">Example</span></span>  
 <span data-ttu-id="d1370-115">다음 예제에서는 잘못된 변환 문으로 인해 `System.InvalidCastException` 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-115">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="d1370-116">예외가 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-116">The exception is unhandled.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 <span data-ttu-id="d1370-117">다음 예제에서는 `TryCast` 메서드의 예외가 호출 스택의 위에 있는 메서드에서 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-117">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 <span data-ttu-id="d1370-118">`finally`에 대한 자세한 내용은 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1370-118">For more information about `finally`, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
 <span data-ttu-id="d1370-119">C#에는 <xref:System.IDisposable> 개체에 대한 유사한 기능을 편리한 구문으로 제공하는 [using 문](../../../csharp/language-reference/keywords/using-statement.md)도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1370-119">C# also contains the [using statement](../../../csharp/language-reference/keywords/using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d1370-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d1370-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1370-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1370-121">See Also</span></span>  
 [<span data-ttu-id="d1370-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d1370-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d1370-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d1370-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d1370-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d1370-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d1370-125">try, throw 및 catch 문(C++)</span><span class="sxs-lookup"><span data-stu-id="d1370-125">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [<span data-ttu-id="d1370-126">예외 처리 문</span><span class="sxs-lookup"><span data-stu-id="d1370-126">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="d1370-127">throw</span><span class="sxs-lookup"><span data-stu-id="d1370-127">throw</span></span>](../../../csharp/language-reference/keywords/throw.md)  
 [<span data-ttu-id="d1370-128">try-catch</span><span class="sxs-lookup"><span data-stu-id="d1370-128">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="d1370-129">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="d1370-129">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
