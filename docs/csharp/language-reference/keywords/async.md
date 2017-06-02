---
title: "async(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- async_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 50e128137fde445f64e10cf7c2a1ee5fdecb34e6
ms.openlocfilehash: e7f4cfa81de3c4db41d9303abf65cfd0edc926a4
ms.contentlocale: ko-kr
ms.lasthandoff: 05/01/2017

---
# <a name="async-c-reference"></a>async(C# 참조)
`async` 한정자를 사용하여 메서드, [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) 또는 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)를 비동기로 지정합니다. 메서드 또는 식에 이 한정자를 사용하면 비동기 메서드라고 합니다.  
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
  
```  
  
 비동기 프로그래밍이 처음이거나 비동기 메서드가 `await` 키워드를 사용하여 호출자의 스레드를 차단하지 않고 장기 실행 작업을 수행할 수 있는 방법을 모르는 경우 [async 및 await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md)의 지침을 읽어야 합니다.  
  
```  
string contents = await contentsTask;  
```  
  
 대기 중이던 작업이 완료될 때까지 메서드는 `await` 식, 즉 메서드가 일시 중단된 지점에 도달할 때까지 동기적으로 실행됩니다. 다음 단원의 예제에서처럼 그 동안에는 제어가 메서드 호출자에게 반환됩니다.  
  
 `async` 키워드에서 수정하는 메서드에 `await` 식 또는 문이 없는 경우 해당 메서드가 동기적으로 실행됩니다. `await`가 포함되지 않은 모든 비동기 메서드에서는 오류가 발생할 있으므로 컴파일러 경고가 나타납니다. [컴파일러 경고(수준 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md)를 참조하세요.  
  
 `async` 키워드는 메서드, 람다 식 또는 무명 메서드를 수정할 때만 키워드로 사용됩니다. 다른 모든 컨텍스트에서는 식별자로 해석됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 이벤트 처리기, `StartButton_Click`, 비동기 메서드 및 `ExampleMethodAsync` 간의 제어 흐름과 구조를 보여 줍니다. 비동기 메서드의 결과는 다운로드한 웹 사이트의 길이입니다. 이 코드는 Visual Studio에서 만든 WPF(Windows Presentation Foundation) 앱 또는 Windows 스토어 앱에 적합합니다. 앱을 설정하는 방법은 코드 주석을 참조하세요.  
  
```csharp  
// You can run this code in Visual Studio as a WPF app or a Windows Store app.  
// You need a button (StartButton) and a textbox (ResultsTextBox).  
// Remember to set the names and handler so that you have something like this:  
// <Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
//         Click="StartButton_Click" Name="StartButton"/>  
// <TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
//          Text="TextBox" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
  
// To run the code as a WPF app:  
//    paste this code into the MainWindow class in MainWindow.xaml.cs,  
//    add a reference to System.Net.Http, and  
//    add a using directive for System.Net.Http.  
  
// To run the code as a Windows Store app:  
//    paste this code into the MainPage class in MainPage.xaml.cs, and  
//    add using directives for System.Net.Http and System.Threading.Tasks.  
  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // ExampleMethodAsync returns a Task<int>, which means that the method  
    // eventually produces an int result. However, ExampleMethodAsync returns  
    // the Task<int> value as soon as it reaches an await.  
    ResultsTextBox.Text += "\n";  
    try  
    {  
        int length = await ExampleMethodAsync();  
        // Note that you could put "await ExampleMethodAsync()" in the next line where  
        // "length" is, but due to when '+=' fetches the value of ResultsTextBox, you  
        // would not see the global side effect of ExampleMethodAsync setting the text.  
        ResultsTextBox.Text += String.Format("Length: {0}\n", length);  
    }  
    catch (Exception)  
    {  
        // Process the exception if one occurs.  
    }  
}  
  
public async Task<int> ExampleMethodAsync()  
{  
    var httpClient = new HttpClient();  
    int exampleInt = (await httpClient.GetStringAsync("http://msdn.microsoft.com")).Length;  
    ResultsTextBox.Text += "Preparing to finish ExampleMethodAsync.\n";  
    // After the following return statement, any method that's awaiting  
    // ExampleMethodAsync (in this case, StartButton_Click) can get the   
    // integer result.  
    return exampleInt;  
}  
// Output:  
// Preparing to finish ExampleMethodAsync.  
// Length: 53292  
  
```  
  
> [!IMPORTANT]
>  작업 및 작업 완료를 기다리는 동안 실행되는 코드에 대한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md)을 참조하세요. 비슷한 요소를 사용하는 전체 WPF 예제에 대해서는 [연습: Async 및 Await를 사용하여 웹에 액세스](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)를 참조하세요. [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191)(비동기 샘플: 웹 액세스 연습(C# 및 Visual Basic))에서 연습 코드를 다운로드할 수 있습니다.  
  
## <a name="return-types"></a>반환 형식  
 비동기 메서드에는 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> 또는 [void](../../../csharp/language-reference/keywords/void.md)의 반환 형식이 있을 수 있습니다. 이 메서드는 모든 [re](../../../csharp/language-reference/keywords/ref.md)f 또는 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.  
  
 메서드의 [return](../../../csharp/language-reference/keywords/return.md) 문에서 `TResult` 형식의 피연산자를 지정할 경우 비동기 메서드의 반환 형식으로 `Task<TResult>`를 지정합니다. 메서드가 완료되었을 때 의미 있는 값이 반환되지 않을 경우 `Task`를 사용합니다. 즉, 이 메서드를 호출하면 `Task`가 반환되지만 `Task`가 완료되면 `await`를 기다리는 모든 `Task` 식이 `void`가 됩니다.  
  
 `void` 반환 형식은 주로 해당 반환 형식이 필요한 이벤트 처리기를 정의할 때 사용합니다. `void` 반환 비동기 메서드의 호출자는 기다릴 수 없으므로 메서드가 throw하는 예외를 catch할 수 없습니다.  
  
 자세한 내용과 예제는 [비동기 반환 형식](../../../csharp/programming-guide/concepts/async/async-return-types.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [await](../../../csharp/language-reference/keywords/await.md)   
 [연습: Async 및 Await를 사용하여 웹에 액세스](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Async 및 Await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md)
