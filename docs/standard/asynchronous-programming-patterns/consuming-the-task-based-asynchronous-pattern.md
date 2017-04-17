---
title: "Consuming the Task-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, and TAP"
  - "asynchronous design patterns, .NET Framework"
  - "TAP, .NET Framework support for"
  - "Task-based Asynchronous Pattern, .NET Framework support for"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Consuming the Task-based Asynchronous Pattern
비동기 작업으로 작업하기 위해 TAP\(작업 기반 비동기 패턴\)를 사용하면 콜백을 사용하여 차단되지 않고 대기를 달성할 수 있습니다.  이 작업의 경우 <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=fullName>와 같은 메서드를 통해 수행됩니다.  언어 기반 비동기 지원은 일반 제어 흐름 내에서 비동기 작업을 대기할 수 있도록 함으로써 콜백을 숨기며, 컴파일러에서 생성된 코드는 이와 동일한 API 수준 지원을 제공합니다.  
  
## 대기를 사용하여 실행 일시 중단  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작하여 비동기식으로 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체를 기다리기 위해 C\#과 [Await Operator](../Topic/Await%20Operator%20\(Visual%20Basic\).md) Visual Basic에서 [await](../Topic/await%20\(C%23%20Reference\).md) 키워드를 사용할 수 있습니다.  <xref:System.Threading.Tasks.Task>를 대기할 때 `await` 식은 `void` 형식입니다.  <xref:System.Threading.Tasks.Task%601>를 대기할 때 `await` 식은 `TResult` 형식입니다.  `await` 식은 비동기 메서드의 본문 내에서 발생해야 합니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 C\# 및 Visual Basic 언어 지원에 대한 자세한 내용은 C\# 및 Visual Basic 언어 사양을 참조하십시오.  
  
 내부적으로 대기 기능에서 작업 수행 시 콜백을 연속하여 설치합니다.  이 콜백으로 일시 중단 시점에 비동기 메서드가 다시 시작됩니다.  비동기 메서드가 다시 시작되었을 때 대기한 작업을 성공적으로 완료하고 <xref:System.Threading.Tasks.Task%601>인 경우 `TResult`가 반환됩니다.  <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>이 <xref:System.Threading.Tasks.TaskStatus> 상태에서 종료되기를 기다린 경우 <xref:System.OperationCanceledException> 예외가 throw됩니다.  <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>가 <xref:System.Threading.Tasks.TaskStatus> 상태에서 종료되기를 기다린 경우 결함을 초래한 예외가 throw됩니다.  여러 예외로 인해 `Task`가 결함을 일으킬 수 있지만 이러한 예외 중 한 가지만 전달됩니다.  그러나 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> 속성은 모든 오류를 포함하는 <xref:System.AggregateException> 예외를 반환합니다.  
  
 만약 동기 컨텍스트\(<xref:System.Threading.SynchronizationContext> 개체\)가 일시 중단 상태에서 비동기 메서드를 실행하면, 예를 들어, <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=fullName> 속성이 `null`이 아닌 경우, 비동기 메세드는 컨텍스트의 <xref:System.Threading.SynchronizationContext.Post%2A>메서드를 이용하여 같은 동기 컨텍스트를 다시 시작합니다.  그렇지 않으면 중지 시 존재했던 작업 스케줄러\(<xref:System.Threading.Tasks.TaskScheduler> 개체\)에 의존하게 됩니다.  일반적으로 스레드 풀을 대상으로 하는 기본 작업 스케줄러\(<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=fullName>\)입니다.  이 작업 스케줄러에서 완료된 대기 중인 비동기 작업을 다시 시작해야 하는지 또는 재시작의 일정을 계획해야 하는지 여부를 결정합니다.  기본 스케줄러에서는 일반적으로 연속 기능을 통해 대기된 작업이 완료될 때마다 모든 스레드에서 실행할 수 있게 합니다.  
  
 비동기 메서드가 호출되면 호출이 호출자에게 반환되는 지점에서 await를 사용할 수 있는 아직 완료되지 않은 인스턴스에 있는 첫 번째 await 식에 도달할 때까지 함수의 본문을 동기적으로 실행합니다.  비동기 메서드가 `void`를 반환하지 않는 경우 지속적인 계산을 나타내기 위해  <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 개체가 반환됩니다.  void가 아닌 비동기 메서드에서 return 문이 있거나, 메서드 본문 끝에 도달한 경우 작업은 <xref:System.Threading.Tasks.TaskStatus> 최종 상태로 완료됩니다.  컨트롤에서 비동기 메서드의 본문에 처리되지 않은 예외가 발생하면 <xref:System.Threading.Tasks.TaskStatus>상태에서 작업 종료합니다.  해당 예외가 <xref:System.OperationCanceledException>이면, 대신에 <xref:System.Threading.Tasks.TaskStatus> 상태에서 작업을 종료합니다.  이 방식으로 결국 결과나 예외가 발생합니다.  
  
 이 동작에서 여러 가지 중요한 변형이 있습니다.  성능 상의 이유로 작업을 기다리는 시간까지 작업이 이미 완료된 경우 컨트롤이 생성되지 않으며 대신 기능은 계속 실행됩니다.  또한 원래 컨텍스트를 반환하는 것이 항상 바람직한 동작은 아니며 변경될 수 있습니다. 이에 대한 내용은 다음 섹션에서 자세히 설명합니다.  
  
