---
title: "비동기 반환 형식 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a62556fb93a3d8547d880e4ea6770b206ead900
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="a12f6-102">비동기 반환 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12f6-102">Async Return Types (Visual Basic)</span></span>
<span data-ttu-id="a12f6-103">비동기 메서드에 세 가지 가능한 반환 형식: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, 및 void입니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="a12f6-104">Visual Basic에서 void 반환 형식은 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="a12f6-105">비동기 메서드에 대 한 자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="a12f6-106">다음 섹션 중 하나에서 각 반환 형식을 살펴보고 세 가지 형식 모두를 사용하는 전체 예제는 이 항목의 끝에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a12f6-107">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <a name="BKMK_TaskTReturnType"></a> <span data-ttu-id="a12f6-108">Task(T) 반환 형식</span><span class="sxs-lookup"><span data-stu-id="a12f6-108">Task(T) Return Type</span></span>  
 <span data-ttu-id="a12f6-109"><xref:System.Threading.Tasks.Task%601> 반환 형식은 포함 하는 비동기 메서드 사용 됩니다는 [반환](../../../../visual-basic/language-reference/statements/return-statement.md) 피연산자의 형식이 문을 `TResult`합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>  
  
 <span data-ttu-id="a12f6-110">다음 예제에서 `TaskOfT_MethodAsync` 비동기 메서드는 정수를 반환하는 return 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="a12f6-111">따라서 메서드 선언은 `Task(Of Integer)`의 반환 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 <span data-ttu-id="a12f6-112">`TaskOfT_MethodAsync`를 await 식 내에서 호출하면 await 식이 `TaskOfT_MethodAsync`에서 반환된 작업에 저장된 정수 값(`leisureHours` 값)을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="a12f6-113">에 대 한 자세한 내용은 await 표현을, 참조 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>  
  
 <span data-ttu-id="a12f6-114">다음 코드는 `TaskOfT_MethodAsync` 메서드를 호출하고 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="a12f6-115">결과는 `result1` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-115">The result is assigned to the `result1` variable.</span></span>  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 <span data-ttu-id="a12f6-116">다음 코드와 같이 `TaskOfT_MethodAsync` 호출을 `Await`의 적용과 구분하면 이 과정을 더욱 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="a12f6-117">곧바로 대기 상태가 되지 않는 `TaskOfT_MethodAsync` 메서드를 호출하면 메서드 선언에서 예상한 대로 `Task(Of Integer)`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="a12f6-118">예제에서 작업이 `integerTask` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="a12f6-119">`integerTask`가 <xref:System.Threading.Tasks.Task%601>이기 때문에 `TResult` 형식의 <xref:System.Threading.Tasks.Task%601.Result> 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="a12f6-120">이 경우 TResult는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="a12f6-121">`Await`가 `integerTask`에 적용되는 경우 await 식은 `integerTask`의 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성 내용으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="a12f6-122">값은 `result2` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-122">The value is assigned to the `result2` variable.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a12f6-123"><xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 차단 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="a12f6-124">해당 작업이 완료되기 전에 액세스하려고 하면, 작업이 완료되고 값을 사용할 수 있을 때까지 현재 활성화된 스레드가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="a12f6-125">대부분의 경우 속성에 직접 액세스하지 않고 `Await`를 사용하여 값에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 <span data-ttu-id="a12f6-126">다음 코드의 display 문은 `result1` 변수, `result2` 변수 및 `Result` 속성의 값이 동일한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="a12f6-127">`Result` 속성은 차단 속성이므로 해당 작업이 대기 상태가 되기 전에 액세스하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a> <span data-ttu-id="a12f6-128">Task 반환 형식</span><span class="sxs-lookup"><span data-stu-id="a12f6-128">Task Return Type</span></span>  
 <span data-ttu-id="a12f6-129">return 문을 포함 하지 않거나 피연산자를 일반적으로 반환 하지 않는 return 문을 포함 하는 비동기 메서드에 반환 형식이 <xref:System.Threading.Tasks.Task>합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="a12f6-130">이러한 메서드는 것 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저 동기적으로 실행 되도록 작성 된 경우.</span><span class="sxs-lookup"><span data-stu-id="a12f6-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="a12f6-131">비동기 메서드에 대해 `Task` 반환 형식을 사용하는 경우 호출된 비동기 메서드가 완료될 때까지 호출 메서드는 `Await` 연산자를 사용하여 호출자의 완료를 일시 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>  
  
 <span data-ttu-id="a12f6-132">다음 예제에서는 `Task_MethodAsync` 비동기 메서드가 return 문을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="a12f6-133">따라서 이 메서드에 대해 `Task_MethodAsync`가 대기할 수 있도록 `Task`의 반환 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="a12f6-134">`Task` 형식의 정의는 반환 값을 저장하기 위한 `Result` 속성을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 <span data-ttu-id="a12f6-135">`Task_MethodAsync`호출 되 고 동기에 대 한 호출 문과 비슷하게 await 식 대신 await 문을 사용 하 여 대기 `Sub` 또는 void를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="a12f6-136">응용 프로그램 `Await` 연산자가 경우 값을 생성 하지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>  
  
 <span data-ttu-id="a12f6-137">다음 코드는 `Task_MethodAsync` 메서드를 호출하고 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="a12f6-138">이전 처럼 <xref:System.Threading.Tasks.Task%601> 예제에 대 한 호출을 구분할 수 있습니다 `Task_MethodAsync` 의 적용는 `Await` 다음 코드 에서처럼 연산자.</span><span class="sxs-lookup"><span data-stu-id="a12f6-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="a12f6-139">그러나 `Task`에는 `Result` 속성이 없으므로 await 연산자가 `Task`에 적용될 때 값이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>  
  
 <span data-ttu-id="a12f6-140">다음 코드는 `Task_MethodAsync`가 반환하는 작업을 대기하는 것에서 `Task_MethodAsync` 호출을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim simpleTask As Task = Task_MethodAsync()  
  
