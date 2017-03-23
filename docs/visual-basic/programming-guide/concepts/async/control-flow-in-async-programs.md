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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a>비동기 프로그램 (Visual Basic)의 제어 흐름
작성 하 고 사용 하 여 비동기 프로그램을 더욱 쉽게 유지할 수는 `Async` 및 `Await` 키워드입니다. 그러나 결과 놀라운 프로그램의 작동 방식을 이해 되지 않아도 됩니다. 이 항목의 컨트롤에서 한 가지 방법은 다른 및 어떤 정보를 이동 하는 경우 표시 하는 간단한 비동기 프로그램을 통해 제어 흐름 때마다 전송 되를 추적 합니다.  
  
> [!NOTE]
>  `Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.  
  
 사용 하 여 비동기 코드를 포함 하는 메서드를 표시 하는 일반적으로 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다. Async 한정자로 표시 된 메서드를 사용할 수 있습니다는 [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) 호출된 비동기 프로세스가 완료 될 때까지 대기 하는 메서드 일시 중지 하는 위치를 지정 하는 연산자입니다. 자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
 문자열로 지정된 된 웹 사이트의 콘텐츠를 다운로드 하 고 문자열의 길이 표시 하려면 다음 예제에서는 비동기 메서드를 사용 합니다. 이 예제에는 다음 두 가지 방법 포함 되어 있습니다.  
  
-   `startButton_Click`를 호출 하 `AccessTheWebAsync` 결과 표시 합니다.  
  
-   `AccessTheWebAsync`를 문자열로 웹 사이트의 내용을 다운로드 하 고 문자열의 길이 반환 합니다. `AccessTheWebAsync`사용 하 여 비동기 <xref:System.Net.Http.HttpClient>메서드를 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, 콘텐츠 다운로드.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient>  
  
 디스플레이 선이 표시 되는 프로그램이 실행 되는 방법을 이해할 수 있도록 하 고 표시 된 각 지점에서 발생 하는 기능을 설명 하는 프로그램 전체에 걸쳐 중요 한 지점에 번호가 지정 됩니다. 표시 줄에는 레이블이 지정 "1"부터 "6." 레이블은은 프로그램 코드의 다음이 줄을 도달 하는 순서를 나타냅니다.  
  
 다음 코드에서는 프로그램의 개요를 보여 줍니다.  
  
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
  
 각 "1"부터 "6," 레이블이 지정 된 위치, 프로그램의 현재 상태에 대 한 정보를 표시합니다. 다음과 같은 출력이 생성 됩니다.  
  
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
  
## <a name="set-up-the-program"></a>프로그램 설정  
 MSDN에서이 항목에서 사용 하는 코드를 다운로드할 수 또는 직접 빌드할 수 있습니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
### <a name="download-the-program"></a>프로그램 다운로드  
 이 항목에 대 한 응용 프로그램을 다운로드할 수 있습니다 [Async 샘플: 비동기 프로그램의 제어 흐름](http://go.microsoft.com/fwlink/?LinkId=255285)합니다. 다음 단계를 열고 프로그램을 실행 합니다.  
  
1.  다운로드 한 파일을 압축 하 고 Visual Studio를 시작 합니다.  
  
2.  메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.  
  
3.  압축 푼된 샘플 코드를 포함 하는 폴더로 이동한 솔루션 (.sln) 파일을 열고 빌드하고 프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
### <a name="build-the-program-yourself"></a>프로그램 직접 빌드  
 다음 Windows Presentation Foundation (WPF) 프로젝트에는이 항목에 대 한 코드 예제에서는 포함 되어 있습니다.  
  
 프로젝트를 실행하려면 다음 단계를 수행합니다.  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  에 **설치 된 템플릿** 창에서 선택 **Visual Basic**를 선택한 다음 **WPF 응용 프로그램** 의 프로젝트 형식 목록에서.  
  
4.  입력 `AsyncTracer` , 프로젝트의 이름으로 선택 하 고는 **확인** 단추입니다.  
  
     새 프로젝트가 표시 **솔루션 탐색기**합니다.  
  
5.  Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.  
  
     탭이 표시 되지 않으면 mainwindow.xaml의 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 다음 **코드 보기**합니다.  
  
6.  에 **XAML** MainWindow.xaml의 보기에서 코드를 다음 코드로 바꿉니다.  
  
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
  
     에 텍스트 상자와 단추가 포함 된 간단한 창이 표시는 **디자인** MainWindow.xaml의 보기입니다.  
  
7.  <xref:System.Net.Http>.</xref:System.Net.Http> 에 대 한 참조를 추가 합니다.  
  
8.  **솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.  
  
9. MainWindow.xaml.vb에서 코드를 다음 코드로 바꿉니다.  
  
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
  
10. F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     다음과 같은 출력이 표시됩니다.  
  
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
  
## <a name="trace-the-program"></a>프로그램 추적  
  
### <a name="steps-one-and-two"></a>1단계 및&2;단계  
 으로 경로 추적 하는 처음 두 표시 줄 `startButton_Click` 호출 `AccessTheWebAsync`, 및 `AccessTheWebAsync` 비동기 <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> 메서드</xref:System.Net.Http.HttpClient> 호출 다음 이미지는 메서드를 호출 하 여 간략하게 설명합니다.  
  
 ![1,&2; 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")  
  
 반환 유형은 둘 다 `AccessTheWebAsync` 및 `client.GetStringAsync` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 는 에 대 한 `AccessTheWebAsync`, TResult는 정수입니다. 에 대 한 `GetStringAsync`, TResult가 문자열인 합니다. 비동기 메서드 반환 형식에 대 한 자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.  
  
 작업 반환 비동기 메서드를 다시 호출자로 컨트롤이 이동 하면 작업 인스턴스를 반환 합니다. 비동기 메서드는 호출자에 게 제어가 반환 하거나 경우에는 `Await` 메서드가 또는 호출된 된 메서드가 종료 시점에 연산자가 발생 합니다. "3"부터 "6" 레이블이 지정 된 표시 줄 프로세스의이 부분을 추적 합니다.  
  
### <a name="step-three"></a>3단계  
 `AccessTheWebAsync`, 비동기 메서드의 <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>대상 웹 페이지의 콘텐츠를 다운로드 하기 위해 호출 됩니다.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> 컨트롤이 반환 `client.GetStringAsync` 를 `AccessTheWebAsync` 때 `client.GetStringAsync` 를 반환 합니다.  
  
 `client.GetStringAsync` 에 할당 된 문자열의 작업을 반환 하는 메서드는 `getStringTask` 변수에 `AccessTheWebAsync`합니다. 예제 프로그램의 다음 줄에 대 한 호출을 보여 줍니다. `client.GetStringAsync` 및 할당 합니다.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Promise로 서 하 여 작업의 생각할 수 있습니다 `client.GetStringAsync` 결국는 실제 문자열을 생성 합니다. 그동안 경우 `AccessTheWebAsync` 약속된 문자열에 의존 하지 않는 작업을 수행 `client.GetStringAsync`, 작업을 계속할 수 동안 `client.GetStringAsync` 될 때까지 대기 합니다. 예제에서는 레이블이 "3"는 출력의 다음 줄 나타내는 독립적인 작업을 수행할 수 있는 기회  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
 다음 문은에서 진행 상황을 일시 중단 `AccessTheWebAsync` 때 `getStringTask` 에 대기 됩니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
 다음 그림에서는 컨트롤의 흐름을 보여 줍니다. `client.GetStringAsync` 에 대 한 할당을 `getStringTask` 의 생성 및 `getStringTask` Await 연산자 응용 프로그램에 있습니다.  
  
 ![3 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace&3;")  
  
 Await 식을 일시 중단 `AccessTheWebAsync` 될 때까지 `client.GetStringAsync` 를 반환 합니다. 컨트롤의 호출자에 게 반환 하는 한편, `AccessTheWebAsync`, `startButton_Click`합니다.  
  
> [!NOTE]
>  일반적으로 기다릴는 비동기 메서드 호출을 즉시 합니다. 예를 들어, 다음 할당을 만들고 다음 대기 하는 앞의 코드를 대체할 수 `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`  
>   
>  이 항목에서는 await 연산자는 프로그램을 통해 제어 흐름을 표시 하는 출력 행을 수용 하기 위해 나중에 적용 됩니다.  
  
### <a name="step-four"></a>4단계  
 선언 된 반환 형식이 `AccessTheWebAsync` 는 `Task(Of Integer)`합니다. 따라서, `AccessTheWebAsync` 는 정수를 작업을 반환 하기 일시 중단 `startButton_Click`합니다. 반환된 된 작업이 없음을 이해 해야 `getStringTask`합니다. 반환 된 작업은 일시 중단 된 메서드에서 수행할 남은 것을 나타내는 정수는 새 작업 `AccessTheWebAsync`합니다. 이 작업은에서 약속 `AccessTheWebAsync` 작업이 완료 되 면 정수를 생성 합니다.  
  
 다음 문은 대입 하 여이 작업은 `getLengthTask` 변수입니다.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 와 같이 `AccessTheWebAsync`, `startButton_Click` 는 비동기 작업의 결과에 의존 하지 않는 작업 계속할 수 있습니다 (`getLengthTask`) 작업은 대기 될 때까지 합니다. 다음 출력 줄 해당 작업을 나타냅니다.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 진행 `startButton_Click` 때 일시 중단 됩니다 `getLengthTask` 에 대기 됩니다. 다음 대입문을 일시 중단 `startButton_Click` 될 때까지 `AccessTheWebAsync` 완료 되었습니다.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
 다음 그림에서는 화살표 await 식에서 제어 흐름을 보여 줍니다. `AccessTheWebAsync` 값을 할당에 `getLengthTask`, 정상적인 처리에 차례로 `startButton_Click` 될 때까지 `getLengthTask` 대기 않으므로 합니다.  
  
 ![4 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace&4;")  
  
### <a name="step-five"></a>5단계  
 때 `client.GetStringAsync` 처리 완료 되었음을 알리는 `AccessTheWebAsync` 일시 중단에서 해제 되 고 await 문에서 계속할 수 있습니다. 출력의 다음 줄 다시 처리 하기 시작을 나타냅니다.  
  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 Return 문의 피연산자 `urlContents.Length`, 작업에 저장 하는 `AccessTheWebAsync` 를 반환 합니다. Await 식에서 해당 값을 검색 `getLengthTask` 에서 `startButton_Click`합니다.  
  
 다음 이미지는 다음 컨트롤의 전송을 표시 `client.GetStringAsync` (및 `getStringTask`)를 완료 합니다.  
  
 ![5 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace&5;")  
  
 `AccessTheWebAsync`실행 완료 및 제어를 반환 `startButton_Click`, 완료 대기 중이입니다.  
  
### <a name="step-six"></a>6단계  
 때 `AccessTheWebAsync` 신호 처리 완료를 await 문에서 계속할 수 `startButton_Async`합니다. 실제로 프로그램에 더 많은 아무 관련이 없습니다.  
  
 출력의 다음 줄에서의 처리 다시 시작을 나타내는 `startButton_Async`:  
  
<CodeContentPlaceHolder>12</CodeContentPlaceHolder>  
 Await 식에서 검색 `getLengthTask` 의 return 문에의 피연산자는 정수 값 `AccessTheWebAsync`합니다. 다음 문은에 해당 값을 할당은 `contentLength` 변수입니다.  
  
<CodeContentPlaceHolder>13</CodeContentPlaceHolder>  
 다음 이미지는 컨트롤에서 반환 되는 표시 `AccessTheWebAsync` 를 `startButton_Click`합니다.  
  
 ![6 단계](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace&6;")  
  
## <a name="see-also"></a>참고 항목  
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기 프로그램 (C# 및 Visual Basic)의 Async 샘플: 제어 흐름](http://go.microsoft.com/fwlink/?LinkId=255285)
