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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6708bd92d8dc2455b9dcb8e02dcc0a4455e00cda
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>(Visual Basic) 기간 이후 비동기 작업 취소
사용 하 여 일정 기간 후에 비동기 작업을 취소할 수는 <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>메서드 작업이 끝날 때까지 대기 하지 않으려는 경우.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> 가 지정 하는 기간 내에 완료 되지 않은 모든 연결 된 작업의 취소를 예약 하는이 메서드는 `CancelAfter` 식입니다.  
  
 개발 하는 코드에 추가 하는이 예제 [는 목록의의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 웹 사이트 목록을 다운로드 하 고 각각의 콘텐츠 길이 표시 합니다.  
  
> [!NOTE]
>  예제를 실행 하려면.NET Framework 4.5와 Visual Studio 2012 이상이 있어야 하거나 나중에 컴퓨터에 설치 합니다.  
  
## <a name="downloading-the-example"></a>예제 다운로드  
 전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046) 다음이 단계를 수행 하 고 있습니다.  
  
1.  다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  에 **프로젝트 열기** 대화 상자에서 압축을 해제 하는 샘플 코드를 보유 하는 폴더를 연 다음 AsyncFineTuningVB에 대 한 솔루션 (.sln) 파일을 엽니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고는 **CancelAfterTime** 프로젝트를 선택한 다음 **시작 프로젝트로 설정**합니다.  
  
5.  프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
     디버깅 하지 않고 프로젝트를 실행 하려면 Ctrl + f&5;를 선택 합니다.  
  
6.  프로그램을 여러 번 실행 확인 출력 모든 웹 사이트, 웹, 또는 일부 웹 사이트에 대 한 출력을 표시할 수 있습니다.  
  
 프로젝트를 다운로드 하지 않으려는 경우에이 항목의 끝에 MainWindow.xaml.vb 파일을 검토할 수 있습니다.  
  
## <a name="building-the-example"></a>예제 빌드  
 개발 하는 프로젝트에 추가 하는이 항목의 예제 [는 목록의의 작업 (Visual Basic) 또는 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) 작업 목록 취소 합니다. 하지만 예제에서는 동일한 UI를 사용 여 **취소** 단추 명시적으로 사용 되지 않습니다.  
  
 예제를 빌드하려면 "예제 다운로드" 섹션의 지침에 따라 사용자가 직접 단계별로 하지만를 선택할 **CancelAListOfTasks** 으로 **시작 프로젝트**합니다. 이 항목의 변경 내용이 해당 프로젝트에 추가 합니다.  
  
 작업 취소 됨으로 표시 되는 최대 시간을 지정 하려면 호출을 추가 하면 `CancelAfter` 를 `startButton_Click`다음 예제와 같이 합니다. 추가 별표로 표시 됩니다.  
  
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
  
 프로그램을 여러 번 실행 확인 출력 모든 웹 사이트, 웹, 또는 일부 웹 사이트에 대 한 출력을 표시할 수 있습니다. 다음과 같은 출력 샘플입니다.  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
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
  
## <a name="see-also"></a>참고 항목  
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기 작업 또는 작업 (Visual Basic) 목록이 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)   
 [Async (Visual Basic) 응용 프로그램을 미세 조정](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)
