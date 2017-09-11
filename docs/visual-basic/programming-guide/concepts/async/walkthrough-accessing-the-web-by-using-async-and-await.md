---
title: "비동기 웹 액세스 및 Await (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="ca5f0-102">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca5f0-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="ca5f0-103">더 쉽고 직관적으로에 도입 된 기능을 사용 하 여 비동기 프로그램을 작성할 수 [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-103">You can write asynchronous programs more easily and intuitively by using features that were introduced in [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span></span> <span data-ttu-id="ca5f0-104">동기 코드처럼 보이는 비동기 코드를 작성하고 일반적으로 비동기 코드에 수반되는 어려운 콜백 함수 및 연속 작업을 컴파일러에서 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="ca5f0-105">비동기 기능에 대 한 자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="ca5f0-106">이 연습은 웹 사이트 목록에 있는 바이트 수의 합계를 계산하는 동기 WPF(Windows Presentation Foundation) 응용 프로그램에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="ca5f0-107">그런 다음 새로운 기능을 사용하여 응용 프로그램을 비동기 솔루션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="ca5f0-108">응용 프로그램을 직접 작성 하지 않으려는 경우 다운로드할 수 있습니다 "Async 샘플: 웹 연습 (C# 및 Visual Basic)에 액세스 하기"에서 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="ca5f0-109">이 연습에서는 다음 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="ca5f0-110">WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="ca5f0-111">간단한 WPF MainWindow를 디자인 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="ca5f0-112">참조를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="ca5f0-113">필요한 Import 문 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-113">To add necessary Imports statements</span></span>](#ImportsState)  
  
-   [<span data-ttu-id="ca5f0-114">동기 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="ca5f0-115">동기 솔루션을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="ca5f0-116">GetURLContents를 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="ca5f0-117">SumPageSizes를 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="ca5f0-118">StartButton_Click을 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="ca5f0-119">비동기 솔루션을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="ca5f0-120">GetURLContentsAsync 메서드는.NET Framework 메서드로 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="ca5f0-121">예제</span><span class="sxs-lookup"><span data-stu-id="ca5f0-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="ca5f0-122">필수 조건</span><span class="sxs-lookup"><span data-stu-id="ca5f0-122">Prerequisites</span></span>  
 <span data-ttu-id="ca5f0-123">Visual Studio 2012 이상이 컴퓨터에 설치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="ca5f0-124">자세한 내용은 참조는 [Microsoft 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=235233)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="ca5f0-125"><a name="CreateWPFApp"></a>WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="ca5f0-126">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="ca5f0-127">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="ca5f0-128">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ca5f0-129">에 **설치 된 템플릿** 창에서 Visual Basic을 선택한 다음 선택 **WPF 응용 프로그램** 프로젝트 형식 목록에서.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="ca5f0-130">에 **이름** 텍스트 상자에 입력 합니다 `AsyncExampleWPF`를 선택한 다음는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="ca5f0-131">새 프로젝트가 표시 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="ca5f0-132"><a name="MainWindow"></a>간단한 WPF MainWindow를 디자인 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="ca5f0-133">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="ca5f0-134">경우는 **도구 상자** 창이 표시, 열기 않은 **보기** 메뉴를 선택한 다음 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="ca5f0-135">추가 **단추** 컨트롤 및 **TextBox** 컨트롤을 **MainWindow** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="ca5f0-136">강조 표시는 **TextBox** 컨트롤에는 **속성** 창에서 다음 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="ca5f0-137">설정의 **이름** 속성을 `resultsTextBox`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="ca5f0-138">설정의 **높이** 250 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="ca5f0-139">설정의 **너비** 500 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="ca5f0-140">에 **텍스트** 탭에서 운영 체제에 따라 또는 전역 Monospace 등의 고정 폭 글꼴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="ca5f0-141">강조 표시는 **단추** 컨트롤에는 **속성** 창에서 다음 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="ca5f0-142">설정의 **이름** 속성을 `startButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="ca5f0-143">값을 변경 하는 **콘텐츠** 속성에서 **단추** 를 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="ca5f0-144">동시에 표시 되도록 텍스트 상자와 단추를 배치는 **MainWindow** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="ca5f0-145">WPF XAML 디자이너에 대 한 자세한 내용은 참조 [XAML 디자이너를 사용 하 여 UI 만들기](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="ca5f0-146"><a name="AddRef"></a>참조를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="ca5f0-147">**솔루션 탐색기**, 프로젝트의 이름을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="ca5f0-148">메뉴 모음에서 **프로젝트**, **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="ca5f0-149">**참조 관리자** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="ca5f0-150">대화 상자 맨 위에 있는 프로젝트는.NET Framework 4.5 이상를 대상으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="ca5f0-151">에 **어셈블리** 영역에서 선택 **프레임 워크** 선택 되어 있지 않으면.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="ca5f0-152">이름 목록에서 선택 된 **System.Net.Http** 확인란입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="ca5f0-153">선택 된 **확인** 단추 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="ca5f0-154"><a name="ImportsState"></a>필요한 Import 문 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-154"><a name="ImportsState"></a> To add necessary Imports statements</span></span>  
  
1.  <span data-ttu-id="ca5f0-155">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="ca5f0-156">다음 코드를 추가 `Imports` 경우 이미 존재 하는 코드 파일 맨 위에 있는 문.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="ca5f0-157"><a name="synchronous"></a>동기 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="ca5f0-158">디자인 창에서 MainWindow.xaml 두 번 클릭은 **시작** 만들기 단추는 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="ca5f0-159">본문에 다음 코드를 복사, MainWindow.xaml.vb에서 `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="ca5f0-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     <span data-ttu-id="ca5f0-160">이 코드는 응용 프로그램 `SumPageSizes`를 구동하는 메서드를 호출하고 컨트롤이 `startButton_Click`으로 반환될 때 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="ca5f0-161">동기 솔루션에 대한 코드에는 다음 네 가지 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="ca5f0-162">`SumPageSizes` - `SetUpURLList`에서 웹 페이지 URL 목록을 가져온 다음 `GetURLContents` 및 `DisplayResults`를 호출하여 각 URL을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="ca5f0-163">`SetUpURLList` - 웹 주소 목록을 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="ca5f0-164">`GetURLContents` - 각 웹 사이트의 콘텐츠를 다운로드하고 해당 콘텐츠를 바이트 배열로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="ca5f0-165">`DisplayResults`- 각 URL에 대한 바이트 배열의 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="ca5f0-166">다음 네 가지 메서드를 복사한 다음 아래에 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>  
  
    ```vb  
    Private Sub SumPageSizes()  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetURLContents returns the contents of url as a byte array.  
            Dim urlContents As Byte() = GetURLContents(url)  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)  
    End Sub  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
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
            }  
        Return urls  
    End Function  
  
    Private Function GetURLContents(url As String) As Byte()  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        Using response As WebResponse = webReq.GetResponse()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <span data-ttu-id="ca5f0-167"><a name="testSynch"></a>동기 솔루션을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="ca5f0-168">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="ca5f0-169">다음 목록과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-169">Output that resembles the following list should appear.</span></span>  
  
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
  
     <span data-ttu-id="ca5f0-170">개수를 표시하려면 몇 초 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="ca5f0-171">이 시간 동안 UI 스레드는 차단되어 요청한 리소스가 다운로드될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="ca5f0-172">결과적으로 이동할 수 없습니다 최대화, 최소화, 또는 선택한 후 표시 창의 닫을 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="ca5f0-173">이러한 작업은 바이트 개수가 나타나기 시작할 때까지 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="ca5f0-174">웹 사이트가 응답하지 않는 경우 실패한 사이트를 표시하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="ca5f0-175">대기를 중지하고 프로그램을 닫는 것도 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="ca5f0-176"><a name="GetURLContents"></a>GetURLContents를 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="ca5f0-177">시작 하는 것이 좋습니다 중인 동기 솔루션을 비동기 솔루션을 변환 하려면 `GetURLContents` 때문에에 대 한 호출에서 <xref:System.Net.HttpWebRequest>메서드 <xref:System.Net.HttpWebRequest.GetResponse%2A>와 <xref:System.IO.Stream>메서드 <xref:System.IO.Stream.CopyTo%2A>여기서 응용 프로그램 웹에 액세스 하는.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest></span><span class="sxs-lookup"><span data-stu-id="ca5f0-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="ca5f0-178">.NET Framework는 두 메서드의 비동기 버전을 제공하여 변환을 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="ca5f0-179">사용 되는 방법에 대 한 자세한 내용은 `GetURLContents`, <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca5f0-180">이 연습 단계를 수행하면 여러 가지 컴파일러 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="ca5f0-181">이러한 오류는 무시하고 연습을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="ca5f0-182">세 번째 줄에서 라고 하는 방법을 변경 `GetURLContents` 에서 `GetResponse` 는 비동기 작업 기반 <xref:System.Net.WebRequest.GetResponseAsync%2A>메서드.</xref:System.Net.WebRequest.GetResponseAsync%2A></span><span class="sxs-lookup"><span data-stu-id="ca5f0-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  <span data-ttu-id="ca5f0-183">`GetResponseAsync`<xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ca5f0-184">이 경우에 *작업 반환 변수*, `TResult`, 형식이 <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse></span><span class="sxs-lookup"><span data-stu-id="ca5f0-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="ca5f0-185">작업은 요청한 데이터를 다운로드하고 작업을 실행하여 완료한 후 실제 `WebResponse` 개체를 생성한다는 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="ca5f0-186">검색 하는 `WebResponse` 작업에서 값을 적용 한 [Await](../../../../visual-basic/language-reference/operators/await-operator.md) 연산자에 대 한 호출으로 `GetResponseAsync`다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="ca5f0-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ca5f0-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="ca5f0-188">`Await` 연산자 현재 메서드의 실행을 일시 중단 `GetURLContents`대기 중인된 작업이 완료 될 때까지, 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-188">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="ca5f0-189">반면, 컨트롤은 현재 메서드의 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-189">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="ca5f0-190">이 예제에서 현재 메서드는 `GetURLContents`이고 호출자는 `SumPageSizes`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-190">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="ca5f0-191">작업이 완료되면 약속된 `WebResponse` 개체가 대기 중인 작업의 값으로 생성되고 `response` 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-191">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<span data-ttu-id="ca5f0-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ca5f0-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="ca5f0-193">`webReq.GetResponseAsync`를 호출하면 `Task(Of WebResponse)` 또는 `Task<WebResponse>`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-193">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="ca5f0-194">아니라면 `Await` 연산자가 검색 하는 작업에 적용 된 `WebResponse` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-194">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  <span data-ttu-id="ca5f0-195">추가 했기 때문에 `Await` 연산자는 이전 단계에서 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-195">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="ca5f0-196">로 표시 된 메서드에만에서 연산자를 사용할 수는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-196">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="ca5f0-197">`CopyTo` 호출을 `CopyToAsync` 호출로 바꾸는 변환 단계를 반복하는 동안에는 오류를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-197">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="ca5f0-198"><xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A> 라고 하는 메서드의 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-198">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="ca5f0-199">`CopyTo` 또는 `CopyToAsync` 메서드는 바이트를 해당 인수 `content`에 복사하고 의미 있는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-199">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="ca5f0-200">동기 버전에서 `CopyTo` 호출은 값을 반환하지 않는 단순 문입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-200">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="ca5f0-201">비동기 버전 `CopyToAsync`, <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-201">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="ca5f0-202">작업은 "Task(void)"처럼 작동하고 메서드를 대기하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-202">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="ca5f0-203">다음 코드에 표시된 대로 `Await` 또는 `await`를 `CopyToAsync` 호출에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-203">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="ca5f0-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ca5f0-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
         <span data-ttu-id="ca5f0-205">위의 문은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
