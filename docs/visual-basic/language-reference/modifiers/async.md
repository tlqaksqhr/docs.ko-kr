---
title: "Async (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Async"
helpviewer_keywords: 
  - "Async [Visual Basic]"
  - "Async keyword [Visual Basic]"
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Async (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 `Async` 수정자는는 메서드 혹은 이를 비동기적으로 수정하는 [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) 를 나타냅니다.  이러한 메서드는 *비동기 메서드* 처럼 참조됩니다.  
  
 비동기 방법은 호출자의 스레드를 차단하지 않고 오래 실행될 수 있는 작업을 수행하는 편리한 방법을 제공합니다.  비동기 메서드의 호출자는 비동기 메서드 완료를 기다리지 않고 작업을 계속할 수 있습니다.  
  
> [!NOTE]
>  `Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.  비동기 프로그래밍에 대한 소개는 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 다음 예제에서는 비동기 메서드의 구조를 보여 줍니다.  규첵에 따라, 비동기 메서드는 "Async"로 지정합니다.  
  
```vb  
  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 일반적으로, `Async` 키워드로 수정되는 메서드에는 하나 이상의 [Await](../../../visual-basic/language-reference/modifiers/async.md) 식 또는 문이 있어야 합니다.  대기 중이던 작업이 완료될 때까지 메서드는 `Await`, 즉 메서드가 일시 중단된 지점에 도달할 때까지 동기적으로 실행됩니다.  한편, 컨트롤이 메서드의 호출자로 반환됩니다.  이 `Await` 식 혹은 상태를 포함하지 않는 메소드의 경우, 메소드는 일시중단 되고 동기적인 메소드로 실행합니다.  `Await`이 포함되지 않은 모든 비동기 메서드에서는 오류가 발생할 있으므로 컴파일러 경고를 표시합니다.  자세한 내용은 를 참조하실려면, [compiler error](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md) 를 보세요.  
  
 이 `Async` 키워드는 예약된 키워드가 있습니다.  람다 식 또는 메서드를 수정하는 때의 키워드입니다.  다른 모든 컨텍스트에서는 식별자로 해석됩니다.  
  
## 반환 유형  
 비동기 메소드는 [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저, 혹은 <xref:System.Threading.Tasks.Task> 나 <xref:System.Threading.Tasks.Task%601> 의 형식을 반환하는 [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) 프로시저 입니다.  메서드는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 매개변수 모두를 선언할 수 없습니다.  
  
 메서드의 [return](../../../visual-basic/language-reference/statements/return-statement.md) 문에서 TResult 형식의 피연산자를 지정할 경우 비동기 메서드의 반환 형식으로 `Task(Of TResult)` 를 지정합니다.  메서드가 완료되었을 때 의미 있는 값이 반환되지 않을 경우 `Task`를 사용합니다.  즉, 대기중인 `Task` 가 결과 값을 생성하지 않는 모든 `Await` 명세서인, `Task` 가 완료하지만 그때, 메소드 호출은 `Task`를 반환합니다.  
  
 Async 서브루틴은 `Sub` 프로시저가 요구하는 이벤트 핸들러를 정의하는 데에 주로 사용합니다.  비동기 서브 루틴의 호출자는 기다릴 수 없으므로 메서드가 throw하는 예외를 catch할 수 없습니다.  
  
 자세한 내용과 예제를 보려면 [비동기 반환 형식](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 예제  
 다음 예제는 비동기 메서드 비동기 이벤트 처리기를 비동기 람다 식으로 보여 줍니다.  이들 요소를 사용하는 전체 예제를 보려면 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)에서 연습 코드를 다운로드할 수 있습니다.  
  
```vb  
  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
  
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)