### Yield 및 ConfigureAwait를 사용하여 일시 중단과 재개 구성  
 여러 메서드에서 비동기 메서드의 실행을 위한 기타 컨트롤을 제공합니다.  예를 들어, <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=fullName> 메서드를 비동기 메서드의 생성점을 만드는데 사용할 수 있습니다.  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
  
```  
  
 비동기적으로 게시하거나 최신 컨텍스트에 따라 다시 예약하는 것과 같습니다.  
  
```csharp  
Task.Run(async  delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
  
```  
  
 비동기 메서드의 일시 중단과 다시 시작을 보다 효과적으로 제어하기 위해 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> 메서드를 사용할 수도 있습니다.  앞서 언급했듯이 기본적으로 비동기 메서드가 일시 중단되었던 당시의 현재 컨텍스트가 캡처되며 캡처된 해당 컨텍스트는 다시 시작할 때 비동기 메서드의 계속을 호출하는 데 사용합니다.  대부분의 경우 이 동작은 사용자가 원하는 동작입니다.  다른 경우에는 연속 컨텍스트를 상관하지 않고, 원래 컨텍스트로 다시 게시되는 것을 방지하여 성능을 향상시킬 수 있습니다.  이를 활성화하려면 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName>를 사용하여 컨텍스트에서 캡처하거나 다시 시작하지 않고 비동기 작업을 완료 대기 중인 곳마다 계속 실행하도록 대기 작업에 알릴 수 있습니다.  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
  
```  
  
## 비동기 작업 취소  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]로 시작하는 TAP 메서드는 취소 시 취소 토큰을 허락하는 최소 한 개의 오버로드를 지원합니다\(<xref:System.Threading.CancellationToken> 개체\).  
  
 취소 토큰은 취소 토큰 소스\(<xref:System.Threading.CancellationTokenSource> 개체\)를 통해 만들어집니다.  소스의 <xref:System.Threading.CancellationTokenSource.Token%2A> 속성은 소스의 <xref:System.Threading.CancellationTokenSource.Cancel%2A> 메서드를 호출할 때 신호를 보내는 취소 토큰을 반환합니다.  예를 들어, 단일 웹 페이지를 다운로드하고 작업을 취소하려는 경우에는 <xref:System.Threading.CancellationTokenSource> 개체를 생성하고, TAP 메서드에 토큰을 전달한 후, 취소 작업이 준비된 경우 소스의 <xref:System.Threading.CancellationTokenSource.Cancel%2A> 메서드를 호출합니다.  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
  
```  
  
 여러 비동기 호출을 취소하려면 모든 호출에 동일한 토큰이 전달합니다.  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
  
```  
  
 또는 선택적 작업의 하위 집합에 동일한 토큰을 전달할 수 있습니다.  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
  
```  
  
 취소 요청은 스레드에서 초기화할 수 있습니다.  
  
 취소가 요청되지 않음을 나타내기 위해 취소 토큰을 적용하는 모든 메서드에 <xref:System.Threading.CancellationToken.None%2A?displayProperty=fullName> 값을 전달할 수 있습니다.  이로 인해 해당 <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=fullName> 속성에서 `false`를 반환하고 호출된 메서드는 그에 맞게 최적화할 수 있습니다.  테스트 목적으로 이미 취소되었거나 취소할 수 없는 상태에서 시작해야 하는지 여부를 나타내기 위해 부울 값을 허용하는 생성자를 사용하여 인스턴스화한 미리 취소된 최소 토큰을 전달할 수 있습니다.  
  
 취소에 대한 이 접근 방식에는 여러 가지 장점이 있습니다.  
  
-   동일한 취소 토큰을 비동기 및 동기 작업 수에 전달할 수 있습니다  
  
-   동일한 취소 요청은 많은 수의 수신기에 확산시킬 수 있습니다.  
  
-   비동기 API의 개발자는 취소 요청 여부와 적용 시기를 완벽하게 제어합니다.  
  
-   API를 사용하는 코드는 취소 요청을 전파할 비동기 호출을 선택적으로 결정할 수 있습니다.  
  
## 진행률 모니터링  
 진행 중인 비동기 메서드는 비동기 메서드로 전달된 진행률 인터페이스를 통해 진행률을 노출합니다.  예를 들어, 텍스트 문자열을 비동기적으로 다운로드하는 기능과 함께 지금까지 완료된 다운로드의 비율을 포함하는 진행 상황 업데이트를 발생시키는 방식을 고려하십시오.  이러한 메서드는 Windows Presentation Foundation\(WPF\) 응용 프로그램에서 다음과 같이 사용될 수 있습니다.  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)    
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,   
            new Progress<int>(p => pbDownloadProgress.Value = p));  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
  
```  
  
<a name="combinators"></a>   
## 기본 제공 조합기 사용  
 <xref:System.Threading.Tasks> 네임스페이스는 작업을 구성하고 수행하는 몇 가지 방법을 포함합니다.  
  
### Task.Run  
 <xref:System.Threading.Tasks.Task> 클래스에는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>로 스레드 풀에 쉽게 작업을 오프로드할 수 있는 여러 <xref:System.Threading.Tasks.Task.Run%2A> 메서드가 포함되어 있습니다. 예를 들어:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
  
```  
  
 <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName> 오버로드 같은 이러한 <xref:System.Threading.Tasks.Task.Run%2A> 메서드 중 일부는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName> 메서드의 축약형으로 제공됩니다.  <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName> 같은 기타 오버로드를 사용하면 다음과 같이 오프로드 작업 내에서 사용을 기다릴 수 있습니다. 예:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 이런 오버로드는 작업 병렬 라이브러리에서 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장 메서드와 함께 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName> 메서드를 사용하는 것과 논리적으로 동일합니다.  
  
### Task.FromResult  
 데이터를 이미 사용할 수 있고 <xref:System.Threading.Tasks.Task%601>에 리프트된 작업 반환 메서드에서 반환해야 하는 시나리오의 경우 <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 사용할 수 없습니다.  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async  Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
  
```  
  
### Task.WhenAll  
 <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드는 작업으로 나타나는 여러 비동기 작업에서 비동기적으로 대기하는 데 사용됩니다.  메서드에는 제네릭이 아닌 작업 또는 제네릭 작업의 균일하지 않은 집합\(예: 여러 void 반환 작업을 비동기적으로 대기 또는 각 값의 형식이 다를 수 있는 여러 값 반환 메서드를 비동기적으로 대기\)을 수용하고 제네릭 작업의 균일한 집합\(예: 여러 `TResult`를 비동기적으로 대기\-반환 매서드\)을 수용하는 여러 오버로드가 있습니다.  
  
 여러 고객에게 전자 메일 메시지를 전송하려는 경우를 가정해 봅시다.  다음 메시지를 보내기 전에 한 메시지가 완료되기를 기다리지 않도록 메시지 보내기를 겹칠 수 있습니다.  보내기 작업이 완료되었을 때와 오류가 발생했는지 여부를 찾을 수도 있습니다.  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
  
```  
  
 이 코드는 발생할 수 있는 예외를 명시적으로 처리하는 대신 예외가 <xref:System.Threading.Tasks.Task.WhenAll%2A>의 결과 작업에 대해 `await`의 외부로 전파될 수 있도록 합니다.  예외를 처리하려면 다음과 같은 코드를 사용할 수 있습니다.  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    ...  
}  
  
```  
  
 이러한 경우에 모든 비동기 작업이 실패할 경우 모든 예외는 <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드에서 반환되어 <xref:System.Threading.Tasks.Task>에 저장된<xref:System.AggregateException> 예외로 통합됩니다.  그러나, 이러한 예외 중 하나만이 `await` 키워드로 전파됩니다.  모든 예외를 검사하려는 경우 이전 코드를 다음과 같이 다시 작성할 수 있습니다.  
  
```csharp  
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
  
```  
  
 웹에서 여러 개의 파일을 비동기적으로 다운로드하는 또 다른 예를 살펴보겠습니다.  이 경우 모든 비동기 작업에는 유형이 같은 결과 형식이 있고 이 결과에 쉽게 액세스할 수 있습니다.  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 이전의 void 반환 시나리오에서 설명한 것과 같은 예외 처리 기술을 사용할 수 있습니다.  
  
```csharp  
Task [] asyncOps =   
    (from url in urls select DownloadStringAsync(url)).ToArray();  
try  
{  
    string [] pages = await Task.WhenAll(asyncOps);  
    ...  
}  
catch(Exception exc)  
{  
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
  
```  
  
### Task.WhenAny  
 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드를 사용하여 완료할 작업으로 표시되는 여러 비동기 작업 중 하나만 비동기적으로 대기할 수 있습니다.  이 메서드는 4가지 기본 사용 사례로 사용됩니다.  
  
-   중복: 작업을 여러 번 수행하고 먼저 완료되는 작업을 선택합니다\(예를 들어, 단일의 결과를 생성하는 여러 주식 시세 웹 서비스에 연결하고 가장 빨리 완료되는 결과를 선택\).  
  
-   인터리브: 여러 작업을 시작하고 모두 완료해야 하지만 완료되었을 때 작업을 처리합니다.  
  
-   제한: 다른 작업이 완료되면 추가 작업을 시작할 수 있습니다.  이 항목은 인터리빙 시나리오의 확장입니다.  
  
-   초기 재귀 한도: 예를 들어, 작업 t1으로 표시되는 작업은 다른 작업 t2를 사용하여 <xref:System.Threading.Tasks.Task.WhenAny%2A> 작업에서 그룹화할 수 있으며 <xref:System.Threading.Tasks.Task.WhenAny%2A> 작업에서 대기할 수 있습니다.  작업 t2는 시간 초과나 취소 또는 t1을 완료하기 전에 <xref:System.Threading.Tasks.Task.WhenAny%2A> 작업이 완료되도록 하는 일부 다른 신호를 나타낼 수 있습니다.  
  
#### 중복  
 주식 구매 여부에 대한 결정을 원하는 경우를 살펴봅니다.  여러 스톡 권장사항으로 신뢰하는 웹 서비스가 있지만 때에 따라 각 서비스가 일일 부하로 인해 느려질 수 있습니다.  <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드를 사용하여 작업이 완료될 때 알림을 받을 수 있습니다.  
  
```csharp  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol),   
    GetBuyRecommendation2Async(symbol),  
    GetBuyRecommendation3Async(symbol)  
};  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
if (await recommendation) BuyStock(symbol);  
  
```  
  
 성공적으로 완료된 모든 작업의 래핑된 결과를 반환하는 <xref:System.Threading.Tasks.Task.WhenAll%2A>과는 달리 <xref:System.Threading.Tasks.Task.WhenAny%2A>는 완료된 작업을 반환합니다.  만약 작업이 실패하면 실패 사실을 아는 것이 중요하고, 작업이 성공하면 어떤 작업이 반환값과 연관되었는지 아는 것이 중요합니다.  따라서 반환된 작업의 결과에 액세스하거나 이 예제에 나타난 대로 더 기다려야 합니다.  
  
 <xref:System.Threading.Tasks.Task.WhenAll%2A>과 같이 예외를 수용할 수 있어야 합니다.  완료된 작업을 수신해야 하므로 오류가 전파되도록 반환되는 작업을 기다리고 이 작업을 적절히 `try/catch`할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```csharp  
Task<bool> [] recommendations = …;  
while(recommendations.Count > 0)  
{   
    Task<bool> recommendation = await Task.WhenAny(recommendations);      
    try  
    {  
        if (await recommendation) BuyStock(symbol);  
        break;  
    }  
    catch(WebException exc)  
    {  
        recommendations.Remove(recommendation);  
    }  
}  
  
```  
  
 또한 첫 번째 작업이 성공적으로 완료된 경우에도 후속 작업이 실패할 수 있습니다.  이 시점에서 예외를 처리할 수 있는 여러 옵션이 있습니다. <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드를 사용할 수 있는 경우 시작된 모든 작업이 완료될 때까지 기다릴 수도 있고 또는 모든 예외가 중요하며 로그온해야 한다고 결정할 수도 있습니다.  이 경우 작업을 비동기적으로 완료하면 알림을 받도록 연속 작업을 직접 활용할 수 있습니다.  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => { if (t.IsFaulted) Log(t.Exception); });  
}  
  
