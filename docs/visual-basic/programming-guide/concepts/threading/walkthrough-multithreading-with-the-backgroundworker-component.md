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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d0711c8e417ae5c95b0e109504b69882015241
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="98e41-102">연습: BackgroundWorker 구성 요소 (Visual Basic)를 사용한 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="98e41-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="98e41-103">이 연습에서는 텍스트 파일에서 특정 단어 검색 하는 다중 스레드 Windows Forms 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="98e41-104">내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="98e41-105">클래스에서 호출할 수 있는 메서드로 정의 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="98e41-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="98e41-106">에 의해 발생 하는 이벤트를 처리는 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="98e41-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="98e41-107">시작 하는 <xref:System.ComponentModel.BackgroundWorker>구성 요소가 메서드를 실행 합니다.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="98e41-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="98e41-108">구현 된 `Cancel` 중지 단추는 <xref:System.ComponentModel.BackgroundWorker>구성 요소.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="98e41-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="98e41-109">사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="98e41-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="98e41-110">새 Visual Basic Windows Forms 응용 프로그램 프로젝트를 열고 라는 폼을 만들 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="98e41-111">두 개의 단추와 텍스트 상자에&4; 개의 추가 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="98e41-112">다음 표에 나와 있는 것 처럼 개체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="98e41-113">개체</span><span class="sxs-lookup"><span data-stu-id="98e41-113">Object</span></span>|<span data-ttu-id="98e41-114">속성</span><span class="sxs-lookup"><span data-stu-id="98e41-114">Property</span></span>|<span data-ttu-id="98e41-115">설정</span><span class="sxs-lookup"><span data-stu-id="98e41-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="98e41-116">첫 번째 단추</span><span class="sxs-lookup"><span data-stu-id="98e41-116">First button</span></span>|<span data-ttu-id="98e41-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-117">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-118">시작, 시작</span><span class="sxs-lookup"><span data-stu-id="98e41-118">Start, Start</span></span>|  
    |<span data-ttu-id="98e41-119">두 번째 단추</span><span class="sxs-lookup"><span data-stu-id="98e41-119">Second button</span></span>|<span data-ttu-id="98e41-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-120">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-121">취소, 취소</span><span class="sxs-lookup"><span data-stu-id="98e41-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="98e41-122">첫 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="98e41-122">First text box</span></span>|<span data-ttu-id="98e41-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-123">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="98e41-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="98e41-125">두 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="98e41-125">Second text box</span></span>|<span data-ttu-id="98e41-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-126">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="98e41-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="98e41-128">세 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="98e41-128">Third text box</span></span>|<span data-ttu-id="98e41-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-129">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-130">"0" WordsCounted</span><span class="sxs-lookup"><span data-stu-id="98e41-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="98e41-131">네 번째 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="98e41-131">Fourth text box</span></span>|<span data-ttu-id="98e41-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="98e41-132">`Name`, `Text`</span></span>|<span data-ttu-id="98e41-133">"0" LinesCounted</span><span class="sxs-lookup"><span data-stu-id="98e41-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="98e41-134">각 텍스트 상자 옆에 레이블을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-134">Add a label next to each text box.</span></span> <span data-ttu-id="98e41-135">설정의 `Text` 다음 표와에서 같이 각 레이블에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="98e41-136">개체</span><span class="sxs-lookup"><span data-stu-id="98e41-136">Object</span></span>|<span data-ttu-id="98e41-137">속성</span><span class="sxs-lookup"><span data-stu-id="98e41-137">Property</span></span>|<span data-ttu-id="98e41-138">설정</span><span class="sxs-lookup"><span data-stu-id="98e41-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="98e41-139">첫 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="98e41-139">First label</span></span>|`Text`|<span data-ttu-id="98e41-140">소스 파일</span><span class="sxs-lookup"><span data-stu-id="98e41-140">Source File</span></span>|  
    |<span data-ttu-id="98e41-141">두 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="98e41-141">Second label</span></span>|`Text`|<span data-ttu-id="98e41-142">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="98e41-142">Compare String</span></span>|  
    |<span data-ttu-id="98e41-143">세 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="98e41-143">Third label</span></span>|`Text`|<span data-ttu-id="98e41-144">일치 하는 단어</span><span class="sxs-lookup"><span data-stu-id="98e41-144">Matching Words</span></span>|  
    |<span data-ttu-id="98e41-145">네 번째 레이블</span><span class="sxs-lookup"><span data-stu-id="98e41-145">Fourth label</span></span>|`Text`|<span data-ttu-id="98e41-146">계산 된 줄</span><span class="sxs-lookup"><span data-stu-id="98e41-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="98e41-147">BackgroundWorker 구성 요소를 작성 하 고 해당 이벤트에 가입 하려면</span><span class="sxs-lookup"><span data-stu-id="98e41-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="98e41-148">추가 <xref:System.ComponentModel.BackgroundWorker>구성 요소에서 **구성 요소** 의 섹션은 **도구 상자** 폼에.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="98e41-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="98e41-149">폼의 구성 요소 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="98e41-150">BackgroundWorker1 개체에 대 한 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="98e41-151">속성</span><span class="sxs-lookup"><span data-stu-id="98e41-151">Property</span></span>|<span data-ttu-id="98e41-152">설정</span><span class="sxs-lookup"><span data-stu-id="98e41-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="98e41-153">True</span><span class="sxs-lookup"><span data-stu-id="98e41-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="98e41-154">True</span><span class="sxs-lookup"><span data-stu-id="98e41-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="98e41-155">별도 스레드에서 실행 될 메서드를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="98e41-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="98e41-156">**프로젝트** 메뉴에서 선택 **클래스 추가** 를 프로젝트에 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="98e41-157">**새 항목 추가** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="98e41-158">선택 **클래스** 템플릿 창에서 입력 하 고 `Words.vb` 이름 필드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="98e41-159">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-159">Click **Add**.</span></span> <span data-ttu-id="98e41-160">`Words` 클래스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="98e41-161">`Words` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="98e41-162">스레드에서 이벤트를 처리 하기</span><span class="sxs-lookup"><span data-stu-id="98e41-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="98e41-163">기본 폼에 다음 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="98e41-164">시작 하 고 WordCount 메서드를 실행 하는 새 스레드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="98e41-165">프로그램에 다음 프로시저를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="98e41-166">호출 된 `StartThread` 메서드에서 `Start` 폼에 단추:</span><span class="sxs-lookup"><span data-stu-id="98e41-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="98e41-167">취소 단추를 구현 하 고 스레드를 중지 하는</span><span class="sxs-lookup"><span data-stu-id="98e41-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="98e41-168">호출의 `StopThread` 에서 프로시저는 `Click` 에 대 한 이벤트 처리기는 `Cancel` 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="98e41-169">테스트</span><span class="sxs-lookup"><span data-stu-id="98e41-169">Testing</span></span>  
 <span data-ttu-id="98e41-170">이제 올바르게 작동 하는지 확인 하도록 응용 프로그램을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="98e41-171">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="98e41-171">To test the application</span></span>  
  
