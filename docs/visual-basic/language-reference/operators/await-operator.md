---
title: Await 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d639d1398c0f783fcfa40ee9ff278922fd6fc7b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="32e6e-102">Await 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32e6e-102">Await Operator (Visual Basic)</span></span>
<span data-ttu-id="32e6e-103">대기 중인 작업이 완료될 때까지 메서드 실행을 일시 중단하려면 비동기 메서드 또는 람다 식의 피연산자에 `Await` 연산자를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="32e6e-104">작업은 진행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-104">The task represents ongoing work.</span></span>  
  
 <span data-ttu-id="32e6e-105">메서드는 `Await` 사용 있어야는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="32e6e-106">`Async` 한정자를 사용하여 정의하고 일반적으로 하나 이상의 `Await` 식을 포함하는 이러한 메서드를 *비동기 메서드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32e6e-107">`Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="32e6e-108">비동기 프로그래밍에 대 한 소개를 참조 하십시오. [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="32e6e-109">적용 하는 작업을 일반적으로 `Await` 연산자가 구현 하는 메서드 호출에서 반환 값은 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=204847), 즉, 한 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="32e6e-110">다음 코드에서 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>는 `getContentsTask`, `Task(Of Byte())`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="32e6e-111">이 작업은 작업이 완료될 때 실제 바이트 배열을 생성하기 위한 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="32e6e-112">`Await` 연산자는 `getContentsTask`에 적용되어 `getContentsTask`가 완료될 때까지 `SumPageSizesAsync`의 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="32e6e-113">동시에 컨트롤은 `SumPageSizesAsync` 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="32e6e-114">`getContentsTask`가 완료되면 `Await` 식이 바이트 배열로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>  
  
```vb  
Private Async Function SumPageSizesAsync() As Task  
  
    ' To use the HttpClient type in desktop apps, you must include a using directive and add a   
    ' reference for the System.Net.Http namespace.  
    Dim client As HttpClient = New HttpClient()   
    ' . . .   
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
    Dim urlContents As Byte() = Await getContentsTask  
  
    ' Equivalently, now that you see how it works, you can write the same thing in a single line.  
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ' . . .  
End Function  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="32e6e-115">전체 예제는 [연습: Async 및 Await를 사용하여 웹에 액세스](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32e6e-115">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="32e6e-116">샘플은 Microsoft 웹 사이트의 [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409)(비동기 샘플: 웹 액세스 연습(C# 및 Visual Basic))에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-116">You can download the sample from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) on the Microsoft website.</span></span> <span data-ttu-id="32e6e-117">예제는 AsyncWalkthrough_HttpClient 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-117">The example is in the AsyncWalkthrough_HttpClient project.</span></span>  
  
 <span data-ttu-id="32e6e-118">`Await`가 `Task(Of TResult)`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식의 형식은 TResult입니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-118">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="32e6e-119">`Await`가 `Task`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식은 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-119">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="32e6e-120">다음 예제에서 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-120">The following example illustrates the difference.</span></span>  
  
```vb  
' Await used with a method that returns a Task(Of TResult).  
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()  
  
' Await used with a method that returns a Task.  
Await AsyncMethodThatReturnsTask()  
```  
  
 <span data-ttu-id="32e6e-121">`Await` 식 또는 문은 식이 실행되고 있는 스레드를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-121">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="32e6e-122">대신 `Await` 식 이후 컴파일러가 대기 중인 작업에서 연속된 작업으로 비동기 메서드의 나머지 부분을 등록하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-122">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="32e6e-123">그런 다음 컨트롤이 비동기 메서드 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-123">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="32e6e-124">작업이 완료되면 해당 연속 작업이 호출되고 중단된 비동기 메서드의 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-124">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>  
  
 <span data-ttu-id="32e6e-125">`Await` 식은 `Async` 수정자로 표시된 람다 식 또는 바로 바깥쪽에 있는 메서드의 본문에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-125">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="32e6e-126">용어 *Await* 해당 컨텍스트에서만에서 키워드 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-126">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="32e6e-127">다른 컨텍스트에서는 식별자로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-127">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="32e6e-128">비동기 메서드 또는 람다 식 안에 `Await` 식은 쿼리 식에서 발생할 수 없습니다는 `catch` 또는 `finally` 블록는 [시도 중... Catch 하는 중... 마지막으로](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 의 루프 제어 변수 식에서 문에 `For` 또는 `For Each` 루프 또는 본문에는 [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) 문.</span><span class="sxs-lookup"><span data-stu-id="32e6e-128">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="32e6e-129">예외</span><span class="sxs-lookup"><span data-stu-id="32e6e-129">Exceptions</span></span>  
 <span data-ttu-id="32e6e-130">대부분의 비동기 메서드는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-130">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="32e6e-131">반환된 작업의 속성은 작업의 완료 여부, 비동기 메서드가 예외를 발생시켰는지 취소되었는지 여부 및 최종 결과 등 해당 상태 및 기록에 대한 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-131">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="32e6e-132">`Await` 연산자는 해당 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-132">The `Await` operator accesses those properties.</span></span>  
  
 <span data-ttu-id="32e6e-133">예외를 발생시키는 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-133">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>  
  
 <span data-ttu-id="32e6e-134">취소된 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 <xref:System.OperationCanceledException>을 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-134">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>  
  
 <span data-ttu-id="32e6e-135">오류가 발생한 상태의 단일 작업에는 여러 예외가 반영될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-135">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="32e6e-136">예를 들어 작업은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 호출의 결과일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-136">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="32e6e-137">이러한 작업을 기다릴 경우 await 작업에서 예외 중 하나만 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-137">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="32e6e-138">그러나 다시 throw되는 예외를 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-138">However, you can't predict which of the exceptions is rethrown.</span></span>  
  
 <span data-ttu-id="32e6e-139">비동기 메서드에의 오류 처리의 예 참조 [시도 중... Catch 하는 중... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-139">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e6e-140">예제</span><span class="sxs-lookup"><span data-stu-id="32e6e-140">Example</span></span>  
 <span data-ttu-id="32e6e-141">다음 Windows Forms 예제에서는 비동기 메서드 `WaitAsynchronouslyAsync`에서 `Await`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-141">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="32e6e-142">해당 메서드의 동작을 `WaitSynchronously`의 동작과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-142">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="32e6e-143">`Await` 연산자가 없는 경우 `WaitSynchronously`는 해당 정의에 `Async` 수정자가 사용되었고 해당 본문에서 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 호출이 있더라도 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="32e6e-143">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> in its body.</span></span>  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="32e6e-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32e6e-144">See Also</span></span>  
 [<span data-ttu-id="32e6e-145">Async 및 Await를 사용한 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="32e6e-145">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="32e6e-146">연습: Async 및 Await를 사용하여 웹에 액세스</span><span class="sxs-lookup"><span data-stu-id="32e6e-146">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="32e6e-147">비동기</span><span class="sxs-lookup"><span data-stu-id="32e6e-147">Async</span></span>](../../../visual-basic/language-reference/modifiers/async.md)
