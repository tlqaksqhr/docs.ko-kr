---
title: "하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소 | Microsoft 문서"
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
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
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
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="e456f-102">하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="e456f-102">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>
<span data-ttu-id="e456f-103">사용 하 여는 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>와 함께 메서드는 <xref:System.Threading.CancellationToken>, 한 작업이 완료 되 면 모든 나머지 작업을 취소할 수 있습니다.</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e456f-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="e456f-104">`WhenAny` 메서드 작업의 컬렉션을 나타내는 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="e456f-105">메서드는 모든 작업을 시작 하 고 작업을 단일 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="e456f-106">컬렉션에서 모든 작업이 완료 되 면 단일 작업이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="e456f-107">와 함께에서 취소 토큰을 사용 하는 방법을 보여 주는이 예제 `WhenAny` 작업의 컬렉션에서 완료 하 고 나머지 작업을 취소 하는 첫 번째 작업에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="e456f-108">웹 사이트의 콘텐츠를 다운로드 하는 각 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="e456f-109">이 예제는 첫 번째 다운로드를 완료 하려면의 콘텐츠 길이 표시 하 고 다른 다운로드를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e456f-110">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="e456f-111">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="e456f-111">Downloading the Example</span></span>  
 <span data-ttu-id="e456f-112">전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="e456f-113">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="e456f-114">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="e456f-115">에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="e456f-116">**솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelAfterOneTask** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="e456f-117">프로젝트를 실행 하려면 F5 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="e456f-118">디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="e456f-119">다른 다운로드를 먼저 완료를 확인 하려면 프로그램을 여러 번 실행.</span><span class="sxs-lookup"><span data-stu-id="e456f-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="e456f-120">프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="e456f-121">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="e456f-121">Building the Example</span></span>  
 <span data-ttu-id="e456f-122">이 항목의 예제에서 개발한 프로젝트에 추가 [비동기 작업 또는 작업 목록 취소](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) 작업 목록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) to cancel a list of tasks.</span></span> <span data-ttu-id="e456f-123">하지만 예제에서는 동일한 UI를 사용 여 **취소** 단추 명시적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="e456f-124">예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAListOfTasks** 으로 **시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="e456f-125">이 항목의 변경 내용이 해당 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="e456f-126">MainWindow.xaml.vb 파일에는 **CancelAListOfTasks** 프로젝트를에서 루프의 각 웹 사이트에 대 한 처리 단계를 이동 하 여 전환을 시작 `AccessTheWebAsync` 다음 비동기 메서드.</span><span class="sxs-lookup"><span data-stu-id="e456f-126">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```vb  
' ***Bundle the processing steps for a website into one async method.  
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
    ' GetAsync returns a Task(Of HttpResponseMessage).   
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
    ' Retrieve the website contents from the HttpResponseMessage.  
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
    Return urlContents.Length  
End Function  
```  
  
 <span data-ttu-id="e456f-127">`AccessTheWebAsync`, 쿼리를 사용 하 여이 예제는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 및 `WhenAny` 메서드를 만들고 시작 작업의 배열입니다.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="e456f-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="e456f-128">응용 프로그램의 `WhenAny` 배열에는 단일 태스크를 반환 대기할 때 대기 작업을 완료 배열에 연결할 첫 번째 작업으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="e456f-129">다음과 같이 변경 `AccessTheWebAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="e456f-130">별표는 코드 파일의 변경 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="e456f-131">주석으로 처리 하거나 루프를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="e456f-132">쿼리 만들기, 실행 제네릭 작업 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="e456f-133">호출할 때마다 `ProcessURLAsync` 반환는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 는 정수입니다.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="e456f-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="e456f-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e456f-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
3.  <span data-ttu-id="e456f-135">호출 `ToArray` 쿼리를 실행 하는 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="e456f-136">응용 프로그램은 `WhenAny` 메서드는 다음 단계에서 쿼리를 실행 하 고 사용 하지 않고 작업을 시작 합니다 `ToArray`, 하지만 다른 방법 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="e456f-137">쿼리 실행을 명시적으로 적용 하는 것이 가장 안전이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-137">The safest practice is to force execution of the query explicitly.</span></span>  
  
<span data-ttu-id="e456f-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e456f-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="e456f-139">호출 `WhenAny` 작업의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-139">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="e456f-140">`WhenAny`반환 된 `Task(Of Task(Of Integer))` 또는 `Task<Task<int>>`합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-140">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="e456f-141">즉, `WhenAny` 단일 계산 되는 작업을 반환 합니다. `Task(Of Integer)` 또는 `Task<int>` 대기 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e456f-141">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="e456f-142">단일 작업 끝나기를 컬렉션의 첫 번째 작업은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-142">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="e456f-143">먼저 완료 된 작업에 할당 된 `firstFinishedTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-143">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="e456f-144">유형의 `firstFinishedTask` 는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 정수가 반환 형식 이므로 `ProcessURLAsync`.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="e456f-144">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  <span data-ttu-id="e456f-145">이 예제에서는 먼저 완료 하는 작업에만 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-145">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="e456f-146">따라서 사용 하 여 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>나머지 작업을 취소 합니다.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e456f-146">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> to cancel the remaining tasks.</span></span>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  <span data-ttu-id="e456f-147">마지막으로, await `firstFinishedTask` 다운로드 한 콘텐츠 길이 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-147">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 <span data-ttu-id="e456f-148">다른 다운로드를 먼저 완료를 확인 하려면 프로그램을 여러 번 실행.</span><span class="sxs-lookup"><span data-stu-id="e456f-148">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="e456f-149">완성된 예제</span><span class="sxs-lookup"><span data-stu-id="e456f-149">Complete Example</span></span>  
 <span data-ttu-id="e456f-150">다음 코드는 예제에 대 한 전체 MainWindow.xaml.vb 또는 MainWindow.xaml.cs 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-150">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="e456f-151">별표는이 예제에 대 한 추가 된 요소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-151">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="e456f-152"><xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 해야 한다고 공지</span><span class="sxs-lookup"><span data-stu-id="e456f-152">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="e456f-153">프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.</span><span class="sxs-lookup"><span data-stu-id="e456f-153">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            resultsTextBox.Text &= vbCrLf & "Download complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
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
  
        '' Comment out or delete the loop.  
        ''For Each url In urlList  
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).   
        ''    ' Argument ct carries the message if the Cancel button is chosen.   
        ''    ' Note that the Cancel button can cancel all remaining downloads.  
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ''    ' Retrieve the website contents from the HttpResponseMessage.  
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ''    resultsTextBox.Text &=  
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        ''Next  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToArray to execute the query and start the download tasks.   
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' ***Call WhenAny and then await the result. The task that finishes   
        ' first is assigned to firstFinishedTask.  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
        ' ***Cancel the rest of the downloads. You just want the first one.  
        cts.Cancel()  
  
        ' ***Await the first completed task and display the results  
        ' Run the program several times to demonstrate that different  
        ' websites can finish first.  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
    End Function  
  
    ' ***Bundle the processing steps for a website into one async method.  
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
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e456f-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e456f-154">See Also</span></span>  
 <span data-ttu-id="e456f-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="e456f-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="e456f-156"> [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="e456f-156"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="e456f-157"> [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="e456f-157"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="e456f-158"> [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="e456f-158"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
