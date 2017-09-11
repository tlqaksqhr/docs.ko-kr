---
title: "비동기 프로그램 (Visual Basic)의 흐름 제어 | Microsoft 문서"
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
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
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="fd96f-102">비동기 프로그램 (Visual Basic)의 제어 흐름</span><span class="sxs-lookup"><span data-stu-id="fd96f-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="fd96f-103">작성 하 고 사용 하 여 비동기 프로그램을 더욱 쉽게 유지할 수는 `Async` 및 `Await` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="fd96f-104">그러나 결과 놀라운 프로그램의 작동 방식을 이해 되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="fd96f-105">이 항목의 컨트롤에서 한 가지 방법은 다른 및 어떤 정보를 이동 하는 경우 표시 하는 간단한 비동기 프로그램을 통해 제어 흐름 때마다 전송 되를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd96f-106">`Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="fd96f-107">사용 하 여 비동기 코드를 포함 하는 메서드를 표시 하는 일반적으로 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="fd96f-108">Async 한정자로 표시 된 메서드를 사용할 수 있습니다는 [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) 호출된 비동기 프로세스가 완료 될 때까지 대기 하는 메서드 일시 중지 하는 위치를 지정 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="fd96f-109">자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="fd96f-110">문자열로 지정된 된 웹 사이트의 콘텐츠를 다운로드 하 고 문자열의 길이 표시 하려면 다음 예제에서는 비동기 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="fd96f-111">이 예제에는 다음 두 가지 방법 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="fd96f-112">`startButton_Click`를 호출 하 `AccessTheWebAsync` 결과 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="fd96f-113">`AccessTheWebAsync`를 문자열로 웹 사이트의 내용을 다운로드 하 고 문자열의 길이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="fd96f-114">`AccessTheWebAsync`사용 하 여 비동기 <xref:System.Net.Http.HttpClient>메서드를 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, 콘텐츠 다운로드.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="fd96f-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="fd96f-115">디스플레이 선이 표시 되는 프로그램이 실행 되는 방법을 이해할 수 있도록 하 고 표시 된 각 지점에서 발생 하는 기능을 설명 하는 프로그램 전체에 걸쳐 중요 한 지점에 번호가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="fd96f-116">표시 줄에는 레이블이 지정 "1"부터 "6."</span><span class="sxs-lookup"><span data-stu-id="fd96f-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="fd96f-117">레이블은은 프로그램 코드의 다음이 줄을 도달 하는 순서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="fd96f-118">다음 코드에서는 프로그램의 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-118">The following code shows an outline of the program.</span></span>  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 <span data-ttu-id="fd96f-119">각 "1"부터 "6," 레이블이 지정 된 위치, 프로그램의 현재 상태에 대 한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="fd96f-120">다음과 같은 출력이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-120">The following output is produced.</span></span>  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a><span data-ttu-id="fd96f-121">프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="fd96f-121">Set Up the Program</span></span>  
 <span data-ttu-id="fd96f-122">MSDN에서이 항목에서 사용 하는 코드를 다운로드할 수 또는 직접 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd96f-123">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="fd96f-124">프로그램 다운로드</span><span class="sxs-lookup"><span data-stu-id="fd96f-124">Download the Program</span></span>  
 <span data-ttu-id="fd96f-125">이 항목에 대 한 응용 프로그램을 다운로드할 수 있습니다 [Async 샘플: 비동기 프로그램의 제어 흐름](http://go.microsoft.com/fwlink/?LinkId=255285)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span></span> <span data-ttu-id="fd96f-126">다음 단계를 열고 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="fd96f-127">다운로드 한 파일을 압축 하 고 Visual Studio를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fd96f-128">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="fd96f-129">압축 푼된 샘플 코드를 포함 하는 폴더로 이동한 솔루션 (.sln) 파일을 열고 빌드하고 프로젝트를 실행 하려면 F5 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="fd96f-130">프로그램 직접 빌드</span><span class="sxs-lookup"><span data-stu-id="fd96f-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="fd96f-131">다음 Windows Presentation Foundation (WPF) 프로젝트에는이 항목에 대 한 코드 예제에서는 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="fd96f-132">프로젝트를 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="fd96f-133">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fd96f-134">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="fd96f-135">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fd96f-136">에 **설치 된 템플릿** 창에서 선택 **Visual Basic**를 선택한 다음 **WPF 응용 프로그램** 의 프로젝트 형식 목록에서.</span><span class="sxs-lookup"><span data-stu-id="fd96f-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="fd96f-137">입력 `AsyncTracer` , 프로젝트의 이름으로 선택 하 고는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="fd96f-138">새 프로젝트가 표시 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="fd96f-139">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="fd96f-140">탭이 표시 되지 않으면 mainwindow.xaml의 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="fd96f-141">에 **XAML** MainWindow.xaml의 보기에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="fd96f-142">에 텍스트 상자와 단추가 포함 된 간단한 창이 표시는 **디자인** MainWindow.xaml의 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="fd96f-143"><xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="fd96f-144">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="fd96f-145">MainWindow.xaml.vb에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. <span data-ttu-id="fd96f-146">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="fd96f-147">다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-147">The following output should appear.</span></span>  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a><span data-ttu-id="fd96f-148">프로그램 추적</span><span class="sxs-lookup"><span data-stu-id="fd96f-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="fd96f-149">1단계 및&2;단계</span><span class="sxs-lookup"><span data-stu-id="fd96f-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="fd96f-150">으로 경로 추적 하는 처음 두 표시 줄 `startButton_Click` 호출 `AccessTheWebAsync`, 및 `AccessTheWebAsync` 비동기 <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> 메서드</xref:System.Net.Http.HttpClient> 호출</span><span class="sxs-lookup"><span data-stu-id="fd96f-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="fd96f-151">다음 이미지는 메서드를 호출 하 여 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="fd96f-152">![1,&2; 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")</span><span class="sxs-lookup"><span data-stu-id="fd96f-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="fd96f-153">반환 유형은 둘 다 `AccessTheWebAsync` 및 `client.GetStringAsync` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 는</span><span class="sxs-lookup"><span data-stu-id="fd96f-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fd96f-154">에 대 한 `AccessTheWebAsync`, TResult는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="fd96f-155">에 대 한 `GetStringAsync`, TResult가 문자열인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="fd96f-156">비동기 메서드 반환 형식에 대 한 자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="fd96f-157">작업 반환 비동기 메서드를 다시 호출자로 컨트롤이 이동 하면 작업 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="fd96f-158">비동기 메서드는 호출자에 게 제어가 반환 하거나 경우에는 `Await` 메서드가 또는 호출된 된 메서드가 종료 시점에 연산자가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="fd96f-159">"3"부터 "6" 레이블이 지정 된 표시 줄 프로세스의이 부분을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="fd96f-160">3단계</span><span class="sxs-lookup"><span data-stu-id="fd96f-160">Step THREE</span></span>  
 <span data-ttu-id="fd96f-161">`AccessTheWebAsync`, 비동기 메서드의 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>대상 웹 페이지의 콘텐츠를 다운로드 하기 위해 호출 됩니다.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="fd96f-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="fd96f-162">컨트롤이 반환 `client.GetStringAsync` 를 `AccessTheWebAsync` 때 `client.GetStringAsync` 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="fd96f-163">`client.GetStringAsync` 에 할당 된 문자열의 작업을 반환 하는 메서드는 `getStringTask` 변수에 `AccessTheWebAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="fd96f-164">예제 프로그램의 다음 줄에 대 한 호출을 보여 줍니다. `client.GetStringAsync` 및 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
