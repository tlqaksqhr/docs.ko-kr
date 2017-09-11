---
title: "비동기 응용 프로그램 (Visual Basic)에서 재진입 처리 | Microsoft 문서"
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
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 8c35f0b393f38ea32f456a60ebd520065d16c6eb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="106a7-102">비동기 응용 프로그램 (Visual Basic)에서 재진입 처리</span><span class="sxs-lookup"><span data-stu-id="106a7-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>
<span data-ttu-id="106a7-103">앱에 비동기 코드를 포함하는 경우 완료되기 전에 비동기 작업을 다시 입력하는 것을 나타내는 재입력을 고려하고 방지할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="106a7-104">재입력 가능성을 식별하고 처리하지 못하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>  
  
 <span data-ttu-id="106a7-105">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="106a7-105">**In this topic**</span></span>  
  
-   [<span data-ttu-id="106a7-106">재진입 인식</span><span class="sxs-lookup"><span data-stu-id="106a7-106">Recognizing Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="106a7-107">재진입 처리</span><span class="sxs-lookup"><span data-stu-id="106a7-107">Handling Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="106a7-108">시작 단추를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="106a7-108">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="106a7-109">취소 하 고 작업을 다시 시작</span><span class="sxs-lookup"><span data-stu-id="106a7-109">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="106a7-110">여러 작업을 실행 하 고 출력 큐</span><span class="sxs-lookup"><span data-stu-id="106a7-110">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="106a7-111">검토 및 예제 응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="106a7-111">Reviewing and Running the Example App</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
> [!NOTE]
>  <span data-ttu-id="106a7-112">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-112">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="106a7-113"><a name="BKMK_RecognizingReentrancy"></a>재진입 인식</span><span class="sxs-lookup"><span data-stu-id="106a7-113"><a name="BKMK_RecognizingReentrancy"></a> Recognizing Reentrancy</span></span>  
 <span data-ttu-id="106a7-114">이 항목의 예제에서는 사용자가 선택 된 **시작** 일련의 웹 사이트를 다운로드 하 고 다운로드 하는 바이트의 총 수를 계산 하는 비동기 응용 프로그램을 시작 하려면 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-114">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="106a7-115">예제의 동기 버전은 처음 실행 후 앱 실행이 완료될 때까지 UI 스레드에서 해당 이벤트를 무시하므로 사용자가 단추를 선택하는 횟수에 관계없이 동일한 방식으로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-115">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="106a7-116">그러나 비동기 앱에서 UI 스레드는 계속 응답하므로 완료되기 전에 비동기 작업을 다시 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-116">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>  
  
 <span data-ttu-id="106a7-117">다음 예제에서는 예상 되는 사용자가 선택 하는 경우 출력은 **시작** 단추를 두 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-117">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="106a7-118">다운로드된 웹 사이트 목록이 각 사이트의 크기(바이트)와 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-118">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="106a7-119">총 바이트 수는 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-119">The total number of bytes appears at the end.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="106a7-120">그러나 사용자가 단추를 두 번 이상 선택하면 이벤트 처리기가 반복적으로 호출되고 다운로드 프로세스가 매번 다시 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-120">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="106a7-121">따라서 여러 개의 비동기 작업이 동시에 실행되고 출력에서 결과를 인터리브하며 총 바이트 수가 혼동됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-121">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/en-us/library/jj155761.aspx                29019  
7. msdn.microsoft.com                                            42972  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
7. msdn.microsoft.com                                            42972  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="106a7-122">이 항목의 끝으로 스크롤하면 이 출력을 생성하는 코드를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-122">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="106a7-123">로컬 컴퓨터에 솔루션을 다운로드 하 고 다음 WebsiteDownload 프로젝트를 실행 하 여 코드를 시험해 하거나 자세한 내용 및 지침에 대 한 고유한 프로젝트를 만들려면이 항목의 끝에 코드를 사용, 참조 수 [검토 및 예제 응용 프로그램을 실행](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-123">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span>  
  
##  <span data-ttu-id="106a7-124"><a name="BKMK_HandlingReentrancy"></a>재진입 처리</span><span class="sxs-lookup"><span data-stu-id="106a7-124"><a name="BKMK_HandlingReentrancy"></a> Handling Reentrancy</span></span>  
 <span data-ttu-id="106a7-125">앱에서 수행하려는 작업에 따라 다양한 방법으로 재진입을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-125">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="106a7-126">이 항목에서는 다음 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-126">This topic presents the following examples:</span></span>  
  
-   [<span data-ttu-id="106a7-127">시작 단추를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="106a7-127">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="106a7-128">사용 하지 않도록 설정 된 **시작** 사용자가 중단 하지 않도록 작업이 실행 되는 동안 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-128">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>  
  
-   [<span data-ttu-id="106a7-129">취소 하 고 작업을 다시 시작</span><span class="sxs-lookup"><span data-stu-id="106a7-129">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="106a7-130">사용자가 여전히 실행 되 고 모든 작업이 취소 된 **시작** 단추를 다시 선택한 다음 let 가장 최근 요청 된 작업을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-130">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>  
  
-   [<span data-ttu-id="106a7-131">여러 작업을 실행 하 고 출력 큐</span><span class="sxs-lookup"><span data-stu-id="106a7-131">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="106a7-132">요청한 모든 작업이 비동기적으로 실행되도록 허용하지만 각 작업의 결과가 함께 순서대로 나타나도록 출력의 표시를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-132">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>  
  
###  <span data-ttu-id="106a7-133"><a name="BKMK_DisableTheStartButton"></a>시작 단추를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="106a7-133"><a name="BKMK_DisableTheStartButton"></a> Disable the Start Button</span></span>  
 <span data-ttu-id="106a7-134">차단할 수는 **시작** 맨 위에 있는 단추를 비활성화 하 여 작업이 실행 되는 동안 단추는 `StartButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-134">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="106a7-135">그런 다음 작업이 완료되면 `Finally` 블록 내에서 단추를 다시 사용하도록 설정하여 사용자가 앱을 다시 실행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-135">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>  
  
 <span data-ttu-id="106a7-136">다음 코드에서는 이러한 변경 내용을 보여 주며, 별표로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-136">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="106a7-137">변경 내용을이 항목의 끝에 코드를 추가 하거나에서 완성된 된 응용 프로그램을 다운로드할 수 있습니다 [Async 샘플:.NET 데스크톱 응용 프로그램에서 재진입](http://go.microsoft.com/fwlink/?LinkId=266571)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-137">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="106a7-138">프로젝트 이름은 DisableStartButton입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-138">The project name is DisableStartButton.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' This line is commented out to make the results clearer in the output.  
    'ResultsTextBox.Text = ""  
  
    ' ***Disable the Start button until the downloads are complete.   
    StartButton.IsEnabled = False  
  
    Try  
        Await AccessTheWebAsync()  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    ' ***Enable the Start button in case you want to run the program again.   
    Finally  
        StartButton.IsEnabled = True  
  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="106a7-139">변경의 결과로 `AccessTheWebAsync`에서 웹 사이트를 다운로드하는 동안 단추가 응답하지 않으므로 프로세스를 다시 입력할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-139">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>  
  
###  <span data-ttu-id="106a7-140"><a name="BKMK_CancelAndRestart"></a>취소 하 고 작업을 다시 시작</span><span class="sxs-lookup"><span data-stu-id="106a7-140"><a name="BKMK_CancelAndRestart"></a> Cancel and Restart the Operation</span></span>  
 <span data-ttu-id="106a7-141">사용 하지 않도록 설정 하는 대신는 **시작** 단추를 단추는 활성 상태로 유지 하지만 수, 사용자가 단추를 다시 선택 하는 경우 이미 실행 하 고 가장 최근에 시작한 작업을 계속 할 작업을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-141">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>  
  
 <span data-ttu-id="106a7-142">취소에 대 한 자세한 내용은 참조 [미세 조정 Your 비동기 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-142">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="106a7-143">이 시나리오를 설정 하려면 다음과 같이 변경에 제공 되는 기본 코드가 [검토 및 예제 응용 프로그램을 실행](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-143">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span> <span data-ttu-id="106a7-144">완성된 된 응용 프로그램에서 다운로드할 수 [Async 샘플:.NET 데스크톱 응용 프로그램에서 재진입](http://go.microsoft.com/fwlink/?LinkId=266571)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-144">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="106a7-145">이 프로젝트의 이름은 CancelAndRestart입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-145">The name of this project is CancelAndRestart.</span></span>  
  
1.  <span data-ttu-id="106a7-146">선언는 <xref:System.Threading.CancellationTokenSource>변수인 `cts`, 모든 메서드에 대 한 범위에는.</xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="106a7-146">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>  
  
    ```vb  
    Class MainWindow // Or Class MainPage  
  
        ' *** Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="106a7-147">`StartButton_Click`에서 작업이 이미 진행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-147">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="106a7-148">하는 경우의 값 `cts` 는 `Nothing`, 작업이 이미 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-148">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="106a7-149">값이 없으면 `Nothing`, 이미 실행 중인 작업이 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-149">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>  
  
    ```vb  
    ' *** If a download process is already underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
    ```  
  
3.  <span data-ttu-id="106a7-150">`cts`를 현재 프로세스를 나타내는 다른 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-150">Set `cts` to a different value that represents the current process.</span></span>  
  
    ```vb  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
    ```  
  
4.  <span data-ttu-id="106a7-151">끝에 `StartButton_Click`, 현재 프로세스가 완료 되의 값을 설정 하므로 `cts` 다시 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-151">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>  
  
    ```vb  
    ' *** When the process completes, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
    ```  
  
 <span data-ttu-id="106a7-152">다음 코드에서는 `StartButton_Click`의 모든 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-152">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="106a7-153">추가된 내용은 별표로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-153">The additions are marked with asterisks.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' This line is commented out to make the results clearer.   
    'ResultsTextBox.Text = ""  
  
    ' *** If a download process is underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
  
    Try  
        ' *** Send a token to carry the message if the operation is canceled.  
        Await AccessTheWebAsync(cts.Token)  
  
    Catch ex As OperationCanceledException  
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    End Try  
  
    ' *** When the process is complete, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
End Sub  
```  
  
 <span data-ttu-id="106a7-154">`AccessTheWebAsync`에서 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-154">In `AccessTheWebAsync`, make the following changes.</span></span>  
  
-   <span data-ttu-id="106a7-155">`StartButton_Click`에서 취소 토큰을 허용하도록 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-155">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>  
  
-   <span data-ttu-id="106a7-156">사용 된 <xref:System.Net.Http.HttpClient.GetAsync%2A>때문에 웹 사이트를 다운로드 하려면 `GetAsync` 허용는 <xref:System.Threading.CancellationToken>인수.</xref:System.Threading.CancellationToken> </xref:System.Net.Http.HttpClient.GetAsync%2A></span><span class="sxs-lookup"><span data-stu-id="106a7-156">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>  
  
-   <span data-ttu-id="106a7-157">`DisplayResults`를 호출하여 다운로드한 각 웹 사이트에 대한 결과를 표시하려면 먼저 `ct`를 확인하여 현재 작업이 취소되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-157">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>  
  
 <span data-ttu-id="106a7-158">다음 코드에서는 이러한 변경 내용을 보여 주며, 별표로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-158">The following code shows these changes, which are marked with asterisks.</span></span>  
  
```vb  
' *** Provide a parameter for the CancellationToken from StartButton_Click.  
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
    ' Declare an HttpClient object.  
    Dim client = New HttpClient()  
  
    ' Make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    Dim total = 0  
    Dim position = 0  
  
    For Each url In urlList  
        ' *** Use the HttpClient.GetAsync method because it accepts a   
        ' cancellation token.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' *** Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' *** Check for cancellations before displaying information about the   
        ' latest site.   
        ct.ThrowIfCancellationRequested()  
  
        position += 1  
        DisplayResults(url, urlContents, position)  
  
        ' Update the total.  
        total += urlContents.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
```  
  
 <span data-ttu-id="106a7-159">선택 하는 경우는 **시작** 단추를 몇 번이이 앱이 실행 되는 동안 다음과 같은 출력을 유사한 결과 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-159">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               122505  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 <span data-ttu-id="106a7-160">부분 목록을 제거하려면 `StartButton_Click`에서 코드 첫 줄의 주석 처리를 제거하여 사용자가 작업을 다시 시작할 때마다 텍스트 상자의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-160">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>  
  
###  <span data-ttu-id="106a7-161"><a name="BKMK_RunMultipleOperations"></a>여러 작업을 실행 하 고 출력 큐</span><span class="sxs-lookup"><span data-stu-id="106a7-161"><a name="BKMK_RunMultipleOperations"></a> Run Multiple Operations and Queue the Output</span></span>  
 <span data-ttu-id="106a7-162">이 세 번째 예제는 앱이 시작 될 때마다 사용자가 선택 하는 다른 비동기 작업에는 가장 복잡 한는 **시작** 단추 및 모든 작업 실행을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-162">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="106a7-163">요청한 모든 작업은 목록에서 비동기적으로 웹 사이트를 다운로드하지만 작업의 출력은 순차적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-163">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="106a7-164">즉, 실제 다운로드 활동 인터리브되지에서 출력으로 [재진입 인식](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) 표시 되지만 각 그룹에 대 한 결과 목록은 개별적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-164">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) shows, but the list of results for each group is presented separately.</span></span>  
  
 <span data-ttu-id="106a7-165">작업 공유 전역 <xref:System.Threading.Tasks.Task>, `pendingWork`, 디스플레이 프로세스에 대 한 게이트 키퍼도 작동 합니다.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="106a7-165">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>  
  
 <span data-ttu-id="106a7-166">변경 내용을 코드에 붙여넣어이 예제를 실행할 수 있습니다 [응용 프로그램 작성](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), 지침에 따르면 또는 [응용 프로그램 다운로드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) 샘플을 다운로드 하 고 다음 QueueResults 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-166">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample and then run the QueueResults project.</span></span>  
  
 <span data-ttu-id="106a7-167">다음과 같은 출력 결과 표시 하는 경우 사용자가 선택 된 **시작** 단추를 두 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-167">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="106a7-168">결과에서 처음으로 문자, 레이블 및 A 나타냅니다는 **시작** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-168">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="106a7-169">숫자는 다운로드 대상 목록에서 URL의 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-169">The numbers show the order of the URLs in the list of download targets.</span></span>  
  
```  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               209858  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
A-7. msdn.microsoft.com                                            53266  
A-8. msdn.microsoft.com/library/ff730837.aspx               148020  
  
TOTAL bytes returned:  918876  
  
#Group A is complete.  
```  
  
 <span data-ttu-id="106a7-170">사용자가 선택 된 **시작** 단추를 세 번, 다음 줄을 유사한 출력을 생성 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-170">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="106a7-171">파운드 기호(#)로 시작하는 정보 줄은 응용 프로그램의 진행률을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-171">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>  
  
```  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71259  
A-6. msdn.microsoft.com/library/ms404677.aspx               199185  
  
#Starting group B.  
#Task assigned for group B.  
  
A-7. msdn.microsoft.com                                            53266  
  
#Starting group C.  
#Task assigned for group C.  
  
A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916095  
  
B-1. msdn.microsoft.com/library/hh191443.aspx                87389  
B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
  
#Group A is complete.  
  
B-7. msdn.microsoft.com                                            53266  
B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916097  
  
C-1. msdn.microsoft.com/library/hh191443.aspx                87389  
C-2. msdn.microsoft.com/library/aa578028.aspx               207089  
  
#Group B is complete.  
  
C-3. msdn.microsoft.com/library/jj155761.aspx                30870  
C-4. msdn.microsoft.com/library/hh290140.aspx               119027  
C-5. msdn.microsoft.com/library/hh524395.aspx                72765  
C-6. msdn.microsoft.com/library/ms404677.aspx               199186  
C-7. msdn.microsoft.com                                            56190  
C-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  920526  
  
#Group C is complete.  
```  
  
 <span data-ttu-id="106a7-172">그룹 B와 C는 그룹 A가 완료되기 전에 시작되지만 각 그룹에 대한 출력은 별도로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-172">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="106a7-173">그룹 A에 대 한 모든 출력 그룹 B에 대 한 모든 출력 한 다음 모든 출력&3;. 그룹에 대 한 다음, 첫 번째로 표시 앱 항상 순서에 그룹을 표시 하며, 각 그룹에 대해 항상 표시는 개별 웹 사이트에 대 한 정보 Url은 Url의 목록에 표시 되는 순서 대로.</span><span class="sxs-lookup"><span data-stu-id="106a7-173">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>  
  
 <span data-ttu-id="106a7-174">그러나 다운로드가 실제로 수행되는 순서는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-174">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="106a7-175">여러 그룹이 시작된 후에는 그룹이 생성하는 다운로드 작업이 모두 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-175">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="106a7-176">A-1이 B-1보다 먼저 다운로드된다고 가정할 수 없으며 A-1이 A-2보다 먼저 다운로드된다고 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-176">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>  
  
#### <a name="global-definitions"></a><span data-ttu-id="106a7-177">전역 정의</span><span class="sxs-lookup"><span data-stu-id="106a7-177">Global Definitions</span></span>  
 <span data-ttu-id="106a7-178">샘플 코드는 모든 메서드에서 표시되는 다음과 같은 두 가지 전역 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-178">The sample code contains the following two global declarations that are visible from all methods.</span></span>  
  
```vb  
Class MainWindow    ' Class MainPage in Windows Store app.  
  
    ' ***Declare the following variables where all methods can access them.   
    Private pendingWork As Task = Nothing  
    Private group As Char = ChrW(AscW("A") - 1)  
```  
  
 <span data-ttu-id="106a7-179">`Task` 변수 `pendingWork`는 표시 프로세스를 감독하고 모든 그룹이 다른 그룹의 표시 작업을 방해하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-179">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="106a7-180">문자 변수 `group`은 다른 그룹의 출력에 레이블을 지정하여 해당 결과가 예상 순서대로 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-180">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>  
  
#### <a name="the-click-event-handler"></a><span data-ttu-id="106a7-181">Click 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="106a7-181">The Click Event Handler</span></span>  
 <span data-ttu-id="106a7-182">이벤트 처리기 `StartButton_Click`, 그룹 문자를 선택할 때마다 증가 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-182">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="106a7-183">그런 다음 처리기에서 `AccessTheWebAsync`를 호출하여 다운로드 중인 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-183">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' ***Verify that each group's results are displayed together, and that  
    ' the groups display in order, by marking each group with a letter.  
    group = ChrW(AscW(group) + 1)  
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)  
  
    Try  
        ' *** Pass the group value to AccessTheWebAsync.  
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)  
  
        ' The following line verifies a successful return from the download and   
        ' display procedures.   
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
    End Try  
End Sub  
```  
  
#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="106a7-184">AccessTheWebAsync 메서드</span><span class="sxs-lookup"><span data-stu-id="106a7-184">The AccessTheWebAsync Method</span></span>  
 <span data-ttu-id="106a7-185">이 예제에서는 `AccessTheWebAsync`를 두 개의 메서드로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-185">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="106a7-186">첫 번째 메서드 `AccessTheWebAsync`는 그룹에 대해 모든 다운로드 작업을 시작하고 `pendingWork`를 설정하여 표시 프로세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-186">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="106a7-187">언어 통합 쿼리 (LINQ 쿼리)를 사용 하는 메서드 및 <xref:System.Linq.Enumerable.ToArray%2A>를 동시에 모든 다운로드 작업을 시작 합니다.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="106a7-187">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>  
  
 <span data-ttu-id="106a7-188">그런 다음 `AccessTheWebAsync`는 `FinishOneGroupAsync`를 호출하여 각 다운로드가 완료될 때까지 대기하고 해당 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-188">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>  
  
 <span data-ttu-id="106a7-189">`FinishOneGroupAsync`는 `AccessTheWebAsync`의 `pendingWork`에 할당되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-189">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="106a7-190">해당 값은 작업이 완료되기 전에 다른 작업에 의한 중단을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-190">That value prevents interruption by another operation before the task is complete.</span></span>  
  
```vb  
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)  
  
    Dim client = New HttpClient()  
  
    ' Make a list of the web addresses to download.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.  
    Dim getContentTasks As Task(Of Byte())() =  
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()  
  
    ' ***Call the method that awaits the downloads and displays the results.  
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.  
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)  
  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)  
  
    ' ***This task is complete when a group has finished downloading and displaying.  
    Await pendingWork  
  
    ' You can do other work here or just return.  
    Return grp  
End Function  
```  
  
#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="106a7-191">FinishOneGroupAsync 메서드</span><span class="sxs-lookup"><span data-stu-id="106a7-191">The FinishOneGroupAsync Method</span></span>  
 <span data-ttu-id="106a7-192">이 메서드는 한 그룹의 다운로드 작업을 순환하여 각 작업을 대기하고 다운로드한 웹 사이트의 길이를 표시하고 길이를 합계에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-192">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>  
  
 <span data-ttu-id="106a7-193">첫 번째 문에 `FinishOneGroupAsync` 사용 하 여 `pendingWork` 되도록 하는 이미 디스플레이 프로세스 중이거나 이미 대기 되는 작업을 방해 하지 메서드를 입력 하십시오.</span><span class="sxs-lookup"><span data-stu-id="106a7-193">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="106a7-194">이러한 작업이 진행 중인 경우 입력 작업은 해당 순서를 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-194">If such an operation is in progress, the entering operation must wait its turn.</span></span>  
  
```vb  
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task  
  
    ' Wait for the previous group to finish displaying results.  
    If pendingWork IsNot Nothing Then  
        Await pendingWork  
    End If  
  
    Dim total = 0  
  
    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.  
    For i As Integer = 0 To contentTasks.Length - 1  
        ' Await the download of a particular URL, and then display the URL and  
        ' its length.  
        Dim content As Byte() = Await contentTasks(i)  
        DisplayResults(urls(i), content, i, grp)  
        total += content.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
```  
  
 <span data-ttu-id="106a7-195">변경 내용을 코드에 붙여넣어이 예제를 실행할 수 있습니다 [응용 프로그램 작성](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), 지침에 따르면 또는 [응용 프로그램 다운로드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) 샘플을 다운로드 하 고 다음 QueueResults 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-195">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample, and then run the QueueResults project.</span></span>  
  
#### <a name="points-of-interest"></a><span data-ttu-id="106a7-196">관심 영역</span><span class="sxs-lookup"><span data-stu-id="106a7-196">Points of Interest</span></span>  
 <span data-ttu-id="106a7-197">출력에서 파운드 기호(#)로 시작하는 정보 줄은 이 예제의 작동 방식을 명확히 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-197">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>  
  
 <span data-ttu-id="106a7-198">출력은 다음과 같은 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-198">The output shows the following patterns.</span></span>  
  
-   <span data-ttu-id="106a7-199">이전 그룹이 출력을 표시하는 동안 그룹이 시작될 수 있지만 이전 그룹의 출력 표시가 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-199">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>  
  
    ```  
    #Starting group A.  
    #Task assigned for group A. Download tasks are active.  
  
    A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
    A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
    A-4. msdn.microsoft.com/library/hh290140.aspx               119037  
    A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
  
    A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    A-7. msdn.microsoft.com                                            53078  
    A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915919  
  
    B-1. msdn.microsoft.com/library/hh191443.aspx                87388  
    B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
  
    #Group A is complete.  
  
    B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
    B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
    B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    B-7. msdn.microsoft.com                                            53078  
    B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915908  
    ```  
  
-   <span data-ttu-id="106a7-200">`pendingWork` 작업은 `Nothing` 의 시작 부분에 `FinishOneGroupAsync` 그룹 A에 대해서만 먼저 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-200">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="106a7-201">그룹 A는 `FinishOneGroupAsync`에 도달할 때 await 식을 아직 완료하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-201">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="106a7-202">따라서 컨트롤이 `AccessTheWebAsync`로 반환되지 않았으며 `pendingWork`에 대한 첫 번째 할당이 발생되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-202">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>  
  
-   <span data-ttu-id="106a7-203">다음 두 줄은 항상 출력에 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-203">The following two lines always appear together in the output.</span></span> <span data-ttu-id="106a7-204">코드는 `StartButton_Click`의 그룹 작업 시작과 `pendingWork`에 그룹에 대한 작업 할당 사이에서 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-204">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>  
  
    ```  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
    ```  
  
     <span data-ttu-id="106a7-205">그룹이 `StartButton_Click`을 입력한 후 작업은 `FinishOneGroupAsync`를 입력한 다음에야 await 식을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-205">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="106a7-206">따라서 코드의 해당 세그먼트 중에는 다른 작업에서 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-206">Therefore, no other operation can gain control during that segment of code.</span></span>  
  
##  <span data-ttu-id="106a7-207"><a name="BKMD_SettingUpTheExample"></a>검토 및 예제 응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="106a7-207"><a name="BKMD_SettingUpTheExample"></a> Reviewing and Running the Example App</span></span>  
 <span data-ttu-id="106a7-208">예제 앱을 더 잘 이해하려면 다운로드하거나, 직접 빌드하거나, 앱을 구현하지 않고 이 항목의 끝에 있는 코드를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-208">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="106a7-209">Windows Presentation Foundation (WPF) 데스크톱 응용 프로그램으로는 예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-209">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <span data-ttu-id="106a7-210"><a name="BKMK_DownloadingTheApp"></a>응용 프로그램 다운로드</span><span class="sxs-lookup"><span data-stu-id="106a7-210"><a name="BKMK_DownloadingTheApp"></a> Downloading the App</span></span>  
  
1.  <span data-ttu-id="106a7-211">압축 된 파일을 다운로드할 [Async 샘플:.NET 데스크톱 응용 프로그램에서 재진입](http://go.microsoft.com/fwlink/?LinkId=266571)합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-211">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span>  
  
2.  <span data-ttu-id="106a7-212">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-212">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
3.  <span data-ttu-id="106a7-213">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-213">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="106a7-214">압축을 푼 샘플 코드가 저장된 폴더로 이동한 다음 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-214">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>  
  
5.  <span data-ttu-id="106a7-215">**솔루션 탐색기**를 실행 하 고 다음을 선택 하려는 프로젝트에 대 한 바로 가기 메뉴를 열고 **StartUpProject으로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-215">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>  
  
6.  <span data-ttu-id="106a7-216">CTRL+F5를 선택하여 프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-216">Choose the CTRL+F5 keys to build and run the project.</span></span>  
  
###  <span data-ttu-id="106a7-217"><a name="BKMK_BuildingTheApp"></a>응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="106a7-217"><a name="BKMK_BuildingTheApp"></a> Building the App</span></span>  
 <span data-ttu-id="106a7-218">다음 섹션으로 WPF 응용 프로그램 예제를 빌드하려면 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-218">The following section provides the code to build the example as a WPF app.</span></span>  
  
##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="106a7-219">WPF 응용 프로그램을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="106a7-219">To build a WPF app</span></span>  
  
1.  <span data-ttu-id="106a7-220">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-220">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="106a7-221">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-221">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="106a7-222">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-222">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="106a7-223">에 **설치 된 템플릿** 창 확장 **Visual Basic**를 차례로 확장 한 다음 **Windows**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-223">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>  
  
4.  <span data-ttu-id="106a7-224">프로젝트 형식 목록에서 선택 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-224">In the list of project types, choose **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="106a7-225">프로젝트 이름을 `WebsiteDownloadWPF`를 선택한 다음는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-225">Name the project `WebsiteDownloadWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="106a7-226">새 프로젝트가 표시 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-226">The new project appears in **Solution Explorer**.</span></span>  
  
6.  <span data-ttu-id="106a7-227">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-227">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="106a7-228">탭이 표시 되지 않으면 mainwindow.xaml의 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-228">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
7.  <span data-ttu-id="106a7-229">에 **XAML** MainWindow.xaml의 보기에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-229">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:local="using:WebsiteDownloadWPF"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        mc:Ignorable="d">  
  
        <Grid Width="517" Height="360">  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="106a7-230">에 텍스트 상자와 단추가 포함 된 간단한 창이 표시는 **디자인** MainWindow.xaml의 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-230">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
8.  <span data-ttu-id="106a7-231"><xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-231">Add a reference for <xref:System.Net.Http>.</span></span>  
  
9. <span data-ttu-id="106a7-232">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-232">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
10. <span data-ttu-id="106a7-233">MainWindow.xaml.vb에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-233">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add the following Imports statements, and add a reference for System.Net.Http.  
    Imports System.Net.Http  
    Imports System.Threading  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
            ' This line is commented out to make the results clearer in the output.  
            'ResultsTextBox.Text = ""  
  
            Try  
                Await AccessTheWebAsync()  
  
            Catch ex As Exception  
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
            End Try  
        End Sub  
  
        Private Async Function AccessTheWebAsync() As Task  
  
            ' Declare an HttpClient object.  
            Dim client = New HttpClient()  
  
            ' Make a list of web addresses.  
            Dim urlList As List(Of String) = SetUpURLList()  
  
            Dim total = 0  
            Dim position = 0  
  
            For Each url In urlList  
                ' GetByteArrayAsync returns a task. At completion, the task  
                ' produces a byte array.  
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
                position += 1  
                DisplayResults(url, urlContents, position)  
  
                ' Update the total.  
                total += urlContents.Length  
            Next  
  
            ' Display the total count for all of the websites.  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
        End Function  
  
        Private Function SetUpURLList() As List(Of String)  
            Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/hh191443.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/jj155761.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/hh524395.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
            Return urls  
        End Function  
  
        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)  
            ' Display the length of each website. The string format is designed  
            ' to be used with a monospaced font, such as Lucida Console or  
            ' Global Monospace.  
  
            ' Strip off the "http:'".  
            Dim displayURL = url.Replace("http://", "")  
            ' Display position in the URL list, the URL, and the number of bytes.  
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)  
        End Sub  
    End Class  
    ```  
  
11. <span data-ttu-id="106a7-234">프로그램을 실행 한 다음 CTRL + F5 키를 선택 된 **시작** 단추를 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-234">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>  
  
12. <span data-ttu-id="106a7-235">변경 [시작 단추를 사용 하지 않도록 설정](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [취소 하 고 작업을 다시 시작](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), 또는 [여러 작업을 실행 하 고 출력 큐](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) 는 재진입 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="106a7-235">Make the changes from [Disable the Start Button](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Cancel and Restart the Operation](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or [Run Multiple Operations and Queue the Output](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to handle the reentrancy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106a7-236">참고 항목</span><span class="sxs-lookup"><span data-stu-id="106a7-236">See Also</span></span>  
 <span data-ttu-id="106a7-237">[연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="106a7-237">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="106a7-238"> [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)</span><span class="sxs-lookup"><span data-stu-id="106a7-238"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)</span></span>

