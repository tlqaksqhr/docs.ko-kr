---
title: "호출이 완료 되기 전에 실행 하 고 현재 메서드가 계속이 호출이 대기 되지 않으므로 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: acee06829c246fbff866bfe188d6685f7cd8a263
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a><span data-ttu-id="a65af-102">이 호출이 대기되지 않으므로 호출이 완료되기 전에 현재 메서드가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-102">Because this call is not awaited, the current method continues to run before the call is completed</span></span>
<span data-ttu-id="a65af-103">이 호출이 대기되지 않으므로 호출이 완료되기 전에 현재 메서드가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-103">Because this call is not awaited, execution of the current method continues before the call is completed.</span></span> <span data-ttu-id="a65af-104">'Await' 연산자는 호출 결과에 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-104">Consider applying the 'Await' operator to the result of the call.</span></span>  
  
 <span data-ttu-id="a65af-105">현재 메서드를 반환 하는 비동기 메서드 호출을 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>적용 하지는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) ê.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="a65af-105">The current method calls an async method that returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601> and doesn’t apply the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator to the result.</span></span> <span data-ttu-id="a65af-106">비동기 메서드 호출이 비동기 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-106">The call to the async method starts an asynchronous task.</span></span> <span data-ttu-id="a65af-107">그러나 `Await` 연산자가 적용되지 않기 때문에 프로그램이 작업이 완료될 때까지 기다리지 않고 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-107">However, because no `Await` operator is applied, the program continues without waiting for the task to complete.</span></span> <span data-ttu-id="a65af-108">대부분의 경우 예상대로 동작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-108">In most cases, that behavior isn't expected.</span></span> <span data-ttu-id="a65af-109">대개 호출 메서드의 다른 부분은 호출의 결과에 따라 다르거나, 최소한 호출을 포함하는 메서드에서 돌아오기 전에 호출된 메서드가 완료되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-109">Usually other aspects of the calling method depend on the results of the call or, minimally, the called method is expected to complete before you return from the method that contains the call.</span></span>  
  
 <span data-ttu-id="a65af-110">호출된 비동기 메서드에서 발생하는 예외로 인해 어떤 상황이 발생하는지도 중요한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-110">An equally important issue is what happens with exceptions that are raised in the called async method.</span></span> <span data-ttu-id="a65af-111">반환 하는 메서드에서 발생 하는 예외는 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>반환된 된 작업에 저장 됩니다.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="a65af-111">An exception that’s raised in a method that returns a <xref:System.Threading.Tasks.Task> or  <xref:System.Threading.Tasks.Task%601> is stored in the returned task.</span></span> <span data-ttu-id="a65af-112">작업을 기다리지 않거나 예외를 명시적으로 확인하지 않는 경우 예외가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-112">If you don't await the task or explicitly check for exceptions, the exception is lost.</span></span> <span data-ttu-id="a65af-113">작업을 기다리는 경우 예외가 다시 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-113">If you await the task, its exception is rethrown.</span></span>  
  
 <span data-ttu-id="a65af-114">가장 좋은 방법은 항상 호출을 기다리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-114">As a best practice, you should always await the call.</span></span>  
  
 <span data-ttu-id="a65af-115">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-115">By default, this message is a warning.</span></span> <span data-ttu-id="a65af-116">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-116">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a65af-117">**오류 ID:** BC42358</span><span class="sxs-lookup"><span data-stu-id="a65af-117">**Error ID:** BC42358</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="a65af-118">이 경고를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a65af-118">To address this warning</span></span>  
  
-   <span data-ttu-id="a65af-119">비동기 호출이 완료될 때까지 기다리지 않으려고 하거나 호출된 메서드가 예외를 발생시키지 않는 경우에만 경고가 표시되지 않게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-119">You should consider suppressing the warning only if you're sure that you don't want to wait for the asynchronous call to complete and that the called method won't raise any exceptions.</span></span> <span data-ttu-id="a65af-120">이 경우 변수에 호출의 작업 결과를 할당하여 경고가 표시되지 않게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-120">In that case, you can suppress the warning by assigning the task result of the call to a variable.</span></span>  
  
     <span data-ttu-id="a65af-121">다음 예제는 경고를 발생시키는 방법, 경고가 표시되지 않게 하는 방법 및 호출을 대기하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-121">The following example shows how to cause the warning, how to suppress it, and how to await the call.</span></span>  
  
    ```vb  
    Async Function CallingMethodAsync() As Task  
  
        ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
        ' Variable delay is used to slow down the called method so that you  
        ' can distinguish between awaiting and not awaiting in the program's output.   
        ' You can adjust the value to produce the output that this topic shows   
        ' after the code.  
        Dim delay = 5000  
  
        ' Call #1.  
        ' Call an async method. Because you don't await it, its completion isn't   
        ' coordinated with the current method, CallingMethodAsync.  
        ' The following line causes the warning.  
        CalledMethodAsync(delay)  
  
        ' Call #2.  
        ' To suppress the warning without awaiting, you can assign the   
        ' returned task to a variable. The assignment doesn't change how  
        ' the program runs. However, the recommended practice is always to  
        ' await a call to an async method.  
        ' Replace Call #1 with the following line.  
        'Task delayTask = CalledMethodAsync(delay)  
  
        ' Call #3  
        ' To contrast with an awaited call, replace the unawaited call   
        ' (Call #1 or Call #2) with the following awaited call. The best   
        ' practice is to await the call.  
  
        'Await CalledMethodAsync(delay)  
  
        ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
        ' continues to run and, in this example, finishes its work and returns  
        ' to its caller.  
        ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
    End Function  
  
    Async Function CalledMethodAsync(howLong As Integer) As Task  
  
        ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
        ' Slow the process down a little so you can distinguish between awaiting  
        ' and not awaiting. Adjust the value for howLong if necessary.  
        Await Task.Delay(howLong)  
        ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
    End Function  
    ```  
  
     <span data-ttu-id="a65af-122">이 예제에서는 Call #1 또는 Call #2를 선택할 경우 해당 호출자(`CalledMethodAsync`)와 호출자의 호출자(`CallingMethodAsync`)가 모두 완료된 후 기다리지 않는 비동기 메서드(`StartButton_Click`)가 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-122">In the example, if you choose Call #1 or Call #2, the unawaited async method (`CalledMethodAsync`) finishes after both its caller (`CallingMethodAsync`) and the caller's caller (`StartButton_Click`) are complete.</span></span> <span data-ttu-id="a65af-123">다음 출력의 마지막 줄은 호출된 메서드가 끝나는 시기를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-123">The last line in the following output shows you when the called method finishes.</span></span> <span data-ttu-id="a65af-124">전체 예제에서 `CallingMethodAsync` 를 호출하는 이벤트 처리기의 시작과 종료가 출력에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-124">Entry to and exit from the event handler that calls `CallingMethodAsync` in the full example are marked in the output.</span></span>  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a><span data-ttu-id="a65af-125">예제</span><span class="sxs-lookup"><span data-stu-id="a65af-125">Example</span></span>  
 <span data-ttu-id="a65af-126">다음 Windows Presentation Foundation(WPF) 응용 프로그램은 이전 예제의 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-126">The following Windows Presentation Foundation (WPF) application contains the methods from the previous example.</span></span> <span data-ttu-id="a65af-127">다음 단계는 응용 프로그램을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-127">The following steps set up the application.</span></span>  
  