' You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
Await simpleTask  
```  
  
##  <a name="BKMK_VoidReturnType"></a> <span data-ttu-id="a12f6-141">Void 반환 형식</span><span class="sxs-lookup"><span data-stu-id="a12f6-141">Void Return Type</span></span>  
 <span data-ttu-id="a12f6-142">주된 용도 `Sub` 프로시저는 이벤트 처리기에서 (다른 언어에서 void 반환 형식이 라고도 함)는 반환 형식이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="a12f6-142">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="a12f6-143">void 반환은 또한 "실행 후 제거"로 분류할 수 있는 작업을 수행하는 메서드 또는 viod를 반환하는 메서드를 재정의하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-143">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="a12f6-144">하지만 void를 반환하는 비동기 메서드는 대기할 수가 없기 때문에 가능할 때마다 `Task`를 반환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-144">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="a12f6-145">이러한 메서드의 호출자는 호출된 비동기 메서드가 마치는 것을 기다리지 않고 완료될 때까지 계속 진행할 수 있어야 하므로, 해당 호출자는 비동기 메서드가 생성하는 모든 값 또는 예외와 독립되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-145">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>  
  
 <span data-ttu-id="a12f6-146">void를 반환하는 비동기 메서드의 호출자는 메서드에서 throw되는 예외를 catch할 수 없으므로 이러한 처리되지 않은 예외를 사용하면 응용 프로그램이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-146">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="a12f6-147">비동기 메서드에서 반환 하는 경우 예외가 발생 한 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>, 예외는 반환된 된 작업에 저장 되 고 작업은 대기할 때 다시 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-147">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="a12f6-148">따라서 예외를 생성할 수 있는 모든 비동기 메서드에 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>의 반환 형식이 있고 메서드 호출이 대기 상태인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-148">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>  
  
 <span data-ttu-id="a12f6-149">비동기 메서드에서 예외를 catch하는 방법에 대한 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a12f6-149">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="a12f6-150">다음 코드는 비동기 이벤트 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-150">The following code defines an async event handler.</span></span>  
  
```vb  
' SUB EXAMPLE  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
    textBox1.Clear()  
  
    ' Start the process and await its completion. DriverAsync is a   
    ' Task-returning async method.  
    Await DriverAsync()  
  
    ' Say goodbye.  
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
End Sub  
```  
  
##  <a name="BKMK_Example"></a> <span data-ttu-id="a12f6-151">전체 예제</span><span class="sxs-lookup"><span data-stu-id="a12f6-151">Complete Example</span></span>  
 <span data-ttu-id="a12f6-152">다음 WPF(Windows Presentation Foundation) 프로젝트는 이 항목의 코드 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-152">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>  
  
 <span data-ttu-id="a12f6-153">프로젝트를 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-153">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="a12f6-154">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-154">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a12f6-155">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-155">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="a12f6-156">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-156">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a12f6-157">에 **설치 됨**, **템플릿** 범주를 선택 **Visual Basic**를 선택한 후 **Windows**합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-157">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="a12f6-158">프로젝트 형식 목록에서 **WPF 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-158">Choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="a12f6-159">프로젝트의 이름으로 `AsyncReturnTypes`를 입력한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-159">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="a12f6-160">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-160">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="a12f6-161">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-161">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="a12f6-162">탭이 표시되지 않는 경우 **솔루션 탐색기**에서 MainWindow.xaml의 바로 가기 메뉴를 열고 **열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-162">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>  
  
6.  <span data-ttu-id="a12f6-163">MainWindow.xaml의 **XAML** 창에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-163">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="a12f6-164">텍스트 상자와 단추가 포함된 간단한 창이 MainWindow.xaml의 **디자인** 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-164">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="a12f6-165">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 후 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-165">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
8.  <span data-ttu-id="a12f6-166">MainWindow.xaml.vb의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-166">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. <span data-ttu-id="a12f6-167">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-167">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a12f6-168">다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a12f6-168">The following output should appear.</span></span>  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a12f6-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a12f6-169">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.FromResult%2A>  
 [<span data-ttu-id="a12f6-170">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12f6-170">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="a12f6-171">비동기 프로그램의 제어 흐름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12f6-171">Control Flow in Async Programs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)  
 [<span data-ttu-id="a12f6-172">비동기</span><span class="sxs-lookup"><span data-stu-id="a12f6-172">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)  
 [<span data-ttu-id="a12f6-173">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="a12f6-173">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)
