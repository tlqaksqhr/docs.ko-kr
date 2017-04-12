---
title: "BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩 | Microsoft 문서"
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
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
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
ms.openlocfilehash: 3686eb230349876f6cfffd2ad94ed1f547779ab1
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>연습: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩
이 연습에서는 텍스트 파일에서 특정 단어 검색 하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다. 내용은 다음과 같습니다.  
  
-   클래스에서 호출할 수 있는 메서드로 정의 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker>  
  
-   에 의해 발생 하는 이벤트를 처리는 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker>  
  
-   시작 하는 <xref:System.ComponentModel.BackgroundWorker>구성 요소가 메서드를 실행 합니다.</xref:System.ComponentModel.BackgroundWorker>  
  
-   구현 된 `Cancel` 중지 단추는 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker>  
  
### <a name="to-create-the-user-interface"></a>사용자 인터페이스를 만들려면  
  
1.  새 Visual Basic Windows Forms 응용 프로그램 프로젝트를 열고 라는 폼을 만들 `Form1`합니다.  
  
2.  두 개의 단추와 텍스트 상자에&4; 개의 추가 `Form1`합니다.  
  
3.  다음 표에 나와 있는 것 처럼 개체 이름을 지정 합니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |첫 번째 단추|`Name`, `Text`|시작, 시작|  
    |두 번째 단추|`Name`, `Text`|취소, 취소|  
    |첫 번째 텍스트 상자|`Name`, `Text`|SourceFile, ""|  
    |두 번째 텍스트 상자|`Name`, `Text`|CompareString, ""|  
    |세 번째 텍스트 상자|`Name`, `Text`|"0" WordsCounted|  
    |네 번째 텍스트 상자|`Name`, `Text`|"0" LinesCounted|  
  
4.  각 텍스트 상자 옆에 레이블을 추가 합니다. 설정의 `Text` 다음 표와에서 같이 각 레이블에 대 한 속성입니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |첫 번째 레이블|`Text`|소스 파일|  
    |두 번째 레이블|`Text`|문자열 비교|  
    |세 번째 레이블|`Text`|일치 하는 단어|  
    |네 번째 레이블|`Text`|계산 된 줄|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>BackgroundWorker 구성 요소를 작성 하 고 해당 이벤트에 가입 하려면  
  
1.  추가 <xref:System.ComponentModel.BackgroundWorker>구성 요소에서 **구성 요소** 의 섹션은 **도구 상자** 폼에.</xref:System.ComponentModel.BackgroundWorker> 폼의 구성 요소 트레이에 표시 됩니다.  
  
2.  BackgroundWorker1 개체에 대 한 다음 속성을 설정 합니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>별도 스레드에서 실행 될 메서드를 정의 하려면  
  
1.  **프로젝트** 메뉴에서 선택 **클래스 추가** 를 프로젝트에 클래스를 추가 합니다. **새 항목 추가** 대화 상자가 표시 됩니다.  
  
2.  선택 **클래스** 템플릿 창에서 입력 하 고 `Words.vb` 이름 필드에 있습니다.  
  
3.  **추가**를 클릭합니다. `Words` 클래스가 표시 됩니다.  
  
4.  `Words` 클래스에 다음 코드를 추가합니다.  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>스레드에서 이벤트를 처리 하기  
  
-   기본 폼에 다음 이벤트 처리기를 추가 합니다.  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>시작 하 고 WordCount 메서드를 실행 하는 새 스레드를 호출 합니다.  
  
1.  프로그램에 다음 프로시저를 추가 합니다.  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  호출 된 `StartThread` 메서드에서 `Start` 폼에 단추:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>취소 단추를 구현 하 고 스레드를 중지 하는  
  
-   호출의 `StopThread` 에서 프로시저는 `Click` 에 대 한 이벤트 처리기는 `Cancel` 단추입니다.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>테스트  
 이제 올바르게 작동 하는지 확인 하도록 응용 프로그램을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  테스트 하려는 파일에 대 한 파일 경로 입력 폼이 표시 하는 경우는 `sourceFile` 상자입니다. 예를 들어 테스트 파일 Test.txt 라는 가정 하 고, C:\Test.txt를 입력 합니다.  
  
3.  두 번째 텍스트 상자에 단어나 구를 검색할 텍스트 파일에서 응용 프로그램을 입력 합니다.  
  
4.  `Start` 단추를 클릭합니다. `LinesCounted` 단추 증가 하는 즉시 시작 해야 합니다. 응용 프로그램이 완료 되 면 "완료 계산" 하는 메시지를 표시 합니다.  
  
#### <a name="to-test-the-cancel-button"></a>취소 단추를 테스트 하려면  
  
1.  F5 키를 눌러 응용 프로그램을 시작 하 고 이전 절차에서 설명한 대로 파일 이름 및 검색 단어를 입력 합니다. 파일을 선택한 완료 되기 전에 절차를 취소 하는 시간을 할 수 있도록 충분히 큰 인지 확인 합니다.  
  
2.  클릭 된 `Start` 단추는 응용 프로그램을 시작 합니다.  
  
3.  `Cancel` 단추를 클릭합니다. 응용 프로그램은 즉시 계산 중지 해야 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램에는 기본적인 오류 처리 기능이 포함 되어 있습니다. 빈 검색 문자열을 검색합니다. 단어 또는 계산 될 수 있는 줄의 최대 수를 초과 하는 등의 다른 오류를 처리 하 여이 프로그램을 더욱 강력한 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [연습: Visual Basic로 간단한 다중 스레드 구성 요소 제작](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)   
 [방법: 이벤트 구독 및 구독 취소](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
