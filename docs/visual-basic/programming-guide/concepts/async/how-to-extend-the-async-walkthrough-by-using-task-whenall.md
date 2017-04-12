---
title: "방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장 | Microsoft 문서"
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
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 46c5cb9328f2fa1a4ffc5116d318bc3286419e13
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장
비동기 솔루션의 성능을 향상 시킬 수 있습니다 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) 를 사용 하 여는 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>메서드.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 이 메서드는 작업의 컬렉션으로 표시 되는 여러 개의 비동기 작업을 비동기적으로 기다립니다.  
  
 보았을 것 연습에서 웹 사이트를 서로 다른 속도로 다운로드 합니다. 때로는 웹 사이트 중 하나 매우 느립니다, 나머지 모든 다운로드를 지연입니다. 이 연습에서 작성 하는 비동기 솔루션을 실행 하면 수를 종료할 때는 프로그램 쉽게 대기 하지 않으려는 경우 더 나은 옵션을 동시에 모든 다운로드를 시작 하 고 더 빠르게 사용 하는 것 다운로드 지연 되는 것을 기다리지 않고 계속 있습니다.  
  
 적용 하면는 `Task.WhenAll` 메서드를 작업의 컬렉션입니다. 응용 프로그램의 `WhenAll` 컬렉션의 모든 작업이 완료 될 때까지 완료 되지 않은 단일 작업을 반환 합니다. 작업을 병렬로 실행할 처럼 보이지만는 추가 스레드가 생성 됩니다. 작업 순서에 관계 없이 완료할 수 있습니다.  
  
> [!IMPORTANT]
>  다음 절차에서 개발 된 비동기 응용 프로그램에 대 한 확장 설명 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 연습을 완료 하거나 코드를 다운로드 하 여 응용 프로그램을 개발할 수 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)합니다.  
>   
>  예제를 실행 하려면 Visual Studio 2012 있어야 합니다. 또는 나중에 컴퓨터에 설치 합니다.  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>GetURLContentsAsync 솔루션에 Task.WhenAll을 추가하려면  
  
1.  추가 된 `ProcessURLAsync` 에서 개발 된 첫 번째 응용 프로그램에 메서드 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   코드를 다운로드 한 경우 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일에 있습니다.  
  
    -   이 연습을 완료 하 여 코드를 개발 하는 경우 추가 `ProcessURLAsync` 포함 된 응용 프로그램에는 `GetURLContentsAsync` 메서드. 이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션의 첫 번째 예제입니다.  
  
     `ProcessURLAsync` 메서드 통합 작업의 본문에는 `For Each` 루프 `SumPageSizesAsync` 원래 연습에서 합니다. 메서드가는 비동기적으로 바이트 배열로 지정된 된 웹 사이트의 내용을 다운로드 다음 표시 되며 및 바이트 배열의 길이 반환 합니다.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  주석으로 처리 하거나 삭제는 `For Each` 루프 `SumPageSizesAsync`다음 코드와 같이 합니다.  
  
    ```vb  
    'Dim total = 0  
    'For Each url In urlList  
  
    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
    '    ' The previous line abbreviates the following two assignment statements.  
  
    '    ' GetURLContentsAsync returns a task. At completion, the task  
    '    ' produces a byte array.  
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
    '    'Dim urlContents As Byte() = Await getContentsTask  
  
    '    DisplayResults(url, urlContents)  
  
    '    ' Update the total.  
    '    total += urlContents.Length  
    'Next  
    ```  
  
3.  작업 컬렉션을 만듭니다. 다음 코드를 정의 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 를 실행 하면는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 각 웹 사이트의 콘텐츠를 다운로드 하는 작업의 컬렉션을 만듭니다.</xref:System.Linq.Enumerable.ToArray%2A> 작업에는 쿼리가 평가 될 때 시작 됩니다.  
  
     메서드에 다음 코드를 추가 `SumPageSizesAsync` 의 선언 뒤 `urlList`합니다.  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  적용 `Task.WhenAll` 작업의 컬렉션에 `downloadTasks`합니다. `Task.WhenAll`작업의 컬렉션에서 모든 작업이 완료 될 때 완료 하는 단일 작업을 반환 합니다.  
  
     다음 예제에서는 `Await` 식을 단일의 완료를 대기 하는 작업입니다 `WhenAll` 반환 합니다. 식은 각 정수는 다운로드 한 웹 사이트의 길이 정수 배열이 됩니다. 다음 코드를 추가 `SumPageSizesAsync`를 이전 단계에서 추가한 코드 뒤 뿐입니다.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  마지막으로, 사용 된 <xref:System.Linq.Enumerable.Sum%2A>모든 웹 사이트의 길이의 합을 계산 하는 방법.</xref:System.Linq.Enumerable.Sum%2A> 다음 줄을 추가 `SumPageSizesAsync`합니다.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>HttpClient.GetByteArrayAsync 솔루션에 Task.WhenAll을 추가하려면  
  