```  
  
 또는  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);  
}  
  
```  
  
 또는 같을 때  
  
```  
private static async  void LogCompletionIfFailed(IEnumerable<Task> tasks)  
{  
    foreach(var task in tasks)  
    {  
        try { await task; }  
        catch(Exception exc) { Log(exc); }  
    }  
}  
…  
LogCompletionIfFailed(recommendations);  
  
```  
  
 마지막으로, 나머지 작업을 모두 취소할 수도 있습니다.  
  
```csharp  
var cts = new CancellationTokenSource();  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol, cts.Token),   
    GetBuyRecommendation2Async(symbol, cts.Token),  
    GetBuyRecommendation3Async(symbol, cts.Token)  
};  
  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
cts.Cancel();  
if (await recommendation) BuyStock(symbol);  
  
```  
  
#### 인터리빙  
 웹에서 이미지를 다운로드하고 UI 컨트롤 추가와 같은 각 이미지를 처리하는 경우를 고려합니다.  UI 스레드에서 순차적으로 처리를 수행해야 하지만 가능한 동시에 이미지를 다운로드할 수 있습니다.  또한 모두 다운로드될 때까지 이미지 추가를 대기하지 않고 다운로드가 완료되면 추가합니다.  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
  
```  
  
 인터리빙을 다음과 같이 다운로드된 이미지의 <xref:System.Threading.ThreadPool>에서 계산 처리를 많이 하는 시나리오에도 적용할 수 있습니다.  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)  
         .ContinueWith(t => ConvertImage(t.Result)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
  
```  
  
