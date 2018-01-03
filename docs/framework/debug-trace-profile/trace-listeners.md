---
title: "추적 수신기"
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
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 042b8a6f7c25c34fc06d5d0bfd4ebce6417b920f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="trace-listeners"></a><span data-ttu-id="583d4-102">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="583d4-102">Trace Listeners</span></span>
<span data-ttu-id="583d4-103">**Trace**, **Debug** 및 <xref:System.Diagnostics.TraceSource>를 사용하는 경우 전송된 메시지를 수집 및 기록하는 메커니즘이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-103">When using **Trace**, **Debug** and <xref:System.Diagnostics.TraceSource>, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="583d4-104">*수신기*가 추적 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-104">Trace messages are received by *listeners*.</span></span> <span data-ttu-id="583d4-105">수신기의 목적은 추적 메시지를 수집, 저장 및 라우팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-105">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="583d4-106">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절한 대상에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-106">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="583d4-107">각각 출력을 다양한 수신기 개체에 전송할 수 있는 **Debug**, **Trace** 및 <xref:System.Diagnostics.TraceSource> 클래스에서 수신기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-107">Listeners are available to the **Debug**, **Trace**, and <xref:System.Diagnostics.TraceSource> classes, each of which can send its output to a variety of listener objects.</span></span> <span data-ttu-id="583d4-108">일반적으로 사용되는 미리 정의된 수신기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-108">The following are the commonly used predefined listeners:</span></span>  
  
-   <span data-ttu-id="583d4-109"><xref:System.Diagnostics.TextWriterTraceListener>는 출력을 <xref:System.IO.TextWriter> 클래스 인스턴스 또는 <xref:System.IO.Stream> 클래스에 해당하는 항목에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-109">A <xref:System.Diagnostics.TextWriterTraceListener> redirects output to an instance of the <xref:System.IO.TextWriter> class or to anything that is a <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="583d4-110">콘솔과 파일은 <xref:System.IO.Stream> 클래스이므로 이 수신기가 콘솔이나 파일에 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-110">It can also write to the console or to a file, because these are <xref:System.IO.Stream> classes.</span></span>  
  
-   <span data-ttu-id="583d4-111"><xref:System.Diagnostics.EventLogTraceListener>는 출력을 이벤트 로그에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-111">An <xref:System.Diagnostics.EventLogTraceListener> redirects output to an event log.</span></span>  
  
-   <span data-ttu-id="583d4-112"><xref:System.Diagnostics.DefaultTraceListener>는 **Write** 및 **WriteLine** 메시지를 **OutputDebugString** 및 **Debugger.Log** 메서드에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-112">A <xref:System.Diagnostics.DefaultTraceListener> emits **Write** and **WriteLine** messages to the **OutputDebugString** and to the **Debugger.Log** method.</span></span> <span data-ttu-id="583d4-113">Visual Studio에서는 이를 통해 디버깅 메시지가 출력 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-113">In Visual Studio, this causes the debugging messages to appear in the Output window.</span></span> <span data-ttu-id="583d4-114">**Fail** 및 실패한 **Assert** 메시지도 **OutputDebugString** Windows API 및 **Debugger.Log** 메서드에 내보내고 이를 통해 메시지 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-114">**Fail** and failed **Assert** messages also emit to the **OutputDebugString** Windows API and the **Debugger.Log** method, and also cause a message box to be displayed.</span></span> <span data-ttu-id="583d4-115">이 동작은 **Debug** 및 **Trace** 메시지에 대한 기본 동작입니다. 이는 **DefaultTraceListener**가 모든 `Listeners` 컬렉션에 자동으로 포함되고 자동으로 포함되는 유일한 수신기이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-115">This behavior is the default behavior for **Debug** and **Trace** messages, because **DefaultTraceListener** is automatically included in every `Listeners` collection and is the only listener automatically included.</span></span>  
  
-   <span data-ttu-id="583d4-116"><xref:System.Diagnostics.ConsoleTraceListener>는 추적 또는 디버깅 출력을 표준 출력이나 표준 오류 스트림에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-116">A <xref:System.Diagnostics.ConsoleTraceListener> directs tracing or debugging output to either the standard output or the standard error stream.</span></span>  
  
-   <span data-ttu-id="583d4-117"><xref:System.Diagnostics.DelimitedListTraceListener>는 추적 또는 디버깅 출력을 스트림 작성기와 같은 텍스트 작성기 또는 파일 스트림과 같은 스트림으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-117">A <xref:System.Diagnostics.DelimitedListTraceListener> directs tracing or debugging output to a text writer, such as a stream writer, or to a stream, such as a file stream.</span></span> <span data-ttu-id="583d4-118">추적 출력은 <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> 속성으로 지정된 구분 기호를 사용하는 구분된 텍스트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-118">The trace output is in a delimited text format that uses the delimiter specified by the <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> property.</span></span>  
  
