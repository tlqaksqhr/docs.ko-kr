---
title: 비동기 프로그램 (Visual Basic)의 제어 흐름
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: a6783373f4b556694fd79401546665b09f55919d
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728507"
---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="2d620-102">비동기 프로그램 (Visual Basic)의 제어 흐름</span><span class="sxs-lookup"><span data-stu-id="2d620-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="2d620-103">`Async` 및 `Await` 키워드를 사용하면 비동기 프로그램을 더 쉽게 쓰고 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="2d620-104">그러나 프로그램 작동 방식을 이해하지 못한다면 결과가 놀라울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="2d620-105">이 항목에서는 간단한 비동기 프로그램을 통해 제어 흐름을 추적하여 언제 메서드 간에 제어가 이동되고 매번 어떤 정보가 전달되는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d620-106">`Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="2d620-107">사용 하 여 비동기 코드를 포함 하는 메서드를 표시 하는 일반적으로 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="2d620-108">Async 한정자로 표시 된 메서드에서 사용할 수 있습니다는 [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) 메서드는 호출된 된 비동기 프로세스를 완료 하려면 기다려야 일시 중지 하는 위치를 지정 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="2d620-109">자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="2d620-110">다음 예제에서는 비동기 메서드를 사용하여 지정된 웹 사이트의 콘텐츠를 문자열로 다운로드하고 문자열 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="2d620-111">예제에는 다음 두 가지 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="2d620-112">`startButton_Click` - `AccessTheWebAsync`를 호출하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="2d620-113">`AccessTheWebAsync` - 웹 사이트의 콘텐츠를 문자열로 다운로드하고 문자열의 길이를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="2d620-114">`AccessTheWebAsync`는 비동기 <xref:System.Net.Http.HttpClient> 메서드인 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>을 사용하여 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="2d620-115">전체 프로그램에서 전략적 지점에 번호가 매겨진 표시 줄이 나타나 프로그램 실행 방식을 이해하도록 도와주고 표시된 각 지점에서 수행되는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="2d620-116">표시 줄에는 "ONE"~"SIX"의 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="2d620-117">레이블은 프로그램이 이러한 코드 줄에 도달하는 순서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="2d620-118">다음 코드에서는 프로그램의 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-118">The following code shows an outline of the program.</span></span>  
  
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
  
 <span data-ttu-id="2d620-119">"ONE"~"SIX"의 레이블이 지정된 각 위치에는 프로그램의 현재 상태에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="2d620-120">다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-120">The following output is produced.</span></span>  
  
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
  
## <a name="set-up-the-program"></a><span data-ttu-id="2d620-121">프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="2d620-121">Set Up the Program</span></span>  
 <span data-ttu-id="2d620-122">이 항목에서 사용하는 코드를 MSDN에서 다운로드하거나 직접 코드를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d620-123">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 그 이상 버전이 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="2d620-124">프로그램 다운로드</span><span class="sxs-lookup"><span data-stu-id="2d620-124">Download the Program</span></span>  
 <span data-ttu-id="2d620-125">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)(Async 샘플: 비동기 프로그램의 제어 흐름(C# 및 Visual Basic))에서 이 항목에 대한 응용 프로그램을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="2d620-126">다음 단계에서 프로그램을 열고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="2d620-127">다운로드한 파일의 압축을 풀고 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2d620-128">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="2d620-129">압축을 푼 샘플 코드가 포함된 폴더로 이동하고, 솔루션(.sln) 파일을 열고, F5 키를 선택하여 프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="2d620-130">프로그램 직접 빌드</span><span class="sxs-lookup"><span data-stu-id="2d620-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="2d620-131">다음 WPF(Windows Presentation Foundation) 프로젝트는 이 항목의 코드 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="2d620-132">프로젝트를 실행하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="2d620-133">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2d620-134">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="2d620-135">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2d620-136">에 **설치 된 템플릿** 창 선택 **Visual Basic**를 선택한 후 **WPF 응용 프로그램** 프로젝트 형식 목록에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="2d620-137">프로젝트의 이름으로 `AsyncTracer`를 입력한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="2d620-138">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="2d620-139">Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="2d620-140">탭이 표시되지 않는 경우 **솔루션 탐색기**에서 MainWindow.xaml의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="2d620-141">MainWindow.xaml의 **XAML** 보기에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
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
  
     <span data-ttu-id="2d620-142">텍스트 상자와 단추가 포함된 간단한 창이 MainWindow.xaml의 **디자인** 보기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="2d620-143"><xref:System.Net.Http>에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="2d620-144">**솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 후 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="2d620-145">MainWindow.xaml.vb에서 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
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
  
10. <span data-ttu-id="2d620-146">F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="2d620-147">다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-147">The following output should appear.</span></span>  
  
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
  
## <a name="trace-the-program"></a><span data-ttu-id="2d620-148">프로그램 추적</span><span class="sxs-lookup"><span data-stu-id="2d620-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="2d620-149">1, 2단계</span><span class="sxs-lookup"><span data-stu-id="2d620-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="2d620-150">처음 두 표시 줄은 `startButton_Click`이 `AccessTheWebAsync`를 호출하고, `AccessTheWebAsync`가 비동기 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>을 호출할 때 경로를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="2d620-151">다음 그림은 메서드 간의 호출을 간단히 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="2d620-152">![1단계 및 2단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="2d620-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="2d620-153">`AccessTheWebAsync` 및 `client.GetStringAsync`의 반환 형식은 둘 다 <xref:System.Threading.Tasks.Task%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="2d620-154">`AccessTheWebAsync`의 경우 TResult는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="2d620-155">`GetStringAsync`의 경우 TResult는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="2d620-156">비동기 메서드 반환 형식에 대 한 자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="2d620-157">제어가 다시 호출자로 이동할 때 작업 반환 비동기 메서드는 작업 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="2d620-158">호출된 메서드에서 `Await` 연산자가 발견되거나 호출된 메서드가 종료될 때 제어는 비동기 메서드에서 호출자로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="2d620-159">"THREE"~"SIX"의 레이블이 지정된 표시 줄은 이 프로세스 부분을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="2d620-160">3단계</span><span class="sxs-lookup"><span data-stu-id="2d620-160">Step THREE</span></span>  
 <span data-ttu-id="2d620-161">`AccessTheWebAsync`에서 비동기 메서드 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>을 호출하여 대상 웹 페이지의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="2d620-162">`client.GetStringAsync`가 반환되면 제어가 `client.GetStringAsync`에서 `AccessTheWebAsync`로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="2d620-163">`client.GetStringAsync` 메서드는 `AccessTheWebAsync`의 `getStringTask` 변수에 할당된 문자열의 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="2d620-164">예제 프로그램의 다음 줄은 `client.GetStringAsync` 호출 및 할당을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
```vb  
Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
```  
  
 <span data-ttu-id="2d620-165">작업은 결국 실제 문자열을 생성하기 위한 `client.GetStringAsync`의 약속으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-165">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="2d620-166">그리고 `client.GetStringAsync`의 약속된 문자열을 사용하지 않는 작업이 `AccessTheWebAsync`에 있는 경우 `client.GetStringAsync`가 대기하는 동안 해당 작업이 계속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-166">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="2d620-167">예제에서 "THREE" 레이블이 지정된 다음 출력 줄은 독립 작업을 수행할 기회를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-167">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>  
  
```  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
```  
  
 <span data-ttu-id="2d620-168">다음 문은 `getStringTask`가 대기 상태일 때 `AccessTheWebAsync`의 진행을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-168">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
```vb  
Dim urlContents As String = Await getStringTask  
```  
  
 <span data-ttu-id="2d620-169">다음 이미지에서 제어 흐름을 보여 줍니다. `client.GetStringAsync` 에 대 한 할당을 `getStringTask` 의 생성 및 `getStringTask` Await 연산자의 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-169">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="2d620-170">![3단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span><span class="sxs-lookup"><span data-stu-id="2d620-170">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="2d620-171">await 식은 `client.GetStringAsync`가 반환될 때까지 `AccessTheWebAsync`를 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-171">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="2d620-172">그리고 제어는 `AccessTheWebAsync`의 호출자, `startButton_Click`으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-172">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d620-173">일반적으로 즉시 비동기 메서드에 대한 호출을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-173">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="2d620-174">예를 들어 다음 할당은 `getStringTask`를 만들고 기다리는 이전 코드를 대체할 수 있습니다. `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`.</span><span class="sxs-lookup"><span data-stu-id="2d620-174">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="2d620-175">이 항목에서 await 연산자는 나중에 프로그램을 통해 제어 흐름을 표시하는 출력 줄을 수용하기 위해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-175">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="2d620-176">4단계</span><span class="sxs-lookup"><span data-stu-id="2d620-176">Step FOUR</span></span>  
 <span data-ttu-id="2d620-177">`AccessTheWebAsync`의 선언된 반환 형식은 `Task(Of Integer)`입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-177">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="2d620-178">따라서 `AccessTheWebAsync`가 일시 중단될 경우 정수 작업을 `startButton_Click`으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-178">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="2d620-179">반환된 작업이 `getStringTask`가 아니라는 것을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-179">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="2d620-180">반환된 작업은 일시 중단된 메서드 `AccessTheWebAsync`에서 수행하도록 남아 있는 작업을 나타내는 새로운 정수 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-180">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="2d620-181">작업은 작업이 완료될 때 정수를 생성하기 위한 `AccessTheWebAsync`의 약속입니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-181">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="2d620-182">다음 문은 이 작업을 `getLengthTask` 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-182">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
```vb  
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
```  
  
 <span data-ttu-id="2d620-183">`AccessTheWebAsync`에서처럼 `startButton_Click`은 작업이 대기 상태가 될 때까지 비동기 작업(`getLengthTask`)의 결과를 사용하지 않는 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-183">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="2d620-184">다음 출력 줄은 해당 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-184">The following output lines represent that work.</span></span>  
  
```  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
```  
  
 <span data-ttu-id="2d620-185">`startButton_Click`의 진행은 `getLengthTask`가 대기 상태일 때 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-185">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="2d620-186">다음 대입문은 `AccessTheWebAsync`가 완료될 때까지 `startButton_Click`을 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-186">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
```vb  
Dim contentLength As Integer = Await getLengthTask  
```  
  
 <span data-ttu-id="2d620-187">다음 그림에서 화살표는 `AccessTheWebAsync`의 await 식에서 `getLengthTask`에 대한 값 할당으로의 제어 흐름에 이어 `getLengthTask`가 대기 상태가 될 때까지 `startButton_Click`의 일반적인 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-187">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="2d620-188">![4단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="2d620-188">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="2d620-189">5단계</span><span class="sxs-lookup"><span data-stu-id="2d620-189">Step FIVE</span></span>  
 <span data-ttu-id="2d620-190">`client.GetStringAsync`가 완료되었음을 알리면 `AccessTheWebAsync` 처리는 일시 중단이 해제되고 await 문을 무시하고 계속 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-190">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="2d620-191">다음 출력 줄은 처리 다시 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-191">The following lines of output represent the resumption of processing.</span></span>  
  
```  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
```  
  
 <span data-ttu-id="2d620-192">return 문의 피연산자, `urlContents.Length`는 `AccessTheWebAsync`가 반환하는 작업에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-192">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="2d620-193">await 식은 `startButton_Click`의 `getLengthTask`에서 해당 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-193">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="2d620-194">다음 그림은 `client.GetStringAsync`(및 `getStringTask`)가 완료된 후 제어의 전송을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-194">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="2d620-195">![5단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="2d620-195">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="2d620-196">`AccessTheWebAsync`는 완료될 때까지 실행되고 제어는 완료를 기다리고 있는 `startButton_Click`으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-196">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="2d620-197">6단계</span><span class="sxs-lookup"><span data-stu-id="2d620-197">Step SIX</span></span>  
 <span data-ttu-id="2d620-198">`AccessTheWebAsync`가 완료되었음을 알리면 처리는 `startButton_Async`의 await 문을 무시하고 계속 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-198">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="2d620-199">실제로 프로그램에는 추가로 수행할 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-199">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="2d620-200">다음 출력 줄은 `startButton_Async`의 처리 다시 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-200">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
```  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
```  
  
 <span data-ttu-id="2d620-201">await 식은 `getLengthTask`에서 `AccessTheWebAsync`에 있는 return 문의 피연산자인 정수 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-201">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="2d620-202">다음 문은 이 해당 값을 `contentLength` 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-202">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
```vb  
Dim contentLength As Integer = Await getLengthTask  
```  
  
 <span data-ttu-id="2d620-203">다음 그림은 `AccessTheWebAsync`에서 `startButton_Click`로의 제어 반환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d620-203">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="2d620-204">![6단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="2d620-204">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d620-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d620-205">See Also</span></span>  
 [<span data-ttu-id="2d620-206">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d620-206">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="2d620-207">비동기 반환 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d620-207">Async Return Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)  
 [<span data-ttu-id="2d620-208">연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d620-208">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 <span data-ttu-id="2d620-209">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)(Async 샘플: 비동기 프로그램의 제어 흐름(C# 및 Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="2d620-209">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)</span></span>
