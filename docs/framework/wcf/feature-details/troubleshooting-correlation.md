---
title: "상관 관계 문제 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 07fd03d929c99638b2cb148beded118bbdd679a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-correlation"></a><span data-ttu-id="c11b1-102">상관 관계 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c11b1-102">Troubleshooting Correlation</span></span>
<span data-ttu-id="c11b1-103">상관 관계는 워크플로 서비스 메시지를 서로 연결하거나 올바른 워크플로 인스턴스에 연결하는 데 사용되지만, 제대로 구성되지 않으면 메시지가 수신되지 않고 응용 프로그램이 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-103">Correlation is used to relate workflow service messages to each other and to the correct workflow instance, but if it is not configured correctly, messages will not be received and applications will not work correctly.</span></span> <span data-ttu-id="c11b1-104">이 항목에서는 상관 관계 문제를 해결하기 위한 몇 가지 방법을 간략히 설명하고 상관 관계를 사용할 때 발생할 수 있는 일반적인 문제도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-104">This topic provides an overview of several methods for troubleshooting correlation issues, and also lists some common issues that can occur when you use correlation.</span></span>  
  
## <a name="handle-the-unknownmessagereceived-event"></a><span data-ttu-id="c11b1-105">UnknownMessageReceived 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="c11b1-105">Handle the UnknownMessageReceived Event</span></span>  
 <span data-ttu-id="c11b1-106"><xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> 이벤트는 서비스에서 기존 인스턴스와 연결할 수 없는 메시지를 포함하여 알 수 없는 메시지를 받을 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-106">The <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> event occurs when an unknown message is received by a service, including messages that cannot be correlated to an existing instance.</span></span> <span data-ttu-id="c11b1-107">자체 호스팅 서비스의 경우 이 이벤트는 호스트 응용 프로그램에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-107">For self-hosted services, this event can be handled in the host application.</span></span>  
  
```csharp  
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
{  
    Console.WriteLine("Unknown Message Received:");  
    Console.WriteLine(e.Message);  
};  
```  
  
 <span data-ttu-id="c11b1-108">웹 호스팅 서비스의 경우에는 <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory>에서 클래스를 파생시키고 <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>를 재정의하여 이 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-108">For Web-hosted services, this event can be handled by deriving a class from <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> and overriding <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span></span>  
  
```csharp  
class CustomFactory : WorkflowServiceHostFactory  
{  
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)  
    {  
        // Create the WorkflowServiceHost.  
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);  
  
        // Handle the UnknownMessageReceived event.  
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
        {  
            Console.WriteLine("Unknown Message Received:");  
            Console.WriteLine(e.Message);  
        };  
  
        return host;  
    }  
}  
```  
  
 <span data-ttu-id="c11b1-109">그런 다음 서비스의 <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> 파일에서 이 사용자 지정 `svc`를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-109">This custom <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> can then be specified in the `svc` file for the service.</span></span>  
  
```  
<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>  
```  
  
 <span data-ttu-id="c11b1-110">이 처리기가 호출되면 <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A>의 <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> 속성을 사용하여 메시지를 검색할 수 있으며 이 메시지는 다음 메시지와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-110">When this handler is invoked, the message can be retrieved by using the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> property of the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>, and will resemble the following message.</span></span>  
  
