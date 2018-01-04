---
title: HttpCookieSession
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c06efd7450afe93eaecca1e678eb6f8bf5de7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="httpcookiesession"></a><span data-ttu-id="07927-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="07927-102">HttpCookieSession</span></span>
<span data-ttu-id="07927-103">이 샘플에서는 세션 관리에 HTTP 쿠키를 사용하기 위해 사용자 지정 프로토콜 채널을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07927-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="07927-104">이 채널은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스와 ASMX 클라이언트 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 ASMX 서비스 사이의 통신을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-104">This channel enables communication between [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services and ASMX clients or between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and ASMX services.</span></span>  
  
 <span data-ttu-id="07927-105">클라이언트가 세션 기반의 ASMX 웹 서비스에 있는 웹 메서드를 호출하면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 엔진은 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-105">When a client calls a Web method in an ASMX Web service that is session-based, the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] engine does the following:</span></span>  
  
-   <span data-ttu-id="07927-106">고유 ID(세션 ID)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-106">Generates a unique ID (session ID).</span></span>  
  
-   <span data-ttu-id="07927-107">세션 개체를 생성하여 고유 ID에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-107">Generates the session object and associates it with the unique ID.</span></span>  
  
-   <span data-ttu-id="07927-108">고유 ID를 Set-Cookie HTTP 응답 헤더에 추가하여 클라이언트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07927-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
-   <span data-ttu-id="07927-109">클라이언트로 보내는 세션 ID를 기반으로 이후의 호출에서 클라이언트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="07927-110">클라이언트는 이후에 서버로 보내는 요청에 이 세션 ID를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="07927-111">서버는 클라이언트가 보낸 세션 ID를 사용하여 현재 HTTP 컨텍스트에 적절한 세션 개체를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07927-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="07927-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="07927-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="07927-114">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="07927-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="07927-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="07927-116">HttpCookieSession 채널 메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="07927-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  
 <span data-ttu-id="07927-117">이 샘플에서는 ASMX와 같은 시나리오에 대해 세션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="07927-118">채널 스택의 맨 아래에는 <xref:System.ServiceModel.Channels.IRequestChannel> 및 <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 HTTP 전송이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="07927-119">채널은 채널 스택의 상위 수준에 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="07927-120">이 샘플에서는 세션을 지원하는 두 개의 채널(<xref:System.ServiceModel.Channels.IRequestSessionChannel> 및 <xref:System.ServiceModel.Channels.IReplySessionChannel>)을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="07927-121">서비스 채널</span><span class="sxs-lookup"><span data-stu-id="07927-121">Service Channel</span></span>  
 <span data-ttu-id="07927-122">이 샘플은 `HttpCookieReplySessionChannelListener` 클래스에 서비스 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="07927-123">이 클래스는 <xref:System.ServiceModel.Channels.IChannelListener> 인터페이스를 구현하고 채널 스택의 하위 수준에 있는 <xref:System.ServiceModel.Channels.IReplyChannel> 채널을 <xref:System.ServiceModel.Channels.IReplySessionChannel>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="07927-124">이 프로세스는 다음과 같이 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-124">This process can be divided into the following parts:</span></span>  
  
