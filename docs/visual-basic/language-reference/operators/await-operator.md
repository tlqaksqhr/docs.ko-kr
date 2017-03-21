---
title: "Await 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a>Await 연산자(Visual Basic)
대기 중인 작업이 완료될 때까지 메서드 실행을 일시 중단하려면 비동기 메서드 또는 람다 식의 피연산자에 `Await` 연산자를 적용합니다. 작업은 진행 중인 작업을 나타냅니다.  
  
 메서드를 `Await` 사용 있어야는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다. 이러한 메서드를 사용 하 여 정의 `Async` 한정자를 일반적으로 포함 된 하나 이상의 `Await` 식 이라고는 *비동기 메서드의*합니다.  
  
> [!NOTE]
>  `Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다. 비동기 프로그래밍에 대 한 소개를 참조 하십시오. [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
 일반적으로 적용 하는 작업의 `Await` 연산자가 구현 하는 메서드 호출에서 반환 값은 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=204847), 즉, 한 <xref:System.Threading.Tasks.Task>나 <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 다음 코드에서는 <xref:System.Net.Http.HttpClient>메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>반환 `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient> 이 작업은 작업이 완료될 때 실제 바이트 배열을 생성하기 위한 약속입니다. `Await` 연산자는 `getContentsTask`에 적용되어 `getContentsTask`가 완료될 때까지 `SumPageSizesAsync`의 실행을 일시 중단합니다. 동시에 컨트롤은 `SumPageSizesAsync` 호출자에게 반환됩니다. `getContentsTask`가 완료되면 `Await` 식이 바이트 배열로 계산됩니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  전체 예제를 참조 하십시오. [연습:를 사용 하 여 Async 및 Await 하 여 웹 서비스에 액세스](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다. 샘플을 다운로드할 수 있습니다 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) Microsoft 웹 사이트입니다. 예제는 AsyncWalkthrough_HttpClient 프로젝트에 있습니다.  
  
 `Await`가 `Task(Of TResult)`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식의 형식은 TResult입니다. `Await`가 `Task`를 반환하는 메서드 호출의 결과에 적용되는 경우, `Await`식은 값을 반환하지 않습니다. 다음 예제에서 차이점을 보여 줍니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 `Await` 식 또는 문은 식이 실행되고 있는 스레드를 차단하지 않습니다. 대신 `Await` 식 이후 컴파일러가 대기 중인 작업에서 연속된 작업으로 비동기 메서드의 나머지 부분을 등록하게 됩니다. 그런 다음 컨트롤이 비동기 메서드 호출자에게 반환됩니다. 작업이 완료되면 해당 연속 작업이 호출되고 중단된 비동기 메서드의 실행이 다시 시작됩니다.  
  
 `Await` 식은 `Async` 수정자로 표시된 람다 식 또는 바로 바깥쪽에 있는 메서드의 본문에만 발생할 수 있습니다. 용어 *Await* 해당 컨텍스트에서 키워드로 사용 합니다. 다른 컨텍스트에서는 식별자로 해석됩니다. 비동기 메서드 또는 람다 식 안에 `Await` 식은 쿼리 식에서 발생할 수 없습니다는 `catch` 또는 `finally` 블록는 [시도 중... Catch... 마지막으로](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 의 루프 제어 변수 식 문에 `For` 또는 `For Each` 루프 또는 본문에는 [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) 문.  
  
## <a name="exceptions"></a>예외  
 대부분의 비동기 메서드는 반환 <xref:System.Threading.Tasks.Task>또는 <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> 반환된 작업의 속성은 작업의 완료 여부, 비동기 메서드가 예외를 발생시켰는지 취소되었는지 여부 및 최종 결과 등 해당 상태 및 기록에 대한 정보를 전달합니다. `Await` 연산자는 해당 속성에 액세스합니다.  
  
 예외를 발생시키는 작업 반환 비동기 메서드를 기다릴 경우 `Await` 연산자는 예외를 다시 throw합니다.  
  
 취소 된 작업 반환 비동기 메서드를 기다릴 경우는 `Await` 연산자 <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException> 를 다시 throw  
  
 오류가 발생한 상태의 단일 작업에는 여러 예외가 반영될 수 있습니다.  예를 들어, 작업 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 에 대 한 호출의 결과 수 있습니다. 이러한 작업을 기다릴 경우 await 작업에서 예외 중 하나만 다시 throw합니다. 그러나 다시 throw되는 예외를 예측할 수 없습니다.  
  
 비동기 메서드의 오류 처리의 예 참조 [시도 중... Catch... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 Windows Forms 예제에서는 비동기 메서드 `WaitAsynchronouslyAsync`에서 `Await`의 사용을 보여 줍니다. 해당 메서드의 동작을 `WaitSynchronously`의 동작과 대조합니다. 없이 `Await` 연산자를 `WaitSynchronously` 사용 되지만 동기적으로 실행 된 `Async` 한정자의 정 및에 대 한 호출의 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>해당 본문에.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>  
  
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
  
## <a name="see-also"></a>참고 항목  
 [비동기 프로그래밍 async 및 Await](../../../visual-basic/programming-guide/concepts/async/index.md)   
 [연습: Async를 사용 하 여 웹 서비스에 액세스 하 고 기다립니다](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [비동기](../../../visual-basic/language-reference/modifiers/async.md)