1.  다음 버전의 추가 `ProcessURLAsync` 에서 개발 된 두 번째 응용 프로그램에 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   코드를 다운로드 한 경우 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough_HttpClient 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일에 있습니다.  
  
    -   이 연습을 완료 하 여 코드를 개발 하는 경우 추가 `ProcessURLAsync` 사용 하 여 응용 프로그램에는 `HttpClient.GetByteArrayAsync` 메서드. 이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션에 두 번째 예제입니다.  
  
     `ProcessURLAsync` 메서드 통합 작업의 본문에는 `For Each` 루프 `SumPageSizesAsync` 원래 연습에서 합니다. 메서드가는 비동기적으로 바이트 배열로 지정된 된 웹 사이트의 내용을 다운로드 다음 표시 되며 및 바이트 배열의 길이 반환 합니다.  
  
     유일한 차이점은 `ProcessURLAsync` 이전 절차에서 메서드를 사용 하는는 <xref:System.Net.Http.HttpClient>인스턴스, `client`.</xref:System.Net.Http.HttpClient>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  주석으로 처리 하거나 삭제는 `For Each` 루프 `SumPageSizesAsync`다음 코드와 같이 합니다.  
  
    ```vb  
    'Dim total = 0   
    'For Each url In urlList   
    '    ' GetByteArrayAsync returns a task. At completion, the task   
    '    ' produces a byte array.   
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)   
  
    '    ' The following two lines can replace the previous assignment statement.   
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)   
    '    'Dim urlContents As Byte() = Await getContentsTask   
  
    '    DisplayResults(url, urlContents)   
  
    '    ' Update the total.   
    '    total += urlContents.Length   
    'Next  
  
    ```  
  
3.  정의 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 를 실행 하면는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 각 웹 사이트의 콘텐츠를 다운로드 하는 작업의 컬렉션을 만듭니다.</xref:System.Linq.Enumerable.ToArray%2A> 작업에는 쿼리가 평가 될 때 시작 됩니다.  
  
     메서드에 다음 코드를 추가 `SumPageSizesAsync` 의 선언 뒤 `client` 및 `urlList`합니다.  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  다음으로, 적용 `Task.WhenAll` 작업의 컬렉션에 `downloadTasks`합니다. `Task.WhenAll`작업의 컬렉션에서 모든 작업이 완료 될 때 완료 하는 단일 작업을 반환 합니다.  
  
     다음 예제에서는 `Await` 식을 단일의 완료를 대기 하는 작업입니다 `WhenAll` 반환 합니다. 완료 되 면는 `Await` 식이 있는 각 정수는 다운로드 한 웹 사이트의 길이, 정수의 배열입니다. 다음 코드를 추가 `SumPageSizesAsync`를 이전 단계에서 추가한 코드 뒤 뿐입니다.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  마지막으로 사용 하 여는 <xref:System.Linq.Enumerable.Sum%2A>를 모든 웹 사이트의 길이 합한 값을 가져오는 메서드입니다.</xref:System.Linq.Enumerable.Sum%2A> 다음 줄을 추가 `SumPageSizesAsync`합니다.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a>Task.WhenAll 솔루션을 테스트하려면  
  
-   두 솔루션에 대 한 프로그램을 실행 하려면 F5 키를 선택 하 고 선택 된 **시작** 단추입니다. 출력의 출력에서 비동기 솔루션을 비슷해야 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 그러나 웹 사이트 나타나는 각 시간에 다른 순서로 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 사용 하는 프로젝트에 대 한 확장은 `GetURLContentsAsync` 메서드는 웹에서 콘텐츠를 다운로드 합니다.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.   
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        'Dim total = 0  
        'For Each url In urlList  
  
        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
        '    ' The previous line abbreviates the following two assignment statements.  
  
        '    ' GetURLContentsAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    ' The actions from the foreach loop are moved to this async method.  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                ' CopyToAsync returns a Task, not a Task<T>.  
                Await responseStream.CopyToAsync(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
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
  
## <a name="example"></a>예제  
 다음 코드에서는 메서드를 사용 하는 프로젝트에 대 한 확장 `HttpClient.GetByteArrayAsync` 웹에서 콘텐츠를 다운로드 합니다.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        ''<snippet7>  
        'Dim total = 0  
        'For Each url In urlList  
        '    ' GetByteArrayAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    '<snippet31>  
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
        '    '</snippet31>  
  
        '    ' The following two lines can replace the previous assignment statement.  
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>   
 [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
