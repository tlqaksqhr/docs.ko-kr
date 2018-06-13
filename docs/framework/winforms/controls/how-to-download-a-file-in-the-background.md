---
title: '방법: 백그라운드에서 파일 다운로드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: 616aa5495ec5ec5d3db6f816a96c34b3ac9f3fed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536571"
---
# <a name="how-to-download-a-file-in-the-background"></a><span data-ttu-id="819df-102">방법: 백그라운드에서 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="819df-102">How to: Download a File in the Background</span></span>
<span data-ttu-id="819df-103">파일 다운로드는 일반 작업이며, 대체로 시간이 많이 걸릴 수 있는 이 작업을 별도 스레드에서 실행하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-103">Downloading a file is a common task, and it is often useful to run this potentially time-consuming operation on a separate thread.</span></span> <span data-ttu-id="819df-104">매우 적은 양의 코드로 이 작업을 수행려면 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-104">Use the <xref:System.ComponentModel.BackgroundWorker> component to accomplish this task with very little code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="819df-105">예제</span><span class="sxs-lookup"><span data-stu-id="819df-105">Example</span></span>  
 <span data-ttu-id="819df-106">다음 코드 예제에서는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 사용하여 URL에서 XML 파일을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="819df-106">The following code example demonstrates how to use a <xref:System.ComponentModel.BackgroundWorker> component to load an XML file from a URL.</span></span> <span data-ttu-id="819df-107">사용자가 클릭할 때는 **다운로드** 단추를는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 호출의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 의 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소 다운로드 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-107">When the user clicks the **Download** button, the <xref:System.Windows.Forms.Control.Click> event handler calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of a <xref:System.ComponentModel.BackgroundWorker> component to start the download operation.</span></span> <span data-ttu-id="819df-108">다운로드 기간 중에는 단추를 사용할 수 없으며, 다운로드가 완료되면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819df-108">The button is disabled for the duration of the download, and then enabled when the download is complete.</span></span> <span data-ttu-id="819df-109"><xref:System.Windows.Forms.MessageBox>는 파일 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-109">A <xref:System.Windows.Forms.MessageBox> displays the contents of the file.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 <span data-ttu-id="819df-110">**파일 다운로드**</span><span class="sxs-lookup"><span data-stu-id="819df-110">**Downloading the file**</span></span>  
  
 <span data-ttu-id="819df-111"><xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 실행하는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 작업자 스레드에서 파일이 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="819df-111">The file is downloaded on the <xref:System.ComponentModel.BackgroundWorker> component's worker thread, which runs the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="819df-112">이 스레드는 코드에서 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 메서드를 호출할 때 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="819df-112">This thread starts when your code calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 <span data-ttu-id="819df-113">**BackgroundWorker가 완료될 때까지 대기**</span><span class="sxs-lookup"><span data-stu-id="819df-113">**Waiting for a BackgroundWorker to finish**</span></span>  
  
 <span data-ttu-id="819df-114">`downloadButton_Click` 이벤트 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 비동기 작업을 완료할 때까지 기다리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="819df-114">The `downloadButton_Click` event handler demonstrates how to wait for a <xref:System.ComponentModel.BackgroundWorker> component to finish its asynchronous task.</span></span>  
  
 <span data-ttu-id="819df-115">응용 프로그램에서 이벤트에 응답만 하고 백그라운드 스레드가 완료될 때까지 기다리는 동안 주 스레드에서 작업을 수행하지 않으려는 경우 처리기를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-115">If you only want the application to respond to events and do not want to do any work in the main thread while you wait for the background thread to complete, just exit the handler.</span></span>  
  
 <span data-ttu-id="819df-116">주 스레드에서 작업을 계속하려는 경우 <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> 속성을 사용하여 <xref:System.ComponentModel.BackgroundWorker> 스레드가 여전히 실행되고 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-116">If you want to continue doing work in the main thread, use the <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> property to determine whether the <xref:System.ComponentModel.BackgroundWorker> thread is still running.</span></span> <span data-ttu-id="819df-117">예제에서는 다운로드가 처리되는 동안 진행률 표시줄이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="819df-117">In the example, a progress bar is updated while the download is processing.</span></span> <span data-ttu-id="819df-118"><xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 메서드를 호출하여 UI 응답성을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-118">Be sure to call the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method to keep the UI responsive.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 <span data-ttu-id="819df-119">**결과 표시**</span><span class="sxs-lookup"><span data-stu-id="819df-119">**Displaying the result**</span></span>  
  
 <span data-ttu-id="819df-120">`backgroundWorker1_RunWorkerCompleted` 메서드는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 처리하며, 백그라운드 작업이 완료될 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="819df-120">The `backgroundWorker1_RunWorkerCompleted` method handles the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event and is called when the background operation is completed.</span></span> <span data-ttu-id="819df-121">이 메서드는 먼저 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-121">This method first checks the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="819df-122"><xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>가 `null`이면 이 메서드는 파일 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-122">If <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> is `null`, then this method displays the contents of the file.</span></span> <span data-ttu-id="819df-123">다운로드를 시작할 때 사용할 수 없게 된 다운로드 단추를 사용할 수 있도록 하며 진행률 표시줄을 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-123">It then enables the download button, which was disabled when the download began, and it resets the progress bar.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="819df-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="819df-124">Compiling the Code</span></span>  
 <span data-ttu-id="819df-125">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-125">This example requires:</span></span>  
  
-   <span data-ttu-id="819df-126">System.Drawing, System.Windows.Forms 및 System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="819df-126">References to the System.Drawing, System.Windows.Forms, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="819df-127">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-127">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="819df-128">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819df-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="819df-129">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="819df-129">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="819df-130">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="819df-130">Robust Programming</span></span>  
 <span data-ttu-id="819df-131"><xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> 속성이나 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기의 영향을 받았을 수 있는 다른 개체에 액세스하기 전에 항상 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기의 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="819df-131">Always check the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property in your <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler before attempting to access the <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> property or any other object that may have been affected by the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819df-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="819df-132">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="819df-133">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="819df-133">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="819df-134">방법: 배경 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="819df-134">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
