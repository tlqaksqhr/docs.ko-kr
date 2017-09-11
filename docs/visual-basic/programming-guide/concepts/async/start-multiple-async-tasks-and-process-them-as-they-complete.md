---
title: "여러 비동기 작업을 시작 하 고 (Visual Basic) 완료 될 때마다 처리 | Microsoft 문서"
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
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
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
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="340b2-102">여러 비동기 작업을 시작 하 고 (Visual Basic) 완료 될 때마다 처리</span><span class="sxs-lookup"><span data-stu-id="340b2-102">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>
<span data-ttu-id="340b2-103">사용 하 여 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, 동시에 여러 작업을 시작할 수 있으며은 완료 된 것 보다는 시작 하는 순서에서이 처리 하는 대로 하나씩 처리 합니다.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="340b2-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="340b2-104">다음 예제에서는 작업의 컬렉션을 만드는 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="340b2-105">지정된 된 웹 사이트의 콘텐츠를 다운로드 하는 각 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="340b2-106">잠시의 각 반복에서 루프에 대 한 대기 중인된 호출 `WhenAny` 다운로드를 먼저 완료 하는 작업의 컬렉션에 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="340b2-107">해당 작업 컬렉션에서 제거 하 고 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="340b2-108">루프는 컬렉션에 더 많은 작업이 포함 될 때까지 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="340b2-109">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="340b2-110">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="340b2-110">Downloading the Example</span></span>  
 <span data-ttu-id="340b2-111">전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="340b2-112">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="340b2-113">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="340b2-114">에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="340b2-115">**솔루션 탐색기**, 바로 가기 메뉴를 열고는 **ProcessTasksAsTheyFinish** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="340b2-116">프로젝트를 실행 하려면 F5 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="340b2-117">디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="340b2-118">다운로드 한 길이 없습니다 동일한 순서로 항상 표시 되는지 확인 하려면 프로젝트를 여러 번 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="340b2-119">프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-119">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="340b2-120">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="340b2-120">Building the Example</span></span>  
 <span data-ttu-id="340b2-121">개발 하는 코드에 추가 하는이 예제 [하나의 완전 (Visual Basic) 한 후 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 동일한 UI를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="340b2-122">예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAfterOneTask** 으로 **시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="340b2-123">이 항목의 변경 내용을 추가 `AccessTheWebAsync` 해당 프로젝트에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="340b2-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="340b2-124">변경 내용은 별표로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="340b2-125">**CancelAfterOneTask** 는 쿼리를 이미 포함 하는 프로젝트를 실행 하면 작업의 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="340b2-126">호출할 때마다 `ProcessURLAsync` 다음 코드를 반환는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 는 정수입니다.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="340b2-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="340b2-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="340b2-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="340b2-128">프로젝트의 MainWindow.xaml.vb 파일에서 다음과 같이 변경 하는 `AccessTheWebAsync` 메서드.</span><span class="sxs-lookup"><span data-stu-id="340b2-128">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="340b2-129"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> 대신</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> 적용 하 여 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-129">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
<span data-ttu-id="340b2-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="340b2-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
-   <span data-ttu-id="340b2-131">잠시 추가 컬렉션의 각 작업에 대해 다음 단계를 수행 하는 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-131">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="340b2-132">에 대 한 호출을 기다리는 `WhenAny` 다운로드를 완료 하려면 컬렉션의 첫 번째 작업을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-132">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
<span data-ttu-id="340b2-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="340b2-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
    2.  <span data-ttu-id="340b2-134">컬렉션에서 해당 작업을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-134">Removes that task from the collection.</span></span>  
  
<span data-ttu-id="340b2-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="340b2-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
    3.  <span data-ttu-id="340b2-136">대기 `firstFinishedTask`에 대 한 호출에서 반환 된 `ProcessURLAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-136">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="340b2-137">`firstFinishedTask` 변수가 <xref:System.Threading.Tasks.Task%601>여기서 `TReturn` 는 정수입니다.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="340b2-137">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="340b2-138">작업이 이미 완료 되 면 하지만 다음 예제와 같이 다운로드 한 웹 사이트의 길이 검색 하기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-138">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="340b2-139">다운로드 한 길이 순서 대로 나타나지 항상 확인을 여러 번 프로젝트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-139">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="340b2-140">사용할 수 있습니다 `WhenAny` 적은 수의 작업을 포함 하는 문제를 해결 하는 예제에 설명 된 대로 루프에서.</span><span class="sxs-lookup"><span data-stu-id="340b2-140">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="340b2-141">그러므로 많은 수의 작업을 처리해야 하는 경우에는 다른 접근 방법이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-141">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="340b2-142">자세한 내용 및 예제에 대 한 참조 [처리 작업이 완료 될 때](http://go.microsoft.com/fwlink/?LinkId=260810)합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-142">For more information and examples, see [Processing Tasks as they complete](http://go.microsoft.com/fwlink/?LinkId=260810).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="340b2-143">전체 예제</span><span class="sxs-lookup"><span data-stu-id="340b2-143">Complete Example</span></span>  
 <span data-ttu-id="340b2-144">다음 코드는 예제에 대 한 MainWindow.xaml.vb 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-144">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="340b2-145">별표는이 예제에 대 한 추가 된 요소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-145">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="340b2-146"><xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 해야 한다고 공지</span><span class="sxs-lookup"><span data-stu-id="340b2-146">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="340b2-147">프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.</span><span class="sxs-lookup"><span data-stu-id="340b2-147">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
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
  
' Sample output:  
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="340b2-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340b2-148">See Also</span></span>  
 <span data-ttu-id="340b2-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="340b2-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="340b2-150"> [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="340b2-150"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="340b2-151"> [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="340b2-151"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="340b2-152"> [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="340b2-152"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
