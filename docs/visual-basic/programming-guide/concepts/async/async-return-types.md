---
title: "비동기 반환 형식 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
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
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a>비동기 반환 형식 (Visual Basic)
비동기 메서드는 세 가지 가능한 반환 형식은: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, void 및.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Visual Basic의 경우 반환 형식이 void로 작성 되는 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저입니다. 비동기 메서드에 대 한 자세한 내용은 참조 하십시오. [Async 및 Await (Visual Basic)를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
 다음 섹션 중 하나에서 각 반환 형식을 살펴보고 세 가지 형식 모두를 사용하는 전체 예제는 이 항목의 끝에 나와 있습니다.  
  
> [!NOTE]
>  예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.  
  
##  <a name="BKMK_TaskTReturnType"></a>Task (t) 반환 형식  
 <xref:System.Threading.Tasks.Task%601>반환 형식을 포함 하는 비동기 메서드에 사용 되는 [반환](../../../../visual-basic/language-reference/statements/return-statement.md) 문이 있는 피연산자 형식 `TResult`.</xref:System.Threading.Tasks.Task%601>  
  
 다음 예제에서는 `TaskOfT_MethodAsync` 비동기 메서드는 정수를 반환 하는 return 문을 포함 합니다. 따라서 메서드 선언에서의 반환 형식을 지정 해야 `Task(Of Integer)`합니다.  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 때 `TaskOfT_MethodAsync` 라고에서 await 식에서 await 식의 정수 값을 검색 (값 `leisureHours`)에서 반환 되는 작업에 저장 된 `TaskOfT_MethodAsync`합니다. 에 대 한 자세한 내용은 await 표현을 참조 하십시오 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)합니다.  
  
 다음 코드를 호출 하 고 메서드를 기다립니다 `TaskOfT_MethodAsync`합니다. 결과에 할당 되는 `result1` 변수입니다.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 이에 대 한 호출을 구분 하 여 문제가 발생 하는 방법을 더 잘 이해할 수 `TaskOfT_MethodAsync` 의 응용 프로그램에서 `Await`다음 코드와 같이 합니다. 메서드를 호출 `TaskOfT_MethodAsync` 대기 중이 던된 즉시 반환이 아닌는 `Task(Of Integer)`메서드의 선언에서 예상 대로입니다. 작업에 할당 되는 `integerTask` 예에서 변수입니다. 때문에 `integerTask` 는 <xref:System.Threading.Tasks.Task%601>, 포함 된 한 <xref:System.Threading.Tasks.Task%601.Result>형식의 속성 `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601> 이 경우 TResult는 정수 형식을 나타냅니다. 때 `Await` 적용할 `integerTask`, await 식이의 내용에는 <xref:System.Threading.Tasks.Task%601.Result%2A>속성 `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A> 값에 할당 되는 `result2` 변수입니다.  
  
