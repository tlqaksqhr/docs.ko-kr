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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)
더 쉽고 직관적으로에 도입 된 기능을 사용 하 여 비동기 프로그램을 작성할 수 [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)]합니다. 동기 코드처럼 보이는 비동기 코드를 작성하고 일반적으로 비동기 코드에 수반되는 어려운 콜백 함수 및 연속 작업을 컴파일러에서 처리하도록 할 수 있습니다.  
  
 비동기 기능에 대 한 자세한 내용은 참조 [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
 이 연습은 웹 사이트 목록에 있는 바이트 수의 합계를 계산하는 동기 WPF(Windows Presentation Foundation) 응용 프로그램에서 시작합니다. 그런 다음 새로운 기능을 사용하여 응용 프로그램을 비동기 솔루션으로 변환합니다.  
  
 응용 프로그램을 직접 작성 하지 않으려는 경우 다운로드할 수 있습니다 "Async 샘플: 웹 연습 (C# 및 Visual Basic)에 액세스 하기"에서 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)합니다.  
  
 이 연습에서는 다음 작업을 완료합니다.  
  
-   [WPF 응용 프로그램을 만들려면](#CreateWPFApp)  
  
-   [간단한 WPF MainWindow를 디자인 하려면](#MainWindow)  
  
-   [참조를 추가 하려면](#AddRef)  
  
-   [필요한 Import 문 추가 하려면](#ImportsState)  
  
-   [동기 응용 프로그램을 만들려면](#synchronous)  
  
-   [동기 솔루션을 테스트 하려면](#testSynch)  
  
-   [GetURLContents를 비동기 메서드로 변환 하려면](#GetURLContents)  
  
-   [SumPageSizes를 비동기 메서드로 변환 하려면](#SumPageSizes)  
  
-   [StartButton_Click을 비동기 메서드로 변환 하려면](#startButton)  
  
-   [비동기 솔루션을 테스트 하려면](#testAsynch)  
  
-   [GetURLContentsAsync 메서드는.NET Framework 메서드로 바꾸려면](#GetURLContentsAsync)  
  
-   [예제](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a>필수 조건  
 Visual Studio 2012 이상이 컴퓨터에 설치 되어야 합니다. 자세한 내용은 참조는 [Microsoft 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=235233)합니다.  
  
###  <a name="CreateWPFApp"></a>WPF 응용 프로그램을 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  에 **설치 된 템플릿** 창에서 Visual Basic을 선택한 다음 선택 **WPF 응용 프로그램** 프로젝트 형식 목록에서.  
  
4.  에 **이름** 텍스트 상자에 입력 합니다 `AsyncExampleWPF`를 선택한 다음는 **확인** 단추입니다.  
  
     새 프로젝트가 표시 **솔루션 탐색기**합니다.  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a>간단한 WPF MainWindow를 디자인 하려면  
  
1.  Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.  
  
2.  경우는 **도구 상자** 창이 표시, 열기 않은 **보기** 메뉴를 선택한 다음 **도구 상자**합니다.  
  
3.  추가 **단추** 컨트롤 및 **TextBox** 컨트롤을 **MainWindow** 창입니다.  
  
4.  강조 표시는 **TextBox** 컨트롤에는 **속성** 창에서 다음 값을 설정 합니다.  
  
    -   설정의 **이름** 속성을 `resultsTextBox`합니다.  
  
    -   설정의 **높이** 250 속성입니다.  
  
    -   설정의 **너비** 500 속성입니다.  
  
    -   에 **텍스트** 탭에서 운영 체제에 따라 또는 전역 Monospace 등의 고정 폭 글꼴을 지정 합니다.  
  
5.  강조 표시는 **단추** 컨트롤에는 **속성** 창에서 다음 값을 설정 합니다.  
  
    -   설정의 **이름** 속성을 `startButton`합니다.  
  
    -   값을 변경 하는 **콘텐츠** 속성에서 **단추** 를 **시작**합니다.  
  
6.  동시에 표시 되도록 텍스트 상자와 단추를 배치는 **MainWindow** 창입니다.  
  
     WPF XAML 디자이너에 대 한 자세한 내용은 참조 [XAML 디자이너를 사용 하 여 UI 만들기](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)합니다.  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a>참조를 추가 하려면  
  
1.  **솔루션 탐색기**, 프로젝트의 이름을 강조 표시 합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **참조 추가**합니다.  
  
     **참조 관리자** 대화 상자가 나타납니다.  
  
3.  대화 상자 맨 위에 있는 프로젝트는.NET Framework 4.5 이상를 대상으로 확인 합니다.  
  
4.  에 **어셈블리** 영역에서 선택 **프레임 워크** 선택 되어 있지 않으면.  
  
5.  이름 목록에서 선택 된 **System.Net.Http** 확인란입니다.  
  
6.  선택 된 **확인** 단추 대화 상자를 닫습니다.  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="ImportsState"></a>필요한 Import 문 추가 하려면  
  
1.  **솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.  
  
2.  다음 코드를 추가 `Imports` 경우 이미 존재 하는 코드 파일 맨 위에 있는 문.  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a>동기 응용 프로그램을 만들려면  
  
1.  디자인 창에서 MainWindow.xaml 두 번 클릭은 **시작** 만들기 단추는 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.  
  
2.  본문에 다음 코드를 복사, MainWindow.xaml.vb에서 `startButton_Click`:  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     이 코드는 응용 프로그램 `SumPageSizes`를 구동하는 메서드를 호출하고 컨트롤이 `startButton_Click`으로 반환될 때 메시지를 표시합니다.  
  
3.  동기 솔루션에 대한 코드에는 다음 네 가지 메서드가 포함되어 있습니다.  
  
    -   `SumPageSizes` - `SetUpURLList`에서 웹 페이지 URL 목록을 가져온 다음 `GetURLContents` 및 `DisplayResults`를 호출하여 각 URL을 처리합니다.  
  
    -   `SetUpURLList` - 웹 주소 목록을 만들어 반환합니다.  
  
    -   `GetURLContents` - 각 웹 사이트의 콘텐츠를 다운로드하고 해당 콘텐츠를 바이트 배열로 반환합니다.  
  
    -   `DisplayResults`- 각 URL에 대한 바이트 배열의 바이트 수를 표시합니다.  
  
     다음 네 가지 메서드를 복사한 다음 아래에 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기가 있습니다.  
  
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
###  <a name="testSynch"></a>동기 솔루션을 테스트 하려면  
  
1.  F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     다음 목록과 유사한 출력이 표시되어야 합니다.  
  
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
  
     개수를 표시하려면 몇 초 정도 걸릴 수 있습니다. 이 시간 동안 UI 스레드는 차단되어 요청한 리소스가 다운로드될 때까지 기다립니다. 결과적으로 이동할 수 없습니다 최대화, 최소화, 또는 선택한 후 표시 창의 닫을 **시작** 단추입니다. 이러한 작업은 바이트 개수가 나타나기 시작할 때까지 실패합니다. 웹 사이트가 응답하지 않는 경우 실패한 사이트를 표시하지 않아도 됩니다. 대기를 중지하고 프로그램을 닫는 것도 어렵습니다.  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a>GetURLContents를 비동기 메서드로 변환 하려면  
  
1.  시작 하는 것이 좋습니다 중인 동기 솔루션을 비동기 솔루션을 변환 하려면 `GetURLContents` 때문에에 대 한 호출에서 <xref:System.Net.HttpWebRequest>메서드 <xref:System.Net.HttpWebRequest.GetResponse%2A>와 <xref:System.IO.Stream>메서드 <xref:System.IO.Stream.CopyTo%2A>여기서 응용 프로그램 웹에 액세스 하는.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest> .NET Framework는 두 메서드의 비동기 버전을 제공하여 변환을 쉽게 만듭니다.  
  
     사용 되는 방법에 대 한 자세한 내용은 `GetURLContents`, <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest> 를 참조 하십시오.  
  
    > [!NOTE]
    >  이 연습 단계를 수행하면 여러 가지 컴파일러 오류가 표시됩니다. 이러한 오류는 무시하고 연습을 진행할 수 있습니다.  
  
     세 번째 줄에서 라고 하는 방법을 변경 `GetURLContents` 에서 `GetResponse` 는 비동기 작업 기반 <xref:System.Net.WebRequest.GetResponseAsync%2A>메서드.</xref:System.Net.WebRequest.GetResponseAsync%2A>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  `GetResponseAsync`<xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 를 반환합니다. 이 경우에 *작업 반환 변수*, `TResult`, 형식이 <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse> 작업은 요청한 데이터를 다운로드하고 작업을 실행하여 완료한 후 실제 `WebResponse` 개체를 생성한다는 약속입니다.  
  
     검색 하는 `WebResponse` 작업에서 값을 적용 한 [Await](../../../../visual-basic/language-reference/operators/await-operator.md) 연산자에 대 한 호출으로 `GetResponseAsync`다음 코드와 같이 합니다.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
     `Await` 연산자 현재 메서드의 실행을 일시 중단 `GetURLContents`대기 중인된 작업이 완료 될 때까지, 합니다. 반면, 컨트롤은 현재 메서드의 호출자에게 반환됩니다. 이 예제에서 현재 메서드는 `GetURLContents`이고 호출자는 `SumPageSizes`입니다. 작업이 완료되면 약속된 `WebResponse` 개체가 대기 중인 작업의 값으로 생성되고 `response` 변수에 할당됩니다.  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
     `webReq.GetResponseAsync`를 호출하면 `Task(Of WebResponse)` 또는 `Task<WebResponse>`가 반환됩니다. 아니라면 `Await` 연산자가 검색 하는 작업에 적용 된 `WebResponse` 값입니다.  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  추가 했기 때문에 `Await` 연산자는 이전 단계에서 컴파일러 오류가 발생 합니다. 로 표시 된 메서드에만에서 연산자를 사용할 수는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다. `CopyTo` 호출을 `CopyToAsync` 호출로 바꾸는 변환 단계를 반복하는 동안에는 오류를 무시합니다.  
  
    -   <xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A> 라고 하는 메서드의 이름을 변경 합니다.  
  
    -   `CopyTo` 또는 `CopyToAsync` 메서드는 바이트를 해당 인수 `content`에 복사하고 의미 있는 값을 반환하지 않습니다. 동기 버전에서 `CopyTo` 호출은 값을 반환하지 않는 단순 문입니다. 비동기 버전 `CopyToAsync`, <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> 를 반환 합니다. 작업은 "Task(void)"처럼 작동하고 메서드를 대기하도록 합니다. 다음 코드에 표시된 대로 `Await` 또는 `await`를 `CopyToAsync` 호출에 적용합니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
         위의 문은 다음 두 줄의 코드를 줄여서 표시한 것입니다.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
4.  `GetURLContents`에서 수행해야 할 나머지 작업은 메서드 서명을 조정하는 것입니다. 사용할 수는 `Await` 메서드에만 표시 된 연산자는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다. 메서드도 표시 하 고 한정자를 추가 *비동기 메서드의*다음 코드와 같이 합니다.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
5.  비동기 메서드의 반환 형식 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> 수만 있습니다. Visual Basic에서 메서드는 `Task` 또는 `Task(Of T)`를 반환하는 `Function`이거나 `Sub`여야 합니다. 일반적으로 `Sub` 메서드는 비동기 이벤트 처리기 에서만에서 사용 됩니다 여기서 `Sub` 가 필요 합니다. 그 밖의 경우 사용 하 여 `Task(T)` 완료 된 메서드에 경우에 [반환](../../../../visual-basic/language-reference/statements/return-statement.md) 형식 T의 값을 반환 하는 문을 사용 하 `Task` 완성 된 메서드 의미 있는 값을 반환 하는 경우.  
  
     자세한 내용은 참조 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.  
  
     `GetURLContents` 메서드에는 return 문이 있고 이 문은 바이트 배열을 반환합니다. 따라서 비동기 버전의 반환 형식은 Task(T)이며, 여기서 T는 바이트 배열입니다. 다음과 같이 메서드 서명을 변경합니다.  
  
    -   반환 형식을 변경 하 `Task(Of Byte())`합니다.  
  
    -   규칙에 따라 비동기 메서드에는 "Async"로 끝나는 이름이 있으므로 `GetURLContentsAsync` 메서드의 이름을 바꿉니다.  
  
     다음 코드에서는 이러한 변경을 보여 줍니다.  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     몇 가지 변경 작업을 통해 `GetURLContents`가 비동기 메서드로 변환되었습니다.  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a>SumPageSizes를 비동기 메서드로 변환 하려면  
  
1.  `SumPageSizes`에 대한 이전 절차의 단계를 반복합니다. 먼저 `GetURLContents` 호출을 비동기 호출로 변경합니다.  
  
    -   호출되는 메서드의 이름을 `GetURLContents`에서 `GetURLContentsAsync`로 변경하지 않은 경우 지금 변경합니다.  
  
    -   적용 `Await` 작업에는 `GetURLContentsAsync` 배열 값을 반환 하는 바이트를 가져옵니다.  
  
     다음 코드에서는 이러한 변경을 보여 줍니다.  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     위의 할당은 다음 두 줄의 코드를 줄여서 표시한 것입니다.  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  메서드의 서명을 다음과 같이 변경합니다.  
  
    -   표시 된 메서드는 `Async` 한정자입니다.  
  
    -   메서드 이름에 "Async"를 추가합니다.  
  
    -   `SumPageSizesAsync`는 T에 대한 값을 반환하지 않으므로 이번에는 작업 반환 변수 T가 없습니다. (이 메서드에 no `Return` 문.) 그러나 메서드는 대기 가능하도록 `Task`를 반환해야 합니다. 따라서 메서드 형식을 변경 `Sub` 를 `Function`합니다. 함수의 반환 형식은 `Task`입니다.  
  
     다음 코드에서는 이러한 변경을 보여 줍니다.  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     `SumPageSizes`가 `SumPageSizesAsync`로 변환되었습니다.  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a>StartButton_Click을 비동기 메서드로 변환 하려면  
  
1.  이벤트 처리기에서 호출된 메서드의 이름을 `SumPageSizes`에서 `SumPageSizesAsync`로 변경하지 않은 경우 지금 변경합니다.  
  
2.  `SumPageSizesAsync`는 비동기 메서드이므로 이벤트 처리기에서 코드를 변경하여 결과를 대기합니다.  
  
     `SumPageSizesAsync` 호출은 `GetURLContentsAsync`에서 `CopyToAsync` 호출을 미러링합니다. 이 호출에서는 `Task(T)`가 아니라 `Task`를 반환합니다.  
  
     이전 절차에서처럼 한 개 또는 두 개의 문을 사용하여 호출을 변환할 수 있습니다. 다음 코드에서는 이러한 변경을 보여 줍니다.  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  실수로 작업을 다시 입력할 필요를 방지 하려면 다음 문을 맨 위에 있는 추가 `startButton_Click` 사용 하지 않도록 설정 하는 **시작** 단추입니다.  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     이벤트 처리기의 끝에서 단추를 다시 사용하도록 설정할 수 있습니다.  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     다시 표시 하는 방법에 대 한 자세한 내용은 참조 [비동기 응용 프로그램 (Visual Basic)에서 재진입 처리](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)합니다.  
  
4.  마지막으로 추가 된 `Async` 한정자는 선언에 이벤트 처리기 await 수 있도록 `SumPagSizesAsync`합니다.  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     일반적으로 이벤트 처리기의 이름은 변경되지 않습니다. 반환 형식에 변경 되지 않고 `Task` 이벤트 처리기 수 있어야 하므로 `Sub` Visual Basic의 프로시저입니다.  
  
     동기에서 비동기 처리로 프로젝트 변환이 완료되었습니다.  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a>비동기 솔루션을 테스트 하려면  
  
1.  F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
2.  동기 솔루션의 출력과 유사한 출력이 표시되어야 합니다. 그러나 다음과 같은 차이가 있습니다.  
  
    -   처리가 완료된 후 결과가 모두 동시에 발생하지는 않습니다. 예를 들어 두 프로그램 모두 텍스트 상자를 지우는 줄을 `startButton_Click`에 포함할 수 있습니다. 선택 하는 경우 실행 사이 있는 텍스트 상자 선택을 취소 하기 위한 것은 **시작** 하나의 결과 집합에 표시 되 면, 두 번째 시간에 대 한 단추입니다. 동기 버전에서는 다운로드가 완료되고 UI 스레드에서 자유롭게 다른 작업을 수행할 수 있게 되면 두 번째로 개수가 표시되기 직전에 텍스트 상자가 지워집니다. 비동기 버전의 텍스트 상자를 지웁니다 선택한 후 바로 **시작** 단추입니다.  
  
    -   가장 중요한 점은 다운로드하는 동안 UI 스레드가 차단되지 않는다는 것입니다. 웹 리소스를 다운로드하고, 개수를 계산하고, 표시하는 동안 창을 이동하거나 크기를 조정할 수 있습니다. 하나는 웹 사이트 느리거나 경우 응답 하지 않을 수 작업을 취소할 수를 선택 하 여는 **닫기** 단추 (오른쪽 위 모서리에 빨간색 필드에 x).  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a>GetURLContentsAsync 메서드는.NET Framework 메서드로 바꾸려면  
  
1.  .NET Framework 4.5는 사용할 수 있는 다양한 비동기 메서드를 제공합니다. 그 중 하나는 <xref:System.Net.Http.HttpClient>메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>,이 연습에 필요한 것만 않습니다.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient> 이전 절차에서 만든 `GetURLContentsAsync` 메서드 대신 사용할 수도 있습니다.  
  
     첫 번째 단계로 `SumPageSizesAsync` 메서드에서 `HttpClient` 개체를 만듭니다. 메서드의 시작 부분에 다음 선언을 추가합니다.  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  `SumPageSizesAsync,`에서 `GetURLContentsAsync` 메서드 호출을 `HttpClient` 메서드 호출로 바꿉니다.  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  작성한 `GetURLContentsAsync` 메서드를 제거하거나 주석 처리합니다.  
  
4.  F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     이 버전의 프로젝트 동작은 "비동기 솔루션을 테스트하려면" 절차에서 설명한 동작과 일치해야 하지만 사용자의 노력은 훨씬 줄어듭니다.  
  
##  <a name="BKMK_CompleteCodeExamples"></a>예제  
 다음 코드는 직접 작성한 `GetURLContentsAsync` 메서드를 사용하여 동기 솔루션에서 비동기 솔루션으로 변환하는 전체 예제입니다. 원래의 동기 솔루션과 매우 유사해야 합니다.  
  
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
  
 다음 코드는 `HttpClient` 메서드 `GetByteArrayAsync`를 사용하는 솔루션에 대한 전체 예제입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [Async 샘플: 웹 연습 (C# 및 Visual Basic) 액세스](http://go.microsoft.com/fwlink/?LinkId=255191)   
 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)   
 [비동기](../../../../visual-basic/language-reference/modifiers/async.md)   
 [비동기 프로그래밍 async 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [비동기 반환 형식 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)   
 [작업 기반 비동기 프로그래밍 (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847)   
 [방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)   
 [방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