-   <span data-ttu-id="07927-125">채널 수신기가 열리면 채널 수신기는 내부 수신기로부터 내부 채널을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="07927-126">내부 수신기는 데이터그램 수신기이고 받은 채널의 수명은 수신기의 수명에서 분리되므로 내부 수신기를 닫고 내부 채널만 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
-   <span data-ttu-id="07927-127">열기 프로세스가 완료되면 내부 채널에서 메시지를 받도록 메시지 루프를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
-   <span data-ttu-id="07927-128">메시지가 도착하면 서비스 채널은 세션 식별자를 확인하고 적절한 세션 채널로 디멀티플렉싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="07927-129">채널 수신기는 세션 식별자를 세션 채널 인스턴스에 매핑하는 사전을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="07927-130">`HttpCookieReplySessionChannel` 클래스는 <xref:System.ServiceModel.Channels.IReplySessionChannel>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="07927-131">채널 스택의 상위 수준에서는 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출하여 이 세션에 대한 요청을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="07927-132">각 세션 채널에는 서비스 채널에서 채우는 개인 메시지 큐가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="07927-133">누군가가 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출했지만 메시지 큐에 메시지가 없는 경우 채널은 지정된 시간 동안 대기한 후에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="07927-134">그러면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이외의 클라이언트에 대해 생성된 세션 채널이 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-134">This cleans up the session channels created for non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients.</span></span>  
  
 <span data-ttu-id="07927-135">`channelMapping`을 사용하여 `ReplySessionChannels`를 추적하며, 받은 채널이 모두 닫힐 때까지 기본 `innerChannel`을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="07927-136">이렇게 하면 `HttpCookieReplySessionChannel`이 `HttpCookieReplySessionChannelListener`의 수명보다 오래 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="07927-137">받은 채널은 `OnClosed` 콜백을 통해 수신기에 대한 참조를 유지하므로 수신기에서 수행되는 가비지 수집에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="07927-138">클라이언트 채널</span><span class="sxs-lookup"><span data-stu-id="07927-138">Client channel</span></span>  
 <span data-ttu-id="07927-139">해당 클라이언트 채널은 `HttpCookieSessionChannelFactory` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="07927-140">채널을 만드는 동안 채널 팩터리는 내부 요청 채널을 `HttpCookieRequestSessionChannel`로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="07927-141">`HttpCookieRequestSessionChannel` 클래스는 호출을 기본 요청 채널로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="07927-142">클라이언트가 프록시를 닫으면 `HttpCookieRequestSessionChannel`은 채널이 닫히는 것을 알리는 메시지를 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07927-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="07927-143">따라서 서비스 채널 스택은 사용 중인 세션 채널을 정상적으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="07927-144">바인딩 및 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="07927-144">Binding and Binding Element</span></span>  
 <span data-ttu-id="07927-145">서비스 및 클라이언트 채널을 만든 다음에는 이 채널을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임에 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-145">After creating the service and client channels, the next step is to integrate them into the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime.</span></span> <span data-ttu-id="07927-146">채널은 바인딩 및 바인딩 요소를 통해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-146">Channels are exposed to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] through bindings and binding elements.</span></span> <span data-ttu-id="07927-147">이 바인딩은 하나 또는 여러 개의 바인딩 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-147">A binding consists of one or many binding elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="07927-148">에서는 BasicHttpBinding 또는 WSHttpBinding과 같은 여러 가지 시스템 정의 바인딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-148"> offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="07927-149">`HttpCookieSessionBindingElement` 클래스에는 바인딩 요소의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="07927-150">이 클래스는 채널 수신기 및 채널 팩터리 만들기 메서드를 재정의하여 필요한 채널 수신기 또는 채널 팩터리 인스턴스화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="07927-151">이 샘플에서는 서비스 설명에 정책 어설션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="07927-152">따라서 이 샘플을 사용하면 서비스를 사용할 수 있는 다른 클라이언트에 채널 요구 사항을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="07927-153">예를 들어 이 바인딩 요소는 정책 어설션을 게시하여 세션을 지원함을 잠재적 클라이언트에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="07927-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="07927-154">이 샘플에서는 바인딩 요소 구성에서 `ExchangeTerminateMessage` 속성을 사용하도록 설정하므로 서비스가 세션 대화를 종료하기 위한 추가 메시지 교환 작업을 지원하는 것을 보여 주기 위해 필요한 어설션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="07927-155">그런 다음 클라이언트는 이 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-155">Clients can then use this action.</span></span> <span data-ttu-id="07927-156">다음 WSDL 코드는 `HttpCookieSessionBindingElement`에서 만든 정책 어설션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07927-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="07927-157">`HttpCookieSessionBinding` 클래스는 이전에 설명한 바인딩 요소를 사용하는 시스템 제공 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="07927-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="07927-158">구성 시스템에 채널 추가</span><span class="sxs-lookup"><span data-stu-id="07927-158">Adding the Channel to the Configuration System</span></span>  
 <span data-ttu-id="07927-159">이 샘플에서는 구성을 통해 샘플 채널을 노출하는 두 개의 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="07927-160">첫 번째 클래스는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>의 `HttpCookieSessionBindingElement`입니다</span><span class="sxs-lookup"><span data-stu-id="07927-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="07927-161">대량의 구현은 `HttpCookieSessionBindingConfigurationElement`로부터 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="07927-162">`HttpCookieSessionBindingConfigurationElement`에는 `HttpCookieSessionBindingElement`의 속성에 대응하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="07927-163">바인딩 요소 확장 섹션</span><span class="sxs-lookup"><span data-stu-id="07927-163">Binding Element Extension Section</span></span>  
 <span data-ttu-id="07927-164">`HttpCookieSessionBindingElementSection` 섹션은 구성 시스템에 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>을 노출하는 `HttpCookieSessionBindingElement`입니다.</span><span class="sxs-lookup"><span data-stu-id="07927-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="07927-165">몇 가지 재정의를 통해 구성 섹션 이름, 바인딩 요소의 형식 및 바인딩 요소를 만드는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="07927-166">그러면 다음과 같이 구성 파일의 확장명 섹션을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>        
    <system.serviceModel>        
      <extensions>          
        <bindingElementExtensions>            
          <add name="httpCookieSession"   
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,   
                    HttpCookieSessionExtension, Version=1.0.0.0,   
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>        
    </system.serviceModel>    
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="07927-167">테스트 코드</span><span class="sxs-lookup"><span data-stu-id="07927-167">Test Code</span></span>  
 <span data-ttu-id="07927-168">이 샘플 전송을 사용하기 위한 테스트 코드는 Client 및 Service 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07927-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="07927-169">두 개의 테스트 구성-하나의 테스트 된 바인딩을 사용 `allowCookies` 로 설정 `true` 클라이언트에서.</span><span class="sxs-lookup"><span data-stu-id="07927-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="07927-170">두 번째 테스트에서는 종료 메시지 교환을 사용하여 바인딩에서 명시적인 종료를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="07927-171">샘플을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07927-171">When you run the sample, you should see the following output:</span></span>  
  
```  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="07927-172">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="07927-172">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="07927-173">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-173">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="07927-174">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="07927-175">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="07927-176">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07927-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07927-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07927-177">See Also</span></span>
