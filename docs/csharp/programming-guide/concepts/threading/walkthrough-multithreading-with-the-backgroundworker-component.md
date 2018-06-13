---
title: '연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(C#)'
ms.date: 07/20/2015
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
ms.openlocfilehash: bc334261dbea7759d1bb571cc61a5f00f84531a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339370"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a>연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(C#)
이 연습에서는 텍스트 파일에서 단어를 검색하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다. 세부 항목은 다음과 같습니다.  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 호출할 수 있는 메서드를 사용하여 클래스 정의  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 발생하는 이벤트 처리  
  
-   메서드를 실행할 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 시작  
  
-   <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 중지하는 `Cancel` 단추 구현  
  
### <a name="to-create-the-user-interface"></a>사용자 인터페이스를 만들려면  
  
1.  새 C# Windows Forms 응용 프로그램 프로젝트를 열고 `Form1`이라는 양식을 만듭니다.  
  
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
  
2.  backgroundWorker1 개체에 대해 다음 속성을 설정합니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
3.  backgroundWorker1 개체의 이벤트를 구독합니다. **속성** 창에 위에서 **이벤트** 아이콘을 클릭합니다. `RunWorkerCompleted` 이벤트를 두 번 클릭하여 이벤트 처리기 메서드를 만듭니다. `ProgressChanged` 및 `DoWork` 이벤트에 대해서도 같은 작업을 수행합니다.  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>별도 스레드에서 실행될 메서드를 정의하려면  
  
1.  **프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 클래스를 추가합니다. **새 항목 추가** 대화 상자가 표시됩니다.  
  
2.  템플릿 창에서 **클래스**를 선택하고 이름 필드에 `Words.cs`를 입력합니다.  
  
3.  **추가**를 클릭합니다. `Words` 클래스가 표시됩니다.  
  
4.  `Words` 클래스에 다음 코드를 추가합니다.  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>스레드에서 이벤트를 처리하려면  
  
-   다음 이벤트 처리기를 기본 양식에 추가합니다.  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>WordCount 메서드를 실행하는 새 스레드를 시작하고 호출하려면  
  
1.  프로그램에 다음 프로시저를 추가합니다.  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  양식의 `Start` 단추에서 `StartThread` 메서드를 호출합니다.  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>스레드를 중지하는 취소 단추를 구현하려면  
  
    -   `Cancel` 단추에 대한 `Click` 이벤트 처리기에서 `StopThread` 프로시저를 호출합니다.  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
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
 [스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [방법: 이벤트 구독 및 구독 취소](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