<span data-ttu-id="fd96f-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-166">Promise로 서 하 여 작업의 생각할 수 있습니다 `client.GetStringAsync` 결국는 실제 문자열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="fd96f-167">그동안 경우 `AccessTheWebAsync` 약속된 문자열에 의존 하지 않는 작업을 수행 `client.GetStringAsync`, 작업을 계속할 수 동안 `client.GetStringAsync` 될 때까지 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="fd96f-168">예제에서는 레이블이 "3"는 출력의 다음 줄 나타내는 독립적인 작업을 수행할 수 있는 기회</span><span class="sxs-lookup"><span data-stu-id="fd96f-168">In the example, the following lines of output, which are labeled "THREE,” represent the opportunity to do independent work</span></span>  
  
<span data-ttu-id="fd96f-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-170">다음 문은에서 진행 상황을 일시 중단 `AccessTheWebAsync` 때 `getStringTask` 에 대기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-170">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
<span data-ttu-id="fd96f-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-172">다음 그림에서는 컨트롤의 흐름을 보여 줍니다. `client.GetStringAsync` 에 대 한 할당을 `getStringTask` 의 생성 및 `getStringTask` Await 연산자 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-172">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="fd96f-173">![3 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace&3;")</span><span class="sxs-lookup"><span data-stu-id="fd96f-173">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="fd96f-174">Await 식을 일시 중단 `AccessTheWebAsync` 될 때까지 `client.GetStringAsync` 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-174">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="fd96f-175">컨트롤의 호출자에 게 반환 하는 한편, `AccessTheWebAsync`, `startButton_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-175">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd96f-176">일반적으로 기다릴는 비동기 메서드 호출을 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-176">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="fd96f-177">예를 들어, 다음 할당을 만들고 다음 대기 하는 앞의 코드를 대체할 수 `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="fd96f-177">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="fd96f-178">이 항목에서는 await 연산자는 프로그램을 통해 제어 흐름을 표시 하는 출력 행을 수용 하기 위해 나중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-178">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="fd96f-179">4단계</span><span class="sxs-lookup"><span data-stu-id="fd96f-179">Step FOUR</span></span>  
 <span data-ttu-id="fd96f-180">선언 된 반환 형식이 `AccessTheWebAsync` 는 `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-180">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="fd96f-181">따라서, `AccessTheWebAsync` 는 정수를 작업을 반환 하기 일시 중단 `startButton_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-181">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="fd96f-182">반환된 된 작업이 없음을 이해 해야 `getStringTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-182">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="fd96f-183">반환 된 작업은 일시 중단 된 메서드에서 수행할 남은 것을 나타내는 정수는 새 작업 `AccessTheWebAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-183">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="fd96f-184">이 작업은에서 약속 `AccessTheWebAsync` 작업이 완료 되 면 정수를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-184">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="fd96f-185">다음 문은 대입 하 여이 작업은 `getLengthTask` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-185">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
