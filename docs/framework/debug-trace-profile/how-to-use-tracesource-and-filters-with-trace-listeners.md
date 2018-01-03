---
title: "방법: 추적 수신기와 함께 TraceSource 및 필터 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 559926fffa52b234dda25ba2f0fd658aa2382c16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="cc81a-102">방법: 추적 수신기와 함께 TraceSource 및 필터 사용</span><span class="sxs-lookup"><span data-stu-id="cc81a-102">How to: Use TraceSource and Filters with Trace Listeners</span></span>
<span data-ttu-id="cc81a-103">.NET Framework 버전 2.0의 새로운 기능 중 하나는 향상된 추적 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-103">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="cc81a-104">기본 전제는 변경되지 않습니다. 추적 메시지는 스위치를 통해 수신기로 전송되고 이러한 수신기는 데이터를 연결된 출력 매체에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-104">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="cc81a-105">버전 2.0에 대한 주요 차이점은 추적이 <xref:System.Diagnostics.TraceSource> 클래스의 인스턴스를 통해 시작될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-105">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="cc81a-106"><xref:System.Diagnostics.TraceSource>는 향상된 추적 시스템으로 작동해야 하고 오래된 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 추적 클래스의 정적 메서드 대신 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-106"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="cc81a-107">익숙한 <xref:System.Diagnostics.Trace> 및 <xref:System.Diagnostics.Debug> 클래스가 있지만 추적에는 <xref:System.Diagnostics.TraceSource> 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-107">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="cc81a-108">이 항목에서는 응용 프로그램 구성 파일과 함께 <xref:System.Diagnostics.TraceSource>를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-108">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="cc81a-109">권장되지는 않지만 구성 파일을 사용하지 않고 <xref:System.Diagnostics.TraceSource>를 사용하여 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-109">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="cc81a-110">구성 파일 없이 추적하는 방법에 대한 자세한 내용은 [방법: 추적 소스 생성 및 초기화](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc81a-110">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="cc81a-111">추적 소스를 만들고 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="cc81a-111">To create and initialize your trace source</span></span>  
  
1.  <span data-ttu-id="cc81a-112">추적을 통해 응용 프로그램을 계측하는 첫 번째 단계는 추적 소스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-112">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="cc81a-113">다양한 구성 요소가 포함된 대규모 프로젝트에서 각 구성 요소에 대한 개별 추적 소스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-113">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="cc81a-114">추적 소스 이름에 대해 응용 프로그램 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-114">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="cc81a-115">이렇게 하면 여러 추적을 쉽게 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-115">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="cc81a-116">다음 코드에서는 이벤트를 추적하는 새 추적 소스(`mySource)`)를 만들고 메서드(`Activity1`)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-116">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="cc81a-117">추적 메시지는 기본 추적 수신기에서 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-117">The trace messages are written by the default trace listener.</span></span>  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="cc81a-118">추적 수신기 및 필터를 만들고 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="cc81a-118">To create and initialize trace listeners and filters</span></span>  
  
1.  <span data-ttu-id="cc81a-119">첫 번째 프로시저의 코드는 추적 수신기 또는 필터를 프로그래밍 방식으로 식별하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-119">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="cc81a-120">이 코드만으로는 추적 메시지가 기본 추적 수신기에 기록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-120">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="cc81a-121">특정 추적 수신기 및 수신기의 연결된 필터를 구성하려면 응용 프로그램 이름에 해당하는 구성 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-121">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="cc81a-122">이 파일에서 수신기를 추가 또는 제거하거나, 수신기에 대한 속성 및 필터를 설정하거나, 수신기를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-122">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="cc81a-123">다음 구성 파일 예제에서는 이전 프로시저에서 만들어진 추적 소스에 대해 콘솔 추적 수신기 및 텍스트 기록기 추적 수신기를 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-123">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="cc81a-124">추적 수신기의 구성 이외에도 구성 파일은 두 수신기에 대한 필터를 만들고 추적 소스에 대한 소스 스위치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-124">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="cc81a-125">추적 수신기를 추가하는 데는 두 가지 방법이 사용됩니다. 즉 수신기를 추적 소스에 직접 추가하는 방법과 수신기를 공유 컬렉션에 추가한 다음 이를 이름별로 추적 소스에 추가하는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-125">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="cc81a-126">두 수신기에 대해 식별된 필터는 서로 다른 소스 수준으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-126">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="cc81a-127">이로 인해 일부 메시지가 두 수신기 중 하나에 의해서만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-127">This results in some messages being written by only one of the two listeners.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="cc81a-128">수신기가 추적 메시지를 기록하는 수준을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="cc81a-128">To change the level at which a listener writes a trace message</span></span>  
  
1.  <span data-ttu-id="cc81a-129">구성 파일은 응용 프로그램이 초기화될 때 추적 소스에 대한 설정을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-129">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="cc81a-130">해당 설정을 변경하려면 구성 파일을 변경하고 응용 프로그램을 다시 시작하거나, <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> 메서드를 사용하여 응용 프로그램을 프로그래밍 방식으로 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-130">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cc81a-131">응용 프로그램은 구성 파일에서 설정되는 속성을 동적으로 변경하여 사용자가 지정한 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-131">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="cc81a-132">예를 들어, 현재의 구성 설정과 관계없이 중대 오류 메시지를 항상 텍스트 파일로 보내도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc81a-132">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cc81a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc81a-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventTypeFilter>  
 [<span data-ttu-id="cc81a-134">방법: 추적 소스 생성 및 초기화</span><span class="sxs-lookup"><span data-stu-id="cc81a-134">How to: Create and Initialize Trace Sources</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)  
 [<span data-ttu-id="cc81a-135">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="cc81a-135">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
