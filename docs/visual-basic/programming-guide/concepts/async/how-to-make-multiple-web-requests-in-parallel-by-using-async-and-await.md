---
title: "방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic) | Microsoft 문서"
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
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e4c41cc3813a9f96d944d115c6aaa5c5842a629b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)
비동기 메서드에서 작업이 처음 만들어질 때 시작 됩니다. [Await](../../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 계속할 수 없습니다 작업이 완료 될 때까지 메서드에서 지점에서 작업에 적용 됩니다. 종종 다음 예제와 같이 생성 되는 즉시 작업 대기 됩니다.  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 작업의 완료에 의존 하지 않는 프로그램에 다른 작업을 수행 하는 작업을 대기 중에서 작업을 만드는 구분할 수 있습니다.  
  
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
  
 작업을 시작 하 고 대기 하는 것 사이 다른 작업을 시작할 수 있습니다. 추가 작업을 암시적으로 병렬로 실행할 수 있지만 추가 스레드가 생성 됩니다.  
  
 다음 프로그램은 세 가지 비동기 웹 다운로드를 시작 하 고 호출 하는 순서에 해당를 기다립니다. 작업 순서는 만들어지고 대기할 항상 완료 하지는 프로그램을 실행할 때 표시입니다. 실행을 시작 하려면, 생성 하 고 메서드가 await 식이 도달 하기 전에 작업 중 하나 이상이 완료 될 수 있습니다.  
  
> [!NOTE]
>  이 프로젝트를 완료 하려면 Visual Studio 2012 이상 및.NET Framework 4.5가 있어야 하거나 이상이 컴퓨터에 설치 합니다.  
  
 동시에 여러 작업을 시작 하는 다른 예제를 참조 하십시오. [하는 방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.  
  
 이 예제에 대 한 코드를 다운로드할 수 있습니다 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=254906)합니다.  
  
### <a name="to-set-up-the-project"></a>프로젝트를 설정하려면  
  
1.  WPF 응용 프로그램을 설정 하려면 다음 단계를 완료 합니다. 다음이 단계에 대 한 자세한 지침을 찾을 수 있습니다 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   텍스트 상자와 단추가 포함 된 WPF 응용 프로그램을 만듭니다. 단추 이름을 `startButton`, 이름 텍스트 상자 및 `resultsTextBox`합니다.  
  
    -   <xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 합니다.  
  
    -   MainWindow.xaml.vb 파일에서 추가 된 `Imports` 문을 `System.Net.Http`합니다.  
  
### <a name="to-add-the-code"></a>코드를 추가하려면  
  
1.  MainWindow.xaml 디자인 창에서 만들기 단추를 두 번 클릭은 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.  
  
2.  다음 코드를 복사 하 고 본문에 붙여 넣습니다 `startButton_Click` MainWindow.xaml.vb에 있습니다.  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     코드는 비동기 메서드를 호출 `CreateMultipleTasksAsync`, 응용 프로그램을 구동입니다.  
  
3.  프로젝트에 다음과 같은 지원 메서드를 추가 합니다.  
  
    -   `ProcessURLAsync`사용 하는 <xref:System.Net.Http.HttpClient>메서드를 바이트 배열로 웹 사이트의 콘텐츠를 다운로드 합니다.</xref:System.Net.Http.HttpClient> 지원 메서드 `ProcessURLAsync` 다음 표시 하 고 배열의 길이 반환 합니다.  
  
    -   `DisplayResults`각 URL에 대 한 바이트 배열의 바이트 수를 표시합니다. 각 작업 다운로드가 완료 되 면이 표시 보여 줍니다.  
  
     다음 메서드를 복사한 후 붙여는 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.  
  
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
  
4.  메서드를 정의 하는 마지막으로, `CreateMultipleTasksAsync`, 다음 단계를 수행 합니다.  
  
    -   메서드 선언는 `HttpClient` 메서드에 액세스 하는 데 필요한 개체 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>에서 `ProcessURLAsync`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>  
  
    -   메서드를 만들어 형식의 세 가지 작업을 시작 <xref:System.Threading.Tasks.Task%601>여기서 `TResult` 는 정수입니다.</xref:System.Threading.Tasks.Task%601> 각 작업을 마치면 `DisplayResults` 작업의 URL 및 다운로드 한 콘텐츠 길이 표시 합니다. 작업이 비동기적으로 실행 되 고 때문에 결과가 표시 되는 순서는 선언 된 순서에서 달라질 수 있습니다.  
  
    -   메서드는 각 작업의 완료를 대기 합니다. 각 `Await` 연산자의 실행을 중단 `CreateMultipleTasksAsync` 대기 중인된 작업이 완료 될 때까지 합니다. 또한 연산자에 대 한 호출에서 반환 값을 검색 `ProcessURLAsync` 에서 각 작업을 완료 합니다.  
  
    -   태스크를 완료 하 고 정수 값이 검색 된 경우 메서드는 웹 사이트의 길이 합산 하 고 결과 표시 합니다.  
  
     다음 메서드를 복사 하 고 솔루션에 붙여 넣습니다.  
  
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
  
5.  F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     프로그램을 여러 번 실행 하는 세 가지 작업 순서 대로 완료 날짜 항상 하지 하 고 완료 하는 순서는 만들어지고 대기할 순서 반드시 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 전체 예제가 포함 되어 있습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)

