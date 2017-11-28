---
title: "파일 액세스에 Async 사용(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d6272baa9beae405148185abfebde84ca0cb7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-async-for-file-access-c"></a><span data-ttu-id="fd9b4-102">파일 액세스에 Async 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="fd9b4-102">Using Async for File Access (C#)</span></span>
<span data-ttu-id="fd9b4-103">파일에 액세스하는 비동기 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-103">You can use the async feature to access files.</span></span> <span data-ttu-id="fd9b4-104">비동기 기능을 사용하면 콜백을 사용하거나 여러 메서드 또는 람다 식에서 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-104">By using the async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="fd9b4-105">동기 코드를 비동기로 만들려면 동기 메서드 대신 비동기 메서드를 호출하고 몇 가지 키워드를 코드에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="fd9b4-106">파일 액세스 호출에 비동기를 추가하는 이유로 다음을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
-   <span data-ttu-id="fd9b4-107">비동기는 UI 응용 프로그램의 응답성을 개선합니다. 작업을 시작하는 UI 스레드가 다른 작업을 수행할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="fd9b4-108">UI 스레드가 시간이 오래 걸리는(예: 50밀리초 이상) 코드를 실행해야 하는 경우, I/O가 완료되고 UI 스레드가 키보드와 마우스 입력 및 기타 이벤트를 다시 처리할 수 있을 때까지 UI가 정지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
-   <span data-ttu-id="fd9b4-109">비동기는 스레드의 필요성을 줄임으로써 ASP.NET 및 기타 서버 기반 응용 프로그램의 확장성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="fd9b4-110">응용 프로그램이 각 응답에 전용 스레드를 사용하고 1,000개의 요청이 동시에 처리되는 경우 수천 개의 스레드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="fd9b4-111">비동기 작업은 대기 중에 종종 스레드를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="fd9b4-112">끝날 때 기존 I/O 완료 스레드를 잠시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
-   <span data-ttu-id="fd9b4-113">파일 액세스 작업의 대기 시간은 현재 조건에서 매우 낮을 수 있지만 나중에 대기 시간이 크게 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="fd9b4-114">예를 들어 전 세계에 있는 서버로 파일을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
-   <span data-ttu-id="fd9b4-115">비동기 기능을 사용할 경우에는 추가되는 오버헤드가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-115">The added overhead of using the Async feature is small.</span></span>  
  
-   <span data-ttu-id="fd9b4-116">비동기 작업은 쉽게 병렬로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="fd9b4-117">예제 실행</span><span class="sxs-lookup"><span data-stu-id="fd9b4-117">Running the Examples</span></span>  
 <span data-ttu-id="fd9b4-118">이 항목의 예제를 실행하려면 **WPF 응용 프로그램** 또는 **Windows Forms 응용 프로그램**을 만든 후 **단추**를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="fd9b4-119">단추의 `Click` 이벤트에서 각 예제의 첫 번째 메서드에 대한 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="fd9b4-120">다음 예제에서는 `using` 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-120">In the following examples, include the following `using` statements.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="fd9b4-121">FileStream 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="fd9b4-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="fd9b4-122">이 항목의 예제에서는 운영 체제 수준에서 비동기 I/O를 일으키는 옵션이 있는 <xref:System.IO.FileStream> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="fd9b4-123">이 옵션을 사용하면 많은 경우 ThreadPool 스레드를 차단하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="fd9b4-124">이 옵션을 사용하도록 설정하려면 생성자 호출에서 `useAsync=true` 또는 `options=FileOptions.Asynchronous` 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="fd9b4-125">파일 경로를 지정하여 직접 여는 경우에는 <xref:System.IO.StreamReader> 및 <xref:System.IO.StreamWriter>와 함께 이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="fd9b4-126">그러나 <xref:System.IO.FileStream> 클래스에서 열린 <xref:System.IO.Stream>을 제공하면 이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="fd9b4-127">대기 중에는 UI 스레드가 차단되지 않으므로, ThreadPool 스레드가 차단된 경우에도 UI 앱에서 비동기 호출이 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="fd9b4-128">텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="fd9b4-128">Writing Text</span></span>  
 <span data-ttu-id="fd9b4-129">다음 예제에서는 파일에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-129">The following example writes text to a file.</span></span> <span data-ttu-id="fd9b4-130">각 await 문에서 메서드가 즉시 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="fd9b4-131">파일 I/O가 완료되면 await 문 뒤에 오는 문에서 메서드가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="fd9b4-132">async 한정자는 await 문을 사용하는 메서드의 정의에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```csharp  
public async void ProcessWrite()  
{  
    string filePath = @"temp2.txt";  
    string text = "Hello World\r\n";  
  
    await WriteTextAsync(filePath, text);  
}  
  
private async Task WriteTextAsync(string filePath, string text)  
{  
    byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize: 4096, useAsync: true))  
    {  
        await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
    };  
}  
```  
  
 <span data-ttu-id="fd9b4-133">원래 예제에 있는 `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);` 문은 다음의 두 문이 축약된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-133">The original example has the statement `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, which is a contraction of the following two statements:</span></span>  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 <span data-ttu-id="fd9b4-134">첫 번째 문은 작업을 반환하여 파일 처리가 시작되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="fd9b4-135">await가 있는 두 번째 문은 메서드를 즉시 종료하고 다른 작업을 반환하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="fd9b4-136">나중에 파일 처리가 완료되면 await 뒤에 오는 문으로 실행이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="fd9b4-137">자세한 내용은 [비동기 프로그램의 제어 흐름(C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-137">For more information, see  [Control Flow in Async Programs (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="fd9b4-138">텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="fd9b4-138">Reading Text</span></span>  
 <span data-ttu-id="fd9b4-139">다음 예제에서는 파일에서 텍스트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-139">The following example reads text from a file.</span></span> <span data-ttu-id="fd9b4-140">텍스트가 버퍼링되고, 이 경우 <xref:System.Text.StringBuilder>에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="fd9b4-141">이전 예제와 달리 await의 계산에서 값이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="fd9b4-142"><xref:System.IO.Stream.ReadAsync%2A> 메서드는 <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>를 반환하므로 작업이 완료된 후 await 평가에서 `Int32` 값(`numRead`)이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="fd9b4-143">자세한 내용은 [비동기 반환 형식(C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-143">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
```csharp  
public async void ProcessRead()  
{  
    string filePath = @"temp2.txt";  
  
    if (File.Exists(filePath) == false)  
    {  
        Debug.WriteLine("file not found: " + filePath);  
    }  
    else  
    {  
        try  
        {  
            string text = await ReadTextAsync(filePath);  
            Debug.WriteLine(text);  
        }  
        catch (Exception ex)  
        {  
            Debug.WriteLine(ex.Message);  
        }  
    }  
}  
  
private async Task<string> ReadTextAsync(string filePath)  
{  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize: 4096, useAsync: true))  
    {  
        StringBuilder sb = new StringBuilder();  
  
        byte[] buffer = new byte[0x1000];  
        int numRead;  
        while ((numRead = await sourceStream.ReadAsync(buffer, 0, buffer.Length)) != 0)  
        {  
            string text = Encoding.Unicode.GetString(buffer, 0, numRead);  
            sb.Append(text);  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="fd9b4-144">병렬 비동기 I/O</span><span class="sxs-lookup"><span data-stu-id="fd9b4-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="fd9b4-145">다음 예제에서는 10개의 텍스트 파일을 작성하여 병렬 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="fd9b4-146">각 파일에서 <xref:System.IO.Stream.WriteAsync%2A> 메서드는 작업 목록에 추가되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="fd9b4-147">`await Task.WhenAll(tasks);` 문은 메서드를 종료하고, 파일 처리가 모든 작업에 대해 완료되면 메서드 내에서 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-147">The `await Task.WhenAll(tasks);` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="fd9b4-148">이 예제는 작업이 완료된 후 `finally` 블록에서 모든 <xref:System.IO.FileStream> 인스턴스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-148">The example closes all <xref:System.IO.FileStream> instances in a `finally` block after the tasks are complete.</span></span> <span data-ttu-id="fd9b4-149">대신 `using` 문에 각 `FileStream`이 만들어진 경우 작업이 완료되기 전에 `FileStream`이 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-149">If each `FileStream` was instead created in a `using` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="fd9b4-150">성능 향상은 거의 대부분 비동기 처리가 아닌 병렬 처리에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="fd9b4-151">비동기의 장점은 다중 스레드를 묶어 두지 않고 사용자 인터페이스 스레드를 묶어 두지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```csharp  
public async void ProcessWriteMult()  
{  
    string folder = @"tempfolder\";  
    List<Task> tasks = new List<Task>();  
    List<FileStream> sourceStreams = new List<FileStream>();  
  
    try  
    {  
        for (int index = 1; index <= 10; index++)  
        {  
            string text = "In file " + index.ToString() + "\r\n";  
  
            string fileName = "thefile" + index.ToString("00") + ".txt";  
            string filePath = folder + fileName;  
  
            byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
            FileStream sourceStream = new FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize: 4096, useAsync: true);  
  
            Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
            sourceStreams.Add(sourceStream);  
  
            tasks.Add(theTask);  
        }  
  
        await Task.WhenAll(tasks);  
    }  
  
    finally  
    {  
        foreach (FileStream sourceStream in sourceStreams)  
        {  
            sourceStream.Close();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="fd9b4-152"><xref:System.IO.Stream.WriteAsync%2A> 및 <xref:System.IO.Stream.ReadAsync%2A> 메서드를 사용하는 경우 중간에 작업을 취소하는 데 사용할 수 있는 <xref:System.Threading.CancellationToken>을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="fd9b4-153">자세한 내용은 [비동기 응용 프로그램 미세 조정(C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) 및 [관리되는 스레드의 취소](../../../../standard/threading/cancellation-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd9b4-153">For more information, see [Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9b4-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd9b4-154">See Also</span></span>  
 [<span data-ttu-id="fd9b4-155">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="fd9b4-155">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="fd9b4-156">비동기 반환 형식(C#)</span><span class="sxs-lookup"><span data-stu-id="fd9b4-156">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)  
 [<span data-ttu-id="fd9b4-157">비동기 프로그램의 제어 흐름(C#)</span><span class="sxs-lookup"><span data-stu-id="fd9b4-157">Control Flow in Async Programs (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)