<span data-ttu-id="ca5f0-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ca5f0-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="ca5f0-207">`GetURLContents`에서 수행해야 할 나머지 작업은 메서드 서명을 조정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-207">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="ca5f0-208">사용할 수는 `Await` 메서드에만 표시 된 연산자는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-208">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="ca5f0-209">메서드도 표시 하 고 한정자를 추가 *비동기 메서드의*다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-209">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
<span data-ttu-id="ca5f0-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="ca5f0-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
5.  <span data-ttu-id="ca5f0-211">비동기 메서드의 반환 형식 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-211">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ca5f0-212">Visual Basic에서 메서드는 `Task` 또는 `Task(Of T)`를 반환하는 `Function`이거나 `Sub`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-212">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="ca5f0-213">일반적으로 `Sub` 메서드는 비동기 이벤트 처리기 에서만에서 사용 됩니다 여기서 `Sub` 가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-213">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="ca5f0-214">그 밖의 경우 사용 하 여 `Task(T)` 완료 된 메서드에 경우에 [반환](../../../../visual-basic/language-reference/statements/return-statement.md) 형식 T의 값을 반환 하는 문을 사용 하 `Task` 완성 된 메서드 의미 있는 값을 반환 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-214">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>  
  
     <span data-ttu-id="ca5f0-215">자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-215">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="ca5f0-216">`GetURLContents` 메서드에는 return 문이 있고 이 문은 바이트 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-216">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="ca5f0-217">따라서 비동기 버전의 반환 형식은 Task(T)이며, 여기서 T는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-217">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="ca5f0-218">다음과 같이 메서드 서명을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-218">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="ca5f0-219">반환 형식을 변경 하 `Task(Of Byte())`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-219">Change the return type to `Task(Of Byte())`.</span></span>  
  
    -   <span data-ttu-id="ca5f0-220">규칙에 따라 비동기 메서드에는 "Async"로 끝나는 이름이 있으므로 `GetURLContentsAsync` 메서드의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-220">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="ca5f0-221">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-221">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     <span data-ttu-id="ca5f0-222">몇 가지 변경 작업을 통해 `GetURLContents`가 비동기 메서드로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-222">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="ca5f0-223"><a name="SumPageSizes"></a>SumPageSizes를 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-223"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="ca5f0-224">`SumPageSizes`에 대한 이전 절차의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-224">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="ca5f0-225">먼저 `GetURLContents` 호출을 비동기 호출로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-225">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="ca5f0-226">호출되는 메서드의 이름을 `GetURLContents`에서 `GetURLContentsAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-226">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="ca5f0-227">적용 `Await` 작업에는 `GetURLContentsAsync` 배열 값을 반환 하는 바이트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-227">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="ca5f0-228">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-228">The following code shows these changes.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     <span data-ttu-id="ca5f0-229">위의 할당은 다음 두 줄의 코드를 줄여서 표시한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-229">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  <span data-ttu-id="ca5f0-230">메서드의 서명을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-230">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="ca5f0-231">표시 된 메서드는 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-231">Mark the method with the `Async` modifier.</span></span>  
  
    -   <span data-ttu-id="ca5f0-232">메서드 이름에 "Async"를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-232">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="ca5f0-233">`SumPageSizesAsync`는 T에 대한 값을 반환하지 않으므로 이번에는 작업 반환 변수 T가 없습니다. (이 메서드에 no `Return` 문.) 그러나 메서드는 대기 가능하도록 `Task`를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-233">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="ca5f0-234">따라서 메서드 형식을 변경 `Sub` 를 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-234">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="ca5f0-235">함수의 반환 형식은 `Task`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-235">The return type of the function is `Task`.</span></span>  
  
     <span data-ttu-id="ca5f0-236">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-236">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     <span data-ttu-id="ca5f0-237">`SumPageSizes`가 `SumPageSizesAsync`로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-237">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="ca5f0-238"><a name="startButton"></a>StartButton_Click을 비동기 메서드로 변환 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-238"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="ca5f0-239">이벤트 처리기에서 호출된 메서드의 이름을 `SumPageSizes`에서 `SumPageSizesAsync`로 변경하지 않은 경우 지금 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-239">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="ca5f0-240">`SumPageSizesAsync`는 비동기 메서드이므로 이벤트 처리기에서 코드를 변경하여 결과를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-240">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="ca5f0-241">`SumPageSizesAsync` 호출은 `GetURLContentsAsync`에서 `CopyToAsync` 호출을 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-241">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="ca5f0-242">이 호출에서는 `Task(T)`가 아니라 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-242">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="ca5f0-243">이전 절차에서처럼 한 개 또는 두 개의 문을 사용하여 호출을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-243">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="ca5f0-244">다음 코드에서는 이러한 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-244">The following code shows these changes.</span></span>  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  <span data-ttu-id="ca5f0-245">실수로 작업을 다시 입력할 필요를 방지 하려면 다음 문을 맨 위에 있는 추가 `startButton_Click` 사용 하지 않도록 설정 하는 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-245">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     <span data-ttu-id="ca5f0-246">이벤트 처리기의 끝에서 단추를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-246">You can reenable the button at the end of the event handler.</span></span>  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     <span data-ttu-id="ca5f0-247">다시 표시 하는 방법에 대 한 자세한 내용은 참조 [비동기 응용 프로그램 (Visual Basic)에서 재진입 처리](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-247">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="ca5f0-248">마지막으로 추가 된 `Async` 한정자는 선언에 이벤트 처리기 await 수 있도록 `SumPagSizesAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-248">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     <span data-ttu-id="ca5f0-249">일반적으로 이벤트 처리기의 이름은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-249">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="ca5f0-250">반환 형식에 변경 되지 않고 `Task` 이벤트 처리기 수 있어야 하므로 `Sub` Visual Basic의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-250">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>  
  
     <span data-ttu-id="ca5f0-251">동기에서 비동기 처리로 프로젝트 변환이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-251">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="ca5f0-252"><a name="testAsynch"></a>비동기 솔루션을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-252"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="ca5f0-253">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-253">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="ca5f0-254">동기 솔루션의 출력과 유사한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-254">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="ca5f0-255">그러나 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-255">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="ca5f0-256">처리가 완료된 후 결과가 모두 동시에 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-256">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="ca5f0-257">예를 들어 두 프로그램 모두 텍스트 상자를 지우는 줄을 `startButton_Click`에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-257">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="ca5f0-258">선택 하는 경우 실행 사이 있는 텍스트 상자 선택을 취소 하기 위한 것은 **시작** 하나의 결과 집합에 표시 되 면, 두 번째 시간에 대 한 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-258">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="ca5f0-259">동기 버전에서는 다운로드가 완료되고 UI 스레드에서 자유롭게 다른 작업을 수행할 수 있게 되면 두 번째로 개수가 표시되기 직전에 텍스트 상자가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-259">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="ca5f0-260">비동기 버전의 텍스트 상자를 지웁니다 선택한 후 바로 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-260">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="ca5f0-261">가장 중요한 점은 다운로드하는 동안 UI 스레드가 차단되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-261">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="ca5f0-262">웹 리소스를 다운로드하고, 개수를 계산하고, 표시하는 동안 창을 이동하거나 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-262">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="ca5f0-263">하나는 웹 사이트 느리거나 경우 응답 하지 않을 수 작업을 취소할 수를 선택 하 여는 **닫기** 단추 (오른쪽 위 모서리에 빨간색 필드에 x).</span><span class="sxs-lookup"><span data-stu-id="ca5f0-263">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="ca5f0-264"><a name="GetURLContentsAsync"></a>GetURLContentsAsync 메서드는.NET Framework 메서드로 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="ca5f0-264"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="ca5f0-265">.NET Framework 4.5는 사용할 수 있는 다양한 비동기 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-265">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="ca5f0-266">그 중 하나는 <xref:System.Net.Http.HttpClient>메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>,이 연습에 필요한 것만 않습니다.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="ca5f0-266">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="ca5f0-267">이전 절차에서 만든 `GetURLContentsAsync` 메서드 대신 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-267">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="ca5f0-268">첫 번째 단계로 `SumPageSizesAsync` 메서드에서 `HttpClient` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-268">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="ca5f0-269">메서드의 시작 부분에 다음 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-269">Add the following declaration at the start of the method.</span></span>  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  <span data-ttu-id="ca5f0-270">`SumPageSizesAsync,`에서 `GetURLContentsAsync` 메서드 호출을 `HttpClient` 메서드 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-270">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  <span data-ttu-id="ca5f0-271">작성한 `GetURLContentsAsync` 메서드를 제거하거나 주석 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-271">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="ca5f0-272">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-272">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="ca5f0-273">이 버전의 프로젝트 동작은 "비동기 솔루션을 테스트하려면" 절차에서 설명한 동작과 일치해야 하지만 사용자의 노력은 훨씬 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-273">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="ca5f0-274"><a name="BKMK_CompleteCodeExamples"></a>예제</span><span class="sxs-lookup"><span data-stu-id="ca5f0-274"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="ca5f0-275">다음 코드는 직접 작성한 `GetURLContentsAsync` 메서드를 사용하여 동기 솔루션에서 비동기 솔루션으로 변환하는 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-275">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="ca5f0-276">원래의 동기 솔루션과 매우 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-276">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        ' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
            ' The previous line abbreviates the following two assignment statements.  
  
            '//<snippet21>  
            ' GetURLContentsAsync returns a task. At completion, the task  
            ' produces a byte array.  
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
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
            }  
        Return urls  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
  
            ' The previous statement abbreviates the following two statements.  
  
            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
            'Using response As WebResponse = Await responseTask  
  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                Await responseStream.CopyToAsync(content)  
  
                ' The previous statement abbreviates the following two statements.  
  
                ' CopyToAsync returns a Task, not a Task<T>.  
                'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
                ' When copyTask is completed, content contains a copy of  
                ' responseStream.  
                'Await copyTask  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 <span data-ttu-id="ca5f0-277">다음 코드는 `HttpClient` 메서드 `GetByteArrayAsync`를 사용하는 솔루션에 대한 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ca5f0-277">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetByteArrayAsync returns a task. At completion, the task  
            ' produces a byte array.  
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
            ' The following two lines can replace the previous assignment statement.  
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
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
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca5f0-278">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca5f0-278">See Also</span></span>  
 <span data-ttu-id="ca5f0-279">[Async 샘플: 웹 연습 (C# 및 Visual Basic) 액세스](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-279">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
<span data-ttu-id="ca5f0-280"> [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-280"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="ca5f0-281"> [비동기](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="ca5f0-282"> [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-282"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="ca5f0-283"> [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-283"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="ca5f0-284"> [작업 기반 비동기 프로그래밍 (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-284"> [Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
<span data-ttu-id="ca5f0-285"> [방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="ca5f0-285"> [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
<span data-ttu-id="ca5f0-286"> [방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="ca5f0-286"> [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