> [!WARNING]
>  <xref:System.Threading.Tasks.Task%601.Result%2A>속성은 차단 속성.</xref:System.Threading.Tasks.Task%601.Result%2A> 해당 작업이 완료되기 전에 액세스하려고 하면, 작업이 완료되고 값을 사용할 수 있을 때까지 현재 활성화된 스레드가 차단됩니다. 사용 하 여 값 액세스 해야 하는 대부분의 경우에서 `Await` 속성에 직접 액세스 하는 대신 합니다.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 디스플레이 문을 다음 코드에서를 확인 하는 값은 `result1` 변수는 `result2` 변수를 및 `Result` 속성은 동일 합니다. 유의 해야는 `Result` 속성은 차단 속성 및 해당 작업에 대기 되지 전에 액세스 해서는 안 되 합니다.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a>작업 반환 형식  
 Return 문을 포함 하지는 또는 일반적으로 피연산자를 반환 하지 않는 return 문이 포함 하는 비동기 메서드는 <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> 의 반환 형식 이러한 메서드는 것 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저 동기적으로 실행 하도록 작성 된 것입니다. 사용 하는 경우는 `Task` 형식을 반환 비동기 메서드를 호출 하는 메서드에서 사용할 수는 `Await` 연산자를 호출된 된 비동기 메서드에서 끝날 때까지 호출자의 완료를 일시 중단 합니다.  
  
 다음 예제에서는 비동기 메서드 `Task_MethodAsync` return 문이 포함 되어 있지 않습니다. 반환 형식을 지정 하는 따라서 `Task` 메서드의 수 있도록 `Task_MethodAsync` 를 대기할 수 있습니다. 정의 `Task` 형식이 포함 되지 않습니다는 `Result` 속성을 반환 값을 저장 합니다.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync`호출 하 고 await 문에서 동기식 호출 문을 비슷합니다 await 식 대신 사용 하 여 대기 `Sub` 또는 메서드의 void를 반환 합니다. 응용 프로그램 `Await` 연산자가 경우 값을 생성 하지는 합니다.  
  
 다음 코드를 호출 하 고 메서드를 기다립니다 `Task_MethodAsync`합니다.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 이전 처럼 <xref:System.Threading.Tasks.Task%601>예제에 대 한 호출을 구분할 수 있습니다 `Task_MethodAsync` 의 응용 프로그램에서 한 `Await` 다음 코드와 같이 연산자.</xref:System.Threading.Tasks.Task%601> 그러나에 유의 해야는 `Task` 없는 `Result` 속성과 await 연산자에 적용 되는 값은 생성 되는 `Task`합니다.  
  
 호출을 구분 하는 다음 코드 `Task_MethodAsync` 에서 작업을 대기 하는 `Task_MethodAsync` 반환 합니다.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a>Void 반환 형식  
 주된 용도 `Sub` 프로시저는 이벤트 처리기의 경우 (다른 언어의 반환 형식이 void 라고도 함) 반환 형식이 없습니다. void 반환은 또한 "실행 후 제거"로 분류할 수 있는 작업을 수행하는 메서드 또는 viod를 반환하는 메서드를 재정의하는 데 사용할 수 있습니다. 하지만 반환 해야 한 `Task` 가능 void 반환 비동기 메서드를 대기할 수 없습니다. 이러한 메서드의 호출자는 호출된 비동기 메서드가 마치는 것을 기다리지 않고 완료될 때까지 계속 진행할 수 있어야 하므로, 해당 호출자는 비동기 메서드가 생성하는 모든 값 또는 예외와 독립되어 있어야 합니다.  
  
 void를 반환하는 비동기 메서드의 호출자는 메서드에서 throw되는 예외를 catch할 수 없으므로 이러한 처리되지 않은 예외를 사용하면 응용 프로그램이 실패할 수 있습니다. 비동기 메서드에서 반환 하는 경우 예외가 발생 한 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>, 예외가 반환된 된 작업에 저장 되 고 작업에 대 한 대기 하는 경우 다시 throw 합니다.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> 따라서 예외를 생성할 수 있는 비동기 메서드가의 반환 형식에 있는지를 확인 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>메서드를 호출 하는 대기 하 고.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 비동기 메서드에서 예외를 catch 하는 방법에 대 한 자세한 내용은 참조 [시도 중... Catch... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.  
  
 다음 코드는 비동기 이벤트 처리기를 정의합니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a>전체 예제  
 다음 WPF(Windows Presentation Foundation) 프로젝트는 이 항목의 코드 예제를 포함합니다.  
  
 프로젝트를 실행하려면 다음 단계를 수행합니다.  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  에 **설치 됨**, **템플릿** 범주를 선택 **Visual Basic**를 선택한 다음 **Windows**합니다. 선택 **WPF 응용 프로그램** 프로젝트 형식 목록에서.  
  
4.  입력 `AsyncReturnTypes` , 프로젝트의 이름으로 선택 하 고는 **확인** 단추입니다.  
  
     새 프로젝트가 표시 **솔루션 탐색기**합니다.  
  
5.  Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.  
  
     탭 보이지 않으면 mainwindow.xaml의 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 다음 **열고**합니다.  
  
6.  에 **XAML** MainWindow.xaml의 창 코드를 다음 코드로 바꿉니다.  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     에 텍스트 상자와 단추가 포함 된 간단한 창이 표시는 **디자인** MainWindow.xaml의 창.  
  
7.  **솔루션 탐색기**, MainWindow.xaml.vb에 대 한 바로 가기 메뉴를 열고 선택한 다음 **코드 보기**합니다.  
  
8.  MainWindow.xaml.vb의 코드를 다음 코드로 바꿉니다.  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     다음과 같은 출력이 표시됩니다.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A>   
 [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기 프로그램 (Visual Basic)의 제어 흐름](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [비동기](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md)