#### 스로틀  
 다운로드를 명시적으로 조절하기 위해 많은 이미지를 다운로드하는 것을 제외하고 대화식 예제를 고려합니다. 예를 들어, 동시에 지정된 개수의 다운로드만 진행할 수 있습니다.  그렇게 하려면 비동기 작업의 하위 집합을 시작합니다.  작업이 완료되면 추가 작업이 발생하도록 시작할 수 있습니다.  
  
```csharp  
const int CONCURRENCY_LEVEL = 15;  
Uri [] urls = …;  
int nextIndex = 0;  
var imageTasks = new List<Task<Bitmap>>();  
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)  
{  
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
    nextIndex++;  
}  
  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch(Exception exc) { Log(exc); }  
  
    if (nextIndex < urls.Length)  
    {  
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
        nextIndex++;  
    }  
}  
  
```  
  
#### 초기 재귀 한도  
 사용자의 취소 단추 클릭과 같은 사용자 취소 요청에 응답하는 동안 작업 완료를 비동기적으로 대기하는 것을 고려합니다.  다음 코드에서는 이러한 시나리오를 보여 줍니다.  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async  void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        if (imageDownload.IsCompleted)  
        {  
            Bitmap image = await imageDownload;  
            panel.AddImage(image);  
        }  
        else imageDownload.ContinueWith(t => Log(t));  
    }  
    finally { btnRun.Enabled = true; }  
}  
  
