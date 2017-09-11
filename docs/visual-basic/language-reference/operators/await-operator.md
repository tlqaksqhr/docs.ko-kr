---
title: "Await 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
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
author: stevehoag
ms.author: shoag
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="f750c-102">Await 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f750c-102">Await Operator (Visual Basic)</span></span>
<span data-ttu-id="f750c-103">대기 중인 작업이 완료될 때까지 메서드 실행을 일시 중단하려면 비동기 메서드 또는 람다 식의 피연산자에 `Await` 연산자를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="f750c-104">작업은 진행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-104">The task represents ongoing work.</span></span>  
  
 <span data-ttu-id="f750c-105">메서드를 `Await` 사용 있어야는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="f750c-106">이러한 메서드를 사용 하 여 정의 `Async` 한정자를 일반적으로 포함 된 하나 이상의 `Await` 식 이라고는 *비동기 메서드의*합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f750c-107">`Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="f750c-108">비동기 프로그래밍에 대 한 소개를 참조 하십시오. [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="f750c-109">일반적으로 적용 하는 작업의 `Await` 연산자가 구현 하는 메서드 호출에서 반환 값은 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=204847), 즉, 한 <xref:System.Threading.Tasks.Task>나 <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="f750c-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="f750c-110">다음 코드에서는 <xref:System.Net.Http.HttpClient>메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>반환 `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="f750c-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="f750c-111">이 작업은 작업이 완료될 때 실제 바이트 배열을 생성하기 위한 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="f750c-112">`Await` 연산자는 `getContentsTask`에 적용되어 `getContentsTask`가 완료될 때까지 `SumPageSizesAsync`의 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="f750c-113">동시에 컨트롤은 `SumPageSizesAsync` 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="f750c-114">`getContentsTask`가 완료되면 `Await` 식이 바이트 배열로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>  
  
<span data-ttu-id="f750c-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f750c-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="f750c-116">전체 예제를 참조 하십시오. [연습:를 사용 하 여 Async 및 Await 하 여 웹 서비스에 액세스](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-116">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="f750c-117">샘플을 다운로드할 수 있습니다 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) Microsoft 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-117">You can download the sample from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) on the Microsoft website.</span></span> <span data-ttu-id="f750c-118">예제는 AsyncWalkthrough_HttpClient 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-118">The example is in the AsyncWalkthrough_HttpClient project.</span></span>  
  
 <span data-ttu-id="f750c-119">`Await`가 `Task(Of TResult)`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식의 형식은 TResult입니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-119">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="f750c-120">`Await`가 `Task`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식은 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-120">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="f750c-121">다음 예제에서 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-121">The following example illustrates the difference.</span></span>  
  
<span data-ttu-id="f750c-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f750c-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f750c-123">`Await` 식 또는 문은 식이 실행되고 있는 스레드를 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-123">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="f750c-124">대신 `Await` 식 이후 컴파일러가 대기 중인 작업에서 연속된 작업으로 비동기 메서드의 나머지 부분을 등록하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-124">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="f750c-125">그런 다음 컨트롤이 비동기 메서드 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-125">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="f750c-126">작업이 완료되면 해당 연속 작업이 호출되고 중단된 비동기 메서드의 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-126">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>  
  
 <span data-ttu-id="f750c-127">`Await` 식은 `Async` 수정자로 표시된 람다 식 또는 바로 바깥쪽에 있는 메서드의 본문에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-127">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="f750c-128">용어 *Await* 해당 컨텍스트에서 키워드로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-128">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="f750c-129">다른 컨텍스트에서는 식별자로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-129">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="f750c-130">비동기 메서드 또는 람다 식 안에 `Await` 식은 쿼리 식에서 발생할 수 없습니다는 `catch` 또는 `finally` 블록는 [시도 중... Catch... 마지막으로](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 의 루프 제어 변수 식 문에 `For` 또는 `For Each` 루프 또는 본문에는 [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) 문.</span><span class="sxs-lookup"><span data-stu-id="f750c-130">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="f750c-131">예외</span><span class="sxs-lookup"><span data-stu-id="f750c-131">Exceptions</span></span>  
 <span data-ttu-id="f750c-132">대부분의 비동기 메서드는 반환 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="f750c-132">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f750c-133">반환된 작업의 속성은 작업의 완료 여부, 비동기 메서드가 예외를 발생시켰는지 취소되었는지 여부 및 최종 결과 등 해당 상태 및 기록에 대한 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-133">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="f750c-134">`Await` 연산자는 해당 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-134">The `Await` operator accesses those properties.</span></span>  
  
 <span data-ttu-id="f750c-135">예외를 발생시키는 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-135">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>  
  
 <span data-ttu-id="f750c-136">취소 된 작업 반환 비동기 메서드를 기다릴 경우는 `Await` 연산자 <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException> 를 다시 throw</span><span class="sxs-lookup"><span data-stu-id="f750c-136">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>  
  
 <span data-ttu-id="f750c-137">오류가 발생한 상태의 단일 작업에는 여러 예외가 반영될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-137">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="f750c-138">예를 들어, 작업 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 에 대 한 호출의 결과 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-138">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="f750c-139">이러한 작업을 기다릴 경우 await 작업에서 예외 중 하나만 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-139">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="f750c-140">그러나 다시 throw되는 예외를 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-140">However, you can't predict which of the exceptions is rethrown.</span></span>  
  
 <span data-ttu-id="f750c-141">비동기 메서드의 오류 처리의 예 참조 [시도 중... Catch... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-141">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f750c-142">예제</span><span class="sxs-lookup"><span data-stu-id="f750c-142">Example</span></span>  
 <span data-ttu-id="f750c-143">다음 Windows Forms 예제에서는 비동기 메서드 `WaitAsynchronouslyAsync`에서 `Await`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-143">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="f750c-144">해당 메서드의 동작을 `WaitSynchronously`의 동작과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="f750c-144">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="f750c-145">없이 `Await` 연산자를 `WaitSynchronously` 사용 되지만 동기적으로 실행 된 `Async` 한정자의 정 및에 대 한 호출의 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>해당 본문에.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f750c-145">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> in its body.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f750c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f750c-146">See Also</span></span>  
 <span data-ttu-id="f750c-147">[비동기 프로그래밍 async 및 Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="f750c-147">[Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="f750c-148"> [연습: Async를 사용 하 여 웹 서비스에 액세스 하 고 기다립니다](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="f750c-148"> [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="f750c-149"> [비동기](../../../visual-basic/language-reference/modifiers/async.md)</span><span class="sxs-lookup"><span data-stu-id="f750c-149"> [Async](../../../visual-basic/language-reference/modifiers/async.md)</span></span>
