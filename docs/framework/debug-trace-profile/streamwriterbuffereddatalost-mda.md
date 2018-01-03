---
title: streamWriterBufferedDataLost MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5a59b8735cf87e8b88036ffb317f7bbeb9f0885
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="f96ef-102">streamWriterBufferedDataLost MDA</span><span class="sxs-lookup"><span data-stu-id="f96ef-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="f96ef-103">`streamWriterBufferedDataLost` MDA(관리 디버깅 도우미)는 <xref:System.IO.StreamWriter>가 기록될 때 활성화되지만 <xref:System.IO.StreamWriter> 인스턴스가 소멸되기 전에 <xref:System.IO.StreamWriter.Flush%2A> 또는 <xref:System.IO.StreamWriter.Close%2A> 메서드가 이후에 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="f96ef-104">이 MDA를 사용하도록 설정하면 런타임이 버퍼링된 데이터가 여전히 <xref:System.IO.StreamWriter> 내에 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="f96ef-105">버퍼링된 데이터가 있으면 MDA가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="f96ef-106"><xref:System.GC.Collect%2A> 및 <xref:System.GC.WaitForPendingFinalizers%2A> 메서드를 호출하면 종료자를 강제로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="f96ef-107">그러지 않으면 종료자가 임의 시간에 실행되고 프로세스 종료 시 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="f96ef-108">이 MDA를 사용하도록 설정하여 명시적으로 종료자를 실행하면 이러한 유형의 문제를 보다 안정적으로 재현하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f96ef-109">증상</span><span class="sxs-lookup"><span data-stu-id="f96ef-109">Symptoms</span></span>  
 <span data-ttu-id="f96ef-110"><xref:System.IO.StreamWriter>는 마지막 1-4KB의 데이터를 파일에 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f96ef-111">원인</span><span class="sxs-lookup"><span data-stu-id="f96ef-111">Cause</span></span>  
 <span data-ttu-id="f96ef-112"><xref:System.IO.StreamWriter>는 내부적으로 데이터를 버퍼링하므로, 기본 데이터 저장소에 버퍼링된 데이터를 쓰기 위해 <xref:System.IO.StreamWriter.Close%2A> 또는 <xref:System.IO.StreamWriter.Flush%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="f96ef-113"><xref:System.IO.StreamWriter.Close%2A> 또는 <xref:System.IO.StreamWriter.Flush%2A>를 적절하게 호출하지 않으면 <xref:System.IO.StreamWriter> 인스턴스에 버퍼링된 데이터가 예상대로 작성되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="f96ef-114">다음은 이 MDA가 catch해야 하는 잘못 작성된 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="f96ef-115">위의 코드는 가비지 수집이 트리거된 다음 종료자가 완료될 때까지 일시 중지되는 경우 이 MDA를 보다 안정적으로 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="f96ef-116">이러한 유형의 문제를 추적하기 위해 디버그 빌드에서 이전 메서드의 끝에 다음 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="f96ef-117">이렇게 하면 MDA가 안정적으로 활성화되지만, 물론 문제의 원인이 수정되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="f96ef-118">해결</span><span class="sxs-lookup"><span data-stu-id="f96ef-118">Resolution</span></span>  
 <span data-ttu-id="f96ef-119"><xref:System.IO.StreamWriter> 인스턴스가 있는 코드 블록이나 응용 프로그램을 닫기 전에 <xref:System.IO.StreamWriter>에서 <xref:System.IO.StreamWriter.Close%2A> 또는 <xref:System.IO.StreamWriter.Flush%2A>를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="f96ef-120">이 작업을 수행하기 위한 최상의 메커니즘 중 하나는 C# `using` 블록(Visual Basic의 `Using` 블록)으로 인스턴스를 만드는 것이며, 이렇게 하면 작성기에 대한 <xref:System.IO.StreamWriter.Dispose%2A> 메서드가 호출되어 인스턴스가 올바르게 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="f96ef-121">다음 코드에서는 `using` 대신 `try/finally`를 사용하여 동일한 솔루션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 <span data-ttu-id="f96ef-122">이러한 솔루션을 사용할 수 없는 경우(예를 들어 <xref:System.IO.StreamWriter>가 정적 변수에 저장되어 있고 수명이 끝날 때 코드를 쉽게 실행할 수 없는 경우), 마지막 사용 후 <xref:System.IO.StreamWriter>에서 <xref:System.IO.StreamWriter.Flush%2A>를 호출하거나 처음 사용하기 전에 <xref:System.IO.StreamWriter.AutoFlush%2A> 속성을 `true`로 설정하면 이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f96ef-123">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f96ef-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="f96ef-124">이 MDA는 런타임에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f96ef-125">출력</span><span class="sxs-lookup"><span data-stu-id="f96ef-125">Output</span></span>  
 <span data-ttu-id="f96ef-126">이 위반이 발생했음을 나타내는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f96ef-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f96ef-127">구성</span><span class="sxs-lookup"><span data-stu-id="f96ef-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f96ef-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f96ef-128">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="f96ef-129">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f96ef-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
