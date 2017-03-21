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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a>여러 비동기 작업을 시작 하 고 (Visual Basic) 완료 될 때마다 처리
사용 하 여 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, 동시에 여러 작업을 시작할 수 있으며은 완료 된 것 보다는 시작 하는 순서에서이 처리 하는 대로 하나씩 처리 합니다.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>  
  
 다음 예제에서는 작업의 컬렉션을 만드는 쿼리를 사용 합니다. 지정된 된 웹 사이트의 콘텐츠를 다운로드 하는 각 작업입니다. 잠시의 각 반복에서 루프에 대 한 대기 중인된 호출 `WhenAny` 다운로드를 먼저 완료 하는 작업의 컬렉션에 작업을 반환 합니다. 해당 작업 컬렉션에서 제거 하 고 처리 됩니다. 루프는 컬렉션에 더 많은 작업이 포함 될 때까지 반복 합니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
## <a name="downloading-the-example"></a>예제 다운로드  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는 **ProcessTasksAsTheyFinish** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.  
  
5.  프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
     디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.  
  
6.  다운로드 한 길이 없습니다 동일한 순서로 항상 표시 되는지 확인 하려면 프로젝트를 여러 번 실행 합니다.  
  
 프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
## <a name="building-the-example"></a>예제 빌드  
 개발 하는 코드에 추가 하는이 예제 [하나의 완전 (Visual Basic) 한 후 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 동일한 UI를 사용 하 여 합니다.  
  
 예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAfterOneTask** 으로 **시작 프로젝트**합니다. 이 항목의 변경 내용을 추가 `AccessTheWebAsync` 해당 프로젝트에서 메서드. 변경 내용은 별표로 표시 됩니다.  
  
 **CancelAfterOneTask** 는 쿼리를 이미 포함 하는 프로젝트를 실행 하면 작업의 컬렉션을 만듭니다. 호출할 때마다 `ProcessURLAsync` 다음 코드를 반환는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 는 정수입니다.</xref:System.Threading.Tasks.Task%601>  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 프로젝트의 MainWindow.xaml.vb 파일에서 다음과 같이 변경 하는 `AccessTheWebAsync` 메서드.  
  
-   <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> 대신</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> 적용 하 여 쿼리를 실행 합니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
-   잠시 추가 컬렉션의 각 작업에 대해 다음 단계를 수행 하는 루프입니다.  
  
    1.  에 대 한 호출을 기다리는 `WhenAny` 다운로드를 완료 하려면 컬렉션의 첫 번째 작업을 식별할 수 있습니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
    2.  컬렉션에서 해당 작업을 제거합니다.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
    3.  대기 `firstFinishedTask`에 대 한 호출에서 반환 된 `ProcessURLAsync`합니다. `firstFinishedTask` 변수가 <xref:System.Threading.Tasks.Task%601>여기서 `TReturn` 는 정수입니다.</xref:System.Threading.Tasks.Task%601> 작업이 이미 완료 되 면 하지만 다음 예제와 같이 다운로드 한 웹 사이트의 길이 검색 하기를 기다립니다.  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 다운로드 한 길이 순서 대로 나타나지 항상 확인을 여러 번 프로젝트를 실행 해야 합니다.  
  
> [!CAUTION]
>  사용할 수 있습니다 `WhenAny` 적은 수의 작업을 포함 하는 문제를 해결 하는 예제에 설명 된 대로 루프에서. 그러므로 많은 수의 작업을 처리해야 하는 경우에는 다른 접근 방법이 더 효율적입니다. 자세한 내용 및 예제에 대 한 참조 [처리 작업이 완료 될 때](http://go.microsoft.com/fwlink/?LinkId=260810)합니다.  
  
## <a name="complete-example"></a>전체 예제  
 다음 코드는 예제에 대 한 MainWindow.xaml.vb 파일의 전체 텍스트입니다. 별표는이 예제에 대 한 추가 된 요소를 표시 합니다.  
  
 <xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 해야 한다고 공지  
  
 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)
