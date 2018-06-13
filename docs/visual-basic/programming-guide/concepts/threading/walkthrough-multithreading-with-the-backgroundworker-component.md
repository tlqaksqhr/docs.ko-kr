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
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="9e7f7-102">연습: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="9e7f7-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="9e7f7-103">이 연습에서는 텍스트 파일에서 단어를 검색하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="9e7f7-104">세부 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="9e7f7-105"><xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 호출할 수 있는 메서드를 사용하여 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="9e7f7-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="9e7f7-106"><xref:System.ComponentModel.BackgroundWorker> 구성 요소에서 발생하는 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="9e7f7-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="9e7f7-107">메서드를 실행할 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 시작</span><span class="sxs-lookup"><span data-stu-id="9e7f7-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="9e7f7-108"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 중지하는 `Cancel` 단추 구현</span><span class="sxs-lookup"><span data-stu-id="9e7f7-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="9e7f7-109">사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="9e7f7-110">새 Visual Basic Windows Forms 응용 프로그램 프로젝트를 열고 라는 양식을 만드는 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="9e7f7-111">두 개의 단추와 네 개의 텍스트 상자를 `Form1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="9e7f7-112">다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="9e7f7-113">개체</span><span class="sxs-lookup"><span data-stu-id="9e7f7-113">Object</span></span>|<span data-ttu-id="9e7f7-114">속성</span><span class="sxs-lookup"><span data-stu-id="9e7f7-114">Property</span></span>|<span data-ttu-id="9e7f7-115">설정</span><span class="sxs-lookup"><span data-stu-id="9e7f7-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="9e7f7-116">첫 번째 단추</span><span class="sxs-lookup"><span data-stu-id="9e7f7-116">First button</span></span>|<span data-ttu-id="9e7f7-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-117">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-118">시작, 시작</span><span class="sxs-lookup"><span data-stu-id="9e7f7-118">Start, Start</span></span>|  
    |<span data-ttu-id="9e7f7-119">두 번째 단추</span><span class="sxs-lookup"><span data-stu-id="9e7f7-119">Second button</span></span>|<span data-ttu-id="9e7f7-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-120">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-121">취소, 취소</span><span class="sxs-lookup"><span data-stu-id="9e7f7-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="9e7f7-122">첫 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="9e7f7-122">First text box</span></span>|<span data-ttu-id="9e7f7-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-123">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="9e7f7-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="9e7f7-125">두 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="9e7f7-125">Second text box</span></span>|<span data-ttu-id="9e7f7-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-126">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="9e7f7-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="9e7f7-128">세 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="9e7f7-128">Third text box</span></span>|<span data-ttu-id="9e7f7-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-129">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="9e7f7-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="9e7f7-131">네 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="9e7f7-131">Fourth text box</span></span>|<span data-ttu-id="9e7f7-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="9e7f7-132">`Name`, `Text`</span></span>|<span data-ttu-id="9e7f7-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="9e7f7-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="9e7f7-134">각 텍스트 상자 옆에 레이블을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-134">Add a label next to each text box.</span></span> <span data-ttu-id="9e7f7-135">다음 표와 같이 각 레이블에 대해 `Text` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="9e7f7-136">Object</span><span class="sxs-lookup"><span data-stu-id="9e7f7-136">Object</span></span>|<span data-ttu-id="9e7f7-137">속성</span><span class="sxs-lookup"><span data-stu-id="9e7f7-137">Property</span></span>|<span data-ttu-id="9e7f7-138">설정</span><span class="sxs-lookup"><span data-stu-id="9e7f7-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="9e7f7-139">첫 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="9e7f7-139">First label</span></span>|`Text`|<span data-ttu-id="9e7f7-140">소스 파일</span><span class="sxs-lookup"><span data-stu-id="9e7f7-140">Source File</span></span>|  
    |<span data-ttu-id="9e7f7-141">두 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="9e7f7-141">Second label</span></span>|`Text`|<span data-ttu-id="9e7f7-142">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="9e7f7-142">Compare String</span></span>|  
    |<span data-ttu-id="9e7f7-143">세 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="9e7f7-143">Third label</span></span>|`Text`|<span data-ttu-id="9e7f7-144">일치하는 단어</span><span class="sxs-lookup"><span data-stu-id="9e7f7-144">Matching Words</span></span>|  
    |<span data-ttu-id="9e7f7-145">네 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="9e7f7-145">Fourth label</span></span>|`Text`|<span data-ttu-id="9e7f7-146">계산된 줄</span><span class="sxs-lookup"><span data-stu-id="9e7f7-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="9e7f7-147">BackgroundWorker 구성 요소를 작성하고 해당 이벤트에 가입하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="9e7f7-148">**도구 상자**의 **구성 요소** 섹션에 있는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 양식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="9e7f7-149">양식의 구성 요소 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="9e7f7-150">BackgroundWorker1 개체에 대 한 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="9e7f7-151">속성</span><span class="sxs-lookup"><span data-stu-id="9e7f7-151">Property</span></span>|<span data-ttu-id="9e7f7-152">설정</span><span class="sxs-lookup"><span data-stu-id="9e7f7-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="9e7f7-153">True</span><span class="sxs-lookup"><span data-stu-id="9e7f7-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="9e7f7-154">True</span><span class="sxs-lookup"><span data-stu-id="9e7f7-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="9e7f7-155">별도 스레드에서 실행될 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="9e7f7-156">**프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="9e7f7-157">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="9e7f7-158">템플릿 창에서 **클래스**를 선택하고 이름 필드에 `Words.vb`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="9e7f7-159">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-159">Click **Add**.</span></span> <span data-ttu-id="9e7f7-160">`Words` 클래스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="9e7f7-161">`Words` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="9e7f7-162">스레드에서 이벤트를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="9e7f7-163">다음 이벤트 처리기를 기본 양식에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="9e7f7-164">WordCount 메서드를 실행하는 새 스레드를 시작하고 호출하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="9e7f7-165">프로그램에 다음 프로시저를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="9e7f7-166">양식의 `Start` 단추에서 `StartThread` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="9e7f7-167">스레드를 중지하는 취소 단추를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="9e7f7-168">`Cancel` 단추에 대한 `Click` 이벤트 처리기에서 `StopThread` 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="9e7f7-169">테스트</span><span class="sxs-lookup"><span data-stu-id="9e7f7-169">Testing</span></span>  
 <span data-ttu-id="9e7f7-170">응용 프로그램을 테스트하여 올바르게 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="9e7f7-171">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-171">To test the application</span></span>  
  