<span data-ttu-id="fd96f-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-187">와 같이 `AccessTheWebAsync`, `startButton_Click` 는 비동기 작업의 결과에 의존 하지 않는 작업 계속할 수 있습니다 (`getLengthTask`) 작업은 대기 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-187">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="fd96f-188">다음 출력 줄 해당 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-188">The following output lines represent that work.</span></span>  
  
<span data-ttu-id="fd96f-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-190">진행 `startButton_Click` 때 일시 중단 됩니다 `getLengthTask` 에 대기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-190">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="fd96f-191">다음 대입문을 일시 중단 `startButton_Click` 될 때까지 `AccessTheWebAsync` 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-191">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
<span data-ttu-id="fd96f-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-193">다음 그림에서는 화살표 await 식에서 제어 흐름을 보여 줍니다. `AccessTheWebAsync` 값을 할당에 `getLengthTask`, 정상적인 처리에 차례로 `startButton_Click` 될 때까지 `getLengthTask` 대기 않으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-193">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="fd96f-194">![4 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace&4;")</span><span class="sxs-lookup"><span data-stu-id="fd96f-194">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="fd96f-195">5단계</span><span class="sxs-lookup"><span data-stu-id="fd96f-195">Step FIVE</span></span>  
 <span data-ttu-id="fd96f-196">때 `client.GetStringAsync` 처리 완료 되었음을 알리는 `AccessTheWebAsync` 일시 중단에서 해제 되 고 await 문에서 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-196">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="fd96f-197">출력의 다음 줄 다시 처리 하기 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-197">The following lines of output represent the resumption of processing.</span></span>  
  
<span data-ttu-id="fd96f-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-199">Return 문의 피연산자 `urlContents.Length`, 작업에 저장 하는 `AccessTheWebAsync` 를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-199">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="fd96f-200">Await 식에서 해당 값을 검색 `getLengthTask` 에서 `startButton_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-200">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="fd96f-201">다음 이미지는 다음 컨트롤의 전송을 표시 `client.GetStringAsync` (및 `getStringTask`)를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-201">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="fd96f-202">![5 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace&5;")</span><span class="sxs-lookup"><span data-stu-id="fd96f-202">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="fd96f-203">`AccessTheWebAsync`실행 완료 및 제어를 반환 `startButton_Click`, 완료 대기 중이입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-203">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="fd96f-204">6단계</span><span class="sxs-lookup"><span data-stu-id="fd96f-204">Step SIX</span></span>  
 <span data-ttu-id="fd96f-205">때 `AccessTheWebAsync` 신호 처리 완료를 await 문에서 계속할 수 `startButton_Async`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-205">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="fd96f-206">실제로 프로그램에 더 많은 아무 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-206">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="fd96f-207">출력의 다음 줄에서의 처리 다시 시작을 나타내는 `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="fd96f-207">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
<span data-ttu-id="fd96f-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-209">Await 식에서 검색 `getLengthTask` 의 return 문에의 피연산자는 정수 값 `AccessTheWebAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-209">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="fd96f-210">다음 문은에 해당 값을 할당은 `contentLength` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-210">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
<span data-ttu-id="fd96f-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd96f-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="fd96f-212">다음 이미지는 컨트롤에서 반환 되는 표시 `AccessTheWebAsync` 를 `startButton_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd96f-212">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="fd96f-213">![6 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace&6;")</span><span class="sxs-lookup"><span data-stu-id="fd96f-213">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd96f-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd96f-214">See Also</span></span>  
 <span data-ttu-id="fd96f-215">[비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd96f-215">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="fd96f-216"> [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="fd96f-216"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="fd96f-217"> [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="fd96f-217"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="fd96f-218"> [비동기 프로그램 (C# 및 Visual Basic)의 Async 샘플: 제어 흐름](http://go.microsoft.com/fwlink/?LinkId=255285)</span><span class="sxs-lookup"><span data-stu-id="fd96f-218"> [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span></span>
