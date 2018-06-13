---
title: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654293"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>연습: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩
이 연습에서는 텍스트 파일에서 단어를 검색하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다. 세부 항목은 다음과 같습니다.  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 호출할 수 있는 메서드를 사용하여 클래스 정의  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 발생하는 이벤트 처리  
  
-   메서드를 실행할 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 시작  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 중지하는 `Cancel` 단추 구현  
  
### <a name="to-create-the-user-interface"></a>사용자 인터페이스를 만들려면  
  
1.  새 Visual Basic Windows Forms 응용 프로그램 프로젝트를 열고 라는 양식을 만드는 `Form1`합니다.  
  
2.  두 개의 단추와 네 개의 텍스트 상자를 `Form1`에 추가합니다.  
  
3.  다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |첫 번째 단추|`Name`, `Text`|시작, 시작|  
    |두 번째 단추|`Name`, `Text`|취소, 취소|  
    |첫 번째 텍스트 상자|`Name`, `Text`|SourceFile, ""|  
    |두 번째 텍스트 상자|`Name`, `Text`|CompareString, ""|  
    |세 번째 텍스트 상자|`Name`, `Text`|WordsCounted, "0"|  
    |네 번째 텍스트 상자|`Name`, `Text`|LinesCounted, "0"|  
  
4.  각 텍스트 상자 옆에 레이블을 추가합니다. 다음 표와 같이 각 레이블에 대해 `Text` 속성을 설정합니다.  
  
    |Object|속성|설정|  
    |------------|--------------|-------------|  
    |첫 번째 레이블|`Text`|소스 파일|  
    |두 번째 레이블|`Text`|문자열 비교|  
    |세 번째 레이블|`Text`|일치하는 단어|  
    |네 번째 레이블|`Text`|계산된 줄|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>BackgroundWorker 구성 요소를 작성하고 해당 이벤트에 가입하려면  
  
1.  **도구 상자**의 **구성 요소** 섹션에 있는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 양식에 추가합니다. 양식의 구성 요소 트레이에 나타납니다.  
  
2.  BackgroundWorker1 개체에 대 한 다음 속성을 설정 합니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>별도 스레드에서 실행될 메서드를 정의하려면  
  
1.  **프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 클래스를 추가합니다. **새 항목 추가** 대화 상자가 표시됩니다.  
  
2.  템플릿 창에서 **클래스**를 선택하고 이름 필드에 `Words.vb`를 입력합니다.  
  
3.  **추가**를 클릭합니다. `Words` 클래스가 표시됩니다.  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>스레드에서 이벤트를 처리하려면  
  
-   다음 이벤트 처리기를 기본 양식에 추가합니다.  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>WordCount 메서드를 실행하는 새 스레드를 시작하고 호출하려면  
  
1.  프로그램에 다음 프로시저를 추가합니다.  
  
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
  
2.  양식의 `Start` 단추에서 `StartThread` 메서드를 호출합니다.  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>스레드를 중지하는 취소 단추를 구현하려면  
  
-   `Cancel` 단추에 대한 `Click` 이벤트 처리기에서 `StopThread` 프로시저를 호출합니다.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>테스트  
 응용 프로그램을 테스트하여 올바르게 작동하는지 확인할 수 있습니다.  
  
#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  양식이 표시되면 테스트할 파일의 경로를 `sourceFile` 상자에 입력합니다. 예를 들어 테스트 파일의 이름이 Test.txt라면 C:\Test.txt를 입력합니다.  
  
3.  두 번째 텍스트 상자에 응용 프로그램이 텍스트 파일에서 검색할 단어나 구를 입력합니다.  
  
4.  `Start` 단추를 클릭합니다. `LinesCounted` 단추에서 숫자가 즉시 증가하기 시작해야 합니다. 응용 프로그램이 완료되면 "계산 완료" 메시지가 표시됩니다.  
  
#### <a name="to-test-the-cancel-button"></a>취소 단추를 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 시작하고 이전 절차에서 설명한 대로 파일 이름 및 검색 단어를 입력합니다. 완료되기 전에 프로시저를 취소할 시간이 있을 정도로 선택한 파일이 큰지 확인합니다.  
  
2.  `Start` 단추를 클릭하여 응용 프로그램을 시작합니다.  
  
3.  `Cancel` 단추를 클릭합니다. 응용 프로그램은 즉시 계산을 중지해야 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램에는 몇 가지 기본적인 오류 처리 기능이 포함되어 있습니다. 이 응용 프로그램은 빈 검색 문자열을 검색합니다. 계산할 수 있는 최대 단어 또는 줄 수 초과 등과 같은 기타 오류를 처리함으로써 이 프로그램을 더욱 강력하게 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [연습: Visual Basic로 간단한 다중 스레드 구성 요소 작성](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [방법: 이벤트 구독 및 구독 취소](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