-   <span data-ttu-id="583d4-119"><xref:System.Diagnostics.XmlWriterTraceListener>는 추적 및 디버깅 출력을 XML로 인코딩된 데이터로 <xref:System.IO.TextWriter> 또는 <xref:System.IO.Stream>(예: <xref:System.IO.FileStream>)에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-119">An <xref:System.Diagnostics.XmlWriterTraceListener> directs tracing or debugging output as XML-encoded data to a <xref:System.IO.TextWriter> or to a <xref:System.IO.Stream>, such as a <xref:System.IO.FileStream>.</span></span>  
  
 <span data-ttu-id="583d4-120"><xref:System.Diagnostics.DefaultTraceListener> 이외의 수신기가 **Debug**, **Trace** 및 <xref:System.Diagnostics.TraceSource> 출력을 수신하게 하려면 수신기를 `Listeners` 컬렉션에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-120">If you want any listener besides the <xref:System.Diagnostics.DefaultTraceListener> to receive **Debug**, **Trace** and <xref:System.Diagnostics.TraceSource> output, you must add it to the `Listeners` collection.</span></span> <span data-ttu-id="583d4-121">자세한 내용은 [방법: 추적 수신기 만들기 및 초기화](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) 및 [방법: 추적 수신기와 함께 TraceSource 및 필터 사용](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="583d4-121">For more information, see [How to: Create and Initialize Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) and [How to: Use TraceSource and Filters with Trace Listeners](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span> <span data-ttu-id="583d4-122">**Listeners** 컬렉션의 모든 수신기는 추적 출력 메서드에서 같은 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-122">Any listener in the **Listeners** collection gets the same messages from the trace output methods.</span></span> <span data-ttu-id="583d4-123">예를 들어 두 가지 수신기인 **TextWriterTraceListener** 및 **EventLogTraceListener**를 설정한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-123">For example, suppose you set up two listeners: a **TextWriterTraceListener** and an **EventLogTraceListener**.</span></span> <span data-ttu-id="583d4-124">각 수신기는 같은 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-124">Each listener receives the same message.</span></span> <span data-ttu-id="583d4-125">**TextWriterTraceListener**는 출력을 스트림에 전달하고 **EventLogTraceListener**는 출력을 이벤트 로그에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-125">The **TextWriterTraceListener** would direct its output to a stream, and the **EventLogTraceListener** would direct its output to an event log.</span></span>  
  
 <span data-ttu-id="583d4-126">다음 예제에서는 출력을 **Listeners** 컬렉션에 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-126">The following example shows how to send output to the **Listeners** collection.</span></span>  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 <span data-ttu-id="583d4-127">Debug 및 Trace는 같은 **Listeners** 컬렉션을 공유하므로, 수신기 개체를 응용 프로그램의 **Debug.Listeners** 컬렉션에 추가하면 **Trace.Listeners** 컬렉션에도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-127">Debug and trace share the same **Listeners** collection, so if you add a listener object to a **Debug.Listeners** collection in your application, it gets added to the **Trace.Listeners** collection as well.</span></span>  
  
 <span data-ttu-id="583d4-128">다음 예제에서는 수신기를 사용하여 추적 정보를 콘솔에 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-128">The following example shows how to use a listener to send tracing information to a console:</span></span>  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a><span data-ttu-id="583d4-129">개발자 정의 수신기</span><span class="sxs-lookup"><span data-stu-id="583d4-129">Developer-Defined Listeners</span></span>  
 <span data-ttu-id="583d4-130">**TraceListener** 기본 클래스에서 상속하고 해당 메서드를 사용자 지정 메서드로 재정의하는 방식으로 고유한 수신기를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="583d4-130">You can define your own listeners by inheriting from the **TraceListener** base class and overriding its methods with your customized methods.</span></span> <span data-ttu-id="583d4-131">개발자 정의 수신기를 만드는 방법에 대한 자세한 내용은 .NET Framework 참조에서 <xref:System.Diagnostics.TraceListener>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="583d4-131">For more information on creating developer-defined listeners, see <xref:System.Diagnostics.TraceListener> in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583d4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="583d4-132">See Also</span></span>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="583d4-133">응용 프로그램 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="583d4-133">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [<span data-ttu-id="583d4-134">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="583d4-134">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
