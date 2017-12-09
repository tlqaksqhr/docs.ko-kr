---
title: "비동기 앱에서 재입력 처리(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a917f88d3d6105f836dc67ef8a9ec92efc300d7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="handling-reentrancy-in-async-apps-c"></a><span data-ttu-id="0a2bb-102">비동기 앱에서 재입력 처리(C#)</span><span class="sxs-lookup"><span data-stu-id="0a2bb-102">Handling Reentrancy in Async Apps (C#)</span></span>
<span data-ttu-id="0a2bb-103">앱에 비동기 코드를 포함하는 경우 완료되기 전에 비동기 작업을 다시 입력하는 것을 나타내는 재입력을 고려하고 방지할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="0a2bb-104">재입력 가능성을 식별하고 처리하지 못하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>  
  
 <span data-ttu-id="0a2bb-105">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="0a2bb-105">**In this topic**</span></span>  
  
-   [<span data-ttu-id="0a2bb-106">재입력 인식</span><span class="sxs-lookup"><span data-stu-id="0a2bb-106">Recognizing Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="0a2bb-107">재입력 처리</span><span class="sxs-lookup"><span data-stu-id="0a2bb-107">Handling Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="0a2bb-108">시작 단추 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a2bb-108">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="0a2bb-109">작업 취소 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="0a2bb-109">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="0a2bb-110">여러 작업을 실행하고 출력을 큐 대기</span><span class="sxs-lookup"><span data-stu-id="0a2bb-110">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="0a2bb-111">예제 앱 검토 및 실행</span><span class="sxs-lookup"><span data-stu-id="0a2bb-111">Reviewing and Running the Example App</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
> [!NOTE]
>  <span data-ttu-id="0a2bb-112">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-112">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="0a2bb-113">재입력 인식</span><span class="sxs-lookup"><span data-stu-id="0a2bb-113">Recognizing Reentrancy</span></span>  
 <span data-ttu-id="0a2bb-114">이 항목의 예제에서는 사용자가 **시작** 단추를 선택하여 일련의 웹 사이트를 다운로드하고 다운로드되는 총 바이트 수를 계산하는 비동기 앱을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-114">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="0a2bb-115">예제의 동기 버전은 처음 실행 후 앱 실행이 완료될 때까지 UI 스레드에서 해당 이벤트를 무시하므로 사용자가 단추를 선택하는 횟수에 관계없이 동일한 방식으로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-115">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="0a2bb-116">그러나 비동기 앱에서 UI 스레드는 계속 응답하므로 완료되기 전에 비동기 작업을 다시 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-116">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>  
  
 <span data-ttu-id="0a2bb-117">다음 예제에서는 사용자가 **시작** 단추를 한 번만 선택하는 경우 예상되는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-117">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="0a2bb-118">다운로드된 웹 사이트 목록이 각 사이트의 크기(바이트)와 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-118">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="0a2bb-119">총 바이트 수는 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-119">The total number of bytes appears at the end.</span></span>  
  
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
  
 <span data-ttu-id="0a2bb-120">그러나 사용자가 단추를 두 번 이상 선택하면 이벤트 처리기가 반복적으로 호출되고 다운로드 프로세스가 매번 다시 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-120">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="0a2bb-121">따라서 여러 개의 비동기 작업이 동시에 실행되고 출력에서 결과를 인터리브하며 총 바이트 수가 혼동됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-121">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>  
  
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
  
 <span data-ttu-id="0a2bb-122">이 항목의 끝으로 스크롤하면 이 출력을 생성하는 코드를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-122">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="0a2bb-123">로컬 컴퓨터에 솔루션을 다운로드한 다음 WebsiteDownload 프로젝트를 실행하거나 이 항목의 끝에 있는 코드를 사용하여 고유한 프로젝트를 만들면 코드를 테스트할 수 있습니다. 자세한 내용 및 지침은 [예제 앱 검토 및 실행](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-123">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span>  
  
##  <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="0a2bb-124">재입력 처리</span><span class="sxs-lookup"><span data-stu-id="0a2bb-124">Handling Reentrancy</span></span>  
 <span data-ttu-id="0a2bb-125">앱에서 수행하려는 작업에 따라 다양한 방법으로 재진입을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-125">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="0a2bb-126">이 항목에서는 다음 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-126">This topic presents the following examples:</span></span>  
  
-   [<span data-ttu-id="0a2bb-127">시작 단추 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a2bb-127">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="0a2bb-128">작업이 실행되는 동안 **시작** 단추를 사용할 수 없도록 설정하여 사용자가 작업을 중단할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-128">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>  
  
-   [<span data-ttu-id="0a2bb-129">작업 취소 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="0a2bb-129">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="0a2bb-130">사용자가 **시작** 단추를 다시 선택하는 경우 계속 실행되고 있는 작업을 취소한 다음 가장 최근에 요청한 작업이 계속되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-130">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>  
  
-   [<span data-ttu-id="0a2bb-131">여러 작업을 실행하고 출력을 큐 대기</span><span class="sxs-lookup"><span data-stu-id="0a2bb-131">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="0a2bb-132">요청한 모든 작업이 비동기적으로 실행되도록 허용하지만 각 작업의 결과가 함께 순서대로 나타나도록 출력의 표시를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-132">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>  
  
###  <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="0a2bb-133">시작 단추 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0a2bb-133">Disable the Start Button</span></span>  
 <span data-ttu-id="0a2bb-134">`StartButton_Click` 이벤트 처리기의 위쪽에 있는 단추를 사용하지 않도록 설정하여 작업이 실행되는 동안 **시작** 단추를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-134">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="0a2bb-135">그런 다음 작업이 완료되면 `finally` 블록 내에서 단추를 다시 사용하도록 설정하여 사용자가 앱을 다시 실행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-135">You can then reenable the button from within a  `finally` block when the operation finishes so that users can run the app again.</span></span>  
  
 <span data-ttu-id="0a2bb-136">다음 코드에서는 이러한 변경 내용을 보여 주며, 별표로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-136">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="0a2bb-137">변경 내용을 이 항목의 끝에 있는 코드에 추가하거나 완성된 앱을 [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571)(비동기 샘플: .NET 데스크톱 앱의 재입력)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-137">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="0a2bb-138">프로젝트 이름은 DisableStartButton입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-138">The project name is DisableStartButton.</span></span>  
  
```csharp  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // This line is commented out to make the results clearer in the output.  
    //ResultsTextBox.Text = "";  
  
    // ***Disable the Start button until the downloads are complete.   
    StartButton.IsEnabled = false;   
  
    try  
    {  
        await AccessTheWebAsync();  
    }  
    catch (Exception)  
    {  
        ResultsTextBox.Text += "\r\nDownloads failed.";  
    }  
    // ***Enable the Start button in case you want to run the program again.   
    finally  
    {  
        StartButton.IsEnabled = true;  
    }  
}  
```  
  
 <span data-ttu-id="0a2bb-139">변경의 결과로 `AccessTheWebAsync`에서 웹 사이트를 다운로드하는 동안 단추가 응답하지 않으므로 프로세스를 다시 입력할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-139">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>  
  
###  <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="0a2bb-140">작업 취소 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="0a2bb-140">Cancel and Restart the Operation</span></span>  
 <span data-ttu-id="0a2bb-141">**시작** 단추를 사용하지 않도록 설정하는 대신 단추를 활성 상태로 유지하지만 사용자가 해당 단추를 다시 선택하는 경우 이미 실행되고 있는 작업을 취소하고 가장 최근에 시작한 작업이 계속되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-141">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>  
  
 <span data-ttu-id="0a2bb-142">취소에 대한 자세한 내용은 [비동기 응용 프로그램 미세 조정(C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-142">For more information about cancellation, see [Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="0a2bb-143">이 시나리오를 설정하려면 [예제 앱 검토 및 실행](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)에서 제공하는 기본 코드를 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-143">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span> <span data-ttu-id="0a2bb-144">[Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571)(비동기 샘플: .NET 데스크톱 앱의 재입력)에서 완성된 앱을 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-144">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="0a2bb-145">이 프로젝트의 이름은 CancelAndRestart입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-145">The name of this project is CancelAndRestart.</span></span>  
  
1.  <span data-ttu-id="0a2bb-146">모든 메서드에 대한 범위 내에 있는 <xref:System.Threading.CancellationTokenSource> 변수 `cts`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-146">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>  
  
    ```csharp  
    public partial class MainWindow : Window   // Or class MainPage  
    {  
        // *** Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
    ```  
  
2.  <span data-ttu-id="0a2bb-147">`StartButton_Click`에서 작업이 이미 진행 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-147">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="0a2bb-148">`cts`의 값이 null인 경우 이미 활성화된 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-148">If the value of `cts` is null, no operation is already active.</span></span> <span data-ttu-id="0a2bb-149">값이 null이 아닌 경우 이미 실행되고 있는 작업이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-149">If the value isn't null, the operation that is already running is canceled.</span></span>  
  
    ```csharp  
    // *** If a download process is already underway, cancel it.  
    if (cts != null)  
    {  
        cts.Cancel();  
    }  
    ```  
  
3.  <span data-ttu-id="0a2bb-150">`cts`를 현재 프로세스를 나타내는 다른 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-150">Set `cts` to a different value that represents the current process.</span></span>  
  
    ```csharp  
    // *** Now set cts to a new value that you can use to cancel the current process  
    // if the button is chosen again.  
    CancellationTokenSource newCTS = new CancellationTokenSource();  
    cts = newCTS;  
    ```  
  
4.  <span data-ttu-id="0a2bb-151">`StartButton_Click`이 끝나면 현재 프로세스가 완료되어 `cts` 값이 다시 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-151">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to null.</span></span>  
  
    ```csharp  
    // *** When the process is complete, signal that another process can begin.  
    if (cts == newCTS)  
        cts = null;  
    ```  
  
 <span data-ttu-id="0a2bb-152">다음 코드에서는 `StartButton_Click`의 모든 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-152">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="0a2bb-153">추가된 내용은 별표로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-153">The additions are marked with asterisks.</span></span>  
  
```csharp  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // This line is commented out to make the results clearer in the output.  
    //ResultsTextBox.Clear();  
  
    // *** If a download process is already underway, cancel it.  
    if (cts != null)  
    {  
        cts.Cancel();  
    }  
  
    // *** Now set cts to cancel the current process if the button is chosen again.  
    CancellationTokenSource newCTS = new CancellationTokenSource();  
    cts = newCTS;  
  
    try  
    {  
        // ***Send cts.Token to carry the message if there is a cancellation request.  
        await AccessTheWebAsync(cts.Token);  
  
    }  
    // *** Catch cancellations separately.  
    catch (OperationCanceledException)  
    {  
        ResultsTextBox.Text += "\r\nDownloads canceled.\r\n";  
    }  
    catch (Exception)  
    {  
        ResultsTextBox.Text += "\r\nDownloads failed.\r\n";  
    }  
    // *** When the process is complete, signal that another process can proceed.  
    if (cts == newCTS)  
        cts = null;  
}  
```  
  
 <span data-ttu-id="0a2bb-154">`AccessTheWebAsync`에서 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-154">In `AccessTheWebAsync`, make the following changes.</span></span>  
  
-   <span data-ttu-id="0a2bb-155">`StartButton_Click`에서 취소 토큰을 허용하도록 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-155">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>  
  
-   <span data-ttu-id="0a2bb-156">`GetAsync`는 <xref:System.Threading.CancellationToken> 인수를 허용하므로 <xref:System.Net.Http.HttpClient.GetAsync%2A> 메서드를 사용하여 웹 사이트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-156">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>  
  
-   <span data-ttu-id="0a2bb-157">`DisplayResults`를 호출하여 다운로드한 각 웹 사이트에 대한 결과를 표시하려면 먼저 `ct`를 확인하여 현재 작업이 취소되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-157">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>  
  
 <span data-ttu-id="0a2bb-158">다음 코드에서는 이러한 변경 내용을 보여 주며, 별표로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-158">The following code shows these changes, which are marked with asterisks.</span></span>  
  
```csharp  
// *** Provide a parameter for the CancellationToken from StartButton_Click.  
async Task AccessTheWebAsync(CancellationToken ct)  
{  
    // Declare an HttpClient object.  
    HttpClient client = new HttpClient();  
  
    // Make a list of web addresses.  
    List<string> urlList = SetUpURLList();  
  
    var total = 0;  
    var position = 0;  
  
    foreach (var url in urlList)  
    {  
        // *** Use the HttpClient.GetAsync method because it accepts a   
        // cancellation token.  
        HttpResponseMessage response = await client.GetAsync(url, ct);  
  
        // *** Retrieve the website contents from the HttpResponseMessage.  
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
        // *** Check for cancellations before displaying information about the   
        // latest site.   
        ct.ThrowIfCancellationRequested();  
  
        DisplayResults(url, urlContents, ++position);  
  
        // Update the total.  
        total += urlContents.Length;  
    }  
  
    // Display the total count for all of the websites.  
    ResultsTextBox.Text +=  
        string.Format("\r\n\r\nTOTAL bytes returned:  {0}\r\n", total);  
}     
```  
  
 <span data-ttu-id="0a2bb-159">이 앱이 실행되는 동안 **시작** 단추를 여러 번 선택하면 다음 출력과 유사한 결과가 생성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-159">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>  
  
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
  
 <span data-ttu-id="0a2bb-160">부분 목록을 제거하려면 `StartButton_Click`에서 코드 첫 줄의 주석 처리를 제거하여 사용자가 작업을 다시 시작할 때마다 텍스트 상자의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-160">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>  
  
###  <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="0a2bb-161">여러 작업을 실행하고 출력을 큐 대기</span><span class="sxs-lookup"><span data-stu-id="0a2bb-161">Run Multiple Operations and Queue the Output</span></span>  
 <span data-ttu-id="0a2bb-162">이 세 번째 예제는 사용자가 **시작** 단추를 선택할 때마다 앱이 다른 비동기 작업을 시작하고 모든 작업이 실행되어 완료된다는 점에서 가장 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-162">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="0a2bb-163">요청한 모든 작업은 목록에서 비동기적으로 웹 사이트를 다운로드하지만 작업의 출력은 순차적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-163">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="0a2bb-164">즉, 실제 다운로드 작업은 [재입력 인식](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 출력에 표시된 대로 인터리브되지만 각 그룹에 대한 결과 목록은 별도로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-164">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) shows, but the list of results for each group is presented separately.</span></span>  
  
 <span data-ttu-id="0a2bb-165">작업은 표시 프로세스의 게이트키퍼 역할을 하는 전역 <xref:System.Threading.Tasks.Task>, `pendingWork`를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-165">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>  
  
 <span data-ttu-id="0a2bb-166">변경 내용을 [앱 빌드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 코드에 붙여 넣어 이 예제를 실행하거나, [앱 다운로드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 지침에 따라 샘플을 다운로드한 다음 QueueResults 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-166">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample and then run the QueueResults project.</span></span>  
  
 <span data-ttu-id="0a2bb-167">다음 출력은 사용자가 **시작** 단추를 한 번만 선택하는 경우의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-167">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="0a2bb-168">문제 레이블 A는 처음으로 **시작** 단추를 선택한 경우의 결과임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-168">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="0a2bb-169">숫자는 다운로드 대상 목록에서 URL의 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-169">The numbers show the order of the URLs in the list of download targets.</span></span>  
  
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
  
 <span data-ttu-id="0a2bb-170">사용자가 **시작** 단추를 세 번 선택하면 앱이 다음 줄과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-170">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="0a2bb-171">파운드 기호(#)로 시작하는 정보 줄은 응용 프로그램의 진행률을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-171">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>  
  
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
  
 <span data-ttu-id="0a2bb-172">그룹 B와 C는 그룹 A가 완료되기 전에 시작되지만 각 그룹에 대한 출력은 별도로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-172">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="0a2bb-173">그룹 A에 대한 모든 출력이 먼저 나타나고 그 뒤에 그룹 B에 대한 모든 출력과 그룹 C에 대한 모든 출력이 차례로 나타납니다. 앱은 항상 순서대로 그룹을 표시하고 각 그룹에 대해 URL이 URL 목록에 나타나는 순서대로 개별 웹 사이트에 대한 정보를 항상 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-173">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>  
  
 <span data-ttu-id="0a2bb-174">그러나 다운로드가 실제로 수행되는 순서는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-174">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="0a2bb-175">여러 그룹이 시작된 후에는 그룹이 생성하는 다운로드 작업이 모두 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-175">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="0a2bb-176">A-1이 B-1보다 먼저 다운로드된다고 가정할 수 없으며 A-1이 A-2보다 먼저 다운로드된다고 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-176">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>  
  
#### <a name="global-definitions"></a><span data-ttu-id="0a2bb-177">전역 정의</span><span class="sxs-lookup"><span data-stu-id="0a2bb-177">Global Definitions</span></span>  
 <span data-ttu-id="0a2bb-178">샘플 코드는 모든 메서드에서 표시되는 다음과 같은 두 가지 전역 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-178">The sample code contains the following two global declarations that are visible from all methods.</span></span>  
  
```csharp  
public partial class MainWindow : Window  // Class MainPage in Windows Store app.  
{  
    // ***Declare the following variables where all methods can access them.   
    private Task pendingWork = null;     
    private char group = (char)('A' - 1);  
```  
  
 <span data-ttu-id="0a2bb-179">`Task` 변수 `pendingWork`는 표시 프로세스를 감독하고 모든 그룹이 다른 그룹의 표시 작업을 방해하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-179">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="0a2bb-180">문자 변수 `group`은 다른 그룹의 출력에 레이블을 지정하여 해당 결과가 예상 순서대로 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-180">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>  
  
#### <a name="the-click-event-handler"></a><span data-ttu-id="0a2bb-181">Click 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="0a2bb-181">The Click Event Handler</span></span>  
 <span data-ttu-id="0a2bb-182">이벤트 처리기 `StartButton_Click`은 사용자가 **시작** 단추를 선택할 때마다 그룹 문자를 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-182">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="0a2bb-183">그런 다음 처리기에서 `AccessTheWebAsync`를 호출하여 다운로드 중인 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-183">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>  
  
```csharp  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // ***Verify that each group's results are displayed together, and that  
    // the groups display in order, by marking each group with a letter.  
    group = (char)(group + 1);  
    ResultsTextBox.Text += string.Format("\r\n\r\n#Starting group {0}.", group);  
  
    try  
    {  
        // *** Pass the group value to AccessTheWebAsync.  
        char finishedGroup = await AccessTheWebAsync(group);  
  
        // The following line verifies a successful return from the download and  
        // display procedures.   
        ResultsTextBox.Text += string.Format("\r\n\r\n#Group {0} is complete.\r\n", finishedGroup);  
    }  
    catch (Exception)  
    {  
        ResultsTextBox.Text += "\r\nDownloads failed.";  
    }  
}  
```  
  
#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="0a2bb-184">AccessTheWebAsync 메서드</span><span class="sxs-lookup"><span data-stu-id="0a2bb-184">The AccessTheWebAsync Method</span></span>  
 <span data-ttu-id="0a2bb-185">이 예제에서는 `AccessTheWebAsync`를 두 개의 메서드로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-185">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="0a2bb-186">첫 번째 메서드 `AccessTheWebAsync`는 그룹에 대해 모든 다운로드 작업을 시작하고 `pendingWork`를 설정하여 표시 프로세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-186">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="0a2bb-187">이 메서드는 LINQ(통합 언어 쿼리) 쿼리 및 <xref:System.Linq.Enumerable.ToArray%2A>를 사용하여 모든 다운로드 작업을 동시에 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-187">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>  
  
 <span data-ttu-id="0a2bb-188">그런 다음 `AccessTheWebAsync`는 `FinishOneGroupAsync`를 호출하여 각 다운로드가 완료될 때까지 대기하고 해당 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-188">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>  
  
 <span data-ttu-id="0a2bb-189">`FinishOneGroupAsync`는 `AccessTheWebAsync`의 `pendingWork`에 할당되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-189">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="0a2bb-190">해당 값은 작업이 완료되기 전에 다른 작업에 의한 중단을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-190">That value prevents interruption by another operation before the task is complete.</span></span>  
  
```csharp  
private async Task<char> AccessTheWebAsync(char grp)  
{  
    HttpClient client = new HttpClient();  
  
    // Make a list of the web addresses to download.  
    List<string> urlList = SetUpURLList();  
  
    // ***Kick off the downloads. The application of ToArray activates all the download tasks.  
    Task<byte[]>[] getContentTasks = urlList.Select(url => client.GetByteArrayAsync(url)).ToArray();  
  
    // ***Call the method that awaits the downloads and displays the results.  
    // Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.  
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp);  
  
    ResultsTextBox.Text += string.Format("\r\n#Task assigned for group {0}. Download tasks are active.\r\n", grp);  
  
    // ***This task is complete when a group has finished downloading and displaying.  
    await pendingWork;  
  
    // You can do other work here or just return.  
    return grp;  
}  
```  
  
#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="0a2bb-191">FinishOneGroupAsync 메서드</span><span class="sxs-lookup"><span data-stu-id="0a2bb-191">The FinishOneGroupAsync Method</span></span>  
 <span data-ttu-id="0a2bb-192">이 메서드는 한 그룹의 다운로드 작업을 순환하여 각 작업을 대기하고 다운로드한 웹 사이트의 길이를 표시하고 길이를 합계에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-192">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>  
  
 <span data-ttu-id="0a2bb-193">`FinishOneGroupAsync`의 첫 번째 문은 `pendingWork`를 사용하여 메서드 입력이 이미 표시 프로세스에 있거나 이미 대기 중인 작업을 방해하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-193">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="0a2bb-194">이러한 작업이 진행 중인 경우 입력 작업은 해당 순서를 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-194">If such an operation is in progress, the entering operation must wait its turn.</span></span>  
  
```csharp  
private async Task FinishOneGroupAsync(List<string> urls, Task<byte[]>[] contentTasks, char grp)  
{  
    // ***Wait for the previous group to finish displaying results.  
    if (pendingWork != null) await pendingWork;  
  
    int total = 0;  
  
    // contentTasks is the array of Tasks that was created in AccessTheWebAsync.  
    for (int i = 0; i < contentTasks.Length; i++)  
    {  
        // Await the download of a particular URL, and then display the URL and  
        // its length.  
        byte[] content = await contentTasks[i];  
        DisplayResults(urls[i], content, i, grp);  
        total += content.Length;  
    }  
  
    // Display the total count for all of the websites.  
    ResultsTextBox.Text +=  
        string.Format("\r\n\r\nTOTAL bytes returned:  {0}\r\n", total);  
}  
```  
  
 <span data-ttu-id="0a2bb-195">변경 내용을 [앱 빌드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 코드에 붙여 넣어 이 예제를 실행하거나, [앱 다운로드](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 지침에 따라 샘플을 다운로드한 다음 QueueResults 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-195">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample, and then run the QueueResults project.</span></span>  
  
#### <a name="points-of-interest"></a><span data-ttu-id="0a2bb-196">관심 영역</span><span class="sxs-lookup"><span data-stu-id="0a2bb-196">Points of Interest</span></span>  
 <span data-ttu-id="0a2bb-197">출력에서 파운드 기호(#)로 시작하는 정보 줄은 이 예제의 작동 방식을 명확히 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-197">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>  
  
 <span data-ttu-id="0a2bb-198">출력은 다음과 같은 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-198">The output shows the following patterns.</span></span>  
  
-   <span data-ttu-id="0a2bb-199">이전 그룹이 출력을 표시하는 동안 그룹이 시작될 수 있지만 이전 그룹의 출력 표시가 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-199">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>  
  
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
  
-   <span data-ttu-id="0a2bb-200">`pendingWork` 작업은 처음에 시작된 그룹 A에 대해서만 `FinishOneGroupAsync`의 시작 부분에서 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-200">The `pendingWork` task is null  at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="0a2bb-201">그룹 A는 `FinishOneGroupAsync`에 도달할 때 await 식을 아직 완료하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-201">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="0a2bb-202">따라서 컨트롤이 `AccessTheWebAsync`로 반환되지 않았으며 `pendingWork`에 대한 첫 번째 할당이 발생되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-202">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>  
  
-   <span data-ttu-id="0a2bb-203">다음 두 줄은 항상 출력에 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-203">The following two lines always appear together in the output.</span></span> <span data-ttu-id="0a2bb-204">코드는 `StartButton_Click`의 그룹 작업 시작과 `pendingWork`에 그룹에 대한 작업 할당 사이에서 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-204">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>  
  
    ```  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
    ```  
  
     <span data-ttu-id="0a2bb-205">그룹이 `StartButton_Click`을 입력한 후 작업은 `FinishOneGroupAsync`를 입력한 다음에야 await 식을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-205">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="0a2bb-206">따라서 코드의 해당 세그먼트 중에는 다른 작업에서 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-206">Therefore, no other operation can gain control during that segment of code.</span></span>  
  
##  <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="0a2bb-207">예제 앱 검토 및 실행</span><span class="sxs-lookup"><span data-stu-id="0a2bb-207">Reviewing and Running the Example App</span></span>  
 <span data-ttu-id="0a2bb-208">예제 앱을 더 잘 이해하려면 다운로드하거나, 직접 빌드하거나, 앱을 구현하지 않고 이 항목의 끝에 있는 코드를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-208">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a2bb-209">예제를 WPF(Windows Presentation Foundation) 데스크톱 앱으로 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-209">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="0a2bb-210">앱 다운로드</span><span class="sxs-lookup"><span data-stu-id="0a2bb-210">Downloading the App</span></span>  
  
1.  <span data-ttu-id="0a2bb-211">[Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571)(비동기 샘플: .NET 데스크톱 앱의 재입력)에서 압축 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-211">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span>  
  
2.  <span data-ttu-id="0a2bb-212">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-212">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
3.  <span data-ttu-id="0a2bb-213">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-213">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="0a2bb-214">압축을 푼 샘플 코드가 저장된 폴더로 이동한 다음 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-214">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>  
  
5.  <span data-ttu-id="0a2bb-215">**솔루션 탐색기**에서 실행하려는 프로젝트의 바로 가기 메뉴를 연 후 **StartUpProject로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-215">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>  
  
6.  <span data-ttu-id="0a2bb-216">CTRL+F5를 선택하여 프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-216">Choose the CTRL+F5 keys to build and run the project.</span></span>  
  
###  <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="0a2bb-217">앱 빌드</span><span class="sxs-lookup"><span data-stu-id="0a2bb-217">Building the App</span></span>  
 <span data-ttu-id="0a2bb-218">다음 섹션에서는 예제를 WPF 앱으로 빌드하는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-218">The following section provides the code to build the example as a WPF app.</span></span>  
  
##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="0a2bb-219">WPF 응용 프로그램을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="0a2bb-219">To build a WPF app</span></span>  
  
1.  <span data-ttu-id="0a2bb-220">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-220">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0a2bb-221">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-221">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="0a2bb-222">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-222">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="0a2bb-223">**설치된 템플릿** 창에서 **Visual C#**을 확장한 다음 **Windows**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-223">In the **Installed Templates** pane, expand **Visual C#**, and then expand **Windows**.</span></span>  
  
4.  <span data-ttu-id="0a2bb-224">프로젝트 형식 목록에서 **WPF 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-224">In the list of project types, choose **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="0a2bb-225">프로젝트 이름을 `WebsiteDownloadWPF`로 지정한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-225">Name the project `WebsiteDownloadWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="0a2bb-226">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-226">The new project appears in **Solution Explorer**.</span></span>  
  
6.  <span data-ttu-id="0a2bb-227">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-227">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="0a2bb-228">탭이 표시되지 않는 경우 **솔루션 탐색기**에서 MainWindow.xaml의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-228">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
7.  <span data-ttu-id="0a2bb-229">MainWindow.xaml의 **XAML** 보기에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-229">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```csharp  
    <Window x:Class="WebsiteDownloadWPF.MainWindow"  
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
  
     <span data-ttu-id="0a2bb-230">텍스트 상자와 단추가 포함된 간단한 창이 MainWindow.xaml의 **디자인** 보기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-230">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
8.  <span data-ttu-id="0a2bb-231"><xref:System.Net.Http>에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-231">Add a reference for <xref:System.Net.Http>.</span></span>  
  
9. <span data-ttu-id="0a2bb-232">**솔루션 탐색기**에서 MainWindow.xaml.cs의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-232">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
10. <span data-ttu-id="0a2bb-233">MainWindow.xaml.cs에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-233">In MainWindow.xaml.cs, replace the code with the following code.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.Threading.Tasks;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Data;  
    using System.Windows.Documents;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    using System.Windows.Media.Imaging;  
    using System.Windows.Navigation;  
    using System.Windows.Shapes;  
  
    // Add the following using directives, and add a reference for System.Net.Http.  
    using System.Net.Http;  
    using System.Threading;  
  
    namespace WebsiteDownloadWPF  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            private async void StartButton_Click(object sender, RoutedEventArgs e)  
            {  
                // This line is commented out to make the results clearer in the output.  
                //ResultsTextBox.Text = "";  
  
                try  
                {  
                    await AccessTheWebAsync();  
                }  
                catch (Exception)  
                {  
                    ResultsTextBox.Text += "\r\nDownloads failed.";  
                }  
            }  
  
            private async Task AccessTheWebAsync()  
            {  
                // Declare an HttpClient object.  
                HttpClient client = new HttpClient();  
  
                // Make a list of web addresses.  
                List<string> urlList = SetUpURLList();  
  
                var total = 0;  
                var position = 0;  
  
                foreach (var url in urlList)  
                {  
                    // GetByteArrayAsync returns a task. At completion, the task  
                    // produces a byte array.  
                    byte[] urlContents = await client.GetByteArrayAsync(url);  
  
                    DisplayResults(url, urlContents, ++position);  
  
                    // Update the total.  
                    total += urlContents.Length;  
                }  
  
                // Display the total count for all of the websites.  
                ResultsTextBox.Text +=  
                    string.Format("\r\n\r\nTOTAL bytes returned:  {0}\r\n", total);  
            }  
  
            private List<string> SetUpURLList()  
            {  
                List<string> urls = new List<string>   
                {   
                    "http://msdn.microsoft.com/library/hh191443.aspx",  
                    "http://msdn.microsoft.com/library/aa578028.aspx",  
                    "http://msdn.microsoft.com/library/jj155761.aspx",  
                    "http://msdn.microsoft.com/library/hh290140.aspx",  
                    "http://msdn.microsoft.com/library/hh524395.aspx",  
                    "http://msdn.microsoft.com/library/ms404677.aspx",  
                    "http://msdn.microsoft.com",  
                    "http://msdn.microsoft.com/library/ff730837.aspx"  
                };  
                return urls;  
            }  
  
            private void DisplayResults(string url, byte[] content, int pos)  
            {  
                // Display the length of each website. The string format is designed  
                // to be used with a monospaced font, such as Lucida Console or   
                // Global Monospace.  
  
                // Strip off the "http://".  
                var displayURL = url.Replace("http://", "");  
                // Display position in the URL list, the URL, and the number of bytes.  
                ResultsTextBox.Text += string.Format("\n{0}. {1,-58} {2,8}", pos, displayURL, content.Length);  
            }  
        }  
    }  
    ```  
  
11. <span data-ttu-id="0a2bb-234">CTRL+F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 여러 번 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-234">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>  
  
12. <span data-ttu-id="0a2bb-235">[시작 단추 사용 안 함](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [작업 취소 및 다시 시작](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) 또는 [여러 작업을 실행하고 출력을 큐 대기](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)의 내용을 변경하여 재입력을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2bb-235">Make the changes from [Disable the Start Button](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Cancel and Restart the Operation](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or [Run Multiple Operations and Queue the Output](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to handle the reentrancy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2bb-236">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a2bb-236">See Also</span></span>  
 [<span data-ttu-id="0a2bb-237">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="0a2bb-237">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="0a2bb-238">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="0a2bb-238">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
