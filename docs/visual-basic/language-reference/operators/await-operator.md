---
title: "Await Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Await"
helpviewer_keywords: 
  - "Await operator [Visual Basic]"
  - "Await [Visual Basic]"
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Await Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

중지된 작업이 완료될때까지 메소드의 실행을 일시중지하기 위해서 비동기 메소드나 람다식에의 피연산자에  `Await` 연산자를 적용시킬 수 있습니다.  작업은 진행 중인 작업을 나타냅니다.  
  
 `Await` 가 사용된 메소드는 [Async](../../../visual-basic/language-reference/modifiers/async.md) 한정자를 반드시 가져야합니다.  `Async` 한정자를 사용해 정의되고 일반적으로 하나 이상의 `Await` 식을 포함하는 이러한 메서드는 *비동기 메서드*로 참고됩니다.  
  
> [!NOTE]
>  `Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.  비동기 프로그래밍에 대한 소개는 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 `Await` 연산자가 일반적으로 적용되는 작업은 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=204847)을 구현하는 메서드에 대한 호출의 반환 값입니다. \-<xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>.  
  
 다음 코드에서 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>는 `getContentsTask`, `Task(Of Byte())`를 반환합니다.  이 작업은 작업이 완료되면 실제 바이트 배열을 생성하기 위한 약속입니다.  `Await` 연산자를 `getContentsTask`에 적용하여 `getContentsTask`가 완료될 때까지 `SumPageSizesAsync`에서 실행을 일시 중지합니다.  한편, 컨트롤은 `SumPageSizesAsync`의 호출자에게 반환됩니다.  `getContentsTask`가 완료되면 `Await` 식이 바이트 배열로 계산됩니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  전체 예제를 보려면 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  Microsoft 웹 사이트의 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409)에서 샘플을 다운로드할 수 있습니다.  이 예제는 AsyncWalkthrough\_HttpClient 프로젝트에 있습니다.  
  
 `Await`가 `Task(Of TResult)`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식의 형식이 TResult됩니다.   `Await`  가  `Task` 를 반환하는 메서드 호출의 결과에 적용되는 경우,  `Await` 식은 값을 반환하지 않습니다.  다음 예제에서는 이러한 차이를 보여 줍니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 `Await` 식 및 문은 식이 실행되고 있는 스레드를 차단하지 않습니다.  대신 컴파일러가 대기 중인 작업에서 `Await`식 이후에 비동기 메서드의 나머지 부분을 연속으로 등록하게 됩니다.  제어한 다음 비동기 메서드의 호출자로 반환됩니다.  작업이 완료되면 연속 작업을 호출하고 앞서 중단했던 지점부터 비동기 메서드의 실행이 다시 시작됩니다.  
  
 `Await` 식은 `Async` 수정자로 표시된 람다식 또는 익명 메서드의 본문에만 발생할 수 있습니다.  *Await*라는 용어는 해당 컨텍스트에서만 키워드 역할을 합니다.  다른 곳에서는 식별자로 해석됩니다.  비동기 메서드 또는 람다식 안에  `Await`  식은 쿼리 식,  `catch`  또는  `finally`  블록 \( [Try...Catch..Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)문\),  `For`  또는  `For Each`  루프의 루프제어 변수식 또는 [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md)문의 본문에서는  실행할 수 없습니다.  
  
## 예외  
 대부분의 비동기 메서드는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.  반환된 작업의 속성에는 작업이 완료되었는지 여부, 비동기 메서드로 예외가 발생했는지 아니며 비동기 메서드가 취소되었는지 여부, 최종 결과 등 작업의 상태와 기록에 대한 정보가 포함됩니다.  `Await` 연산자는 이러한 속성에 액세스합니다.  
  
 예외의 원인이 되는 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 예외를 다시 throw합니다.  
  
 취소된 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 <xref:System.OperationCanceledException>을 다시 throw합니다.  
  
 오류 상태의 단일 작업은 여러 예외를 나타낼 수 있습니다.  예를 들어, 작업이 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>에 대한 호출의 결과일 수 있습니다.  이러한 작업을 기다릴 경우 대기 작업은 예외 중 하나만 다시 throw합니다.  그러나 어떤 예외가 다시 throw 되는지에 대해 예상할 수 없습니다.  
  
 비동기 메서드에서 오류 처리의 예를 보려면 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)를 참조하십시오.  
  
## 예제  
 다음 Windows Forms 예제는 `WaitAsynchronouslyAsync` 비동기 메서드에서의 `Await`의 사용을 보여 줍니다.  해당 메서드의 동작을 `WaitSynchronously`의 동작과 비교합니다.  작업에 적용되는 `Await` 연산자가 없으면 정의에서 `Async` 한정자를 사용하고 본문에서 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>에 대한 호출을 사용하더라도 `WaitSynchronously`는 동기적으로 실행됩니다.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## 참고 항목  
 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)