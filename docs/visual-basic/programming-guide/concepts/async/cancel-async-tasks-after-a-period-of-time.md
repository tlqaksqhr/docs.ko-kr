---
title: "(Visual Basic) 기간 이후 비동기 작업 취소 | Microsoft 문서"
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
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c2c7c09f9af7c9b7bdcb6411b6db6e2ca4984cb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="b48dd-102">(Visual Basic) 기간 이후 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="b48dd-102">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>
<span data-ttu-id="b48dd-103">사용 하 여 일정 기간 후에 비동기 작업을 취소할 수는 <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>메서드 작업이 끝날 때까지 대기 하지 않으려는 경우.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b48dd-103">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="b48dd-104">가 지정 하는 기간 내에 완료 되지 않은 모든 연결 된 작업의 취소를 예약 하는이 메서드는 `CancelAfter` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-104">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>  
  
 <span data-ttu-id="b48dd-105">개발 하는 코드에 추가 하는이 예제 [는 목록의의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 웹 사이트 목록을 다운로드 하 고 각각의 콘텐츠 길이 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-105">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b48dd-106">예제를 실행 하려면.NET Framework 4.5와 Visual Studio 2012 이상이 있어야 하거나 나중에 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-106">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="b48dd-107">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="b48dd-107">Downloading the Example</span></span>  
 <span data-ttu-id="b48dd-108">전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-108">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="b48dd-109">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-109">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b48dd-110">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-110">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="b48dd-111">에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-111">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="b48dd-112">**솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelAfterTime** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-112">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="b48dd-113">프로젝트를 실행 하려면 F5 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-113">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="b48dd-114">디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-114">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="b48dd-115">프로그램을 여러 번 실행 확인 출력 모든 웹 사이트, 웹, 또는 일부 웹 사이트에 대 한 출력을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-115">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>  
  
 <span data-ttu-id="b48dd-116">프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-116">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="b48dd-117">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="b48dd-117">Building the Example</span></span>  
 <span data-ttu-id="b48dd-118">개발 하는 프로젝트에 추가 하는이 항목의 예제 [는 목록의의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 작업 목록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-118">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="b48dd-119">하지만 예제에서는 동일한 UI를 사용 여 **취소** 단추 명시적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-119">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="b48dd-120">예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAListOfTasks** 으로 **시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-120">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="b48dd-121">이 항목의 변경 내용이 해당 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-121">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="b48dd-122">작업 취소 됨으로 표시 되는 최대 시간을 지정 하려면 호출을 추가 하면 `CancelAfter` 를 `startButton_Click`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-122">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="b48dd-123">추가 별표로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-123">The addition is marked with asterisks.</span></span>  
  
```vb  
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' Instantiate the CancellationTokenSource.  
    cts = New CancellationTokenSource()  
  
    resultsTextBox.Clear()  
  
    Try  
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
        ' can adjust the time.)  
        cts.CancelAfter(2500)  
  
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
```  
  
 <span data-ttu-id="b48dd-124">프로그램을 여러 번 실행 확인 출력 모든 웹 사이트, 웹, 또는 일부 웹 사이트에 대 한 출력을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-124">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="b48dd-125">다음과 같은 출력 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-125">The following output is a sample.</span></span>  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a><span data-ttu-id="b48dd-126">전체 예제</span><span class="sxs-lookup"><span data-stu-id="b48dd-126">Complete Example</span></span>  
 <span data-ttu-id="b48dd-127">다음 코드는 예제에 대 한 MainWindow.xaml.vb 파일의 전체 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-127">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="b48dd-128">별표는이 예제에 대 한 추가 된 요소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-128">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="b48dd-129"><xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 해야 한다고 공지</span><span class="sxs-lookup"><span data-stu-id="b48dd-129">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="b48dd-130">프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.</span><span class="sxs-lookup"><span data-stu-id="b48dd-130">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
            ' can adjust the time.)  
            cts.CancelAfter(2500)  
  
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
  
        ' Process each element in the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
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
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="b48dd-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b48dd-131">See Also</span></span>  
 <span data-ttu-id="b48dd-132">[비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="b48dd-132">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="b48dd-133"> [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="b48dd-133"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="b48dd-134"> [비동기 작업 또는 작업 (Visual Basic) 목록이 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b48dd-134"> [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span></span>  
<span data-ttu-id="b48dd-135"> [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="b48dd-135"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="b48dd-136"> [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="b48dd-136"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