private static async  Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
  
```  
  
 이 구현에서는 기본 비동기 작업을 취소하지 않고 종료하기로 결정하는 즉시 사용자 인터페이스를 다시 활성화합니다.  다른 방법은 벗어나기로 결정할 때 보류 중인 작업을 취소하지만 취소 요청으로 인해 조기에 종료되어 작업이 실제로 완료될 가능성이 있을 때까지 사용자 인터페이스를 다시 설정하지 않습니다.  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async  void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        Bitmap image = await imageDownload;  
        panel.AddImage(image);  
    }  
    catch(OperationCanceledException) {}  
    finally { btnRun.Enabled = true; }  
}  
  
```  
  
 초기 재귀 한도의 또 다른 예는 다음 섹션에서 설명하는 것처럼 <xref:System.Threading.Tasks.Task.Delay%2A> 메서드와 함께 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드는 사용하는 것입니다.  
  
### Task.Delay  
 <xref:System.Threading.Tasks.Task.Delay%2A> 메서드를 사용하여 비동기 메서드의 실행을 일시 중지할 수 있습니다.  이는 폴링 루프 빌드, 미리 결정된 기간 동안 사용자 입력 처리 지연 등과 같은 여러 가지 기능에 유용합니다.  <xref:System.Threading.Tasks.Task.Delay%2A> 메서드는 또한 대기할 때 제한 시간을 지정하기 위해 <xref:System.Threading.Tasks.Task.WhenAny%2A>와 조합하여 사용하는 것이 유용할 수 있습니다.  
  
 ASP.NET 웹 서비스와 같이 더 큰 비동기 작업의 일부인 작업을 완료하는 데 시간이 너무 오래 걸리는 경우 특히 작업이 완료되지 않는 경우에도 전체 작업이 영향을 받을 수 있습니다.  이런 이유로 비동기 작업을 대기하는 시간을 초과할 수 있다는 것이 중요합니다.  동기 <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.%2A> WaitAll?qualifyHint=False&autoUpgrade=True 및 <xref:System.Threading.Tasks.Task.%2A> WaitAny?qualifyHint=False&autoUpgrade=True 메서드는 시간 초과 값을 허용하지만 해당 <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>\/ <xref:System.Threading.Tasks.Task.WhenAny%2A> 및 앞에서 언급한 <xref:System.Threading.Tasks.Task.WhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드는 허용하지 않습니다.  대신, <xref:System.Threading.Tasks.Task.Delay%2A> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A>는 제한 시간을 지정하기 위해 조합하여 사용할 수 있습니다.  
  
 예를 들어, UI 응용 프로그램에서 이미지를 다운로드하고 다운로드하는 동안 UI를 비활성하기를 원한다고 가정해 봅시다.  그러나 다운로드가 너무 오래 걸리면 UI를 다시 활성화하고 다운로드를 취소해야 합니다.  
  