```Output  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
  </s:Header>  
  <s:Body>  
    <AddItem xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItem>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="c11b1-111"><xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> 처리기에 디스패치된 메시지를 검사하면 메시지가 워크플로 서비스의 인스턴스에 연결되지 않은 원인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-111">Inspecting messages dispatched to the <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> handler may provide clues about why the message did not correlate to an instance of the workflow service.</span></span>  
  
## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a><span data-ttu-id="c11b1-112">추적을 사용하여 워크플로 진행 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="c11b1-112">Use Tracking to Monitor the Progress of the Workflow</span></span>  
 <span data-ttu-id="c11b1-113">추적을 통해 워크플로의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-113">Tracking provides a way to monitor the progress of a workflow.</span></span> <span data-ttu-id="c11b1-114">기본적으로 워크플로 수명 주기 이벤트, 활동 수명 주기 이벤트, 오류 전파 및 책갈피 다시 시작에 대하여 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-114">By default, tracking records are emitted for workflow life-cycle events, activity life-cycle events, fault propagation, and bookmark resumption.</span></span> <span data-ttu-id="c11b1-115">또한 사용자 지정 활동에서 사용자 지정 추적 레코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-115">Additionally, custom tracking records can be emitted by custom activities.</span></span> <span data-ttu-id="c11b1-116">상관 관계 문제를 해결하는 경우에는 활동 추적 레코드, 책갈피 다시 시작 레코드 및 오류 전파 레코드가 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-116">When troubleshooting correlation, the activity tracking records, the bookmark resumption records, and the fault propagation records are the most useful.</span></span> <span data-ttu-id="c11b1-117">활동 추적 레코드는 워크플로의 현재 진행 상태를 확인하는 데 사용할 수 있으며 현재 메시지를 기다리고 있는 메시징 활동을 식별하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-117">The activity tracking records can be used to determine the current progress of the workflow and can help identify which messaging activity is currently waiting for messages.</span></span> <span data-ttu-id="c11b1-118">책갈피 다시 시작 레코드는 워크플로에서 메시지를 받았음을 나타내므로 유용하며, 오류 전파 레코드에서는 워크플로의 오류에 대한 레코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-118">Bookmark resumption records are useful because they indicate that a message was received by the workflow, and fault propagation records provide a record of any faults in the workflow.</span></span> <span data-ttu-id="c11b1-119">추적을 사용하도록 설정하려면 <xref:System.Activities.Tracking.TrackingParticipant>의 <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A>에서 원하는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-119">To enable tracking, specify the desired <xref:System.Activities.Tracking.TrackingParticipant> in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> of the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="c11b1-120">다음 예제에서는 `ConsoleTrackingParticipant` (에서 [사용자 지정 추적](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) 샘플) 기본 추적 프로필을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-120">In the following example, the `ConsoleTrackingParticipant` (from the [Custom Tracking](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) sample) is configured by using the default tracking profile.</span></span>  
  
```csharp  
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());  
```  
  
 <span data-ttu-id="c11b1-121">ConsoleTrackingParticipant와 같은 추적 참가자는 콘솔 창이 있는 자체 호스팅 워크플로 서비스에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-121">A tracking participant such as the ConsoleTrackingParticipant is useful for self-hosted workflow services that have a console window.</span></span> <span data-ttu-id="c11b1-122">웹 호스팅 서비스에 대 한 영 속 저장소에 추적 정보를 기록 하는 추적 참가자를 사용할지 같은 기본 제공 <xref:System.Activities.Tracking.EtwTrackingParticipant>, 또는 같은 파일에 정보를 기록 하는 사용자 지정 추적 참가자는 `TextWriterTrackingParticpant` 는 에서[ 텍스트 파일을 사용 하 여 추적](../../../../docs/framework/windows-workflow-foundation/samples/tracking-using-a-text-file.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c11b1-122">For a Web-hosted service, a tracking participant that logs the tracking information to a durable store should be used, such as the built-in <xref:System.Activities.Tracking.EtwTrackingParticipant>, or a custom tracking participant that logs the information to a file, such as the `TextWriterTrackingParticpant` from the [Tracking Using a Text File](../../../../docs/framework/windows-workflow-foundation/samples/tracking-using-a-text-file.md) sample.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c11b1-123">추적 및 웹 호스팅 워크플로 서비스에 대 한 추적을 구성을 참조 [워크플로 추적 및 트레이싱](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [워크플로에 대 한 추적 구성](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md), 및 [추적 &#91; WF 샘플 &#93; ](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-123"> tracking and configuring tracking for a Web-hosted workflow service, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md), and the [Tracking &#91;WF Samples&#93;](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) samples.</span></span>  
  
## <a name="use-wcf-tracing"></a><span data-ttu-id="c11b1-124">WCF 추적 사용</span><span class="sxs-lookup"><span data-stu-id="c11b1-124">Use WCF Tracing</span></span>  
 <span data-ttu-id="c11b1-125">WCF 추적은 워크플로 서비스 간의 메시지 흐름에 대한 추적을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-125">WCF tracing provides tracing of the flow of messages to and from a workflow service.</span></span> <span data-ttu-id="c11b1-126">이 추적 정보는 상관 관계 문제, 특히 내용 기반 상관 관계 문제를 해결하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-126">This tracing information is useful when troubleshooting correlation issues, especially for content-based correlation.</span></span> <span data-ttu-id="c11b1-127">추적을 사용하도록 설정하려면 `system.diagnostics` 파일(워크플로 서비스가 웹 호스팅 서비스인 경우) 또는 `web.config` 파일(워크플로 서비스가 자체 호스팅 서비스인 경우)의 `app.config` 섹션에서 원하는 추적 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-127">To enable tracing, specify the desired trace listeners in the `system.diagnostics` section of the `web.config` file if the workflow service is Web-hosted, or the `app.config` file if the workflow service is self-hosted.</span></span> <span data-ttu-id="c11b1-128">메시지의 내용을 추적 파일에 포함하려면 `true`의 `logEntireMessage` 섹션에 있는 `messageLogging` 요소에서 `diagnostics`에 `system.serviceModel`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-128">To include the contents of the messages in the trace file, specify `true` for `logEntireMessage` in the `messageLogging` element in the `diagnostics` section of `system.serviceModel`.</span></span> <span data-ttu-id="c11b1-129">다음 예제에서는 메시지 내용을 포함한 추적 정보를 `service.svclog`라는 파일에 기록하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-129">In the following example, tracing information, including the content of the messages, is configured to be written to a file that is named `service.svclog`.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
    </sources>  
  
    <sharedListeners>  
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging logEntireMessage="true" logMalformedMessages="false"  
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">  
      </messageLogging>  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c11b1-130">에 포함 된 추적 정보를 보려면 `service.svclog`, [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-130">To view the trace information that is contained in `service.svclog`, the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) is used.</span></span> <span data-ttu-id="c11b1-131">이 도구를 사용하면 메시지 내용을 볼 수 있을 뿐 아니라 내용 기반 상관 관계의 경우 전달되는 정확한 정보와 해당 정보가<xref:System.ServiceModel.CorrelationQuery>와 일치하는지 여부를 확인할 수 있으므로 내용 기반 상관 관계의 문제를 해결하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-131">This is especially useful when troubleshooting content-based correlation issues because you can view the message contents and see exactly what is being passed, and whether it matches the <xref:System.ServiceModel.CorrelationQuery> for the content-based correlation.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c11b1-132">WCF 추적 참조 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [추적 구성](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md), 및 [응용 프로그램 문제 해결에 대 한 추적 사용 하 여](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-132"> WCF tracing, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md), and [Using Tracing to Troubleshoot Your Application](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>  
  
## <a name="common-context-exchange-correlation-issues"></a><span data-ttu-id="c11b1-133">일반적인 컨텍스트 교환 상관 관계 문제</span><span class="sxs-lookup"><span data-stu-id="c11b1-133">Common Context Exchange Correlation Issues</span></span>  
 <span data-ttu-id="c11b1-134">일부 형식의 상관 관계에서는 특정 형식의 바인딩을 사용해야 상관 관계가 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-134">Certain types of correlation require that a specific type of binding is used for the correlation to work correctly.</span></span> <span data-ttu-id="c11b1-135">예제에는 <xref:System.ServiceModel.BasicHttpBinding> 같은 양방향 바인딩이 필요한 요청-회신 상관 관계와 <xref:System.ServiceModel.BasicHttpContextBinding> 같은 컨텍스트 기반 바인딩이 필요한 컨텍스트 교환 상관 관계가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-135">Examples include request-reply correlation, which requires a two-way binding such as <xref:System.ServiceModel.BasicHttpBinding>, and context exchange correlation, which requires a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> <span data-ttu-id="c11b1-136">대부분의 바인딩은 양방향 작업을 지원하므로 요청-회신 상관 관계의 경우에는 이러한 사항이 일반적인 문제가 아니지만, 컨텍스트 기반 바인딩은 <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> 및 <xref:System.ServiceModel.NetTcpContextBinding>을 비롯한 일부만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-136">Most bindings support two-way operations so this is not a common issue for request-reply correlation, but there are only a handful of context-based bindings including <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, and <xref:System.ServiceModel.NetTcpContextBinding>.</span></span> <span data-ttu-id="c11b1-137">이러한 바인딩 중 하나를 사용하지 않으면 워크플로 서비스에 대한 초기 호출은 성공하지만 후속 호출은 다음 <xref:System.ServiceModel.FaultException>과 함께 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-137">If one of these bindings is not used, the initial call to a workflow service will succeed, but subsequent calls will fail with the following <xref:System.ServiceModel.FaultException>.</span></span>  
  
```Output  
There is no context attached to the incoming message for the service   
and the current operation is not marked with "CanCreateInstance = true".   
In order to communicate with this service check whether the incoming binding   
supports the context protocol and has a valid context initialized.  
```  
  
 <span data-ttu-id="c11b1-138">컨텍스트 상관 관계에 사용되는 컨텍스트 정보는 <xref:System.ServiceModel.Activities.SendReply>에 의해 컨텍스트 상관 관계를 초기화하는 <xref:System.ServiceModel.Activities.Receive> 활동에 반환되거나(양방향 작업을 사용할 경우) 호출자에 의해 지정될 수 있습니다(단방향 작업을 사용할 경우).</span><span class="sxs-lookup"><span data-stu-id="c11b1-138">The context information that is used for context correlation can be returned by the <xref:System.ServiceModel.Activities.SendReply> to the <xref:System.ServiceModel.Activities.Receive> activity that initializes the context correlation when using a two-way operation, or it can be specified by the caller if the operation is one-way.</span></span> <span data-ttu-id="c11b1-139">컨텍스트를 호출자가 보내지 않거나 워크플로 서비스에서 반환하지 않는 경우에는 후속 작업이 호출될 때 위에서 설명한 것과 동일한 <xref:System.ServiceModel.FaultException>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-139">If the context is not sent by the caller or returned by the workflow service, then the same <xref:System.ServiceModel.FaultException> described previously will be returned when a subsequent operation is invoked.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c11b1-140">[컨텍스트 교환](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-140"> [Context Exchange](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).</span></span>  
  
## <a name="common-request-reply-correlation-issues"></a><span data-ttu-id="c11b1-141">일반적인 요청-회신 상관 관계 문제</span><span class="sxs-lookup"><span data-stu-id="c11b1-141">Common Request-Reply Correlation Issues</span></span>  
 <span data-ttu-id="c11b1-142">요청-회신 상관 관계와 함께 사용 되는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍 및 워크플로 서비스에서 양방향 작업을 구현 하는 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 다른 웹에서 양방향 작업을 호출 하는 쌍 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-142">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="c11b1-143">WCF 서비스에서 양방향 작업을 호출하는 경우 해당 서비스는 일반적인 명령적 코드 기반의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스이거나 워크플로 서비스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-143">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or it can be a workflow service.</span></span> <span data-ttu-id="c11b1-144">요청-회신 상관 관계를 사용하려면 <xref:System.ServiceModel.BasicHttpBinding> 같은 양방향 바인딩을 사용해야 하며 작업이 양방향이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-144">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>, and the operations must be two-way.</span></span>  
  
 <span data-ttu-id="c11b1-145">워크플로 서비스에 양방향 작업이 나란히 있거나 겹치지 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 또는 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 쌍을 다음 암시적 상관 관계 핸들 에서제공하는관리<xref:System.ServiceModel.Activities.WorkflowServiceHost>특히 스트레스가 높은 시나리오에서에서 충분 한 되지 않을 수 있습니다 및 메시지 올바르게 라우팅 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-145">If the workflow service has two-way operations in parallel, or overlapping <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> or <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pairs, then the implicit correlation handle management provided by <xref:System.ServiceModel.Activities.WorkflowServiceHost> may not be sufficient, especially in high-stress scenarios, and messages may not be correctly routed.</span></span> <span data-ttu-id="c11b1-146">이 문제를 방지하려면 요청-회신 상관 관계를 사용할 때 항상 <xref:System.ServiceModel.Activities.CorrelationHandle>을 명시적으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-146">To prevent this issue from occurring, we recommend that you always explicitly specify a <xref:System.ServiceModel.Activities.CorrelationHandle> when using request-reply correlation.</span></span> <span data-ttu-id="c11b1-147">사용 하는 경우는 **SendAndReceiveReply** 및 **ReceiveAndSendReply** 있는 메시징 섹션에서 템플릿에 **도구 상자** 워크플로 디자이너에서는 <xref:System.ServiceModel.Activities.CorrelationHandle> 기본적으로 명시적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-147">When using the **SendAndReceiveReply** and **ReceiveAndSendReply** templates from the Messaging section of the **Toolbox** in the workflow designer, a <xref:System.ServiceModel.Activities.CorrelationHandle> is explicitly configured by default.</span></span> <span data-ttu-id="c11b1-148">코드를 사용하여 워크플로를 바인딩하는 경우 <xref:System.ServiceModel.Activities.CorrelationHandle>은 쌍의 첫 번째 활동에 대한 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-148">When building a workflow by using code, the <xref:System.ServiceModel.Activities.CorrelationHandle> is specified in the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> of the first activity in the pair.</span></span> <span data-ttu-id="c11b1-149">다음 예제에서는 <xref:System.ServiceModel.Activities.Receive>에 <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A>을 명시적으로 지정하여 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 활동을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-149">In the following example, a <xref:System.ServiceModel.Activities.Receive> activity is configured with an explicit <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> specified in the <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = ... // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="c11b1-150">지 속성 간에 허용 되지 않습니다는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍 또는 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-150">Persistence is not permitted between a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair or a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair.</span></span> <span data-ttu-id="c11b1-151">두 활동이 모두 완료될 때까지 유지되는 비지속성 영역이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-151">A no-persist zone is created that lasts until both activities have completed.</span></span> <span data-ttu-id="c11b1-152">지연 활동과 같은 활동이 이 비지속성 영역에 있고 워크플로가 유휴 상태가 되도록 하는 경우 워크플로가 유휴 상태가 될 때 워크플로를 유지하도록 호스트를 구성한 경우에도 워크플로가 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-152">If an activity, such as a delay activity, is in this no-persist zone and causes the workflow to become idle, the workflow will not persist even if it the host is configured to persist workflows when they become idle.</span></span> <span data-ttu-id="c11b1-153">유지 활동과 같은 활동이 비지속성 영역에 명시적으로 유지하려고 하는 경우 치명적 예외가 throw되고 워크플로가 중단되며 <xref:System.ServiceModel.FaultException>이 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-153">If an activity, such as a persist activity, attempts to explicitly persist in the no-persist zone, a fatal exception is thrown, the workflow aborts, and a <xref:System.ServiceModel.FaultException> is returned to the caller.</span></span> <span data-ttu-id="c11b1-154">치명적 예외 메시지는 "System.InvalidOperationException: 지속성 작업은 비지속성 블록 내에 포함할 수 없습니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-154">The fatal exception message is "System.InvalidOperationException: Persist activities cannot be contained within no persistence blocks.".</span></span> <span data-ttu-id="c11b1-155">이 예외는 호출자에게 반환되지 않지만 추적을 사용하는 경우 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-155">This exception is not returned to the caller but can be observed if tracking is enabled.</span></span> <span data-ttu-id="c11b1-156">호출자에게 반환되는 <xref:System.ServiceModel.FaultException> 메시지는 "WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6'이(가) 완료되었으므로 작업을 수행할 수 없습니다."입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-156">The message for the <xref:System.ServiceModel.FaultException> returned to the caller is "The operation could not be performed because WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' has completed".</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c11b1-157">요청-회신 상관 관계 참조 [요청-회신](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-157"> request-reply correlation, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span></span>  
  
## <a name="common-content-correlation-issues"></a><span data-ttu-id="c11b1-158">일반적인 내용 상관 관계 문제</span><span class="sxs-lookup"><span data-stu-id="c11b1-158">Common Content Correlation Issues</span></span>  
 <span data-ttu-id="c11b1-159">내용 기반 상관 관계는 워크플로 서비스에서 여러 개의 메시지를 받으며 교환되는 메시지의 일부 데이터로 원하는 인스턴스를 식별할 수 있는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-159">Content-based correlation is used when a workflow service receives multiple messages and a piece of data in the exchanged messages identifies the desired instance.</span></span> <span data-ttu-id="c11b1-160">내용 기반 상관 관계는 메시지에 있는 이 데이터(예: 고객 번호 또는 주문 ID)를 사용하여 메시지를 올바른 워크플로 인스턴스에 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-160">Content-based correlation uses this data in the message, such as a customer number or order ID, to route messages to the correct workflow instance.</span></span> <span data-ttu-id="c11b1-161">이 단원에서는 내용 기반 상관 관계를 사용할 때 발생할 수 있는 몇 가지 일반적인 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-161">This section describes several common issues that may occur when using content-based correlation.</span></span>  
  
### <a name="ensure-the-identifying-data-is-unique"></a><span data-ttu-id="c11b1-162">식별 데이터가 고유한지 확인</span><span class="sxs-lookup"><span data-stu-id="c11b1-162">Ensure the Identifying Data Is Unique</span></span>  
 <span data-ttu-id="c11b1-163">인스턴스를 식별하는 데 사용되는 데이터는 상관 관계 키로 해시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-163">The data that is used to identify the instance is hashed into a correlation key.</span></span> <span data-ttu-id="c11b1-164">상관 관계에는 고유한 데이터를 사용해야 합니다. 그렇지 않으면 해시된 키에서 충돌이 발생하여 메시지가 잘못 라우트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-164">Care must be taken to guarantee that the data that is used for correlation is unique or else collisions in the hashed key might occur and cause messages to be misrouted.</span></span> <span data-ttu-id="c11b1-165">예를 들어 동일한 이름을 가진 고객이 여러 명 있을 수 있으므로 고객 이름에만 의존하는 상관 관계는 충돌을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-165">For example, a correlation based only on a customer name may cause a collision because there may be multiple customers who have the same name.</span></span> <span data-ttu-id="c11b1-166">메시지를 연결하는 데 사용되는 데이터에 콜론(:)을 포함하면 안 됩니다. 이는 이후에 해시되는 문자열을 만들기 위해 메시지 쿼리의 키와 값을 구분하는 데 콜론이 이미 사용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-166">The colon (:) should not be used as part of the data that is used to correlate the message because it is already used to delimit the message query’s key and value to form the string that is subsequently hashed.</span></span> <span data-ttu-id="c11b1-167">지속성이 사용되는 경우 현재 식별 데이터가 이전에 유지된 인스턴스에서 사용되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-167">If persistence is being used, make sure that the current identifying data has not been used by a previously persisted instance.</span></span> <span data-ttu-id="c11b1-168">지속성을 임시로 사용하지 않도록 설정하면 이 문제를 손쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-168">Temporarily disabling persistence can help identify this issue.</span></span> <span data-ttu-id="c11b1-169">WCF 추적은 계산된 상관 관계 키를 확인하는 데 사용할 수 있으며 이 종류의 문제를 디버깅하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-169">WCF tracing can be used to view the calculated correlation key and is useful for debugging this kind of issue.</span></span>  
  
### <a name="race-conditions"></a><span data-ttu-id="c11b1-170">경합 조건</span><span class="sxs-lookup"><span data-stu-id="c11b1-170">Race Conditions</span></span>  
 <span data-ttu-id="c11b1-171">서비스에서 메시지를 받는 시간과 상관 관계가 실제로 초기화되는 시간 사이에는 약간의 시간 차가 있으며 그 동안 후속 메시지는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-171">There is a small gap in time between the service receiving a message and the correlation actually being initialized, during which follow-up messages will be ignored.</span></span> <span data-ttu-id="c11b1-172">워크플로 서비스에서 단방향 작업을 통해 클라이언트에서 전달된 데이터를 사용하여 내용 기반 상관 관계를 초기화하고 호출자가 즉시 후속 메시지를 보내는 경우 이러한 후속 메시지는 이 간격 동안 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-172">If a workflow service initializes the content-based correlation by using data passed from the client over a one-way operation, and the caller sends immediate follow-up messages, these messages will be ignored during this interval.</span></span> <span data-ttu-id="c11b1-173">양방향 작업을 사용하여 상관 관계를 초기화하거나 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하면 이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-173">This can be avoided by using a two-way operation to initialize the correlation, or by using a <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span>  
  
### <a name="correlation-query-issues"></a><span data-ttu-id="c11b1-174">상관 관계 쿼리 문제</span><span class="sxs-lookup"><span data-stu-id="c11b1-174">Correlation Query Issues</span></span>  
 <span data-ttu-id="c11b1-175">상관 관계 쿼리는 메시지를 상호 연결하는 데 사용되는 메시지 데이터를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-175">Correlation queries are used to specify what data in a message is used to correlate the message.</span></span> <span data-ttu-id="c11b1-176">이 데이터는 XPath 쿼리를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-176">This data is specified by using an XPath query.</span></span> <span data-ttu-id="c11b1-177">모든 사항이 올바른 것으로 보이는데도 서비스로 보내는 메시지가 디스패치되지 않을 경우 문제를 해결하는 한 가지 방법은 XPath 쿼리 대신 메시지 데이터의 값과 일치하는 리터럴 값을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-177">If messages to a service are not being dispatched even though everything appears to be correct, one strategy for troubleshooting is to specify a literal value that matches the value of the message data instead of an XPath query.</span></span> <span data-ttu-id="c11b1-178">리터럴 값을 지정하려면 `string` 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-178">To specify a literal value, use the `string` function.</span></span> <span data-ttu-id="c11b1-179">다음 예제에서는 <xref:System.ServiceModel.MessageQuerySet>에 리터럴 값 `11445`를 사용하도록 `OrderId`을 구성하고 XPath 쿼리를 주석 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-179">In the following example, a <xref:System.ServiceModel.MessageQuerySet> is configured to use a literal value of `11445` for the `OrderId` and the XPath query is commented out.</span></span>  
  
```csharp  
MessageQuerySet = new MessageQuerySet  
{  
    {  
        "OrderId",   
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")  
        new XPathMessageQuery("string('11445')")  
    }  
}  
```  
  
 <span data-ttu-id="c11b1-180">상관 관계 데이터가 검색되지 않도록 XPath 쿼리가 잘못 구성된 경우 "상관 관계 쿼리에서 빈 결과 집합이 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-180">If an XPath query is configured incorrectly such that no correlation data is retrieved, a fault is returned with the following message: "A correlation query yielded an empty result set.</span></span> <span data-ttu-id="c11b1-181">끝점에 대해 상관 관계 쿼리가 올바르게 구성되었는지 확인하십시오."라는 메시지와 함께 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-181">Please ensure correlation queries for the endpoint are correctly configured."</span></span> <span data-ttu-id="c11b1-182">이 문제를 신속하게 해결하는 한 가지 방법은 이전 단원에서 설명한 대로 XPath 쿼리를 리터럴 값으로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-182">One quick way to troubleshoot this is to replace the XPath query with a literal value as described in the previous section.</span></span> <span data-ttu-id="c11b1-183">XPath 쿼리 작성기를 사용 하는 경우이 문제가 발생할 수 있습니다는 **상관 관계 이니셜라이저 추가** 또는 **CorrelatesOn 정의** 대화 상자와 워크플로 서비스 메시지 계약을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-183">This issue can occur if you use the XPath query builder in the **Add Correlation Initializers** or **CorrelatesOn Definition** dialog boxes and your workflow service uses message contracts.</span></span> <span data-ttu-id="c11b1-184">다음 예제에서는 메시지 계약 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-184">In the following example, a message contract class is defined.</span></span>  
  
```csharp  
[MessageContract]  
public class AddItemMessage  
{  
    [MessageHeader]  
    public string CartId;  
  
