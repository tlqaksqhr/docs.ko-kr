---
title: "await(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "await_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "await[C#]"
  - "await 키워드[C#]"
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
caps.handback.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# await(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`await` 연산자는 비동기 메서드의 작업에 적용되어 대기 중인 작업이 완료될 때까지 메서드의 실행을 일시 중단합니다.  작업은 진행 중인 작업을 나타냅니다.  
  
 `await`가 사용되는 비동기 메서드는 [async](../../../visual-basic/language-reference/modifiers/async.md) 키워드로 수정해야 합니다.  `async` 한정자를 사용하여 정의하고 일반적으로 하나 이상의 `await` 식을 포함하는 이러한 메서드를 *비동기 메서드*라고 합니다.  
  
> [!NOTE]
>  `async` 및 `await` 키워드는 Visual Studio 2012에서 도입되었습니다.  비동기 프로그래밍에 대한 소개는 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
 일반적으로 `await` 연산자가 적용되는 작업은 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=204847)\(영문\)을 구현하는 메서드를 호출하여 얻은 반환 값입니다.  예를 들어 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 형식의 값이 포함됩니다.  
  
 다음 코드에서 <xref:System.Net.Http.HttpClient> 메서드 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>는 `Task\<byte[]>`, `getContentsTask`를 반환합니다.  작업은 작업이 완료될 때 실제 바이트 배열을 생성하기 위한 약속입니다.  `await` 연산자는 `getContentsTask`에 적용되어 `getContentsTask`가 완료될 때까지 `SumPageSizesAsync`의 실행을 일시 중단합니다.  동시에 컨트롤은 `SumPageSizesAsync` 호출자에게 반환됩니다.  `getContentsTask`가 완료되면 `await` 식이 바이트 배열로 계산됩니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  전체 예제는 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  샘플은 Microsoft 웹 사이트의 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409)\(영문\)에서 다운로드할 수 있습니다.  예제는 AsyncWalkthrough\_HttpClient 프로젝트에 있습니다.  
  
 이전 예제와 같이 `await`가 `Task<TResult>`를 반환하는 메서드 호출의 결과에 적용되는 경우 `await`식의 형식은 TResult입니다.  `await`가 `Task`를 반환하는 메서드 호출의 결과에 적용되는 경우 `await`식의 형식은 void입니다.  다음 예제에서 차이점을 보여 줍니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 `await` 식은 해당 식이 실행되고 있는 스레드를 차단하지 않습니다.  대신 컴파일러가 대기 중인 작업에서 연속된 작업으로 비동기 메서드의 나머지 부분을 등록하도록 합니다.  그런 다음 컨트롤이 비동기 메서드 호출자에게 반환됩니다.  작업이 완료되면 해당 연속 작업이 호출되고 중단된 비동기 메서드의 실행이 다시 시작됩니다.  
  
 `await` 식은 바로 바깥쪽의 메서드, 람다 식 또는 `async` 한정자로 표시되는 무명 메서드의 본문에서만 발생할 수 있습니다.  *await*라는 용어는 해당 컨텍스트에서만 키워드 역할을 합니다.  다른 컨텍스트에서는 식별자로 해석됩니다.  메서드, 람다 식 또는 무명 메서드 내에서 `await` 식은 동기 함수의 본문, 쿼리 식, [lock 문](../../../csharp/language-reference/keywords/lock-statement.md)의 블록 또는 [안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트에서 발생할 수 있습니다.  
  
## 예외  
 대부분의 비동기 메서드는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.  반환된 작업의 속성은 작업의 완료 여부, 비동기 메서드가 예외를 발생시켰는지 취소되었는지 여부 및 최종 결과 등 해당 상태 및 기록에 대한 정보를 전달합니다.  `await` 연산자는 해당 속성에 액세스합니다.  
  
 예외를 발생시키는 작업 반환 비동기 메서드를 기다릴 경우 `await` 연산자는 예외를 다시 throw합니다.  
  
 취소된 작업 반환 비동기 메서드를 기다릴 경우 `await` 연산자는 <xref:System.OperationCanceledException>을 다시 throw합니다.  
  
 오류가 발생한 상태의 단일 작업에는 여러 예외가 반영될 수 있습니다.  예를 들어 작업은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 호출의 결과일 수 있습니다.  이러한 작업을 기다릴 경우 await 작업에서 예외 중 하나만 다시 throw합니다.  그러나 다시 throw되는 예외를 예측할 수 없습니다.  
  
 비동기 메서드에서 오류 처리에 대한 예제는 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)를 참조하세요.  
  
## 예제  
 다음 Windows Forms 예제에서는 비동기 메서드 `WaitAsynchronouslyAsync`에서 `await`의 사용을 보여 줍니다.  해당 메서드의 동작을 `WaitSynchronously`의 동작과 대조합니다.  `await` 연산자가 작업에 적용되지 않으면 해당 정의에서 `async` 한정자를 사용하고 본문에서 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>을 호출하더라도 `WaitSynchronously`가 동기적으로 실행됩니다.  
  
```c#  
  
private async void button1_Click(object sender, EventArgs e)  
{  
    // Call the method that runs asynchronously.  
    string result = await WaitAsynchronouslyAsync();  
  
    // Call the method that runs synchronously.  
    //string result = await WaitSynchronously ();  
  
    // Display the result.  
    textBox1.Text += result;  
}  
  
// The following method runs asynchronously. The UI thread is not  
// blocked during the delay. You can move or resize the Form1 window   
// while Task.Delay is running.  
public async Task<string> WaitAsynchronouslyAsync()  
{  
    await Task.Delay(10000);  
    return "Finished";  
}  
  
// The following method runs synchronously, despite the use of async.  
// You cannot move or resize the Form1 window while Thread.Sleep  
// is running because the UI thread is blocked.  
public async Task<string> WaitSynchronously()  
{  
    // Add a using directive for System.Threading.  
    Thread.Sleep(10000);  
    return "Finished";  
}  
```  
  
## 참고 항목  
 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: Async 및 Await를 사용하여 웹에 액세스](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [async](../../../visual-basic/language-reference/modifiers/async.md)