```csharp  
public async  void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = “Timed out”;  
            var ignored = download.ContinueWith(  
                t => Trace(“Task finally completed”));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
 <xref:System.Threading.Tasks.Task.WhenAll%2A>에서 작업을 반환하기 때문에 동일한 작업이 여러 다운로드에 적용됩니다.  
  
```csharp  
public async  void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            status.Text = “Timed out”;  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
## 작업 기반 코디네이터 구축  
 작업이 비동기 작업을 완벽하게 나타내고 작업에 참가하고 결과를 검색하기 위해 동기와 비동기 기능을 제공할 수 있기 때문에 더 큰 패턴을 만드는 작업을 작성하는 유용한 라이브러리 조합을 빌드할 수 있게 됩니다.  이전 섹션에서 설명한 대로 몇 가지 기본 제공된 조합이 .NET Framework에 포함되어 있지만 자신만의 빌드를 만들 수도 있습니다.  다음 단원은 잠재적인 조합기 메서드 및 형식에 대한 몇 가지 예제를 제공합니다.  
  
### RetryOnFault  
 많은 상황에서 이전 시도가 실패하는 경우 작업을 다시 시도할 수 있습니다.  동기 코드의 경우에는 다음 예의 `RetryOnFault`와 같이 이 기능을 수행하는 도우미 메서드를 빌드할 수 있습니다.  
  
```csharp  
public static T RetryOnFault<T>(  
    Func<T> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return function(); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
  
```  
  
 TAP과 함께 구현되는 비동기 작업에 대해 도우미 메서드를 거의 동일하게 작성할 수 있으며 따라서 다음의 작업을 반환합니다.  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 그런 다음 이 코디네이터를 활용하여 응용 프로그램 논리로의 재시도를 인코딩할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
  
```  
  
 `RetryOnFault` 함수를 더욱 확장할 수 있습니다.  예를 들어 함수는 작업을 다시 시도할 시기를 결정하기 위해 다시 시도하는 중에 호출되는 다른 `Func<Task>`를 허용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
        await retryWhen().ConfigureAwait(false);  
    }  
    return default(T);  
}  
```  
  
 그런 다음 작업을 다시 시도하기 전에 다음과 같은 함수를 사용하여 잠시 대기할 수 있습니다.  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
  