    [MessageBodyMember]  
    public string Item;  
}  
```  
  
 <span data-ttu-id="c11b1-185">이 메시지 계약은 워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-185">This message contract is used by a <xref:System.ServiceModel.Activities.Receive> activity in a workflow.</span></span> <span data-ttu-id="c11b1-186">메시지 헤더의 `CartId`는 메시지를 올바른 인스턴스와 상호 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-186">The `CartId` in the header of the message is used to correlate the message to the correct instance.</span></span> <span data-ttu-id="c11b1-187">`CartId`를 검색하는 XPath 쿼리가 워크플로 디자이너의 상관 관계 대화 상자를 사용하여 만들어지는 경우 다음과 같은 잘못된 XPath 쿼리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-187">If the XPath query that retrieves the `CartId` is created using the correlation dialogs in the workflow designer, the following incorrect XPath query is generated.</span></span>  
  
```  
sm:body()/xg0:AddItemMessage/xg0:CartId  
```  
  
 <span data-ttu-id="c11b1-188"><xref:System.ServiceModel.Activities.Receive> 활동이 데이터에 대한 매개 변수를 사용한다면 이 XPath 쿼리가 올바르지만 이 활동이 메시지 계약을 사용하므로 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-188">This XPath query would be correct if the <xref:System.ServiceModel.Activities.Receive> activity used parameters for the data, but since it is using a message contract it is incorrect.</span></span> <span data-ttu-id="c11b1-189">다음 XPath 쿼리는 헤더에서 `CartId`를 검색하는 올바른 XPath 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-189">The following XPath query is the correct XPath query to retrieve the `CartId` from the header.</span></span>  
  
```  
sm:header()/tempuri:CartId  
```  
  
 <span data-ttu-id="c11b1-190">이는 메시지 본문을 검사하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-190">This can be confirmed by examining the body of the message.</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>  
  </s:Header>  
  <s:Body>  
    <AddItemMessage xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItemMessage>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="c11b1-191">다음 예제에서는 이전 메시지 계약을 사용하여 데이터를 받는 <xref:System.ServiceModel.Activities.Receive> 작업에 대해 구성된 `AddItem` 활동을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-191">The following example shows a <xref:System.ServiceModel.Activities.Receive> activity configured for an `AddItem` operation that uses the previous message contract to receive data.</span></span> <span data-ttu-id="c11b1-192">XPath 쿼리는 올바르게 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11b1-192">The XPath query is correctly configured.</span></span>  
  
```xaml  
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">  
  <Receive.CorrelatesOn>  
    <XPathMessageQuery x:Key="key1">  
      <XPathMessageQuery.Namespaces>  
        <ssx:XPathMessageContextMarkup>  
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>  
        </ssx:XPathMessageContextMarkup>  
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>  
  </Receive.CorrelatesOn>  
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">  
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>  
  </ReceiveMessageContent>  
</Receive>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c11b1-193">내용 기반 상관 관계 참조 [콘텐츠 기반](../../../../docs/framework/wcf/feature-details/content-based-correlation.md) 및 [상관 관계가 지정 된 계산기](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c11b1-193"> content-based correlation, see [Content Based](../../../../docs/framework/wcf/feature-details/content-based-correlation.md) and the [Correlated Calculator](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) sample.</span></span>
