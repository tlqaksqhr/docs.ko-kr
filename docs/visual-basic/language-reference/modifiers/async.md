---
title: "Async (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fa15daee8f3b6ddcc137356896a20cf82e0cc1d0
ms.lasthandoff: 03/13/2017

---
# <a name="async-visual-basic"></a>Async(Visual Basic)
`Async` 한정자가 나타내는 메서드 또는 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) 수정 하는 비동기적입니다. 이러한 메서드는 라고 *비동기 메서드*합니다.  
  
 비동기 메서드는 호출자의 스레드를 차단하지 않고 오래 실행될 수 있는 작업을 수행하는 편리한 방법을 제공합니다. 비동기 메서드의 호출자는 비동기 메서드 완료 될 때까지 기다리지 않고 작업을 계속할 수 있습니다.  
  
> [!NOTE]
>  `Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다. 비동기 프로그래밍에 대 한 소개를 참조 하십시오. [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
 다음 예제에서는 비동기 메서드의 구조를 보여줍니다. 규칙에 따라 비동기 메서드는 "Async"로 끝납니다.  
  
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
  
 일반적으로 수정 되는 메서드에 `Async` 키워드를 하나 이상 포함 [Await](../../../visual-basic/language-reference/modifiers/async.md) 식 또는 문입니다. 대기 중인 작업이 완료될 때까지 일시 중단된 지점인 첫 번째 `Await`에 도달할 때까지 이 메서드는 동기적으로 실행됩니다. 그리고 메서드의 호출자로 컨트롤이 반환됩니다. 메서드에 `Await` 식 혹은 문이 포함되지 않은 경우에는 메서드가 일시 중단되지 않고 동기 메서드와 같은 방식으로 실행됩니다. 컴파일러 경고를 포함 하지 않는 모든 비동기 메서드에서 알려 `Await` 해당 발생할 수 있으므로 오류가 발생 합니다. 자세한 내용은 참조는 [컴파일러 오류](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md)합니다.  
  
 `Async` 키워드는 예약되지 않은 키워드입니다. 이 키워드는 메서드 또는 람다 식을 수정할 때의 키워드입니다. 다른 모든 컨텍스트에서는 식별자로 해석됩니다.  
  
## <a name="return-types"></a>반환 형식  
 비동기 메서드는 [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) 프로시저 또는 [함수](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> 의 반환 형식이 있는 프로시저 모든 메서드를 선언할 수 없습니다 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수입니다.  
  
 지정한 `Task(Of TResult)` 비동기 메서드의 반환 형식에 대 한 경우는 [반환](../../../visual-basic/language-reference/statements/return-statement.md) 메서드는 문에 TResult 형식의 피연산자입니다. 메서드가 완료되었을 때 의미 있는 값이 반환되지 않을 경우 `Task`를 사용합니다. 즉, 메서드를 호출하면 `Task`가 반환되지만 `Task`가 완료된 경우 `Await`를 대기 중인 모든 `Task` 문이 결과 값을 생성하지 않습니다.  
  
 비동기 서브루틴은 `Sub` 프로시저가 필요한 이벤트 처리기를 정의하는 데 주로 사용됩니다. 비동기 서브 루틴의 호출자는 이를 기다릴 수 없으며, 메서드가 throw하는 예외를 catch할 수 없습니다.  
  
 자세한 내용 및 예제에 대 한 참조 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 비동기 이벤트 처리기, 비동기 람다 식 및 비동기 메서드를 보여줍니다. 이러한 요소를 사용 하는 전체 예제를 보려면 [연습:를 사용 하 여 Async 및 Await 하 여 웹 서비스에 액세스](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 연습 코드를 다운로드할 수 있습니다 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute></xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [Await 연산자](../../../visual-basic/language-reference/operators/await-operator.md)   
 [비동기 프로그래밍 async 및 Await](../../../visual-basic/programming-guide/concepts/async/index.md)   
 [연습: Async 및 Await를 사용하여 웹에 액세스](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
