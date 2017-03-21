---
title: "비동기 작업 또는 작업 (Visual Basic) 목록이 취소 | Microsoft 문서"
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
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
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a>비동기 작업 또는 작업 (Visual Basic) 목록이 취소
완료 될 때까지 대기 하지 않으려는 경우 비동기 응용 프로그램을 취소 하는 데 사용할 수 있는 단추를 설정할 수 있습니다. 이 항목의 예제를 따라 웹 사이트 목록이 나 웹 사이트의 콘텐츠를 다운로드 하는 응용 프로그램에 취소 단추를 추가할 수 있습니다.  
  
 예제에서는 UI를 사용 하는 [미세 조정 Your 비동기 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) 에 대해 설명 합니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
##  <a name="BKMK_CancelaTask"></a>작업 취소  
 첫 번째 예제에서는 연결에서 **취소** 번 다운로드 작업에는 단추입니다. 응용 프로그램은 콘텐츠를 다운로드 하는 동안 단추를 선택 하면 다운로드가 취소 됩니다.  
  
### <a name="downloading-the-example"></a>예제 다운로드  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelATask** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.  
  
5.  프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
     디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.  
  
 프로젝트를 다운로드 하지 않으려는 경우이 항목의 끝부분에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
### <a name="building-the-example"></a>예제 빌드  
 다음과 같은 변경 내용이 추가 **취소** 웹 사이트를 다운로드 하는 응용 프로그램에 단추입니다. 예제를 작성 하거나 다운로드 하 고 않으려면,이 항목의 끝에 있는 "예제" 섹션에서 최종 제품을 검토할 수 있습니다. 별표는 코드의 변경 내용을 표시합니다.  
  
 예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **StarterCode** 으로 **시작 프로젝트** 대신 **CancelATask**합니다.  
  
 그런 다음 다음과 같은 변경 내용이 해당 프로젝트의 MainWindow.xaml.vb 파일에 추가.  
  
1.  선언는 `CancellationTokenSource` 변수인 `cts`, 액세스 하는 모든 메서드에 대 한 범위에 있습니다.  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  다음 이벤트 처리기에 대 한 추가 **취소** 단추입니다. 이벤트 처리기에서 사용 된 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>에 알리기 위해 메서드 `cts` 사용자가 취소를 요청 하는 경우.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  변경 다음 이벤트에 대 한 처리기는 **시작** 단추 `startButton_Click`합니다.  
  
    -   인스턴스화하는 `CancellationTokenSource`, `cts`합니다.  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   에 대 한 호출에서 `AccessTheWebAsync`, 지정된 된 웹 사이트의 콘텐츠를 다운로드 하는, 보내기는 <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>속성 `cts` 인수로.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> `Token` 속성 취소가 요청 된 경우 메시지를 전파 합니다. 사용자가 다운로드 작업을 취소 하도록 선택 하는 경우 메시지를 표시 하는 catch 블록을 추가 합니다. 다음 코드에서는 변경 내용을 보여 줍니다.  
  
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
  
4.  `AccessTheWebAsync`를 사용 하 여는 <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>오버 로드는 `GetAsync` 에서 메서드는 <xref:System.Net.Http.HttpClient>웹 사이트의 내용을 다운로드 하는 형식입니다.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> 전달 `ct`, <xref:System.Threading.CancellationToken>의 매개 변수 `AccessTheWebAsync`, 두 번째 인수로.</xref:System.Threading.CancellationToken> 토큰이 사용자가 선택 하는 경우 메시지 전달의 **취소** 단추입니다.  
  
     다음 코드에서는의 변경 내용을 `AccessTheWebAsync`합니다.  
  
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
  
5.  프로그램을 취소 하지는 다음과 같은 출력을 생성 합니다.  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     선택 하는 경우는 **취소** 단추 프로그램 하기 전에 콘텐츠를 다운로드 하는 완료 되 면을 다음과 같은 출력을 생성 하는 프로그램입니다.  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <a name="BKMK_CancelaListofTasks"></a>작업 목록 취소  
 동일한 연결 하 여 다양 한 작업을 취소 하는 앞의 예제를 확장할 수 있습니다 `CancellationTokenSource` 각 작업을 사용 하 여 인스턴스. 선택 하는 경우는 **취소** 완료 아직 되지 않은 모든 작업을 취소 단추를 합니다.  
  
### <a name="downloading-the-example"></a>예제 다운로드  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelAListOfTasks** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.  
  
5.  프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
     디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.  
  
 프로젝트를 다운로드 하지 않으려는 경우이 항목의 끝부분에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
### <a name="building-the-example"></a>예제 빌드  
 예제를 확장 하려면 "예 다운로드" 섹션의 지침에 따라 직접 단계별로 하지만를 선택할 **CancelATask** 으로 **시작 프로젝트**합니다. 다음과 같은 변경 내용이 해당 프로젝트에 추가 합니다. 별표는 프로그램의 변경 내용을 표시합니다.  
  
1.  웹 주소 목록을 만드는 메서드를 추가 합니다.  
  
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
  
2.  메서드를 호출 `AccessTheWebAsync`합니다.  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  다음 루프에 추가 `AccessTheWebAsync` 목록에서 각 웹 주소를 처리 합니다.  
  
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
  
4.  때문에 `AccessTheWebAsync` 표시 길이 메서드를 아무것도 반환할 필요가 없습니다. Return 문을 제거 하 고 <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 대신</xref:System.Threading.Tasks.Task> 하는 메서드의 반환 형식 변경  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
     메서드를 호출 `startButton_Click` 식 대신 사용 하 여 합니다.  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  프로그램을 취소 하지는 다음과 같은 출력을 생성 합니다.  
  
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
  
     선택 하는 경우는 **취소** 출력 다운로드를 완료 하기 전에 단추를 취소 하기 전에 완료 하는 다운로드의 길이 포함 합니다.  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <a name="BKMK_CompleteExamples"></a>전체 예제  
 다음 섹션에서는 각각 이전 예제에 대 한 코드를 포함. <xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 해야 한다고 공지  
  
 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.  
  
### <a name="cancel-a-task-example"></a>작업 취소 예제  
 다음 코드는 단일 작업을 취소 하는 예제에 대 한 전체 MainWindow.xaml.vb 파일입니다.  
  
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
  
### <a name="cancel-a-list-of-tasks-example"></a>작업 목록 취소 예제  
 다음 코드는 작업 목록 취소 하는 예제에 대 한 전체 MainWindow.xaml.vb 파일입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource>   
 <xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken>   
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)
