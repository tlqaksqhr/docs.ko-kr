---
title: '연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(C#)'
ms.date: 07/20/2015
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
ms.openlocfilehash: bc334261dbea7759d1bb571cc61a5f00f84531a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="786d2-102">연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(C#)</span><span class="sxs-lookup"><span data-stu-id="786d2-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="786d2-103">이 연습에서는 텍스트 파일에서 단어를 검색하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="786d2-104">세부 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="786d2-105"><xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 호출할 수 있는 메서드를 사용하여 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="786d2-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="786d2-106"><xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 발생하는 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="786d2-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="786d2-107">메서드를 실행할 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 시작</span><span class="sxs-lookup"><span data-stu-id="786d2-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="786d2-108"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 중지하는 `Cancel` 단추 구현</span><span class="sxs-lookup"><span data-stu-id="786d2-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="786d2-109">사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="786d2-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="786d2-110">새 C# Windows Forms 응용 프로그램 프로젝트를 열고 `Form1`이라는 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="786d2-111">두 개의 단추와 네 개의 텍스트 상자를 `Form1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="786d2-112">다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="786d2-113">개체</span><span class="sxs-lookup"><span data-stu-id="786d2-113">Object</span></span>|<span data-ttu-id="786d2-114">속성</span><span class="sxs-lookup"><span data-stu-id="786d2-114">Property</span></span>|<span data-ttu-id="786d2-115">설정</span><span class="sxs-lookup"><span data-stu-id="786d2-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="786d2-116">첫 번째 단추</span><span class="sxs-lookup"><span data-stu-id="786d2-116">First button</span></span>|<span data-ttu-id="786d2-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-117">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-118">시작, 시작</span><span class="sxs-lookup"><span data-stu-id="786d2-118">Start, Start</span></span>|  
    |<span data-ttu-id="786d2-119">두 번째 단추</span><span class="sxs-lookup"><span data-stu-id="786d2-119">Second button</span></span>|<span data-ttu-id="786d2-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-120">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-121">취소, 취소</span><span class="sxs-lookup"><span data-stu-id="786d2-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="786d2-122">첫 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="786d2-122">First text box</span></span>|<span data-ttu-id="786d2-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-123">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="786d2-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="786d2-125">두 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="786d2-125">Second text box</span></span>|<span data-ttu-id="786d2-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-126">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="786d2-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="786d2-128">세 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="786d2-128">Third text box</span></span>|<span data-ttu-id="786d2-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-129">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="786d2-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="786d2-131">네 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="786d2-131">Fourth text box</span></span>|<span data-ttu-id="786d2-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="786d2-132">`Name`, `Text`</span></span>|<span data-ttu-id="786d2-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="786d2-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="786d2-134">각 텍스트 상자 옆에 레이블을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-134">Add a label next to each text box.</span></span> <span data-ttu-id="786d2-135">다음 표와 같이 각 레이블에 대해 `Text` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="786d2-136">Object</span><span class="sxs-lookup"><span data-stu-id="786d2-136">Object</span></span>|<span data-ttu-id="786d2-137">속성</span><span class="sxs-lookup"><span data-stu-id="786d2-137">Property</span></span>|<span data-ttu-id="786d2-138">설정</span><span class="sxs-lookup"><span data-stu-id="786d2-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="786d2-139">첫 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="786d2-139">First label</span></span>|`Text`|<span data-ttu-id="786d2-140">소스 파일</span><span class="sxs-lookup"><span data-stu-id="786d2-140">Source File</span></span>|  
    |<span data-ttu-id="786d2-141">두 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="786d2-141">Second label</span></span>|`Text`|<span data-ttu-id="786d2-142">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="786d2-142">Compare String</span></span>|  
    |<span data-ttu-id="786d2-143">세 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="786d2-143">Third label</span></span>|`Text`|<span data-ttu-id="786d2-144">일치하는 단어</span><span class="sxs-lookup"><span data-stu-id="786d2-144">Matching Words</span></span>|  
    |<span data-ttu-id="786d2-145">네 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="786d2-145">Fourth label</span></span>|`Text`|<span data-ttu-id="786d2-146">계산된 줄</span><span class="sxs-lookup"><span data-stu-id="786d2-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="786d2-147">BackgroundWorker 구성 요소를 작성하고 해당 이벤트에 가입하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="786d2-148">**도구 상자**의 **구성 요소** 섹션에 있는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 양식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="786d2-149">양식의 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="786d2-150">backgroundWorker1 개체에 대해 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="786d2-151">속성</span><span class="sxs-lookup"><span data-stu-id="786d2-151">Property</span></span>|<span data-ttu-id="786d2-152">설정</span><span class="sxs-lookup"><span data-stu-id="786d2-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="786d2-153">True</span><span class="sxs-lookup"><span data-stu-id="786d2-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="786d2-154">True</span><span class="sxs-lookup"><span data-stu-id="786d2-154">True</span></span>|  
  
3.  <span data-ttu-id="786d2-155">backgroundWorker1 개체의 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="786d2-156">**속성** 창에 위에서 **이벤트** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="786d2-157">`RunWorkerCompleted` 이벤트를 두 번 클릭하여 이벤트 처리기 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="786d2-158">`ProgressChanged` 및 `DoWork` 이벤트에 대해서도 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="786d2-159">별도 스레드에서 실행될 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="786d2-160">**프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="786d2-161">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="786d2-162">템플릿 창에서 **클래스**를 선택하고 이름 필드에 `Words.cs`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="786d2-163">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-163">Click **Add**.</span></span> <span data-ttu-id="786d2-164">`Words` 클래스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="786d2-165">`Words` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-165">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="786d2-166">스레드에서 이벤트를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="786d2-167">다음 이벤트 처리기를 기본 양식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-167">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="786d2-168">WordCount 메서드를 실행하는 새 스레드를 시작하고 호출하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="786d2-169">프로그램에 다음 프로시저를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-169">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="786d2-170">양식의 `Start` 단추에서 `StartThread` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="786d2-171">스레드를 중지하는 취소 단추를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="786d2-172">`Cancel` 단추에 대한 `Click` 이벤트 처리기에서 `StopThread` 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="786d2-173">테스트</span><span class="sxs-lookup"><span data-stu-id="786d2-173">Testing</span></span>  
 <span data-ttu-id="786d2-174">응용 프로그램을 테스트하여 올바르게 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="786d2-175">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-175">To test the application</span></span>  
  
1.  <span data-ttu-id="786d2-176">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="786d2-177">양식이 표시되면 테스트할 파일의 경로를 `sourceFile` 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="786d2-178">예를 들어 테스트 파일의 이름이 Test.txt라면 C:\Test.txt를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="786d2-179">두 번째 텍스트 상자에 응용 프로그램이 텍스트 파일에서 검색할 단어나 구를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="786d2-180">`Start` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-180">Click the `Start` button.</span></span> <span data-ttu-id="786d2-181">`LinesCounted` 단추에서 숫자가 즉시 증가하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="786d2-182">응용 프로그램이 완료되면 "계산 완료" 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="786d2-183">취소 단추를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="786d2-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="786d2-184">F5 키를 눌러 응용 프로그램을 시작하고 이전 절차에서 설명한 대로 파일 이름 및 검색 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="786d2-185">완료되기 전에 프로시저를 취소할 시간이 있을 정도로 선택한 파일이 큰지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="786d2-186">`Start` 단추를 클릭하여 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="786d2-187">`Cancel` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-187">Click the `Cancel` button.</span></span> <span data-ttu-id="786d2-188">응용 프로그램은 즉시 계산을 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="786d2-189">다음 단계</span><span class="sxs-lookup"><span data-stu-id="786d2-189">Next Steps</span></span>  
 <span data-ttu-id="786d2-190">이 응용 프로그램에는 몇 가지 기본적인 오류 처리 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-190">This application contains some basic error handling.</span></span> <span data-ttu-id="786d2-191">이 응용 프로그램은 빈 검색 문자열을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-191">It detects blank search strings.</span></span> <span data-ttu-id="786d2-192">계산할 수 있는 최대 단어 또는 줄 수 초과 등과 같은 기타 오류를 처리함으로써 이 프로그램을 더욱 강력하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d2-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786d2-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="786d2-193">See Also</span></span>  
 [<span data-ttu-id="786d2-194">스레딩(C#)</span><span class="sxs-lookup"><span data-stu-id="786d2-194">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="786d2-195">방법: 이벤트 구독 및 구독 취소</span><span class="sxs-lookup"><span data-stu-id="786d2-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
