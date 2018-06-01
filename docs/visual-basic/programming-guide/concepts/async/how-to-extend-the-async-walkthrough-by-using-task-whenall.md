---
title: '방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장'
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: 12d195caa11cd33b4e450e5a57699da4037ed4a2
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34696353"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장
비동기 솔루션의 성능을 향상 시킬 수 있습니다 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) 를 사용 하 여는 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 메서드. 이 메서드는 작업 컬렉션으로 표시되는 여러 개의 비동기 작업을 비동기적으로 기다립니다.  
  
 연습에서 웹 사이트 다운로드 속도가 각기 다른 것을 보셨을 것입니다. 때로는 웹 사이트 중 하나가 매우 느려 나머지 다운로드가 모두 지연됩니다. 연습에서 빌드하는 비동기 솔루션을 실행하는 경우 대기하지 않으려면 프로그램을 쉽게 종료할 수 있지만, 동시에 모든 다운로드를 시작한 후 더 빠른 다운로드는 지연되는 다운로드를 기다리지 않고 계속되도록 하는 것이 더 낫습니다.  
  
 작업 컬렉션에 `Task.WhenAll` 메서드를 적용합니다. `WhenAll` 응용 프로그램은 컬렉션의 모든 작업이 완료될 때까지 완료되지 않는 단일 작업을 반환합니다. 작업이 병렬로 실행되는 것처럼 보이지만 추가 스레드는 생성되지 않습니다. 작업이 임의 순서로 완료될 수 있습니다.  
  
> [!IMPORTANT]
>  다음 절차에서는에서 개발 된 비동기 응용 프로그램에 대 한 확장 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 연습을 완료하거나 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)에서 코드를 다운로드하여 응용 프로그램을 개발할 수 있습니다.  
>   
>  예제를 실행하려면 Visual Studio 2012 이상이 컴퓨터에 설치되어 있어야 합니다.  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>GetURLContentsAsync 솔루션에 Task.WhenAll을 추가하려면  
  
1.  추가 `ProcessURLAsync` 에서 개발 된 첫 번째 응용 프로그램에 메서드 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   코드를 다운로드 한 경우 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)AsyncWalkthrough 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일로 합니다.  
  
    -   연습을 완료하여 코드를 개발한 경우 `GetURLContentsAsync` 메서드를 포함하는 응용 프로그램에 `ProcessURLAsync`를 추가합니다. 이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션의 첫 번째 예제입니다.  
  
     `ProcessURLAsync` 메서드는 원래 연습의 `SumPageSizesAsync`에 `For Each` 루프 본문의 작업을 통합합니다. 이 메서드는 비동기적으로 지정된 웹 사이트의 내용을 바이트 배열로 다운로드한 다음 바이트 배열의 길이를 표시하고 반환합니다.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  다음 코드와 같이 `SumPageSizesAsync`의 `For Each` 루프를 주석으로 처리하거나 삭제합니다.  
  
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
  
3.  작업 컬렉션을 만듭니다. 다음 코드는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드가 실행할 때 각 웹 사이트의 내용을 다운로드하는 작업 컬렉션을 만드는 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)를 정의합니다. 작업은 쿼리가 평가될 때 시작됩니다.  
  
     `SumPageSizesAsync` 메서드의 `urlList` 선언 뒤에 다음 코드를 추가합니다.  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  작업 컬렉션 `downloadTasks`에서 `Task.WhenAll`을 적용합니다. `Task.WhenAll`은 작업 컬렉션의 모든 작업이 완료될 때 완료되는 단일 작업을 반환합니다.  
  
     다음 예제에서 `Await` 식은 `WhenAll`이 반환하는 단일 작업이 완료될 때까지 기다립니다. 식은 각 정수가 다운로드된 웹 사이트의 길이인 정수 배열로 평가됩니다. 이전 단계에서 추가한 코드 뒤의 `SumPageSizesAsync`에 다음 코드를 추가합니다.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  마지막으로, <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 모든 웹 사이트의 길이 합계를 계산합니다. `SumPageSizesAsync`에 다음 줄을 추가합니다.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>HttpClient.GetByteArrayAsync 솔루션에 Task.WhenAll을 추가하려면  
  
1.  다음 버전의 추가 `ProcessURLAsync` 에서 개발 하는 두 번째 응용 프로그램에 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   코드를 다운로드 한 경우 [개발자 코드 샘플](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)AsyncWalkthrough_HttpClient 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일로 합니다.  
  
    -   연습을 완료하여 코드를 개발한 경우 `HttpClient.GetByteArrayAsync` 메서드를 사용하는 응용 프로그램에 `ProcessURLAsync`를 추가합니다. 이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션에서 두 번째 예제입니다.  
  
     `ProcessURLAsync` 메서드는 원래 연습의 `SumPageSizesAsync`에 `For Each` 루프 본문의 작업을 통합합니다. 이 메서드는 비동기적으로 지정된 웹 사이트의 내용을 바이트 배열로 다운로드한 다음 바이트 배열의 길이를 표시하고 반환합니다.  
  
     이전 절차의 `ProcessURLAsync` 메서드와 차이점은 <xref:System.Net.Http.HttpClient> 인스턴스 `client`를 사용한다는 것입니다.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  다음 코드와 같이 `SumPageSizesAsync`의 `For Each` 루프를 주석으로 처리하거나 삭제합니다.  
  
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
  
3.  <xref:System.Linq.Enumerable.ToArray%2A> 메서드에서 실행할 때 각 웹 사이트의 내용을 다운로드하는 작업 컬렉션을 만드는 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)를 정의합니다. 작업은 쿼리가 평가될 때 시작됩니다.  
  
     `SumPageSizesAsync` 메서드의 `client` 및 `urlList` 선언 뒤에 다음 코드를 추가합니다.  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  작업 컬렉션 `downloadTasks`에서 `Task.WhenAll`을 적용합니다. `Task.WhenAll`은 작업 컬렉션의 모든 작업이 완료될 때 완료되는 단일 작업을 반환합니다.  
  
     다음 예제에서 `Await` 식은 `WhenAll`이 반환하는 단일 작업이 완료될 때까지 기다립니다. 완료되면 `Await` 식은 각 정수가 다운로드된 웹 사이트의 길이인 정수 배열로 평가됩니다. 이전 단계에서 추가한 코드 뒤의 `SumPageSizesAsync`에 다음 코드를 추가합니다.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  마지막으로, <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 모든 웹 사이트의 길이 합계를 가져옵니다. `SumPageSizesAsync`에 다음 줄을 추가합니다.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a>Task.WhenAll 솔루션을 테스트하려면  
  
-   두 솔루션 중 하나에 대해 F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다. 출력의 출력에서 비동기 솔루션을 비슷해야 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 그러나 웹 사이트가 매번 다른 순서로 나타납니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 `GetURLContentsAsync` 메서드를 사용하여 웹에서 콘텐츠를 다운로드하는 프로젝트에 대한 확장을 보여 줍니다.  
  
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
  
## <a name="example"></a>예  
 다음 코드에서는 `HttpClient.GetByteArrayAsync` 메서드를 사용하여 웹에서 콘텐츠를 다운로드하는 프로젝트에 대한 확장을 보여 줍니다.  
  
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
 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>  
 [연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