```  
  
### NeedOnlyOne  
 때로는 작업의 지연을 개선하고 성공 가능성을 높이기 위해 중복을 활용합니다.  모두 주식 시세를 제공하지만 다양한 시간에 각 서비스가 여러 수준의 품질과 응답 시간을 제공할 수 있는 여러 웹 서비스를 생각합니다.  이러한 변동을 처리하기 위해 모든 웹 서비스에 대한 요청을 발행하고 이러한 요청 중 하나에서 응답을 수신하면 즉시 나머지 요청을 취소합니다.  도우미 함수를 구현하여 대기 중인 여러 작업을 시작하고 그 중 하나의 작업을 기다린 다음 나머지를 취소하는 이러한 일반적인 패턴을 보다 쉽게 구현할 수 있습니다.  다음 예제의 `NeedOnlyOne` 함수는 이 시나리오를 보여 줍니다.  
  
```csharp  
public static async  Task<T> NeedOnlyOne(  
    params Func<CancellationToken,Task<T>> [] functions)  
{  
    var cts = new CancellationTokenSource();  
    var tasks = (from function in functions  
                 select function(cts.Token)).ToArray();  
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);  
    cts.Cancel();  
    foreach(var task in tasks)   
    {  
        var ignored = task.ContinueWith(  
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);  
    }  
    return completed;  
}  
```  
  
 이 함수를 사용하는 방법은 다음과 같습니다.  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer2Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer3Async(“msft”, ct));  
```  
  
### 인터리브 작업  
 매우 큰 작업을 사용하여 작업할 때 인터리빙 시나리오를 지원하기 위한 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드 사용에 대한 잠재적인 성능 문제가 있습니다.  <xref:System.Threading.Tasks.Task.WhenAny%2A>에 대한 모든 호출은 각 작업에 연속 등록됩니다.  N개의 태스크는 인터리빙 작업 수명주기에 대해 O\(N2\) 컨티뉴에이션을 가집니다.  큰 작업을 하는 경우에는 성능 문제를 해결하기 위해 \(다음 예의 `Interleaved`과 같은\) 콤비네이터를 사용할 수 있습니다.  
  
```csharp  
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputTasks = tasks.ToList();  
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)   
                   select new TaskCompletionSource<T>()).ToList();  
    int nextTaskIndex = -1;  
    foreach (var inputTask in inputTasks)  
    {  
        inputTask.ContinueWith(completed =>  
        {  
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];  
            if (completed.IsFaulted)   
                source.TrySetException(completed.Exception.InnerExceptions);  
            else if (completed.IsCanceled)   
                source.TrySetCanceled();  
            else   
                source.TrySetResult(completed.Result);  
        }, CancellationToken.None,   
           TaskContinuationOptions.ExecuteSynchronously,   
           TaskScheduler.Default);  
    }  
    return from source in sources   
           select source.Task;  
}  
  
```  
  
 그런 다음 조합기를 작업이 완료되면 해당 결과를 처리하는 데 사용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### WhenAllOrFirstException  
 특정 분산\/수집 시나리오에서는 예외가 발생하는 즉시 대기를 중지하는 예외 중 하나라도 발생하지 않으면 집합에 있는 모든 작업을 대기하도록 할 수 있습니다.  마찬가지로 조합기 메서드와 함께 수행할 수 있습니다. 예를 들면 다음 예제의 `WhenAllOrFirstException`과 같습니다.  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
  
```  
  
## 작업 기반 데이터 구조 구축  
 사용자 지정 작업 기반 코디네이터를 빌드하는 기능 외에 비동기 작업의 결과는 물론 조인하는 데 필요한 동기화를 모두 나타내는 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601>의 데이터 구조를 갖고 있으면 비동기 시나리오에 사용할 사용자 지정 데이터 구조를 빌드할 매우 강력한 형식을 만들 수 있습니다.  
  
### AsyncCache  
 작업의 한 가지 중요한 측면은 여러 소비자에게 전달할 수 있으며, 이들 모두 대기할 수 있으며 연속 작업을 등록하고 결과 또는 예외 등을 가져올 수 있다는 것입니다\(<xref:System.Threading.Tasks.Task%601>의 경우\).  이는 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601>를 비동기 캐싱 인프라에 사용하기에 적합하게 만듭니다.  다음은 <xref:System.Threading.Tasks.Task%601> 상단에 빌드되어 있는 작지만 강력한 비동기 캐시의 예제입니다.  
  
```csharp  
public class AsyncCache<TKey, TValue>  
{  
    private readonly Func<TKey, Task<TValue>> _valueFactory;  
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;  
  
    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)  
    {  
        if (valueFactory == null) throw new ArgumentNullException("loader");  
        _valueFactory = valueFactory;  
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();  
    }  
  
    public Task<TValue> this[TKey key]  
    {  
        get  
        {  
            if (key == null) throw new ArgumentNullException("key");  
            return _map.GetOrAdd(key, toAdd =>   
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;  
        }  
    }  
}  
  
