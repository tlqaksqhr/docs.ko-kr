---
title: "연습: async 및 await를 사용하여 웹에 액세스(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 533cb4b342e3de3eb3143b001f5a26e36e4d79b9
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="00ef7-102">연습: async 및 await를 사용하여 웹에 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="00ef7-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>
<span data-ttu-id="00ef7-103">async/await 기능을 사용하여 비동기 프로그램을 보다 쉽고 직관적인 방식으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="00ef7-104">동기 코드처럼 보이는 비동기 코드를 작성하고 일반적으로 비동기 코드에 수반되는 어려운 콜백 함수 및 연속 작업을 컴파일러에서 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="00ef7-105">비동기 기능에 대한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/async/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="00ef7-106">이 연습은 웹 사이트 목록에 있는 바이트 수의 합계를 계산하는 동기 WPF(Windows Presentation Foundation) 응용 프로그램에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="00ef7-107">그런 다음 새로운 기능을 사용하여 응용 프로그램을 비동기 솔루션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="00ef7-108">응용 프로그램을 직접 빌드하지 않으려면 [Async 샘플: 웹 연습에 액세스(C# 및 Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-108">If you don't want to build the applications yourself, you can download [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>  
  
 <span data-ttu-id="00ef7-109">이 연습에서는 다음 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="00ef7-110">WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="00ef7-111">간단한 WPF MainWindow를 디자인하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="00ef7-112">참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="00ef7-113">필요한 using 지시문을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-113">To add necessary using directives</span></span>](#usingDir)  
  
-   [<span data-ttu-id="00ef7-114">동기식 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="00ef7-115">동기 솔루션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="00ef7-116">GetURLContents를 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="00ef7-117">SumPageSizes를 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="00ef7-118">startButton_Click을 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="00ef7-119">비동기 솔루션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="00ef7-120">GetURLContentsAsync 메서드를 .NET Framework 메서드로 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="00ef7-121">예제</span><span class="sxs-lookup"><span data-stu-id="00ef7-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
> [!NOTE]
>  <span data-ttu-id="00ef7-122">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-122">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <a name="CreateWPFApp"></a> <span data-ttu-id="00ef7-123">WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-123">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="00ef7-124">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-124">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="00ef7-125">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-125">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="00ef7-126">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-126">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="00ef7-127">**설치된 템플릿** 창에서 Visual C#을 선택한 다음 프로젝트 형식 목록에서 **WPF 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-127">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="00ef7-128">**이름** 텍스트 상자에 `AsyncExampleWPF`를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-128">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="00ef7-129">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-129">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a> <span data-ttu-id="00ef7-130">간단한 WPF MainWindow를 디자인하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-130">To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="00ef7-131">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-131">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="00ef7-132">**도구 상자** 창이 표시되지 않으면 **보기** 메뉴를 열고 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-132">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="00ef7-133">**Button** 컨트롤 및 **TextBox** 컨트롤을 **MainWindow** 창에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-133">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="00ef7-134">**TextBox** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-134">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="00ef7-135">**Name** 속성을 `resultsTextBox`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-135">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="00ef7-136">**Height** 속성을 250으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-136">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="00ef7-137">**Width** 속성을 500으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-137">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="00ef7-138">**Text** 탭에서 Lucida Console 또는 Global Monospace 같은 고정 폭 글꼴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-138">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="00ef7-139">**Button** 컨트롤을 강조 표시하고 **속성** 창에서 다음 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-139">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="00ef7-140">**Name** 속성을 `startButton`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-140">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="00ef7-141">**Content** 속성 값을 **Button**에서 **Start**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-141">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="00ef7-142">텍스트 상자와 단추가 둘 다 **MainWindow** 창에 나타나도록 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-142">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="00ef7-143">WPF XAML 디자이너에 대한 자세한 내용은 [XAML 디자이너를 사용하여 UI 만들기](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-143">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a> <span data-ttu-id="00ef7-144">참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-144">To add a reference</span></span>  
  
1.  <span data-ttu-id="00ef7-145">**솔루션 탐색기**에서 프로젝트의 이름을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-145">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="00ef7-146">메뉴 모음에서 **프로젝트**, **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-146">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="00ef7-147">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-147">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="00ef7-148">대화 상자 맨 위에서 프로젝트가 .NET Framework 4.5 이상을 대상으로 하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-148">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="00ef7-149">**어셈블리** 영역에서 **프레임워크**가 선택되지 않은 경우 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-149">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="00ef7-150">이름 목록에서 **System.Net.Http** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-150">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="00ef7-151">**확인** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-151">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="usingDir"></a> <span data-ttu-id="00ef7-152">필요한 using 지시문을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-152">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="00ef7-153">**솔루션 탐색기**에서 MainWindow.xaml.cs의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-153">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="00ef7-154">다음 `using` 지시문이 없는 경우 코드 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-154">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>  
  
    ```csharp  
    using System.Net.Http;  
    using System.Net;  
    using System.IO;  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a> <span data-ttu-id="00ef7-155">동기식 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-155">To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="00ef7-156">디자인 창 MainWindow.xaml에서 **시작** 단추를 두 번 클릭하여 MainWindow.xaml.cs에서 `startButton_Click` 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-156">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="00ef7-157">MainWindow.xaml.cs에서 다음 코드를 `startButton_Click`의 본문에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-157">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    SumPageSizes();  
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";  
    ```  
  
     <span data-ttu-id="00ef7-158">이 코드는 응용 프로그램 `SumPageSizes`를 구동하는 메서드를 호출하고 컨트롤이 `startButton_Click`으로 반환될 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-158">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="00ef7-159">동기 솔루션에 대한 코드에는 다음 네 가지 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-159">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="00ef7-160">`SumPageSizes` - `SetUpURLList`에서 웹 페이지 URL 목록을 가져온 다음 `GetURLContents` 및 `DisplayResults`를 호출하여 각 URL을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-160">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="00ef7-161">`SetUpURLList` - 웹 주소 목록을 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-161">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="00ef7-162">`GetURLContents` - 각 웹 사이트의 콘텐츠를 다운로드하고 해당 콘텐츠를 바이트 배열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-162">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="00ef7-163">`DisplayResults`- 각 URL에 대한 바이트 배열의 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-163">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="00ef7-164">다음 네 개 메서드를 복사한 다음 MainWindow.xaml.cs의 `startButton_Click` 이벤트 처리기 아래에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-164">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>  
  
    ```csharp  
    private void SumPageSizes()  
    {  
        // Make a list of web addresses.  
        List<string> urlList = SetUpURLList();   
  
        var total = 0;  
        foreach (var url in urlList)  
        {  
            // GetURLContents returns the contents of url as a byte array.  
            byte[] urlContents = GetURLContents(url);  
  
            DisplayResults(url, urlContents);  
  
            // Update the total.  
            total += urlContents.Length;  
        }  
  
        // Display the total count for all of the web addresses.  
        resultsTextBox.Text +=   
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
  
    private List<string> SetUpURLList()  
    {  
        var urls = new List<string>   
        {   
            "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
            "http://msdn.microsoft.com",  
            "http://msdn.microsoft.com/library/hh290136.aspx",  
            "http://msdn.microsoft.com/library/ee256749.aspx",  
            "http://msdn.microsoft.com/library/hh290138.aspx",  
            "http://msdn.microsoft.com/library/hh290140.aspx",  
            "http://msdn.microsoft.com/library/dd470362.aspx",  
            "http://msdn.microsoft.com/library/aa578028.aspx",  
            "http://msdn.microsoft.com/library/ms404677.aspx",  
            "http://msdn.microsoft.com/library/ff730837.aspx"  
        };  
        return urls;  
    }  
  
    private byte[] GetURLContents(string url)  
    {  
        // The downloaded resource ends up in the variable named content.  
        var content = new MemoryStream();  
  
        // Initialize an HttpWebRequest for the current URL.  
        var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
        // Send the request to the Internet resource and wait for  
        // the response.  
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        using (WebResponse response = webReq.GetResponse())  
        {  
            // Get the data stream that is associated with the specified URL.  
            using (Stream responseStream = response.GetResponseStream())  
            {  
                // Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content);  
            }  
        }  
  
        // Return the result as a byte array.  
        return content.ToArray();  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format   
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a> <span data-ttu-id="00ef7-165">동기 솔루션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-165">To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="00ef7-166">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-166">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="00ef7-167">다음 목록과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-167">Output that resembles the following list should appear.</span></span>  
  
    ```  
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832  
    msdn.microsoft.com                                            33964  
    msdn.microsoft.com/library/hh290136.aspx               225793  
    msdn.microsoft.com/library/ee256749.aspx               143577  
    msdn.microsoft.com/library/hh290138.aspx               237372  
    msdn.microsoft.com/library/hh290140.aspx               128279  
    msdn.microsoft.com/library/dd470362.aspx               157649  
    msdn.microsoft.com/library/aa578028.aspx               204457  
    msdn.microsoft.com/library/ms404677.aspx               176405  
    msdn.microsoft.com/library/ff730837.aspx               143474  
  
    Total bytes returned:  1834802  
  
    Control returned to startButton_Click.  
    ```  
  
     <span data-ttu-id="00ef7-168">개수를 표시하려면 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-168">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="00ef7-169">이 시간 동안 UI 스레드는 차단되어 요청한 리소스가 다운로드될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-169">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="00ef7-170">따라서 **시작** 단추를 선택한 후에도 표시 창을 이동, 최대화, 최소화할 수 없으며 닫을 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-170">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="00ef7-171">이러한 작업은 바이트 개수가 나타나기 시작할 때까지 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-171">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="00ef7-172">웹 사이트가 응답하지 않는 경우 실패한 사이트를 표시하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-172">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="00ef7-173">대기를 중지하고 프로그램을 닫는 것도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-173">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a> <span data-ttu-id="00ef7-174">GetURLContents를 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-174">To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="00ef7-175">동기 솔루션을 비동기 솔루션으로 변환하려면 `GetURLContents`에서 시작하는 것이 가장 좋습니다. <xref:System.Net.HttpWebRequest> 메서드 <xref:System.Net.HttpWebRequest.GetResponse%2A> 및 <xref:System.IO.Stream> 메서드 <xref:System.IO.Stream.CopyTo%2A> 호출은 응용 프로그램이 웹에 액세스하는 위치이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-175">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="00ef7-176">.NET Framework는 두 메서드의 비동기 버전을 제공하여 변환을 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-176">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="00ef7-177">`GetURLContents`에서 사용되는 메서드에 대한 자세한 내용은 <xref:System.Net.WebRequest>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-177">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00ef7-178">이 연습 단계를 수행하면 여러 가지 컴파일러 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-178">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="00ef7-179">이러한 오류는 무시하고 연습을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-179">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="00ef7-180">`GetURLContents`의 셋째 줄에서 호출되는 메서드를 `GetResponse`에서 비동기 작업 기반 <xref:System.Net.WebRequest.GetResponseAsync%2A> 메서드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-180">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```csharp  
    using (WebResponse response = webReq.GetResponseAsync())  
    ```  
  
2.  <span data-ttu-id="00ef7-181">`GetResponseAsync`는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-181">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="00ef7-182">이 경우 *작업 반환 변수* `TResult`는 <xref:System.Net.WebResponse> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-182">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="00ef7-183">작업은 요청한 데이터를 다운로드하고 작업을 실행하여 완료한 후 실제 `WebResponse` 개체를 생성한다는 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-183">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="00ef7-184">작업에서 `WebResponse` 값을 검색하려면 다음 코드에 표시된 대로 [await](../../../../csharp/language-reference/keywords/await.md) 연산자를 `GetResponseAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-184">To retrieve the `WebResponse` value from the task, apply an [await](../../../../csharp/language-reference/keywords/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
    ```csharp  
    using (WebResponse response = await webReq.GetResponseAsync())  
    ```  
  
     <span data-ttu-id="00ef7-185">`GetURLContents` 연산자는 대기 중인 작업이 완료될 때까지 현재 메서드 `await`의 실행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-185">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="00ef7-186">반면, 컨트롤은 현재 메서드의 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-186">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="00ef7-187">이 예제에서 현재 메서드는 `GetURLContents`이고 호출자는 `SumPageSizes`입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-187">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="00ef7-188">작업이 완료되면 약속된 `WebResponse` 개체가 대기 중인 작업의 값으로 생성되고 `response` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-188">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     <span data-ttu-id="00ef7-189">위의 문을 다음과 같은 두 개의 문으로 구분하여 수행되는 작업을 명확하게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-189">The previous statement can be separated into the following two statements to clarify what happens.</span></span>  
  
    ```csharp  
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
    //using (WebResponse response = await responseTask)  
    ```  
  
     <span data-ttu-id="00ef7-190">`webReq.GetResponseAsync`를 호출하면 `Task(Of WebResponse)` 또는 `Task<WebResponse>`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-190">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="00ef7-191">그러면 await 연산자가 작업에 적용되어 `WebResponse` 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-191">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     <span data-ttu-id="00ef7-192">비동기 메서드가 작업의 완료에 따라 달라지지 않는 작업을 수행해야 하는 경우 메서드는 비동기 메서드를 호출한 후와 `await` 연산자가 적용되기 전의 두 문 사이에서 해당 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-192">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="00ef7-193">예제는 [방법: async 및 await를 사용하여 병렬로 여러 웹 요청 만들기(C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) 및 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-193">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
3.  <span data-ttu-id="00ef7-194">이전 단계에서 `await` 연산자를 추가했으므로 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-194">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="00ef7-195">이 연산자는 [async](../../../../csharp/language-reference/keywords/async.md) 한정자로 표시되는 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-195">The operator can be used only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="00ef7-196">`CopyTo` 호출을 `CopyToAsync` 호출로 바꾸는 변환 단계를 반복하는 동안에는 오류를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-196">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="00ef7-197">호출되는 메서드의 이름을 <xref:System.IO.Stream.CopyToAsync%2A>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-197">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="00ef7-198">`CopyTo` 또는 `CopyToAsync` 메서드는 바이트를 해당 인수 `content`에 복사하고 의미 있는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-198">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="00ef7-199">동기 버전에서 `CopyTo` 호출은 값을 반환하지 않는 단순 문입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-199">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="00ef7-200">비동기 버전 `CopyToAsync`는 <xref:System.Threading.Tasks.Task>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-200">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="00ef7-201">작업은 "Task(void)"처럼 작동하고 메서드를 대기하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-201">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="00ef7-202">다음 코드에 표시된 대로 `Await` 또는 `await`를 `CopyToAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-202">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
        ```csharp  
        await responseStream.CopyToAsync(content);  
        ```  
  
         <span data-ttu-id="00ef7-203">위의 문은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-203">The previous statement abbreviates the following two lines of code.</span></span>  
  
        ```csharp  
        // CopyToAsync returns a Task, not a Task<T>.  
        //Task copyTask = responseStream.CopyToAsync(content);  
  
        // When copyTask is completed, content contains a copy of  
        // responseStream.  
        //await copyTask;  
        ```  
  
4.  <span data-ttu-id="00ef7-204">`GetURLContents`에서 수행해야 할 나머지 작업은 메서드 시그니처를 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-204">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="00ef7-205">`await` 연산자는 [async](../../../../csharp/language-reference/keywords/async.md) 한정자로 표시되는 메서드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-205">You can use the `await` operator only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="00ef7-206">다음 코드에 표시된 대로 한정자를 추가하여 메서드를 *비동기 메서드*로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-206">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
    ```csharp  
    private async byte[] GetURLContents(string url)  
    ```  
  
5.  <span data-ttu-id="00ef7-207">C#에서 비동기 메서드의 반환 형식은 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> 또는 `void`만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-207">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="00ef7-208">일반적으로 `void`의 반환 형식은 비동기 이벤트 처리기에서만 사용되며, 여기서 `void`는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-208">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="00ef7-209">경우에 따라 완료된 메서드에 T 형식의 값을 반환하는 [return](../../../../csharp/language-reference/keywords/return.md) 문이 있는 경우 `Task(T)`를 사용하고, 완료된 메서드에서 의미 있는 값을 반환하지 않는 경우 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-209">In other cases, you use `Task(T)` if the completed method has a [return](../../../../csharp/language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="00ef7-210">`Task` 반환 형식은 "Task(void)" 의미로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-210">You can think of the `Task` return type as meaning "Task(void)."</span></span>  
  
     <span data-ttu-id="00ef7-211">자세한 내용은 [비동기 반환 형식(C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-211">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="00ef7-212">`GetURLContents` 메서드에는 return 문이 있고 이 문은 바이트 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-212">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="00ef7-213">따라서 비동기 버전의 반환 형식은 Task(T)이며, 여기서 T는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-213">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="00ef7-214">다음과 같이 메서드 시그니처를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-214">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="00ef7-215">반환 형식을 `Task<byte[]>`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-215">Change the return type to `Task<byte[]>`.</span></span>  
  
    -   <span data-ttu-id="00ef7-216">규칙에 따라 비동기 메서드에는 "Async"로 끝나는 이름이 있으므로 `GetURLContentsAsync` 메서드의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-216">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="00ef7-217">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-217">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task<byte[]> GetURLContentsAsync(string url)  
    ```  
  
     <span data-ttu-id="00ef7-218">몇 가지 변경 작업을 통해 `GetURLContents`가 비동기 메서드로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-218">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a> <span data-ttu-id="00ef7-219">SumPageSizes를 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-219">To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="00ef7-220">`SumPageSizes`에 대한 이전 절차의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-220">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="00ef7-221">먼저 `GetURLContents` 호출을 비동기 호출로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-221">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="00ef7-222">호출되는 메서드의 이름을 `GetURLContents`에서 `GetURLContentsAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-222">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="00ef7-223">`GetURLContentsAsync`에서 반환하는 작업에 `await`를 적용하여 바이트 배열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-223">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="00ef7-224">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-224">The following code shows these changes.</span></span>  
  
    ```csharp  
    byte[] urlContents = await GetURLContentsAsync(url);  
    ```  
  
     <span data-ttu-id="00ef7-225">위의 할당은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-225">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```csharp  
    // GetURLContentsAsync returns a Task<T>. At completion, the task  
    // produces a byte array.  
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
    //byte[] urlContents = await getContentsTask;  
    ```  
  
2.  <span data-ttu-id="00ef7-226">메서드의 시그니처를 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-226">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="00ef7-227">`async` 한정자를 사용하여 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-227">Mark the method with the `async` modifier.</span></span>  
  
    -   <span data-ttu-id="00ef7-228">메서드 이름에 "Async"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-228">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="00ef7-229">`SumPageSizesAsync`는 T에 대한 값을 반환하지 않으므로 이번에는 작업 반환 변수 T가 없습니다. 메서드에 `return` 문이 없습니다. 그러나 메서드는 대기 가능하도록 `Task`를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-229">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="00ef7-230">따라서 메서드의 반환 형식을 `void`에서 `Task`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-230">Therefore, change the return type of the method from `void` to `Task`.</span></span>  
  
     <span data-ttu-id="00ef7-231">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-231">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task SumPageSizesAsync()  
    ```  
  
     <span data-ttu-id="00ef7-232">`SumPageSizes`가 `SumPageSizesAsync`로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-232">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a> <span data-ttu-id="00ef7-233">startButton_Click을 비동기 메서드로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-233">To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="00ef7-234">이벤트 처리기에서 호출된 메서드의 이름을 `SumPageSizes`에서 `SumPageSizesAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-234">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="00ef7-235">`SumPageSizesAsync`는 비동기 메서드이므로 이벤트 처리기에서 코드를 변경하여 결과를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-235">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="00ef7-236">`SumPageSizesAsync` 호출은 `GetURLContentsAsync`에서 `CopyToAsync` 호출을 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-236">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="00ef7-237">이 호출에서는 `Task(T)`가 아니라 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-237">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="00ef7-238">이전 절차에서처럼 한 개 또는 두 개의 문을 사용하여 호출을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-238">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="00ef7-239">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-239">The following code shows these changes.</span></span>  
  
    ```csharp  
    // One-step async call.  
    await SumPageSizesAsync();  
  
    // Two-step async call.  
    //Task sumTask = SumPageSizesAsync();  
    //await sumTask;  
    ```  
  
3.  <span data-ttu-id="00ef7-240">실수로 작업을 다시 입력하지 않도록 하려면 `startButton_Click`의 맨 위에 다음 문을 추가하여 **시작** 단추를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-240">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```csharp  
    // Disable the button until the operation is complete.  
    startButton.IsEnabled = false;  
    ```  
  
     <span data-ttu-id="00ef7-241">이벤트 처리기의 끝에서 단추를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-241">You can reenable the button at the end of the event handler.</span></span>  
  
    ```csharp  
    // Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = true;  
    ```  
  
     <span data-ttu-id="00ef7-242">재입력에 대한 자세한 내용은 [비동기 앱에서 재입력 처리(C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ef7-242">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="00ef7-243">마지막으로 `async` 한정자를 선언에 추가하여 이벤트 처리기에서 `SumPagSizesAsync`를 기다릴 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-243">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```csharp  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    ```  
  
     <span data-ttu-id="00ef7-244">일반적으로 이벤트 처리기의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-244">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="00ef7-245">이벤트 처리기가 `void`를 반환해야 하므로 반환 형식은 `Task`로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-245">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>  
  
     <span data-ttu-id="00ef7-246">동기에서 비동기 처리로 프로젝트 변환이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-246">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a> <span data-ttu-id="00ef7-247">비동기 솔루션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-247">To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="00ef7-248">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-248">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="00ef7-249">동기 솔루션의 출력과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-249">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="00ef7-250">그러나 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-250">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="00ef7-251">처리가 완료된 후 결과가 모두 동시에 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-251">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="00ef7-252">예를 들어 두 프로그램 모두 텍스트 상자를 지우는 줄을 `startButton_Click`에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-252">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="00ef7-253">의도는 하나의 결과 집합이 나타난 후 몇 초 동안 **시작** 단추를 선택하면 실행 사이에 텍스트 상자를 지우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-253">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="00ef7-254">동기 버전에서는 다운로드가 완료되고 UI 스레드에서 자유롭게 다른 작업을 수행할 수 있게 되면 두 번째로 개수가 표시되기 직전에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-254">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="00ef7-255">비동기 버전에서는 **시작** 단추를 선택한 직후에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-255">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="00ef7-256">가장 중요한 점은 다운로드하는 동안 UI 스레드가 차단되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-256">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="00ef7-257">웹 리소스를 다운로드하고, 개수를 계산하고, 표시하는 동안 창을 이동하거나 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-257">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="00ef7-258">웹 사이트 중 하나가 속도가 느리거나 응답하지 않는 경우 **닫기** 단추(오른쪽 위 모서리에 있는 빨간색 필드의 x)를 선택하여 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-258">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a> <span data-ttu-id="00ef7-259">GetURLContentsAsync 메서드를 .NET Framework 메서드로 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="00ef7-259">To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="00ef7-260">.NET Framework 4.5는 사용할 수 있는 다양한 비동기 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-260">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="00ef7-261">그 중 하나인 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>가 바로 이 연습에 필요한 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-261">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="00ef7-262">이전 절차에서 만든 `GetURLContentsAsync` 메서드 대신 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-262">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="00ef7-263">첫 번째 단계로 `SumPageSizesAsync` 메서드에서 `HttpClient` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-263">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="00ef7-264">메서드의 시작 부분에 다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-264">Add the following declaration at the start of the method.</span></span>  
  
    ```csharp  
    // Declare an HttpClient object and increase the buffer size. The  
    // default buffer size is 65,536.  
    HttpClient client =  
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
    ```  
  
2.  <span data-ttu-id="00ef7-265">`SumPageSizesAsync,`에서 `GetURLContentsAsync` 메서드 호출을 `HttpClient` 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-265">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```csharp  
    byte[] urlContents = await client.GetByteArrayAsync(url);  
    ```  
  
3.  <span data-ttu-id="00ef7-266">작성한 `GetURLContentsAsync` 메서드를 제거하거나 주석 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-266">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="00ef7-267">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-267">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="00ef7-268">이 버전의 프로젝트 동작은 "비동기 솔루션을 테스트하려면" 절차에서 설명한 동작과 일치해야 하지만 사용자의 노력은 훨씬 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-268">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <a name="BKMK_CompleteCodeExamples"></a> <span data-ttu-id="00ef7-269">예제</span><span class="sxs-lookup"><span data-stu-id="00ef7-269">Example</span></span>  
 <span data-ttu-id="00ef7-270">다음 코드는 직접 작성한 `GetURLContentsAsync` 메서드를 사용하여 동기 솔루션에서 비동기 솔루션으로 변환하는 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-270">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="00ef7-271">원래의 동기 솔루션과 매우 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-271">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            resultsTextBox.Clear();  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            // Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                byte[] urlContents = await GetURLContentsAsync(url);  
  
                // The previous line abbreviates the following two assignment statements.  
  
                // GetURLContentsAsync returns a Task<T>. At completion, the task  
                // produces a byte array.  
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.            
                total += urlContents.Length;  
            }  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        private async Task<byte[]> GetURLContentsAsync(string url)  
        {  
            // The downloaded resource ends up in the variable named content.  
            var content = new MemoryStream();  
  
            // Initialize an HttpWebRequest for the current URL.  
            var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
            // Send the request to the Internet resource and wait for  
            // the response.                  
            using (WebResponse response = await webReq.GetResponseAsync())  
  
            // The previous statement abbreviates the following two statements.  
  
            //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
            //using (WebResponse response = await responseTask)  
            {  
                // Get the data stream that is associated with the specified url.  
                using (Stream responseStream = response.GetResponseStream())  
                {  
                    // Read the bytes in responseStream and copy them to content.   
                    await responseStream.CopyToAsync(content);  
  
                    // The previous statement abbreviates the following two statements.  
  
                    // CopyToAsync returns a Task, not a Task<T>.  
                    //Task copyTask = responseStream.CopyToAsync(content);  
  
                    // When copyTask is completed, content contains a copy of  
                    // responseStream.  
                    //await copyTask;  
                }  
            }  
            // Return the result as a byte array.  
            return content.ToArray();  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="00ef7-272">다음 코드는 `HttpClient` 메서드 `GetByteArrayAsync`를 사용하는 솔루션에 대한 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="00ef7-272">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            //// Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Declare an HttpClient object and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                // GetByteArrayAsync returns a task. At completion, the task  
                // produces a byte array.  
                byte[] urlContents = await client.GetByteArrayAsync(url);                 
  
                // The following two lines can replace the previous assignment statement.  
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.  
                total += urlContents.Length;  
            }  
  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="00ef7-273">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00ef7-273">See Also</span></span>  
 [<span data-ttu-id="00ef7-274">Async 샘플: 웹 연습에 액세스(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00ef7-274">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)  
 [<span data-ttu-id="00ef7-275">async</span><span class="sxs-lookup"><span data-stu-id="00ef7-275">async</span></span>](../../../../csharp/language-reference/keywords/async.md)  
 [<span data-ttu-id="00ef7-276">await</span><span class="sxs-lookup"><span data-stu-id="00ef7-276">await</span></span>](../../../../csharp/language-reference/keywords/await.md)  
 [<span data-ttu-id="00ef7-277">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="00ef7-277">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="00ef7-278">비동기 반환 형식(C#)</span><span class="sxs-lookup"><span data-stu-id="00ef7-278">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)  
 [<span data-ttu-id="00ef7-279">TAP(작업 기반 비동기 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="00ef7-279">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=19957)  
 [<span data-ttu-id="00ef7-280">방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)</span><span class="sxs-lookup"><span data-stu-id="00ef7-280">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)  
 [<span data-ttu-id="00ef7-281">방법: Async 및 Await를 사용하여 병렬로 여러 웹 요청 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="00ef7-281">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
