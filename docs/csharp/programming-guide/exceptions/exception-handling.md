---
title: 예외 처리(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: bbe9db48ab5cc1313c18fce66312f4334b40b9c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="36170-102">예외 처리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="36170-102">Exception Handling (C# Programming Guide)</span></span>
<span data-ttu-id="36170-103">[try](../../../csharp/language-reference/keywords/try-catch.md) 블록은 C# 프로그래머가 예외의 영향을 받을 수 있는 코드를 분할하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-103">A [try](../../../csharp/language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="36170-104">연결된 [catch](../../../csharp/language-reference/keywords/try-catch.md) 블록은 결과 예외를 처리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-104">Associated [catch](../../../csharp/language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="36170-105">[finally](../../../csharp/language-reference/keywords/try-finally.md) 블록에는 `try` 블록에서 할당되는 리소스 해제와 같이 `try` 블록에서 예외가 throw되는지 여부에 관계없이 실행되는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-105">A [finally](../../../csharp/language-reference/keywords/try-finally.md) block contains code that is run regardless of whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="36170-106">`try` 블록에는 하나 이상의 연결된 `catch` 블록, `finally` 블록 또는 둘 다가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-106">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>  
  
 <span data-ttu-id="36170-107">다음 예제에서는 `try-catch` 문, `try-finally` 문 및 `try-catch-finally` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36170-107">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-csharp[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-csharp[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 <span data-ttu-id="36170-108">`try` 블록에 `catch` 또는 `finally` 블록이 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-108">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>  
  
## <a name="catch-blocks"></a><span data-ttu-id="36170-109">catch 블록</span><span class="sxs-lookup"><span data-stu-id="36170-109">Catch Blocks</span></span>  
 <span data-ttu-id="36170-110">`catch` 블록에서는 catch할 예외의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-110">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="36170-111">형식 사양을 *예외 필터*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-111">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="36170-112">예외 형식은 <xref:System.Exception>에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-112">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="36170-113">일반적으로 `try` 블록에서 throw될 수 있는 모든 예외를 처리하는 방법을 알고 있거나 `catch` 블록의 끝에 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 포함한 경우가 아니라면 <xref:System.Exception>을 예외 필터로 지정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="36170-113">In general, do not specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you have included a [throw](../../../csharp/language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>  
  
 <span data-ttu-id="36170-114">다른 예외 필터를 사용하는 여러 `catch` 블록을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-114">Multiple `catch` blocks with different exception filters can be chained together.</span></span> <span data-ttu-id="36170-115">`catch` 블록은 코드의 위에서 아래로 계산되지만 throw되는 각 예외에 대해 하나의 `catch` 블록만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-115">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="36170-116">throw된 예외의 정확한 형식이나 기본 클래스를 지정하는 첫 번째 `catch` 블록이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-116">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="36170-117">`catch` 블록에서 일치하는 예외 필터를 지정하지 않으면 `catch` 블록이 문에 있는 경우 필터가 없는 블록이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-117">If no `catch` block specifies a matching exception filter, a `catch` block that does not have a filter is selected, if one is present in the statement.</span></span> <span data-ttu-id="36170-118">먼저 가장 구체적인(즉, 최다 파생) 예외 형식을 사용하여 `catch` 블록을 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-118">It is important to position `catch` blocks with the most specific (that is, the most derived) exception types first.</span></span>  
  
 <span data-ttu-id="36170-119">다음 조건을 충족하는 경우 예외를 catch해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-119">You should catch exceptions when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="36170-120">예외가 throw되는 이유를 충분히 이해하고 있으면 <xref:System.IO.FileNotFoundException> 개체를 catch할 때 새 파일 이름을 입력하라는 메시지를 사용자에게 표시하는 경우처럼 구체적인 복구를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-120">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>  
  
-   <span data-ttu-id="36170-121">보다 구체적인 새 예외를 생성하고 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-121">You can create and throw a new, more specific exception.</span></span>  
  
     [!code-csharp[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   <span data-ttu-id="36170-122">추가 처리를 위해 예외를 전달하기 전에 부분적으로 처리하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-122">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="36170-123">다음 예제에서 `catch` 블록은 예외를 다시 throw하기 전에 오류 로그에 항목을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-123">In the following example, a `catch` block is used to add an entry to an error log before re-throwing the exception.</span></span>  
  
     [!code-csharp[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## <a name="finally-blocks"></a><span data-ttu-id="36170-124">Finally 블록</span><span class="sxs-lookup"><span data-stu-id="36170-124">Finally Blocks</span></span>  
 <span data-ttu-id="36170-125">`finally` 블록에서는 `try` 블록에서 수행된 작업을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-125">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="36170-126">`finally` 블록이 있는 경우 `try` 블록 및 일치하는 모든 `catch` 블록 다음에 마지막으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-126">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="36170-127">`finally` 블록은 예외가 throw되었는지 예외 형식과 일치하는 `catch` 블록이 있는지에 관계없이 항상 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-127">A `finally` block always runs, regardless of whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>  
  
 <span data-ttu-id="36170-128">`finally` 블록은 런타임의 가비지 수집기가 개체를 종료할 때까지 기다리지 않고 파일 스트림, 데이터베이스 연결, 그래픽 핸들 등의 리소스를 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="36170-128">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="36170-129">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36170-129">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="36170-130">다음 예제에서는 `finally` 블록을 사용하여 `try` 블록에서 연 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-130">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="36170-131">파일을 닫기 전에 파일 핸들의 상태를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36170-131">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="36170-132">`try` 블록에서 파일을 열 수 없는 경우 파일 핸들은 값이 `null`이며 `finally` 블록은 파일을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-132">If the `try` block cannot open the file, the file handle still has the value `null` and the `finally` block does not try to close it.</span></span> <span data-ttu-id="36170-133">또는 `try` 블록에서 파일을 연 경우 `finally` 블록에서 열려 있는 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="36170-133">Alternatively, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="36170-134">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="36170-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36170-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36170-135">See Also</span></span>  
 [<span data-ttu-id="36170-136">C# 참조</span><span class="sxs-lookup"><span data-stu-id="36170-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="36170-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="36170-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="36170-138">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="36170-138">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
 [<span data-ttu-id="36170-139">try-catch</span><span class="sxs-lookup"><span data-stu-id="36170-139">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="36170-140">try-finally</span><span class="sxs-lookup"><span data-stu-id="36170-140">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="36170-141">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="36170-141">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)  
 [<span data-ttu-id="36170-142">using 문</span><span class="sxs-lookup"><span data-stu-id="36170-142">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