1.  <span data-ttu-id="a65af-128">WPF 응용 프로그램을 만들고 이름을 `AsyncWarning`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-128">Create a WPF application, and name it `AsyncWarning`.</span></span>  
  
2.  <span data-ttu-id="a65af-129">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-129">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="a65af-130">탭이 표시되지 않는 경우 **솔루션 탐색기**에서 MainWindow.xaml의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-130">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
3.  <span data-ttu-id="a65af-131">MainWindow.xaml의 **XAML** 보기에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-131">Replace the code in the **XAML** view of MainWindow.xaml with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="StartButton_Click" />  
            <TextBox x:Name="ResultsTextBox" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="a65af-132">단추와 텍스트 상자가 포함된 간단한 창이 MainWindow.xaml의 **디자인** 뷰에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-132">A simple window that contains a button and a text box appears in the **Design** view of MainWindow.xaml.</span></span>  
  
     <span data-ttu-id="a65af-133">XAML 디자이너에 대 한 자세한 내용은 참조 [XAML 디자이너를 사용 하 여 UI 만들기](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-133">For more information about the XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span> <span data-ttu-id="a65af-134">간단한 UI를 직접 작성 하는 방법에 대 한 정보를 참조 하십시오.는 "WPF 응용 프로그램 만들기"를 "하는 간단한 WPF MainWindow를 디자인" 섹션을 [연습:를 사용 하 여 Async 및 Await 하 여 웹 서비스에 액세스](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042)합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-134">For information about how to build your own simple UI, see the "To create a WPF application" and "To design a simple WPF MainWindow" sections of [Walkthrough: Accessing the Web by Using Async and Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span></span>  
  
4.  <span data-ttu-id="a65af-135">MainWindow.xaml.vb의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-135">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow   
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
            ResultsTextBox.Text &= vbCrLf & "Entering the Click event handler."  
            Await CallingMethodAsync()  
            ResultsTextBox.Text &= vbCrLf & "Exiting the Click event handler."  
        End Sub  
  
        Async Function CallingMethodAsync() As Task  
  
            ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
            ' Variable delay is used to slow down the called method so that you  
            ' can distinguish between awaiting and not awaiting in the program's output.   
            ' You can adjust the value to produce the output that this topic shows   
            ' after the code.  
            Dim delay = 5000  
  
            ' Call #1.  
            ' Call an async method. Because you don't await it, its completion isn't   
            ' coordinated with the current method, CallingMethodAsync.  
            ' The following line causes the warning.  
            CalledMethodAsync(delay)  
  
            ' Call #2.  
            ' To suppress the warning without awaiting, you can assign the   
            ' returned task to a variable. The assignment doesn't change how  
            ' the program runs. However, the recommended practice is always to  
            ' await a call to an async method.  
  
            ' Replace Call #1 with the following line.  
            'Task delayTask = CalledMethodAsync(delay)  
  
            ' Call #3  
            ' To contrast with an awaited call, replace the unawaited call   
            ' (Call #1 or Call #2) with the following awaited call. The best   
            ' practice is to await the call.  
  
            'Await CalledMethodAsync(delay)  
  
            ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
            ' continues to run and, in this example, finishes its work and returns  
            ' to its caller.  
            ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
        End Function  
  
        Async Function CalledMethodAsync(howLong As Integer) As Task  
  
            ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
            ' Slow the process down a little so you can distinguish between awaiting  
            ' and not awaiting. Adjust the value for howLong if necessary.  
            Await Task.Delay(howLong)  
            ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
        End Function  
  
    End Class  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    '     Task.Delay is finished--returning from called method.  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '     Task.Delay is finished--returning from called method.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    ```  
  
5.  <span data-ttu-id="a65af-136">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-136">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a65af-137">예상 출력이 코드의 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a65af-137">The expected output appears at the end of the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65af-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a65af-138">See Also</span></span>  
 <span data-ttu-id="a65af-139">[Await 연산자](../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a65af-139">[Await Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="a65af-140"> [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)</span><span class="sxs-lookup"><span data-stu-id="a65af-140"> [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md)</span></span>