1.  <span data-ttu-id="98e41-172">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="98e41-173">테스트 하려는 파일에 대 한 파일 경로 입력 폼이 표시 하는 경우는 `sourceFile` 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="98e41-174">예를 들어 테스트 파일 Test.txt 라는 가정 하 고, C:\Test.txt를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="98e41-175">두 번째 텍스트 상자에 단어나 구를 검색할 텍스트 파일에서 응용 프로그램을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="98e41-176">`Start` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-176">Click the `Start` button.</span></span> <span data-ttu-id="98e41-177">`LinesCounted` 단추 증가 하는 즉시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="98e41-178">응용 프로그램이 완료 되 면 "완료 계산" 하는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="98e41-179">취소 단추를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="98e41-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="98e41-180">F5 키를 눌러 응용 프로그램을 시작 하 고 이전 절차에서 설명한 대로 파일 이름 및 검색 단어를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="98e41-181">파일을 선택한 완료 되기 전에 절차를 취소 하는 시간을 할 수 있도록 충분히 큰 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="98e41-182">클릭 된 `Start` 단추는 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="98e41-183">`Cancel` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-183">Click the `Cancel` button.</span></span> <span data-ttu-id="98e41-184">응용 프로그램은 즉시 계산 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="98e41-185">다음 단계</span><span class="sxs-lookup"><span data-stu-id="98e41-185">Next Steps</span></span>  
 <span data-ttu-id="98e41-186">이 응용 프로그램에는 기본적인 오류 처리 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-186">This application contains some basic error handling.</span></span> <span data-ttu-id="98e41-187">빈 검색 문자열을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-187">It detects blank search strings.</span></span> <span data-ttu-id="98e41-188">단어 또는 계산 될 수 있는 줄의 최대 수를 초과 하는 등의 다른 오류를 처리 하 여이 프로그램을 더욱 강력한 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98e41-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e41-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98e41-189">See Also</span></span>  
 <span data-ttu-id="98e41-190">[스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="98e41-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="98e41-191"> [연습: Visual Basic로 간단한 다중 스레드 구성 요소 제작](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span><span class="sxs-lookup"><span data-stu-id="98e41-191"> [Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span></span>  
<span data-ttu-id="98e41-192"> [방법: 이벤트 구독 및 구독 취소](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="98e41-192"> [How to: Subscribe to and Unsubscribe from Events](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span></span>
