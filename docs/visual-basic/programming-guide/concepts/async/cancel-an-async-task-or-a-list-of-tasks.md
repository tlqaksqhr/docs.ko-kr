---
title: 비동기 작업 또는 작업 (Visual Basic) 목록 취소
ms.date: 07/20/2015
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
ms.openlocfilehash: 2823514bc462f198a43316b40eb05bc1ffed0e72
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728669"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="09f78-102">비동기 작업 또는 작업 (Visual Basic) 목록 취소</span><span class="sxs-lookup"><span data-stu-id="09f78-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="09f78-103">작업이 완료될 때까지 기다리지 않으려면 비동기 응용 프로그램을 취소할 때 사용하는 단추를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="09f78-104">이 항목의 예제에 따라 한 웹 사이트 또는 웹 사이트 목록의 콘텐츠를 다운로드하는 응용 프로그램에 취소 단추를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="09f78-105">예제에서는 UI를 사용 하는 [미세 조정 Your 비동기 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) 에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09f78-106">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <a name="BKMK_CancelaTask"></a> <span data-ttu-id="09f78-107">작업 취소</span><span class="sxs-lookup"><span data-stu-id="09f78-107">Cancel a Task</span></span>  
 <span data-ttu-id="09f78-108">첫 번째 예제에서는 **취소** 단추를 단일 다운로드 작업에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="09f78-109">응용 프로그램이 콘텐츠를 다운로드하는 동안 단추를 선택하면 다운로드가 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="09f78-110">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="09f78-110">Downloading the Example</span></span>  
 <span data-ttu-id="09f78-111">[Async 샘플: 응용 프로그램 세부 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="09f78-112">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="09f78-113">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="09f78-114">에 **프로젝트 열기** 대화 상자, 하면 압축을 푼 샘플 코드가 저장 된 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="09f78-115">**솔루션 탐색기**에서 **CancelATask** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="09f78-116">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="09f78-117">디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="09f78-118">프로젝트를 다운로드 하지 않으려면 하는 경우이 항목의 끝부분에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="09f78-119">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="09f78-119">Building the Example</span></span>  
 <span data-ttu-id="09f78-120">다음 변경 내용은 웹 사이트를 다운로드하는 응용 프로그램에 **취소** 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="09f78-121">예제를 다운로드하거나 빌드하지 않으려면 이 항목의 끝에 있는 “전체 예제” 섹션에서 최종 결과를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="09f78-122">코드에서 변경 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="09f78-123">직접 예제를 빌드하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르지만 **시작 프로젝트**로 **CancelATask** 대신 **StarterCode**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="09f78-124">해당 프로젝트의 MainWindow.xaml.vb 파일에 다음과 같은 변경을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="09f78-125">액세스하는 모든 메서드에 대한 범위 내에 있는 `CancellationTokenSource` 변수 `cts`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="09f78-126">**취소** 단추에 대한 다음 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="09f78-127">이벤트 처리기는 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> 메서드를 사용하여 사용자가 취소를 요청할 때 `cts`에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="09f78-128">이벤트 처리기에서 **시작** 단추 `startButton_Click`을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="09f78-129">`CancellationTokenSource`, `cts`를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="09f78-130">지정된 웹 사이트의 콘텐츠를 다운로드하는 `AccessTheWebAsync` 호출에서 `cts`의 <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> 속성을 인수로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="09f78-131">취소가 요청되면 `Token` 속성은 메시지를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="09f78-132">사용자가 다운로드 작업을 취소하도록 선택할 경우 메시지를 표시하는 catch 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="09f78-133">다음 코드는 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-133">The following code shows the changes.</span></span>  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  <span data-ttu-id="09f78-134">`AccessTheWebAsync`에서 <xref:System.Net.Http.HttpClient> 형식에 있는 `GetAsync` 메서드의 <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> 오버로드를 사용하여 웹 사이트의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="09f78-135">`AccessTheWebAsync`의 <xref:System.Threading.CancellationToken> 매개 변수인 `ct`를 두 번째 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="09f78-136">사용자가 **취소** 단추를 선택하면 토큰이 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="09f78-137">다음 코드는 `AccessTheWebAsync`의 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  <span data-ttu-id="09f78-138">프로그램을 취소하지 않으면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="09f78-139">프로그램이 다운로드를 완료하기 전에 **취소** 단추를 선택하면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <a name="BKMK_CancelaListofTasks"></a> <span data-ttu-id="09f78-140">작업 목록 취소</span><span class="sxs-lookup"><span data-stu-id="09f78-140">Cancel a List of Tasks</span></span>  
 <span data-ttu-id="09f78-141">이전 예제를 확장하여 같은 `CancellationTokenSource` 인스턴스를 각 작업과 연결하는 방식으로 여러 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="09f78-142">**취소** 단추를 선택하면 아직 완료되지 않은 모든 작업이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="09f78-143">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="09f78-143">Downloading the Example</span></span>  
 <span data-ttu-id="09f78-144">[Async 샘플: 응용 프로그램 세부 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="09f78-145">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="09f78-146">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="09f78-147">에 **프로젝트 열기** 대화 상자, 하면 압축을 푼 샘플 코드가 저장 된 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="09f78-148">**솔루션 탐색기**에서 **CancelAListOfTasks** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="09f78-149">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="09f78-150">디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="09f78-151">프로젝트를 다운로드 하지 않으려면 하는 경우이 항목의 끝부분에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="09f78-152">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="09f78-152">Building the Example</span></span>  
 <span data-ttu-id="09f78-153">직접 예제를 확장하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르되, **CancelATask**를 **시작 프로젝트**로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="09f78-154">해당 프로젝트에 다음 변경 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-154">Add the following changes to that project.</span></span> <span data-ttu-id="09f78-155">프로그램에서 변경 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="09f78-156">웹 주소 목록에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-156">Add a method to create a list of web addresses.</span></span>  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
    ```  
  
2.  <span data-ttu-id="09f78-157">`AccessTheWebAsync`에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="09f78-158">`AccessTheWebAsync`에서 다음 루프를 추가하여 목록에 있는 각 웹 주소를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
    ```vb  
    ' ***Add a loop to process the list of web addresses.  
    For Each url In urlList  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' Argument ct carries the message if the Cancel button is chosen.   
        ' ***Note that the Cancel button can cancel all remaining downloads.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  <span data-ttu-id="09f78-159">`AccessTheWebAsync`는 길이를 표시하므로 메서드가 아무것도 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="09f78-160">return 문을 제거하고 메서드의 반환 형식을 <xref:System.Threading.Tasks.Task%601> 대신 <xref:System.Threading.Tasks.Task>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
    ```vb  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
    ```  
  
     <span data-ttu-id="09f78-161">식 대신 문을 사용하여 `startButton_Click`에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="09f78-162">프로그램을 취소하지 않으면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-162">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
    ```  
  
     <span data-ttu-id="09f78-163">다운로드가 완료되기 전에 **취소** 단추를 선택하면 취소하기 전에 완료된 다운로드의 길이가 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
    ```  
  
##  <a name="BKMK_CompleteExamples"></a> <span data-ttu-id="09f78-164">전체 예제</span><span class="sxs-lookup"><span data-stu-id="09f78-164">Complete Examples</span></span>  
 <span data-ttu-id="09f78-165">다음 섹션에는 각각의 이전 예제에 대한 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="09f78-166"><xref:System.Net.Http>에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="09f78-167">[Async 샘플: 응용 프로그램 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 프로젝트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-167">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="09f78-168">작업 취소 예제</span><span class="sxs-lookup"><span data-stu-id="09f78-168">Cancel a Task Example</span></span>  
 <span data-ttu-id="09f78-169">다음 코드는 단일 작업을 취소 하는 예제에 대 한 전체 MainWindow.xaml.vb 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' ***Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' ***Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
End Class  
  
' Output for a successful download:  
  
' Ready to download.  
  
' Length of the downloaded string: 158125.  
  
' Or, if you cancel:  
  
' Ready to download.  
  
' Download canceled.  
```  
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="09f78-170">작업 목록 취소 예제</span><span class="sxs-lookup"><span data-stu-id="09f78-170">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="09f78-171">다음 코드는 작업 목록 취소 예제에 대 한 전체 MainWindow.xaml.vb 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="09f78-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).  
            Await AccessTheWebAsync(cts.Token)  
            '  ***Small change in the display lines.  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' ***Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' ***Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Add a loop to process the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' ***Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Output if you do not choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Length of the downloaded string: 158124.  
  
' Length of the downloaded string: 204890.  
  
' Length of the downloaded string: 175488.  
  
' Length of the downloaded string: 145790.  
  
' Downloads complete.  
  
'  Sample output if you choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="09f78-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09f78-172">See Also</span></span>  
 <xref:System.Threading.CancellationTokenSource>  
 <xref:System.Threading.CancellationToken>  
 [<span data-ttu-id="09f78-173">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09f78-173">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="09f78-174">Async 응용 프로그램 미세 조정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09f78-174">Fine-Tuning Your Async Application (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [<span data-ttu-id="09f78-175">Async 샘플: 응용 프로그램 미세 조정</span><span class="sxs-lookup"><span data-stu-id="09f78-175">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
