---
title: '방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 4d4ccda6657dd4d889e8495fa000715c1f7a5ba6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728445"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="f84ea-102">방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84ea-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="f84ea-103">비동기 메서드에서 작업은 만들어질 때 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="f84ea-104">[Await](../../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 계속할 수 없습니다 작업이 완료 될 때까지 메서드의 지점에서 작업에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-104">The [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="f84ea-105">다음 예제와 같이 작업이 생성되는 즉시 대기되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 <span data-ttu-id="f84ea-106">그러나 프로그램에서 작업 완료에 의존하지 않는 다른 작업을 수행해야 하는 경우 작업 생성과 작업 대기를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```vb  
' The following line creates and starts the task.  
Dim myTask = someWebAccessMethodAsync(url)  
  
' While the task is running, you can do other work that does not depend  
' on the results of the task.  
' . . . . .  
  
' The application of Await suspends the rest of this method until the task is   
' complete.  
Dim result = Await myTask  
```  
  
 <span data-ttu-id="f84ea-107">작업 시작과 작업 대기 사이에 다른 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="f84ea-108">추가 작업은 암시적으로 병렬로 실행되지만 추가 스레드는 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="f84ea-109">다음 프로그램은 세 개의 비동기 웹 다운로드를 시작한 다음 호출된 순서대로 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="f84ea-110">프로그램을 실행할 때 작업이 항상 생성 및 대기된 순서로 완료되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="f84ea-111">작업은 생성 시 실행을 시작하고, 메서드가 await 식에 도달하기 전에 작업 중 하나 이상이 완료될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f84ea-112">이 프로젝트를 완료하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="f84ea-113">동시에 여러 작업을 시작 하는 또 다른 예로, 참조 [하는 방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-113">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="f84ea-114">이 예제의 코드는 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="f84ea-115">프로젝트를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f84ea-115">To set up the project</span></span>  
  
1.  <span data-ttu-id="f84ea-116">WPF 응용 프로그램을 설정하려면 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="f84ea-117">이러한 단계에 대 한 자세한 지침을 찾을 수 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="f84ea-118">텍스트 상자와 단추가 포함된 WPF 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="f84ea-119">단추의 이름을 `startButton`, 텍스트 상자의 이름을 `resultsTextBox`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="f84ea-120"><xref:System.Net.Http>에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    -   <span data-ttu-id="f84ea-121">MainWindow.xaml.vb 파일에 추가 `Imports` 문을 `System.Net.Http`합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-121">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="f84ea-122">코드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="f84ea-122">To add the code</span></span>  
  
1.  <span data-ttu-id="f84ea-123">디자인 창 MainWindow.xaml에서에서 만들기 단추를 두 번 클릭은 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f84ea-124">다음 코드를 복사 하 고 본문에 붙여 `startButton_Click` MainWindow.xaml.vb에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     <span data-ttu-id="f84ea-125">코드는 응용 프로그램을 구동하는 비동기 메서드 `CreateMultipleTasksAsync`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3.  <span data-ttu-id="f84ea-126">프로젝트에 다음과 같은 지원 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-126">Add the following support methods to the project:</span></span>  
  
    -   <span data-ttu-id="f84ea-127">`ProcessURLAsync`는 <xref:System.Net.Http.HttpClient> 메서드를 사용하여 웹 사이트 내용을 바이트 배열로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="f84ea-128">그런 다음 지원 메서드 `ProcessURLAsync`는 배열의 길이를 표시하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    -   <span data-ttu-id="f84ea-129">`DisplayResults`에 각 URL에 대한 바이트 배열의 바이트 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="f84ea-130">이 표시는 각 작업의 다운로드가 완료된 시간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="f84ea-131">다음 메서드를 복사한 후 붙여는 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
4.  <span data-ttu-id="f84ea-132">마지막으로, 다음 단계를 수행하는 `CreateMultipleTasksAsync` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    -   <span data-ttu-id="f84ea-133">이 메서드는 `ProcessURLAsync`의 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> 메서드에 액세스하는 데 필요한 `HttpClient` 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    -   <span data-ttu-id="f84ea-134">메서드는 `TResult`가 정수인 <xref:System.Threading.Tasks.Task%601> 형식의 세 가지 작업을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="f84ea-135">각 작업이 완료되면 `DisplayResults`에 작업의 URL 및 다운로드한 콘텐츠의 길이가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="f84ea-136">작업이 비동기적으로 실행되므로 결과가 표시되는 순서는 선언된 순서와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    -   <span data-ttu-id="f84ea-137">메서드는 각 작업이 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="f84ea-138">각 `Await` 연산자는 대기된 작업이 완료될 때까지 `CreateMultipleTasksAsync`의 실행을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-138">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="f84ea-139">또한 연산자는 완료된 각 작업에서 `ProcessURLAsync` 호출의 반환 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    -   <span data-ttu-id="f84ea-140">작업이 완료되고 정수 값이 검색된 경우 메서드는 웹 사이트의 길이를 합산하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="f84ea-141">다음 메서드를 복사하고 솔루션에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-141">Copy the following method, and paste it into your solution.</span></span>  
  
    ```vb  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
    ```  
  
5.  <span data-ttu-id="f84ea-142">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="f84ea-143">프로그램을 여러 번 실행하여 세 가지 작업이 항상 동일한 순서로 완료되지는 않으며, 완료되는 순서가 생성 및 대기된 순서와 다를 수도 있음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f84ea-144">예</span><span class="sxs-lookup"><span data-stu-id="f84ea-144">Example</span></span>  
 <span data-ttu-id="f84ea-145">다음 코드에는 전체 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ea-145">The following code contains the full example.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
        resultsTextBox.Clear()  
        Await CreateMultipleTasksAsync()  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="f84ea-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f84ea-146">See Also</span></span>  
 [<span data-ttu-id="f84ea-147">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84ea-147">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="f84ea-148">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84ea-148">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="f84ea-149">방법: Task.WhenAll을 사용하여 비동기 연습 확장(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84ea-149">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