```  
  
 [AsyncCache\<TKey,TValue\>](http://go.microsoft.com/fwlink/p/?LinkId=251941) 클래스는 `TKey` 를 갖는 함수에 생성자로 대리자를 허용하고 <xref:System.Threading.Tasks.Task%601>를 반환합니다.  캐시에서 이전에 액세스한 값은 내부 사전에 저장되며, `AsyncCache`는 캐시를 동시에 액세스하더라도 키 당 한 작업만 생성되도록 합니다.  
  
 예를 들어, 다운로드한 웹 페이지를 위한 캐시를 빌드할 수 있습니다.  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
  
```  
  
 웹 페이지의 내용이 필요할 때마다 비동기 메서드에서 이 캐시를 사용할 수 있습니다.  `AsyncCache` 클래스는 가능한 적은 수의 페이지를 다운로드하도록 하며 결과를 캐시에 저장합니다.  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
  
```  
  
### AsyncProducerConsumerCollection  
 작업을 사용하여 비동기 활동을 조정하기 위해 데이터 구조를 빌드할 수도 있습니다.  병렬 클래식 디자인 패턴인 생산자\/소비자 중 하나를 사용하십시오.  이 패턴으로 생산자는 소비가가 소비하는 데이터를 생성하고 생산자와 소비자가 동시에 실행될 수 있습니다.  예를 들어, 소비자는 항목 1 항목 2 생성 이제는 생산자가 이전에 생성 된 처리 합니다. 공급자\/소비자 패턴에 따라 거의 예외 되지 일부 데이터 구조가 필요 소비 하는 새 데이터에 대 한 알림을 받을 수를 찾을 때 사용할 수 있도록 생산자가 만든 작업을 저장 합니다.  
  
 이것은 비동기 메서드를 생산자와 소비자로 사용할 수 있는 작업의 상단에 빌드된 간단한 데이터 구조입니다.  
  
```csharp  
public class AsyncProducerConsumerCollection<T>  
{  
    private readonly Queue<T> m_collection = new Queue<T>();  
    private readonly Queue<TaskCompletionSource<T>> m_waiting =   
        new Queue<TaskCompletionSource<T>>();  
  
    public void Add(T item)  
    {  
        TaskCompletionSource<T> tcs = null;  
        lock (m_collection)  
        {  
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();  
            else m_collection.Enqueue(item);  
        }  
        if (tcs != null) tcs.TrySetResult(item);  
    }  
  
    public Task<T> Take()  
    {  
        lock (m_collection)  
        {  
            if (m_collection.Count > 0)   
            {  
                return Task.FromResult(m_collection.Dequeue());   
            }  
            else   
            {  
                var tcs = new TaskCompletionSource<T>();  
                m_waiting.Enqueue(tcs);  
                return tcs.Task;  
            }  
        }  
    }  
}  
  
```  
  
 해당 데이터 구조를 배치한 상태에서 다음과 같은 코드를 작성할 수 있습니다.  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.Take();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Add(data);  
}  
```  
  
 <xref:System.Threading.Tasks.Dataflow> 네임스페이스는 사용자 지정 컬렉션 형식을 빌드할 필요 없이 비슷한 방식으로 사용할 수 있는 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 형식을 포함합니다.  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.ReceiveAsync();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Post(data);  
}  
  
```  
  
> [!NOTE]
>  <xref:System.Threading.Tasks.Dataflow> 네임스페이스는 **NuGet**을 통해 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 사용할 수 있습니다.  <xref:System.Threading.Tasks.Dataflow> 네임스페이스가 포함된 어셈블리를 설치하려면 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고 프로젝트 메뉴에서 **NuGet 패키지 관리**를 선택한 후 Microsoft.Tpl.Dataflow 패키지를 온라인으로 검색합니다.  
  
## 참고 항목  
 [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)   
 [Implementing the Task\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)   
 [Interop with Other Asynchronous Patterns and Types](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)