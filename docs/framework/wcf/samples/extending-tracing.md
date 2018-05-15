---
title: 추적 확장
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 59291b6a57ba602e5fea84dcd571a8d767b7cc04
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="extending-tracing"></a><span data-ttu-id="8157f-102">추적 확장</span><span class="sxs-lookup"><span data-stu-id="8157f-102">Extending Tracing</span></span>
<span data-ttu-id="8157f-103">이 샘플에서는 클라이언트 및 서비스 코드에 사용자 정의 동작 추적을 작성 하 여 Windows Communication Foundation (WCF) 추적 기능을 확장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="8157f-104">이렇게 하면 사용자가 작업의 논리 단위에 대한 추적 동작 및 그룹 추적을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="8157f-105">전송(같은 끝점 내)과 전파(끝점 사이)를 통해 동작을 상호 연결시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="8157f-106">이 샘플에서는 클라이언트와 서버 모두에 대해 추적이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="8157f-107">클라이언트 및 서비스 구성 파일에서 추적을 설정 하는 방법에 대 한 자세한 내용은 참조 [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="8157f-108">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8157f-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8157f-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8157f-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8157f-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8157f-112">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8157f-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8157f-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="8157f-114">추적 및 동작 전파</span><span class="sxs-lookup"><span data-stu-id="8157f-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="8157f-115">사용자 정의 동작 추적을 사용 하면 사용자가 직접 추적 동작 추적을 그룹화 하려면 작업의 논리 단위를 만들고, 동작, 전송 및 전파를 통해 상호 연결 (예: 디스크 공간 비용 WCF 추적의 성능 비용을 줄일 수 로그 파일).</span><span class="sxs-lookup"><span data-stu-id="8157f-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="8157f-116">사용자 지정 소스 추가</span><span class="sxs-lookup"><span data-stu-id="8157f-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="8157f-117">사용자 정의 추적은 클라이언트와 서비스 코드 모두에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="8157f-118">이러한 사용자 지정 추적 기록 하 고 표시 하는 클라이언트 또는 서비스 구성 파일에 추적 소스 허용 추가 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="8157f-119">다음 코드에서는 `ServerCalculatorTraceSource`라는 사용자 정의 추적 소스를 구성 파일에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
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
  
### <a name="correlating-activities"></a><span data-ttu-id="8157f-120">동작 상호 연결</span><span class="sxs-lookup"><span data-stu-id="8157f-120">Correlating Activities</span></span>  
 <span data-ttu-id="8157f-121">끝점 사이에서 직접 동작을 상호 연결하려면 `propagateActivity` 추적 소스에서 `true` 특성을 `System.ServiceModel`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="8157f-122">또한 WCF 작업을 수행 하지 않고 추적을 전파 하려면 ServiceModel 동작 추적 꺼야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="8157f-123">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8157f-124">ServiceModel 동작 추적을 끄는 것은 `switchValue` 속성으로 표시되는 추적 수준을 off로 설정하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="8157f-125">수행 비용 절감</span><span class="sxs-lookup"><span data-stu-id="8157f-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="8157f-126">`ActivityTracing` 추적 소스에서 `System.ServiceModel`을 off로 설정하면 ServiceModel 동작 추적이 포함되지 않고 사용자 정의 동작 추적만 포함된 추적 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="8157f-127">그러면 로그 파일의 크기가 훨씬 작아집니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="8157f-128">그러나을 WCF 처리 추적을 상호 연결할 기회는 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8157f-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8157f-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8157f-130">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8157f-131">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8157f-132">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8157f-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8157f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8157f-133">See Also</span></span>  
 [<span data-ttu-id="8157f-134">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="8157f-134">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
