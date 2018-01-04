---
title: "추적 및 메시지 로깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: "53"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91d824efaf8f58074297c417990ecf6b3aef78eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="1cc32-102">추적 및 메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="1cc32-102">Tracing and Message Logging</span></span>
<span data-ttu-id="1cc32-103">이 샘플에서는 추적 및 메시지 로깅을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="1cc32-104">결과 추적 및 메시지 로그를 사용 하 여 표시 되는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="1cc32-105">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cc32-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="1cc32-107">추적</span><span class="sxs-lookup"><span data-stu-id="1cc32-107">Tracing</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1cc32-108">는 <xref:System.Diagnostics> 네임스페이스에 정의된 추적 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-108"> uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="1cc32-109">이 추적 모델에서 추적 데이터는 응용 프로그램이 구현하는 추적 소스에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="1cc32-110">각 소스는 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-110">Each source is identified by a name.</span></span> <span data-ttu-id="1cc32-111">추적 소비자는 정보를 검색하려는 추적 소스에 대한 추적 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="1cc32-112">추적 데이터를 수신하려면 추적 소스에 대한 수신기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="1cc32-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이 작업을 수행하려면 서비스 모델 추적 소스를 `switchValue`로 설정하여 서비스나 클라이언트의 구성 파일에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-113">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="1cc32-114">추적 소스에 대 한 자세한 내용은 참조 추적 소스는 [추적 구성](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="1cc32-115">동작 추적 및 전파</span><span class="sxs-lookup"><span data-stu-id="1cc32-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="1cc32-116">필요 `ActivityTracing` 사용 하도록 설정 하 고 `propagateActivity` 로 설정 `true` 에 `system.ServiceModel` (끝점 내의 동작 사이 (활동), 처리의 논리 단위에서 추적의 상관 관계를 제공 하는 클라이언트와 서비스 모두에 대 한 추적 소스 동작 전송을 통해), 부분과 (동작 ID 전파)를 통해 여러 끝점에 걸쳐 있는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="1cc32-117">이러한 세 가지 메커니즘(동작, 전송 및 전파)은 Service Trace Viewer 도구를 사용하여 오류의 근본 원인을 더 신속하게 찾을 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="1cc32-118">자세한 내용은 참조 [상관 관계가 지정 된 추적 보기 및 문제 해결에 대 한 Service Trace Viewer를 사용 하 여](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="1cc32-119">사용자 정의 동작 추적을 만들어 ServiceModel이 제공되는 추적을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="1cc32-120">사용자 정의 동작 추적을 통해 사용자는 추적 동작을 만들어 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
-   <span data-ttu-id="1cc32-121">추적을 작업의 논리 단위로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-121">Group traces into logical units of work.</span></span>  
  
-   <span data-ttu-id="1cc32-122">전송과 전파를 통해 동작을 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-122">Correlate activities through transfers and propagation.</span></span>  
  
-   <span data-ttu-id="1cc32-123">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추적의 성능 비용(예: 로그 파일의 디스크 공간 비용)을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-123">Lessen the performance cost of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="1cc32-124">사용자 정의 동작 추적에 대 한 자세한 내용은 참조 하십시오는 [추적 확장](../../../../docs/framework/wcf/samples/extending-tracing.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="1cc32-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="1cc32-125">메시지 로깅</span><span class="sxs-lookup"><span data-stu-id="1cc32-125">Message Logging</span></span>  
 <span data-ttu-id="1cc32-126">모든 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램의 클라이언트 및 서비스 둘 다에서 메시지 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-126">Message logging can be enabled both on the client and service of any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="1cc32-127">메시지 로깅을 사용하도록 설정하려면 클라이언트나 서비스에 다음 코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels >  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="1cc32-128">메시지가 기록될 때 클라이언트에서 추적되는지 아니면 서버에서 추적되는지 여부에 따라 추적 유형이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="1cc32-129">예를 들어, 클라이언트에 보내지는 "추가" 메시지는 클라이언트에서는 "TransportWrite" 범주 아래에 추적되지만 서비스에서는 "TransportRead" 범주 아래에 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="1cc32-130">클라이언트의 App.config 파일이나 서비스의 Web.config 파일의 <xref:System.Diagnostics> 섹션에 다음 코드를 추가하여 추적 수신기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="1cc32-131">메시지는 구성 파일에 지정된 대상 디렉터리에 XML 형식으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cc32-132">처음에 로그 디렉터리를 만들어야 추적 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="1cc32-133">C:\logs\ 디렉터리가 있는지 확인하거나 수신기 구성에서 대체 로깅 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="1cc32-134">자세한 내용은 이 문서의 끝에 있는 초기 설정 지침을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1cc32-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="1cc32-135">메시지 로깅에 대 한 자세한 내용은 참조는 [메시지 로깅 구성](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1cc32-136">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1cc32-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1cc32-137">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1cc32-138">Tracing and Message Logging 샘플을 실행하기 전에 .svclog 파일을 서비스에서 기록할 수 있도록 C:\logs\ 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="1cc32-139">이 디렉터리의 이름은 추적 및 메시지를 기록하기 위한 경로로 구성 파일에 정의되며 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="1cc32-140">로그 디렉터리에 대한 Network Service 쓰기 권한을 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3.  <span data-ttu-id="1cc32-141">지침에 따라 솔루션의 C#, c + + 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="1cc32-142">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1cc32-143">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1cc32-144">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1cc32-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1cc32-145">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="1cc32-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1cc32-146">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc32-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="1cc32-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cc32-147">See Also</span></span>  
 [<span data-ttu-id="1cc32-148">추적</span><span class="sxs-lookup"><span data-stu-id="1cc32-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1cc32-149">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="1cc32-149">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
