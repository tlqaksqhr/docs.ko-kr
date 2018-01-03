---
title: "방법: 추적 수신기 만들기 및 초기화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- initializing trace listeners
- trace listeners, creating
- trace listeners, initializing
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 21726de1-61ee-4fdc-9dd0-3be49324d066
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ebc50e4075a5793c344cbc017eb60247c1c8774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-initialize-trace-listeners"></a><span data-ttu-id="31a73-102">방법: 추적 수신기 만들기 및 초기화</span><span class="sxs-lookup"><span data-stu-id="31a73-102">How to: Create and Initialize Trace Listeners</span></span>
<span data-ttu-id="31a73-103"><xref:System.Diagnostics.Debug?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Trace?displayProperty=nameWithType> 클래스는 메시지를 수신하고 처리하는 수신기라는 개체에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-103">The <xref:System.Diagnostics.Debug?displayProperty=nameWithType> and <xref:System.Diagnostics.Trace?displayProperty=nameWithType> classes send messages to objects called listeners that receive and process these messages.</span></span> <span data-ttu-id="31a73-104">추적이나 디버깅을 사용하면 이러한 수신기 중 하나인 <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>가 자동으로 만들어지고 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-104">One such listener, the <xref:System.Diagnostics.DefaultTraceListener?displayProperty=nameWithType>, is automatically created and initialized when tracing or debugging is enabled.</span></span> <span data-ttu-id="31a73-105"><xref:System.Diagnostics.Trace> 또는 <xref:System.Diagnostics.Debug> 출력을 추가 소스에 보내려면 추가 추적 수신기를 만들고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-105">If you want <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.Debug> output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span>  
  
 <span data-ttu-id="31a73-106">수신기를 만들 때는 응용 프로그램에 필요한 내용을 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-106">The listeners you create should reflect your application's needs.</span></span> <span data-ttu-id="31a73-107">예를 들어 모든 추적 출력의 텍스트 레코드가 필요하면 사용될 경우 모든 출력을 새 텍스트 파일에 쓰는 <xref:System.Diagnostics.TextWriterTraceListener> 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-107">For example, if you want a text record of all trace output, create a <xref:System.Diagnostics.TextWriterTraceListener> listener, which writes all output to a new text file when it is enabled.</span></span> <span data-ttu-id="31a73-108">반면에 응용 프로그램 실행 중에만 출력을 보려면 모든 출력을 콘솔 창으로 보내는 <xref:System.Diagnostics.ConsoleTraceListener> 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-108">On the other hand, if you want to view output only during application execution, create a <xref:System.Diagnostics.ConsoleTraceListener> listener, which directs all output to a console window.</span></span> <span data-ttu-id="31a73-109"><xref:System.Diagnostics.EventLogTraceListener>는 추적 출력을 이벤트 로그에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-109">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log.</span></span> <span data-ttu-id="31a73-110">자세한 내용은 [추적 수신기](../../../docs/framework/debug-trace-profile/trace-listeners.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31a73-110">For more information, see [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md).</span></span>  
  
 <span data-ttu-id="31a73-111">[응용 프로그램 구성 파일](../../../docs/framework/configure-apps/index.md) 또는 코드에서 추적 수신기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-111">You can create trace listeners in an [application configuration file](../../../docs/framework/configure-apps/index.md) or in your code.</span></span> <span data-ttu-id="31a73-112">응용 프로그램 구성 파일을 사용하면 코드를 변경할 필요 없이 추적 수신기를 추가, 수정 또는 제거할 수 있으므로 응용 프로그램 구성 파일을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-112">We recommend the use of application configuration files, because they let you add, modify, or remove trace listeners without having to change your code.</span></span>  
  
### <a name="to-create-and-use-a-trace-listener-by-using-a-configuration-file"></a><span data-ttu-id="31a73-113">구성 파일을 사용하여 추적 수신기를 만들고 사용하려면</span><span class="sxs-lookup"><span data-stu-id="31a73-113">To create and use a trace listener by using a configuration file</span></span>  
  
1.  <span data-ttu-id="31a73-114">응용 프로그램 구성 파일에서 추적 수신기를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-114">Declare your trace listener in your application configuration file.</span></span> <span data-ttu-id="31a73-115">만드는 수신기에 다른 개체가 필요하면 이들 개체도 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-115">If the listener you are creating requires any other objects, declare them as well.</span></span> <span data-ttu-id="31a73-116">다음 예제에서는 텍스트 파일을 `TextWriterOutput.log`에 쓰는 `myListener`라는 수신기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-116">The following example shows how to create a listener called `myListener` that writes to the text file `TextWriterOutput.log`.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <trace autoflush="false" indentsize="4">  
          <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener" initializeData="TextWriterOutput.log" />  
            <remove name="Default" />  
          </listeners>  
        </trace>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
2.  <span data-ttu-id="31a73-117">코드에서 <xref:System.Diagnostics.Trace> 클래스를 사용하여 추적 수신기에 메시지를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-117">Use the <xref:System.Diagnostics.Trace> class in your code to write a message to the trace listeners.</span></span>  
  
    ```vb  
    Trace.TraceInformation("Test message.")  
    ' You must close or flush the trace to empty the output buffer.  
    Trace.Flush()  
    ```  
  
    ```csharp  
    Trace.TraceInformation("Test message.");  
    // You must close or flush the trace to empty the output buffer.  
    Trace.Flush();  
    ```  
  
### <a name="to-create-and-use-a-trace-listener-in-code"></a><span data-ttu-id="31a73-118">코드에서 추적 수신기를 만들고 사용하려면</span><span class="sxs-lookup"><span data-stu-id="31a73-118">To create and use a trace listener in code</span></span>  
  
-   <span data-ttu-id="31a73-119">추적 수신기를 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션에 추가하고 추적 정보를 수신기에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-119">Add the trace listener to the <xref:System.Diagnostics.Trace.Listeners%2A> collection and send trace information to the listeners.</span></span>  
  
    ```vb  
    Trace.Listeners.Add(New TextWriterTraceListener("TextWriterOutput.log", "myListener"))  
    Trace.TraceInformation("Test message.")  
    ' You must close or flush the trace to empty the output buffer.  
    Trace.Flush()  
    ```  
  
    ```csharp  
    Trace.Listeners.Add(new TextWriterTraceListener("TextWriterOutput.log", "myListener"));  
    Trace.TraceInformation("Test message.");  
    // You must close or flush the trace to empty the output buffer.  
    Trace.Flush();  
    ```  
  
     - <span data-ttu-id="31a73-120">또는</span><span class="sxs-lookup"><span data-stu-id="31a73-120">or -</span></span>  
  
-   <span data-ttu-id="31a73-121">수신기에서 추적 출력을 수신하지 않으려면 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션에 수신기를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="31a73-121">If you do not want your listener to receive trace output, do not add it to the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span> <span data-ttu-id="31a73-122">수신기의 고유한 출력 메서드를 호출하여 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션과 관계없이 수신기를 통해 출력을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-122">You can emit output through a listener independent of the <xref:System.Diagnostics.Trace.Listeners%2A> collection by calling the listener's own output methods.</span></span> <span data-ttu-id="31a73-123">다음 예제에서는 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션에 없는 수신기에 줄을 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31a73-123">The following example shows how to write a line to a listener that is not in the <xref:System.Diagnostics.Trace.Listeners%2A> collection.</span></span>  
  
    ```vb  
    Dim myListener As New TextWriterTraceListener("TextWriterOutput.log", "myListener")  
    myListener.WriteLine("Test message.")  
    ' You must close or flush the trace listener to empty the output buffer.  
    myListener.Flush()  
    ```  
  
    ```csharp  
    TextWriterTraceListener myListener = new TextWriterTraceListener("TextWriterOutput.log", "myListener");  
    myListener.WriteLine("Test message.");  
    // You must close or flush the trace listener to empty the output buffer.  
    myListener.Flush();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31a73-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31a73-124">See Also</span></span>  
 [<span data-ttu-id="31a73-125">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="31a73-125">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="31a73-126">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="31a73-126">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="31a73-127">방법: 응용 프로그램 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="31a73-127">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="31a73-128">응용 프로그램 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="31a73-128">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
