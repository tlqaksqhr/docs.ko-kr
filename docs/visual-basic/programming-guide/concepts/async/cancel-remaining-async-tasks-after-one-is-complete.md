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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a>하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소
사용 하 여는 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>와 함께 메서드는 <xref:System.Threading.CancellationToken>, 한 작업이 완료 되 면 모든 나머지 작업을 취소할 수 있습니다.</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> `WhenAny` 메서드 작업의 컬렉션을 나타내는 인수를 사용 합니다. 메서드는 모든 작업을 시작 하 고 작업을 단일 작업을 반환 합니다. 컬렉션에서 모든 작업이 완료 되 면 단일 작업이 완료 되었습니다.  
  
 와 함께에서 취소 토큰을 사용 하는 방법을 보여 주는이 예제 `WhenAny` 작업의 컬렉션에서 완료 하 고 나머지 작업을 취소 하는 첫 번째 작업에 저장할 수 있습니다. 웹 사이트의 콘텐츠를 다운로드 하는 각 작업입니다. 이 예제는 첫 번째 다운로드를 완료 하려면의 콘텐츠 길이 표시 하 고 다른 다운로드를 취소 합니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
## <a name="downloading-the-example"></a>예제 다운로드  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelAfterOneTask** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.  
  
5.  프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
     디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.  
  
6.  다른 다운로드를 먼저 완료를 확인 하려면 프로그램을 여러 번 실행.  
  
 프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
## <a name="building-the-example"></a>예제 빌드  
 이 항목의 예제에서 개발한 프로젝트에 추가 [비동기 작업 또는 작업 목록 취소](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) 작업 목록 취소 합니다. 하지만 예제에서는 동일한 UI를 사용 여 **취소** 단추 명시적으로 사용 되지 않습니다.  
  
 예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAListOfTasks** 으로 **시작 프로젝트**합니다. 이 항목의 변경 내용이 해당 프로젝트에 추가 합니다.  
  
 MainWindow.xaml.vb 파일에는 **CancelAListOfTasks** 프로젝트를에서 루프의 각 웹 사이트에 대 한 처리 단계를 이동 하 여 전환을 시작 `AccessTheWebAsync` 다음 비동기 메서드.  
  
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
  
 `AccessTheWebAsync`, 쿼리를 사용 하 여이 예제는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 및 `WhenAny` 메서드를 만들고 시작 작업의 배열입니다.</xref:System.Linq.Enumerable.ToArray%2A> 응용 프로그램의 `WhenAny` 배열에는 단일 태스크를 반환 대기할 때 대기 작업을 완료 배열에 연결할 첫 번째 작업으로 계산 합니다.  
  
 다음과 같이 변경 `AccessTheWebAsync`합니다. 별표는 코드 파일의 변경 내용을 표시합니다.  
  
1.  주석으로 처리 하거나 루프를 삭제 합니다.  
  
2.  쿼리 만들기, 실행 제네릭 작업 컬렉션을 생성 합니다. 호출할 때마다 `ProcessURLAsync` 반환는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 는 정수입니다.</xref:System.Threading.Tasks.Task%601>  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
3.  호출 `ToArray` 쿼리를 실행 하는 작업을 시작 합니다. 응용 프로그램은 `WhenAny` 메서드는 다음 단계에서 쿼리를 실행 하 고 사용 하지 않고 작업을 시작 합니다 `ToArray`, 하지만 다른 방법 되지 않을 수도 있습니다. 쿼리 실행을 명시적으로 적용 하는 것이 가장 안전이 좋습니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
4.  호출 `WhenAny` 작업의 컬렉션입니다. `WhenAny`반환 된 `Task(Of Task(Of Integer))` 또는 `Task<Task<int>>`합니다.  즉, `WhenAny` 단일 계산 되는 작업을 반환 합니다. `Task(Of Integer)` 또는 `Task<int>` 대기 하는 경우. 단일 작업 끝나기를 컬렉션의 첫 번째 작업은 됩니다. 먼저 완료 된 작업에 할당 된 `firstFinishedTask`합니다. 유형의 `firstFinishedTask` 는 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 정수가 반환 형식 이므로 `ProcessURLAsync`.</xref:System.Threading.Tasks.Task%601>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  이 예제에서는 먼저 완료 하는 작업에만 관심이 있습니다. 따라서 사용 하 여 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>나머지 작업을 취소 합니다.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  마지막으로, await `firstFinishedTask` 다운로드 한 콘텐츠 길이 검색할 수 있습니다.  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 다른 다운로드를 먼저 완료를 확인 하려면 프로그램을 여러 번 실행.  
  
## <a name="complete-example"></a>완성된 예제  
 다음 코드는 예제에 대 한 전체 MainWindow.xaml.vb 또는 MainWindow.xaml.cs 파일입니다. 별표는이 예제에 대 한 추가 된 요소를 표시 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)
