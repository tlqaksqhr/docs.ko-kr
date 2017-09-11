---
title: "비동기 반환 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="2b5cb-102">비동기 반환 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b5cb-102">Async Return Types (Visual Basic)</span></span>
<span data-ttu-id="2b5cb-103">비동기 메서드는 세 가지 가능한 반환 형식은: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, void 및.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b5cb-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="2b5cb-104">Visual Basic의 경우 반환 형식이 void로 작성 되는 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="2b5cb-105">비동기 메서드에 대 한 자세한 내용은 참조 하십시오. [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="2b5cb-106">다음 섹션 중 하나에서 각 반환 형식을 살펴보고 세 가지 형식 모두를 사용하는 전체 예제는 이 항목의 끝에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b5cb-107">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="2b5cb-108"><a name="BKMK_TaskTReturnType"></a>Task (t) 반환 형식</span><span class="sxs-lookup"><span data-stu-id="2b5cb-108"><a name="BKMK_TaskTReturnType"></a> Task(T) Return Type</span></span>  
 <span data-ttu-id="2b5cb-109"><xref:System.Threading.Tasks.Task%601>반환 형식을 포함 하는 비동기 메서드에 사용 되는 [반환](../../../../visual-basic/language-reference/statements/return-statement.md) 문이 있는 피연산자 형식 `TResult`.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b5cb-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>  
  
 <span data-ttu-id="2b5cb-110">다음 예제에서는 `TaskOfT_MethodAsync` 비동기 메서드는 정수를 반환 하는 return 문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="2b5cb-111">따라서 메서드 선언에서의 반환 형식을 지정 해야 `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>  
  
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
  
 <span data-ttu-id="2b5cb-112">때 `TaskOfT_MethodAsync` 라고에서 await 식에서 await 식의 정수 값을 검색 (값 `leisureHours`)에서 반환 되는 작업에 저장 된 `TaskOfT_MethodAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="2b5cb-113">에 대 한 자세한 내용은 await 표현을 참조 하십시오 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>  
  
 <span data-ttu-id="2b5cb-114">다음 코드를 호출 하 고 메서드를 기다립니다 `TaskOfT_MethodAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="2b5cb-115">결과에 할당 되는 `result1` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-115">The result is assigned to the `result1` variable.</span></span>  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 <span data-ttu-id="2b5cb-116">이에 대 한 호출을 구분 하 여 문제가 발생 하는 방법을 더 잘 이해할 수 `TaskOfT_MethodAsync` 의 응용 프로그램에서 `Await`다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="2b5cb-117">메서드를 호출 `TaskOfT_MethodAsync` 대기 중이 던된 즉시 반환이 아닌는 `Task(Of Integer)`메서드의 선언에서 예상 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="2b5cb-118">작업에 할당 되는 `integerTask` 예에서 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="2b5cb-119">때문에 `integerTask` 는 <xref:System.Threading.Tasks.Task%601>, 포함 된 한 <xref:System.Threading.Tasks.Task%601.Result>형식의 속성 `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b5cb-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="2b5cb-120">이 경우 TResult는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="2b5cb-121">때 `Await` 적용할 `integerTask`, await 식이의 내용에는 <xref:System.Threading.Tasks.Task%601.Result%2A>속성 `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="2b5cb-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="2b5cb-122">값에 할당 되는 `result2` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-122">The value is assigned to the `result2` variable.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2b5cb-123"><xref:System.Threading.Tasks.Task%601.Result%2A>속성은 차단 속성.</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="2b5cb-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="2b5cb-124">해당 작업이 완료되기 전에 액세스하려고 하면, 작업이 완료되고 값을 사용할 수 있을 때까지 현재 활성화된 스레드가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="2b5cb-125">사용 하 여 값 액세스 해야 하는 대부분의 경우에서 `Await` 속성에 직접 액세스 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 <span data-ttu-id="2b5cb-126">디스플레이 문을 다음 코드에서를 확인 하는 값은 `result1` 변수는 `result2` 변수를 및 `Result` 속성은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="2b5cb-127">유의 해야는 `Result` 속성은 차단 속성 및 해당 작업에 대기 되지 전에 액세스 해서는 안 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <span data-ttu-id="2b5cb-128"><a name="BKMK_TaskReturnType"></a>작업 반환 형식</span><span class="sxs-lookup"><span data-stu-id="2b5cb-128"><a name="BKMK_TaskReturnType"></a> Task Return Type</span></span>  
 <span data-ttu-id="2b5cb-129">Return 문을 포함 하지는 또는 일반적으로 피연산자를 반환 하지 않는 return 문이 포함 하는 비동기 메서드는 <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> 의 반환 형식</span><span class="sxs-lookup"><span data-stu-id="2b5cb-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="2b5cb-130">이러한 메서드는 것 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저 동기적으로 실행 하도록 작성 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="2b5cb-131">사용 하는 경우는 `Task` 형식을 반환 비동기 메서드를 호출 하는 메서드에서 사용할 수는 `Await` 연산자를 호출된 된 비동기 메서드에서 끝날 때까지 호출자의 완료를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>  
  
 <span data-ttu-id="2b5cb-132">다음 예제에서는 비동기 메서드 `Task_MethodAsync` return 문이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="2b5cb-133">반환 형식을 지정 하는 따라서 `Task` 메서드의 수 있도록 `Task_MethodAsync` 를 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="2b5cb-134">정의 `Task` 형식이 포함 되지 않습니다는 `Result` 속성을 반환 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>  
  
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
  
 <span data-ttu-id="2b5cb-135">`Task_MethodAsync`호출 하 고 await 문에서 동기식 호출 문을 비슷합니다 await 식 대신 사용 하 여 대기 `Sub` 또는 메서드의 void를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="2b5cb-136">응용 프로그램 `Await` 연산자가 경우 값을 생성 하지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>  
  
 <span data-ttu-id="2b5cb-137">다음 코드를 호출 하 고 메서드를 기다립니다 `Task_MethodAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="2b5cb-138">이전 처럼 <xref:System.Threading.Tasks.Task%601>예제에 대 한 호출을 구분할 수 있습니다 `Task_MethodAsync` 의 응용 프로그램에서 한 `Await` 다음 코드와 같이 연산자.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="2b5cb-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="2b5cb-139">그러나에 유의 해야는 `Task` 없는 `Result` 속성과 await 연산자에 적용 되는 값은 생성 되는 `Task`합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>  
  
 <span data-ttu-id="2b5cb-140">호출을 구분 하는 다음 코드 `Task_MethodAsync` 에서 작업을 대기 하는 `Task_MethodAsync` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>  
  
<span data-ttu-id="2b5cb-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="2b5cb-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="2b5cb-142"><a name="BKMK_VoidReturnType"></a>Void 반환 형식</span><span class="sxs-lookup"><span data-stu-id="2b5cb-142"><a name="BKMK_VoidReturnType"></a> Void Return Type</span></span>  
 <span data-ttu-id="2b5cb-143">주된 용도 `Sub` 프로시저는 이벤트 처리기의 경우 (다른 언어의 반환 형식이 void 라고도 함) 반환 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-143">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="2b5cb-144">void 반환은 또한 "실행 후 제거"로 분류할 수 있는 작업을 수행하는 메서드 또는 viod를 반환하는 메서드를 재정의하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-144">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="2b5cb-145">하지만 반환 해야 한 `Task` 가능 void 반환 비동기 메서드를 대기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-145">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="2b5cb-146">이러한 메서드의 호출자는 호출된 비동기 메서드가 마치는 것을 기다리지 않고 완료될 때까지 계속 진행할 수 있어야 하므로, 해당 호출자는 비동기 메서드가 생성하는 모든 값 또는 예외와 독립되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-146">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>  
  
 <span data-ttu-id="2b5cb-147">void를 반환하는 비동기 메서드의 호출자는 메서드에서 throw되는 예외를 catch할 수 없으므로 이러한 처리되지 않은 예외를 사용하면 응용 프로그램이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-147">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="2b5cb-148">비동기 메서드에서 반환 하는 경우 예외가 발생 한 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>, 예외가 반환된 된 작업에 저장 되 고 작업에 대 한 대기 하는 경우 다시 throw 합니다.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="2b5cb-148">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="2b5cb-149">따라서 예외를 생성할 수 있는 비동기 메서드가의 반환 형식에 있는지를 확인 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>메서드를 호출 하는 대기 하 고.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="2b5cb-149">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>  
  
 <span data-ttu-id="2b5cb-150">비동기 메서드에서 예외를 catch 하는 방법에 대 한 자세한 내용은 참조 [시도 중... Catch... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-150">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="2b5cb-151">다음 코드는 비동기 이벤트 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-151">The following code defines an async event handler.</span></span>  
  
<span data-ttu-id="2b5cb-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="2b5cb-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="2b5cb-153"><a name="BKMK_Example"></a>전체 예제</span><span class="sxs-lookup"><span data-stu-id="2b5cb-153"><a name="BKMK_Example"></a> Complete Example</span></span>  
 <span data-ttu-id="2b5cb-154">다음 WPF(Windows Presentation Foundation) 프로젝트는 이 항목의 코드 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-154">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>  
  
 <span data-ttu-id="2b5cb-155">프로젝트를 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-155">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="2b5cb-156">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-156">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2b5cb-157">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-157">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="2b5cb-158">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-158">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2b5cb-159">에 **설치 됨**, **템플릿** 범주를 선택 **Visual Basic**를 선택한 다음 **Windows**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-159">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="2b5cb-160">선택 **WPF 응용 프로그램** 프로젝트 형식 목록에서.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-160">Choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="2b5cb-161">입력 `AsyncReturnTypes` , 프로젝트의 이름으로 선택 하 고는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-161">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="2b5cb-162">새 프로젝트가 표시 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-162">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="2b5cb-163">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-163">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="2b5cb-164">탭 보이지 않으면 mainwindow.xaml의 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 다음 **열고**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-164">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>  
  
6.  <span data-ttu-id="2b5cb-165">에 **XAML** MainWindow.xaml의 창 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-165">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>  
  
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
  
     <span data-ttu-id="2b5cb-166">에 텍스트 상자와 단추가 포함 된 간단한 창이 표시는 **디자인** MainWindow.xaml의 창.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-166">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="2b5cb-167">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-167">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
8.  <span data-ttu-id="2b5cb-168">MainWindow.xaml.vb의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-168">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
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
  
9. <span data-ttu-id="2b5cb-169">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-169">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="2b5cb-170">다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5cb-170">The following output should appear.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b5cb-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b5cb-171">See Also</span></span>  
 <span data-ttu-id="2b5cb-172"><xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A></span><span class="sxs-lookup"><span data-stu-id="2b5cb-172"><xref:System.Threading.Tasks.Task.FromResult%2A></span></span>   
<span data-ttu-id="2b5cb-173"> [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="2b5cb-173"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="2b5cb-174"> [비동기 프로그램 (Visual Basic)의 제어 흐름](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span><span class="sxs-lookup"><span data-stu-id="2b5cb-174"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span></span>  
<span data-ttu-id="2b5cb-175"> [비동기](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="2b5cb-175"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="2b5cb-176"> [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)</span><span class="sxs-lookup"><span data-stu-id="2b5cb-176"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md)</span></span>
