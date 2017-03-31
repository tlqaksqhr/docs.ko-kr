---
title: "비동기 반환 형식(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4c1bab99fc1139f03e5f754cfecaee392b947171
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-c"></a>비동기 반환 형식(C#)
비동기 메서드에는 세 가지 가능한 반환 형식인 <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> 및 void가 있습니다. Visual Basic에서 void 반환 형식은 [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저로 작성합니다. 비동기 메서드에 대한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/async/index.md)을 참조하세요.  
  
 다음 섹션 중 하나에서 각 반환 형식을 살펴보고 세 가지 형식 모두를 사용하는 전체 예제는 이 항목의 끝에 나와 있습니다.  
  
> [!NOTE]
>  예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.  
  
##  <a name="BKMK_TaskTReturnType"></a> Task(T) 반환 형식  
 <xref:System.Threading.Tasks.Task%601> 반환 형식은 피연산자의 형식이 `TResult`인 [return](../../../../csharp/language-reference/keywords/return.md)(C#) 문이 포함된 비동기 메서드에 사용됩니다.  
  
 다음 예제에서 `TaskOfT_MethodAsync` 비동기 메서드는 정수를 반환하는 return 문을 포함합니다. 따라서 메서드 선언은 `Task<int>`의 반환 형식을 지정해야 합니다.  
  
```cs  
// TASK<T> EXAMPLE  
async Task<int> TaskOfT_MethodAsync()  
{  
    // The body of the method is expected to contain an awaited asynchronous  
    // call.  
    // Task.FromResult is a placeholder for actual work that returns a string.  
    var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
    // The method then can process the result in some way.  
    int leisureHours;  
    if (today.First() == 'S')  
        leisureHours = 16;  
    else  
        leisureHours = 5;  
  
    // Because the return statement specifies an operand of type int, the  
    // method must have a return type of Task<int>.  
    return leisureHours;  
}  
```  
  
 `TaskOfT_MethodAsync`를 await 식 내에서 호출하면 await 식이 `TaskOfT_MethodAsync`에서 반환된 작업에 저장된 정수 값(`leisureHours` 값)을 검색합니다. await 식에 대한 자세한 내용은 [await](../../../../csharp/language-reference/keywords/await.md)를 참조하세요.  
  
 다음 코드는 `TaskOfT_MethodAsync` 메서드를 호출하고 기다립니다. 결과는 `result1` 변수에 할당됩니다.  
  
```cs  
// Call and await the Task<T>-returning async method in the same statement.  
int result1 = await TaskOfT_MethodAsync();  
```  
  
 다음 코드와 같이 `TaskOfT_MethodAsync` 호출을 `await`의 적용과 구분하면 이 과정을 더욱 잘 이해할 수 있습니다. 곧바로 대기 상태가 되지 않는 `TaskOfT_MethodAsync` 메서드를 호출하면 메서드 선언에서 예상한 대로 `Task<int>`를 반환합니다. 예제에서 작업이 `integerTask` 변수에 할당됩니다. `integerTask`는 <xref:System.Threading.Tasks.Task%601>이므로 `TResult` 형식의 <xref:System.Threading.Tasks.Task%601.Result> 속성을 포함합니다. 이 경우 TResult는 정수 형식을 나타냅니다. `await`가 `integerTask`에 적용되는 경우 await 식은 `integerTask`의 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성 내용으로 평가됩니다. 값은 `result2` 변수에 할당됩니다.  
  
> [!WARNING]
>  <xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 차단 속성입니다. 해당 작업이 완료되기 전에 액세스하려고 하면, 작업이 완료되고 값을 사용할 수 있을 때까지 현재 활성화된 스레드가 차단됩니다. 대부분의 경우 속성에 직접 액세스하지 않고 `await`를 사용하여 값에 액세스해야 합니다.  
  
```cs  
// Call and await in separate statements.  
Task<int> integerTask = TaskOfT_MethodAsync();  
  
// You can do other work that does not rely on integerTask before awaiting.  
textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
int result2 = await integerTask;  
```  
  
 다음 코드의 display 문은 `result1` 변수, `result2` 변수 및 `Result` 속성의 값이 동일한지 확인합니다. `Result` 속성은 차단 속성이므로 해당 작업이 대기 상태가 되기 전에 액세스하지 않아야 합니다.  
  
```cs  
// Display the values of the result1 variable, the result2 variable, and  
// the integerTask.Result property.  
textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
```  
  
##  <a name="BKMK_TaskReturnType"></a> Task 반환 형식  
 return 문을 포함하지 않거나 피연산자를 반환하지 않는 return 문을 포함하는 비동기 메서드에는 일반적으로 <xref:System.Threading.Tasks.Task>의 반환 형식이 있습니다. 이러한 메서드는 동기적으로 실행되도록 작성된 경우 void를 반환하는 메서드입니다. 비동기 메서드에 대해 `Task` 반환 형식을 사용하는 경우 호출된 비동기 메서드가 완료될 때까지 호출 메서드는 await 연산자를 사용하여 호출자의 완료를 일시 중단할 수 있습니다.  
  
 다음 예제에서는 `Task_MethodAsync` 비동기 메서드가 return 문을 포함하지 않습니다. 따라서 이 메서드에 대해 `Task_MethodAsync`가 대기할 수 있도록 `Task`의 반환 형식을 지정합니다. `Task` 형식의 정의는 반환 값을 저장하기 위한 `Result` 속성을 포함하지 않습니다.  
  
```cs  
// TASK EXAMPLE  
async Task Task_MethodAsync()  
{  
    // The body of an async method is expected to contain an awaited   
    // asynchronous call.  
    // Task.Delay is a placeholder for actual work.  
    await Task.Delay(2000);  
    // Task.Delay delays the following line by two seconds.  
    textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
    // This method has no return statement, so its return type is Task.    
}  
```  
  
 동기 void를 반환하는 메서드에 대한 호출 문과 비슷하게 await 식 대신 await 문을 사용하여 `Task_MethodAsync`가 호출되고 대기됩니다. 이 경우 await 연산자를 적용하면 값이 산출되지 않습니다.  
  
 다음 코드는 `Task_MethodAsync` 메서드를 호출하고 기다립니다.  
  
```cs  
// Call and await the Task-returning async method in the same statement.  
await Task_MethodAsync();  
```  
  
 앞의 `Task_MethodAsync` 예제처럼 다음 코드와 같이 <xref:System.Threading.Tasks.Task%601> 호출을 await 연산자의 적용과 구분할 수 있습니다. 그러나 `Task`에는 `Result` 속성이 없으므로 await 연산자가 `Task`에 적용될 때 값이 생성되지 않습니다.  
  
 다음 코드는 `Task_MethodAsync`가 반환하는 작업을 대기하는 것에서 `Task_MethodAsync` 호출을 구분합니다.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a> Void 반환 형식  
 void 반환 형식은 void 반환 형식이 필요한 이벤트 처리기에서 주로 사용합니다. void 반환은 또한 "실행 후 제거"로 분류할 수 있는 작업을 수행하는 메서드 또는 viod를 반환하는 메서드를 재정의하는 데 사용할 수 있습니다. 하지만 void를 반환하는 비동기 메서드는 대기할 수가 없기 때문에 가능할 때마다 `Task`를 반환하는 것이 좋습니다. 이러한 메서드의 호출자는 호출된 비동기 메서드가 마치는 것을 기다리지 않고 완료될 때까지 계속 진행할 수 있어야 하므로, 해당 호출자는 비동기 메서드가 생성하는 모든 값 또는 예외와 독립되어 있어야 합니다.  
  
 void를 반환하는 비동기 메서드의 호출자는 메서드에서 throw되는 예외를 catch할 수 없으므로 이러한 처리되지 않은 예외를 사용하면 응용 프로그램이 실패할 수 있습니다. <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환하는 비동기 메서드에서 예외가 발생하는 경우 이 예외는 반환된 작업에 저장되고 작업이 대기 상태일 때 다시 throw됩니다. 따라서 예외를 생성할 수 있는 모든 비동기 메서드에 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>의 반환 형식이 있고 메서드 호출이 대기 상태인지 확인해야 합니다.  
  
 비동기 메서드에서 예외를 catch하는 방법에 대한 자세한 내용은 [try-catch](../../../../csharp/language-reference/keywords/try-catch.md)를 참조하세요.  
  
 다음 코드는 비동기 이벤트 처리기를 정의합니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a> 전체 예제  
 다음 WPF(Windows Presentation Foundation) 프로젝트는 이 항목의 코드 예제를 포함합니다.  
  
 프로젝트를 실행하려면 다음 단계를 수행합니다.  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **설치됨**, **템플릿** 범주에서 Visual C#을 선택하고 **Windows**를 선택합니다. 프로젝트 형식 목록에서 **WPF 응용 프로그램**을 선택합니다.  
  
4.  프로젝트의 이름으로 `AsyncReturnTypes`를 입력한 다음 **확인** 단추를 선택합니다.  
  
     **솔루션 탐색기**에 새 프로젝트가 표시됩니다.  
  
5.  Visual Studio 코드 편집기에서 **MainWindow.xaml** 탭을 선택합니다.  
  
     탭이 표시되지 않는 경우 **솔루션 탐색기**에서 MainWindow.xaml의 바로 가기 메뉴를 열고 **열기**를 선택합니다.  
  
6.  MainWindow.xaml의 **XAML** 창에서 코드를 다음 코드로 바꿉니다.  
  
    ```cs  
    <Window x:Class="AsyncReturnTypes.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     텍스트 상자와 단추가 포함된 간단한 창이 MainWindow.xaml의 **디자인** 창에 나타납니다.  
  
7.  **솔루션 탐색기**에서 MainWindow.xaml.cs의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.  
  
8.  MainWindow.xaml.cs의 코드를 다음 코드로 바꿉니다.  
  
    ```cs  
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
  
    namespace AsyncReturnTypes  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            // VOID EXAMPLE  
            private async void button1_Click(object sender, RoutedEventArgs e)  
            {  
                textBox1.Clear();  
  
                // Start the process and await its completion. DriverAsync is a   
                // Task-returning async method.  
                await DriverAsync();  
  
                // Say goodbye.  
                textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
            }  
  
            async Task DriverAsync()  
            {  
                // Task<T>   
                // Call and await the Task<T>-returning async method in the same statement.  
                int result1 = await TaskOfT_MethodAsync();  
  
                // Call and await in separate statements.  
                Task<int> integerTask = TaskOfT_MethodAsync();  
  
                // You can do other work that does not rely on integerTask before awaiting.  
                textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
                int result2 = await integerTask;  
  
                // Display the values of the result1 variable, the result2 variable, and  
                // the integerTask.Result property.  
                textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
                textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
                textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
  
                // Task  
                // Call and await the Task-returning async method in the same statement.  
                await Task_MethodAsync();  
  
                // Call and await in separate statements.  
                Task simpleTask = Task_MethodAsync();  
  
                // You can do other work that does not rely on simpleTask before awaiting.  
                textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
                await simpleTask;  
            }  
  
            // TASK<T> EXAMPLE  
            async Task<int> TaskOfT_MethodAsync()  
            {  
                // The body of the method is expected to contain an awaited asynchronous  
                // call.  
                // Task.FromResult is a placeholder for actual work that returns a string.  
                var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
                // The method then can process the result in some way.  
                int leisureHours;  
                if (today.First() == 'S')  
                    leisureHours = 16;  
                else  
                    leisureHours = 5;  
  
                // Because the return statement specifies an operand of type int, the  
                // method must have a return type of Task<int>.  
                return leisureHours;  
            }  
  
            // TASK EXAMPLE  
            async Task Task_MethodAsync()  
            {  
                // The body of an async method is expected to contain an awaited   
                // asynchronous call.  
                // Task.Delay is a placeholder for actual work.  
                await Task.Delay(2000);  
                // Task.Delay delays the following line by two seconds.  
                textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
                // This method has no return statement, so its return type is Task.    
            }  
        }  
    }  
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
 <xref:System.Threading.Tasks.Task.FromResult%2A>   
 [연습: async 및 await를 사용하여 웹에 액세스(C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기 프로그램의 제어 흐름(C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [async](../../../../csharp/language-reference/keywords/async.md)   
 [await](../../../../csharp/language-reference/keywords/await.md)