1.  <span data-ttu-id="9e7f7-172">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="9e7f7-173">양식이 표시되면 테스트할 파일의 경로를 `sourceFile` 상자에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="9e7f7-174">예를 들어 테스트 파일의 이름이 Test.txt라면 C:\Test.txt를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="9e7f7-175">두 번째 텍스트 상자에 응용 프로그램이 텍스트 파일에서 검색할 단어나 구를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="9e7f7-176">`Start` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-176">Click the `Start` button.</span></span> <span data-ttu-id="9e7f7-177">`LinesCounted` 단추에서 숫자가 즉시 증가하기 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="9e7f7-178">응용 프로그램이 완료되면 "계산 완료" 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="9e7f7-179">취소 단추를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="9e7f7-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="9e7f7-180">F5 키를 눌러 응용 프로그램을 시작하고 이전 절차에서 설명한 대로 파일 이름 및 검색 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="9e7f7-181">완료되기 전에 프로시저를 취소할 시간이 있을 정도로 선택한 파일이 큰지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="9e7f7-182">`Start` 단추를 클릭하여 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="9e7f7-183">`Cancel` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-183">Click the `Cancel` button.</span></span> <span data-ttu-id="9e7f7-184">응용 프로그램은 즉시 계산을 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e7f7-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e7f7-185">Next Steps</span></span>  
 <span data-ttu-id="9e7f7-186">이 응용 프로그램에는 몇 가지 기본적인 오류 처리 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-186">This application contains some basic error handling.</span></span> <span data-ttu-id="9e7f7-187">이 응용 프로그램은 빈 검색 문자열을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-187">It detects blank search strings.</span></span> <span data-ttu-id="9e7f7-188">계산할 수 있는 최대 단어 또는 줄 수 초과 등과 같은 기타 오류를 처리함으로써 이 프로그램을 더욱 강력하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e7f7-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7f7-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e7f7-189">See Also</span></span>  
 [<span data-ttu-id="9e7f7-190">스레딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e7f7-190">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="9e7f7-191">연습: Visual Basic로 간단한 다중 스레드 구성 요소 작성</span><span class="sxs-lookup"><span data-stu-id="9e7f7-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="9e7f7-192">방법: 이벤트 구독 및 구독 취소</span><span class="sxs-lookup"><span data-stu-id="9e7f7-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
