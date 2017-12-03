---
title: "추적 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09804e91b872e4daca929d9f9740d691d42b31c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="extending-tracing"></a><span data-ttu-id="4b7ff-102">추적 확장</span><span class="sxs-lookup"><span data-stu-id="4b7ff-102">Extending Tracing</span></span>
<span data-ttu-id="4b7ff-103">이 샘플에서는 클라이언트 및 서비스 코드에 사용자 정의 동작 추적을 써서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 추적 기능을 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-103">This sample demonstrates how to extend the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="4b7ff-104">이렇게 하면 사용자가 작업의 논리 단위에 대한 추적 동작 및 그룹 추적을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="4b7ff-105">전송(같은 끝점 내)과 전파(끝점 사이)를 통해 동작을 상호 연결시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="4b7ff-106">이 샘플에서는 클라이언트와 서버 모두에 대해 추적이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="4b7ff-107">클라이언트 및 서비스 구성 파일에서 추적을 설정 하는 방법에 대 한 자세한 내용은 참조 [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="4b7ff-108">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7ff-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b7ff-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4b7ff-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4b7ff-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4b7ff-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="4b7ff-114">추적 및 동작 전파</span><span class="sxs-lookup"><span data-stu-id="4b7ff-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="4b7ff-115">사용자 정의 동작 추적을 사용하면 사용자가 직접 추적 동작을 만들어 논리적인 작업 단위로 추적을 그룹화하고, 전송 및 전파를 통해 동작을 상호 연결시키고, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추적의 수행 비용을 절감할 수 있습니다(예: 로그 파일의 디스크 공간 비용).</span><span class="sxs-lookup"><span data-stu-id="4b7ff-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="4b7ff-116">사용자 지정 소스 추가</span><span class="sxs-lookup"><span data-stu-id="4b7ff-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="4b7ff-117">사용자 정의 추적은 클라이언트와 서비스 코드 모두에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="4b7ff-118">이러한 사용자 지정 추적 기록 하 고 표시 하는 클라이언트 또는 서비스 구성 파일에 추적 소스 허용 추가 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="4b7ff-119">다음 코드에서는 `ServerCalculatorTraceSource`라는 사용자 정의 추적 소스를 구성 파일에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="4b7ff-120">동작 상호 연결</span><span class="sxs-lookup"><span data-stu-id="4b7ff-120">Correlating Activities</span></span>  
 <span data-ttu-id="4b7ff-121">끝점 사이에서 직접 동작을 상호 연결하려면 `propagateActivity` 추적 소스에서 `true` 특성을 `System.ServiceModel`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="4b7ff-122">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동작을 수행하지 않고 추적을 전파하려면 ServiceModel 동작 추적이 꺼져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-122">Also, to propagate traces without going through [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="4b7ff-123">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7ff-124">ServiceModel 동작 추적을 끄는 것은 `switchValue` 속성으로 표시되는 추적 수준을 off로 설정하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="4b7ff-125">수행 비용 절감</span><span class="sxs-lookup"><span data-stu-id="4b7ff-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="4b7ff-126">`ActivityTracing` 추적 소스에서 `System.ServiceModel`을 off로 설정하면 ServiceModel 동작 추적이 포함되지 않고 사용자 정의 동작 추적만 포함된 추적 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="4b7ff-127">그러면 로그 파일의 크기가 훨씬 작아집니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="4b7ff-128">하지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 처리 추적을 상호 연결할 기회는 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-128">However, the opportunity to correlate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4b7ff-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4b7ff-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4b7ff-130">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4b7ff-131">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4b7ff-132">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ff-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7ff-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b7ff-133">See Also</span></span>  
 [<span data-ttu-id="4b7ff-134">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="4b7ff-134">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
