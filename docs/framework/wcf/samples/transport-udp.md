---
title: '전송: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: 4f69730831ec57efc782a95d7412496aa69a4afb
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="transport-udp"></a><span data-ttu-id="2f59b-102">전송: UDP</span><span class="sxs-lookup"><span data-stu-id="2f59b-102">Transport: UDP</span></span>
<span data-ttu-id="2f59b-103">UDP 전송 샘플을 UDP 유니캐스트 및 멀티 캐스트를 사용자 지정 Windows Communication Foundation (WCF) 전송으로 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-103">The UDP Transport sample demonstrates how to implement UDP unicast and multicast as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="2f59b-104">이 샘플에서는 WCF 최선의 구현 방법 및 채널 프레임 워크를 사용 하 여 wcf에서 사용자 지정 전송을 만드는 권장된 절차를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-104">The sample describes the recommended procedure for creating a custom transport in WCF, by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="2f59b-105">사용자 지정 전송을 만드는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-105">The steps to create a custom transport are as follows:</span></span>  
  
1.  <span data-ttu-id="2f59b-106">채널 결정 [메시지 교환 패턴](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel 또는 IReplyChannel) ChannelFactory 및 ChannelListener를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-106">Decide which of the channel [Message Exchange Patterns](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel, or IReplyChannel) your ChannelFactory and ChannelListener will support.</span></span> <span data-ttu-id="2f59b-107">그런 다음 이러한 인터페이스의 세션 변형을 지원할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-107">Then decide whether you will support the sessionful variations of these interfaces.</span></span>  
  
2.  <span data-ttu-id="2f59b-108">메시지 교환 패턴을 지원하는 채널 팩터리 및 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-108">Create a channel factory and listener that support your Message Exchange Pattern.</span></span>  
  
3.  <span data-ttu-id="2f59b-109">네트워크 관련 예외가 <xref:System.ServiceModel.CommunicationException>의 적절한 파생 클래스로 정규화되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
4.  <span data-ttu-id="2f59b-110">추가 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 사용자 지정 전송을 채널 스택에 추가 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-110">Add a [\<binding>](../../../../docs/framework/misc/binding.md) element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="2f59b-111">자세한 내용은 참조 [바인딩 요소 추가](#AddingABindingElement)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-111">For more information, see [Adding a Binding Element](#AddingABindingElement).</span></span>  
  
5.  <span data-ttu-id="2f59b-112">새 바인딩 요소가 구성 시스템에 노출되도록 바인딩 요소 확장명 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-112">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
6.  <span data-ttu-id="2f59b-113">기능을 다른 끝점에 전달하도록 메타데이터 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-113">Add metadata extensions to communicate capabilities to other endpoints.</span></span>  
  
7.  <span data-ttu-id="2f59b-114">올바르게 정의된 프로필에 따라 바인딩 요소 스택을 미리 구성하는 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-114">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="2f59b-115">자세한 내용은 참조 [표준 바인딩 추가](#AddingAStandardBinding)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-115">For more information, see [Adding a Standard Binding](#AddingAStandardBinding).</span></span>  
  
8.  <span data-ttu-id="2f59b-116">바인딩이 구성 시스템에 노출되도록 바인딩 섹션 및 바인딩 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-116">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="2f59b-117">자세한 내용은 참조 [구성 지원 추가](#AddingConfigurationSupport)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-117">For more information, see [Adding Configuration Support](#AddingConfigurationSupport).</span></span>  
  
<a name="MessageExchangePatterns"></a>   
## <a name="message-exchange-patterns"></a><span data-ttu-id="2f59b-118">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="2f59b-118">Message Exchange Patterns</span></span>  
 <span data-ttu-id="2f59b-119">사용자 지정 전송을 작성하는 첫 번째 단계는 전송에 필요한 MEP(메시지 교환 패턴)를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-119">The first step in writing a custom transport is to decide which Message Exchange Patterns (MEPs) are required for the transport.</span></span> <span data-ttu-id="2f59b-120">다음과 같은 세 개의 MEP가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-120">There are three MEPs to choose from:</span></span>  
  
-   <span data-ttu-id="2f59b-121">데이터그램(IInputChannel/IOutputChannel)</span><span class="sxs-lookup"><span data-stu-id="2f59b-121">Datagram (IInputChannel/IOutputChannel)</span></span>  
  
     <span data-ttu-id="2f59b-122">데이터그램 MEP를 사용하면 클라이언트가 메시지를 보낸 후 회신을 기다리지 않는 "fire and forget" 교환을 사용하여 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-122">When using a datagram MEP, a client sends a message using a "fire and forget" exchange.</span></span> <span data-ttu-id="2f59b-123">실행 후 제거 교환은 성공적인 전달에 대한 out-of-band 확인이 필요한 교환입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-123">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="2f59b-124">메시지는 전송 중에 손실되어 서비스에 전달되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-124">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="2f59b-125">보내기 작업이 클라이언트 쪽에서 완료되더라도 원격 끝점에서 메시지를 수신했다고 보장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-125">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="2f59b-126">데이터그램은 메시징을 위한 기본적인 빌딩 블록으로, 이 위에 신뢰할 수 있는 프로토콜 및 보안 프로토콜을 포함한 고유 프로토콜을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-126">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="2f59b-127">클라이언트 데이터그램 채널은 <xref:System.ServiceModel.Channels.IOutputChannel> 인터페이스를 구현하고, 서비스 데이터그램 채널은 <xref:System.ServiceModel.Channels.IInputChannel> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-127">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
-   <span data-ttu-id="2f59b-128">요청-응답(IRequestChannel/IReplyChannel)</span><span class="sxs-lookup"><span data-stu-id="2f59b-128">Request-Response (IRequestChannel/IReplyChannel)</span></span>  
  
     <span data-ttu-id="2f59b-129">이 MEP에서는 메시지가 전송되고 회신이 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-129">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="2f59b-130">이 패턴은 요청-응답 쌍으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-130">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="2f59b-131">요청-응답 호출의 예로 RPC(원격 프로시저 호출)와 브라우저 GET를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-131">Examples of request-response calls are remote procedure calls (RPC) and browser GETs.</span></span> <span data-ttu-id="2f59b-132">이 패턴을 반이중이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-132">This pattern is also known as Half-Duplex.</span></span> <span data-ttu-id="2f59b-133">이 MEP에서 클라이언트 채널은 <xref:System.ServiceModel.Channels.IRequestChannel>을 구현하고 서비스 채널은 <xref:System.ServiceModel.Channels.IReplyChannel>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-133">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
-   <span data-ttu-id="2f59b-134">이중(IDuplexChannel)</span><span class="sxs-lookup"><span data-stu-id="2f59b-134">Duplex (IDuplexChannel)</span></span>  
  
     <span data-ttu-id="2f59b-135">이중 MEP를 사용하면 임의 개수의 메시지를 클라이언트에서 보내고 임의의 순서로 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-135">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="2f59b-136">이중 MEP는 말로 전달되는 각 단어가 메시지에 해당하는 전화 통화와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-136">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="2f59b-137">이 MEP에서는 양측의 송/수신이 가능하기 때문에 클라이언트와 서비스 채널에서 <xref:System.ServiceModel.Channels.IDuplexChannel> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-137">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="2f59b-138">또한 이러한 MEP는 각각 세션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-138">Each of these MEPs can also support sessions.</span></span> <span data-ttu-id="2f59b-139">채널에서 보내고 받은 모든 메시지를 상호 연결하는 기능이 세션 인식 채널에서 제공하는 기능에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-139">The added functionality provided by a session-aware channel is that it correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="2f59b-140">요청과 회신이 상호 연결되어 있기 때문에 요청-응답 패턴은 두 메시지로 구성된 독립 실행형 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-140">The Request-Response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="2f59b-141">반면 세션을 지원하는 요청-응답 패턴은 해당 채널의 모든 요청/응답 쌍이 서로 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-141">In contrast, the Request-Response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="2f59b-142">따라서 데이터그램, 요청-응답, 이중, 세션 있는 데이터그램, 세션 있는 요청-응답 및 세션 있는 이중 등 6가지 MEP 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-142">This gives you a total of six MEPs—Datagram, Request-Response, Duplex, Datagram with sessions, Request-Response with sessions, and Duplex with sessions—to choose from.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f59b-143">UDP 전송의 경우 UDP는 본래 "fire and forget" 프로토콜이므로 데이터그램 MEP만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-143">For the UDP transport, the only MEP that is supported is Datagram, because UDP is inherently a "fire and forget" protocol.</span></span>  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a><span data-ttu-id="2f59b-144">ICommunicationObject 및 WCF 개체 수명 주기</span><span class="sxs-lookup"><span data-stu-id="2f59b-144">The ICommunicationObject and the WCF object lifecycle</span></span>  
 <span data-ttu-id="2f59b-145">WCF는 같은 개체의 수명 주기 관리에 사용 되는 일반적인 상태 시스템이 <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, 및 <xref:System.ServiceModel.Channels.IChannelListener> 통신에 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-145">WCF has a common state machine that is used for managing the lifecycle of objects like <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, and <xref:System.ServiceModel.Channels.IChannelListener> that are used for communication.</span></span> <span data-ttu-id="2f59b-146">이러한 통신 개체의 상태는 5가지로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-146">There are five states in which these communication objects can exist.</span></span> <span data-ttu-id="2f59b-147">이러한 상태는 <xref:System.ServiceModel.CommunicationState> 열거형으로 나타내며 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-147">These states are represented by the <xref:System.ServiceModel.CommunicationState> enumeration, and are as follows:</span></span>  
  
-   <span data-ttu-id="2f59b-148">Created: <xref:System.ServiceModel.ICommunicationObject>가 처음 인스턴스화되었을 때의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-148">Created: This is the state of a <xref:System.ServiceModel.ICommunicationObject> when it is first instantiated.</span></span> <span data-ttu-id="2f59b-149">이 상태에서는 I/O(입/출력)이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-149">No input/output (I/O) occurs in this state.</span></span>  
  
-   <span data-ttu-id="2f59b-150">Opening: <xref:System.ServiceModel.ICommunicationObject.Open%2A>을 호출하면 개체가 이 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-150">Opening: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="2f59b-151">이때 속성은 변경할 수 없으며 입/출력이 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-151">At this point properties are made immutable, and input/output can begin.</span></span> <span data-ttu-id="2f59b-152">Created 상태에서만 이 상태로 전환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-152">This transition is valid only from the Created state.</span></span>  
  
-   <span data-ttu-id="2f59b-153">Opened: 열기 프로세스가 완료되면 개체는 이 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-153">Opened: Objects transition to this state when the open process completes.</span></span> <span data-ttu-id="2f59b-154">Opening 상태에서만 이 상태로 전환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-154">This transition is valid only from the Opening state.</span></span> <span data-ttu-id="2f59b-155">이때 개체는 전송을 위해 충분히 사용 가능한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-155">At this point, the object is fully usable for transfer.</span></span>  
  
-   <span data-ttu-id="2f59b-156">Closing: 시스템 종료를 위해 <xref:System.ServiceModel.ICommunicationObject.Close%2A>를 호출하면 개체가 이 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-156">Closing: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called for a graceful shutdown.</span></span> <span data-ttu-id="2f59b-157">Opened 상태에서만 이 상태로 전환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-157">This transition is valid only from the Opened state.</span></span>  
  
-   <span data-ttu-id="2f59b-158">Closed: Closed 상태의 개체는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-158">Closed: In the Closed state objects are no longer usable.</span></span> <span data-ttu-id="2f59b-159">일반적으로 검사를 위해 대부분의 구성에 액세스할 수 있지만 통신은 이루어질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-159">In general, most configuration is still accessible for inspection, but no communication can occur.</span></span> <span data-ttu-id="2f59b-160">이 상태는 삭제된 상태와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-160">This state is equivalent to being disposed.</span></span>  
  
-   <span data-ttu-id="2f59b-161">Faulted: Faulted 상태의 개체는 검사를 위해 액세스할 수 있지만 더 이상 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-161">Faulted: In the Faulted state, objects are accessible to inspection but no longer usable.</span></span> <span data-ttu-id="2f59b-162">복구 불가능한 오류가 발생하면 해당 개체는 이 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-162">When a non-recoverable error occurs, the object transitions into this state.</span></span> <span data-ttu-id="2f59b-163">에이 상태에서 유일 하 게 유효한 전환을 `Closed` 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-163">The only valid transition from this state is into the `Closed` state.</span></span>  
  
 <span data-ttu-id="2f59b-164">각 상태 전환 시 실행되는 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-164">There are events that fire for each state transition.</span></span> <span data-ttu-id="2f59b-165"><xref:System.ServiceModel.ICommunicationObject.Abort%2A> 메서드는 언제든지 호출 가능하며, 개체가 현재 상태에서 Closed 상태로 즉시 전환되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-165">The <xref:System.ServiceModel.ICommunicationObject.Abort%2A> method can be called at any time, and causes the object to transition immediately from its current state into the Closed state.</span></span> <span data-ttu-id="2f59b-166"><xref:System.ServiceModel.ICommunicationObject.Abort%2A>를 호출하면 완료되지 않은 작업이 모두 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-166">Calling <xref:System.ServiceModel.ICommunicationObject.Abort%2A> terminates any unfinished work.</span></span>  
  
<a name="ChannelAndChannelListener"></a>   
## <a name="channel-factory-and-channel-listener"></a><span data-ttu-id="2f59b-167">채널 팩터리 및 채널 수신기</span><span class="sxs-lookup"><span data-stu-id="2f59b-167">Channel Factory and Channel Listener</span></span>  
 <span data-ttu-id="2f59b-168">사용자 지정 전송을 작성하는 다음 단계는 클라이언트 채널을 위한 <xref:System.ServiceModel.Channels.IChannelFactory> 및 서비스 채널을 위한 <xref:System.ServiceModel.Channels.IChannelListener>의 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-168">The next step in writing a custom transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span> <span data-ttu-id="2f59b-169">채널 계층은 채널을 만들기 위해 팩토리 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-169">The channel layer uses a factory pattern for constructing channels.</span></span> <span data-ttu-id="2f59b-170">WCF는이 프로세스에 대 한 기본 클래스 도우미를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-170">WCF provides base class helpers for this process.</span></span>  
  
-   <span data-ttu-id="2f59b-171"><xref:System.ServiceModel.Channels.CommunicationObject> 클래스는 <xref:System.ServiceModel.ICommunicationObject>를 구현하고 2단계에서 설명한 상태 시스템을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-171">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine previously described in Step 2.</span></span> 

-   <span data-ttu-id="2f59b-172">'<xref:System.ServiceModel.Channels.ChannelManagerBase> 클래스 구현 <xref:System.ServiceModel.Channels.CommunicationObject> 에 대 한 통합된 기본 클래스를 제공 하 고 <xref:System.ServiceModel.Channels.ChannelFactoryBase> 및 <xref:System.ServiceModel.Channels.ChannelListenerBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-172">The``<xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="2f59b-173"><xref:System.ServiceModel.Channels.ChannelManagerBase> 클래스는 <xref:System.ServiceModel.Channels.ChannelBase>을 구현하는 기본 클래스인 <xref:System.ServiceModel.Channels.IChannel>와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-173">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
-   <span data-ttu-id="2f59b-174">'<xref:System.ServiceModel.Channels.ChannelFactoryBase> 클래스 구현 <xref:System.ServiceModel.Channels.ChannelManagerBase> 및 <xref:System.ServiceModel.Channels.IChannelFactory> 하 고 통합 된 `CreateChannel` 하나에 오버 로드 `OnCreateChannel` 추상 메서드.</span><span class="sxs-lookup"><span data-stu-id="2f59b-174">The``<xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
-   <span data-ttu-id="2f59b-175"><xref:System.ServiceModel.Channels.ChannelListenerBase> 클래스는 <xref:System.ServiceModel.Channels.IChannelListener>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-175">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="2f59b-176">이 클래스는 기본 상태 관리를 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-176">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="2f59b-177">이 샘플에서 팩터리 구현은 UdpChannelFactory.cs에 포함되어 있고, 수신기 구현은 UdpChannelListener.cs에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-177">In this sample, the factory implementation is contained in UdpChannelFactory.cs and the listener implementation is contained in UdpChannelListener.cs.</span></span> <span data-ttu-id="2f59b-178"><xref:System.ServiceModel.Channels.IChannel> 구현은 UdpOutputChannel.cs 및 UdpInputChannel.cs에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-178">The <xref:System.ServiceModel.Channels.IChannel> implementations are in UdpOutputChannel.cs and UdpInputChannel.cs.</span></span>  
  
### <a name="the-udp-channel-factory"></a><span data-ttu-id="2f59b-179">UDP 채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="2f59b-179">The UDP Channel Factory</span></span>  
 <span data-ttu-id="2f59b-180">`UdpChannelFactory`는 <xref:System.ServiceModel.Channels.ChannelFactoryBase>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-180">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="2f59b-181">샘플에서는 메시지 인코더의 메시지 버전에 액세스할 수 있도록 <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-181">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="2f59b-182">또한 샘플에서는 상태 시스템이 전환될 때 <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>의 인스턴스를 중지할 수 있도록 <xref:System.ServiceModel.Channels.BufferManager>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-182">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> so that we can tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="2f59b-183">UDP 출력 채널</span><span class="sxs-lookup"><span data-stu-id="2f59b-183">The UDP Output Channel</span></span>  
 <span data-ttu-id="2f59b-184">`UdpOutputChannel`은 <xref:System.ServiceModel.Channels.IOutputChannel>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-184">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="2f59b-185">생성자는 인수의 유효성을 검사하여 전달되는 <xref:System.Net.EndPoint>를 기반으로 대상 <xref:System.ServiceModel.EndpointAddress> 개체를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-185">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 <span data-ttu-id="2f59b-186">채널이 정상적 또는 비정상적으로 닫힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-186">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="2f59b-187">채널이 정상적으로 닫히면 소켓이 닫히고 기본 클래스 `OnClose` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-187">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="2f59b-188">이 때 예외가 throw되면 인프라가 `Abort`를 호출하여 채널을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-188">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp
this.socket.Close(0);  
```  
  
 <span data-ttu-id="2f59b-189">그런 다음 구현 `Send()` 및 `BeginSend()` / `EndSend()`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-189">We then implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="2f59b-190">그러면 두 개의 기본 섹션으로 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-190">This breaks down into two main sections.</span></span> <span data-ttu-id="2f59b-191">먼저 메시지를 바이트 배열로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-191">First we serialize the message into a byte array.</span></span>  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="2f59b-192">그런 다음 네트워크를 통해 결과 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-192">Then we send the resulting data on the wire.</span></span>  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a><span data-ttu-id="2f59b-193">UdpChannelListener</span><span class="sxs-lookup"><span data-stu-id="2f59b-193">The UdpChannelListener</span></span>  
 <span data-ttu-id="2f59b-194">'에서 파생 되는 샘플 구현 UdpChannelListener는 <xref:System.ServiceModel.Channels.ChannelListenerBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-194">The``UdpChannelListener that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="2f59b-195">단일 UDP 소켓을 사용하여 데이터그램을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-195">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="2f59b-196">`OnOpen` 메서드는 비동기 루프에서 UDP 소켓을 사용하여 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-196">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="2f59b-197">그런 다음 데이터는 메시지 인코딩 프레임워크를 통해 메시지로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-197">The data are then converted into messages using the Message Encoding Framework.</span></span>  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 <span data-ttu-id="2f59b-198">같은 데이터그램 채널은 여러 소스에서 도착한 메시지를 나타내므로 `UdpChannelListener`는 singleton 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-198">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="2f59b-199">가 활성 대부분에서 <xref:System.ServiceModel.Channels.IChannel>' 한 번에이 수신기와 연결 된입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-199">There is, at most, one active <xref:System.ServiceModel.Channels.IChannel>``associated with this listener at a time.</span></span> <span data-ttu-id="2f59b-200">이 샘플에서는 `AcceptChannel` 메서드에서 반환되는 채널이 이후에 삭제되는 경우에만 새 채널을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-200">The sample generates another one only if a channel that is returned by the `AcceptChannel` method is subsequently disposed.</span></span> <span data-ttu-id="2f59b-201">메시지를 받으면 이 singleton 채널의 큐에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-201">When a message is received, it is enqueued into this singleton channel.</span></span>  
  
#### <a name="udpinputchannel"></a><span data-ttu-id="2f59b-202">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="2f59b-202">UdpInputChannel</span></span>  
 <span data-ttu-id="2f59b-203">`UdpInputChannel` 클래스는 `IInputChannel`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-203">The `UdpInputChannel` class implements `IInputChannel`.</span></span> <span data-ttu-id="2f59b-204">이 클래스는 `UdpChannelListener`의 소켓으로 채워지는 들어오는 메시지의 큐로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-204">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="2f59b-205">이러한 메시지는 `IInputChannel.Receive` 메서드에 의해 큐에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-205">These messages are dequeued by the `IInputChannel.Receive` method.</span></span>  
  
<a name="AddingABindingElement"></a>   
## <a name="adding-a-binding-element"></a><span data-ttu-id="2f59b-206">바인딩 요소 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-206">Adding a Binding Element</span></span>  
 <span data-ttu-id="2f59b-207">이제 팩터리와 채널이 빌드되었으므로 바인딩을 통해 ServiceModel 런타임에 팩터리와 채널을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-207">Now that the factories and channels are built, we must expose them to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="2f59b-208">바인딩은 서비스 주소와 연결된 통신 스택을 나타내는 바인딩 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-208">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="2f59b-209">스택의 각 요소에서 표현 됩니다는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-209">Each element in the stack is represented by a [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span>  
  
 <span data-ttu-id="2f59b-210">이 샘플에서 바인딩 요소는 `UdpTransportBindingElement`에서 파생된 <xref:System.ServiceModel.Channels.TransportBindingElement>로,</span><span class="sxs-lookup"><span data-stu-id="2f59b-210">In the sample, the binding element is `UdpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="2f59b-211">바인딩에 연결되는 팩터리를 빌드하기 위해 다음 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-211">It overrides the following methods to build the factories associated with our binding.</span></span>  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 <span data-ttu-id="2f59b-212">이 바인딩 요소에는 `BindingElement`를 복제하고 soap.udp 체계를 반환하는 멤버도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-212">It also contains members for cloning the `BindingElement` and returning our scheme (soap.udp).</span></span>  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a><span data-ttu-id="2f59b-213">전송 바인딩 요소에 대해 메타데이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-213">Adding Metadata Support for a Transport Binding Element</span></span>  
 <span data-ttu-id="2f59b-214">전송을 메타데이터 시스템에 통합하려면 정책 가져오기 및 내보내기를 모두 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-214">To integrate our transport into the metadata system, we must support both the import and export of policy.</span></span> <span data-ttu-id="2f59b-215">이렇게 하면이 바인딩을 통해 클라이언트를 생성 하는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-215">This allows us to generate clients of our binding through the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="2f59b-216">WSDL 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-216">Adding WSDL Support</span></span>  
 <span data-ttu-id="2f59b-217">바인딩의 전송 바인딩 요소는 메타데이터에서 주소 지정 정보를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-217">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="2f59b-218">또한 전송 바인딩 요소는 SOAP 바인딩을 사용할 때 메타데이터에서 올바른 전송 URI을 내보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-218">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="2f59b-219">WSDL 내보내기</span><span class="sxs-lookup"><span data-stu-id="2f59b-219">WSDL Export</span></span>  
 <span data-ttu-id="2f59b-220">주소 지정 정보를 내보내기 위해 `UdpTransportBindingElement`는 `IWsdlExportExtension` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-220">To export addressing information the `UdpTransportBindingElement` implements the `IWsdlExportExtension` interface.</span></span> <span data-ttu-id="2f59b-221">`ExportEndpoint` 메서드는 WSDL 포트에 올바른 주소 지정 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-221">The `ExportEndpoint` method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="2f59b-222">끝점에서 SOAP 바인딩을 사용할 때 `UdpTransportBindingElement` 메서드의 `ExportEndpoint` 구현이 전송 URI도 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-222">The `UdpTransportBindingElement` implementation of the `ExportEndpoint` method also exports a transport URI when the endpoint uses a SOAP binding.</span></span>  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="2f59b-223">WSDL 가져오기</span><span class="sxs-lookup"><span data-stu-id="2f59b-223">WSDL Import</span></span>  
 <span data-ttu-id="2f59b-224">주소 가져오기를 처리하기 위해 WSDL 가져오기 시스템을 확장하려면 Svcutil.exe.config 파일에서처럼 Svcutil.exe의 구성 파일에 다음 구성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-224">To extend the WSDL import system to handle importing the addresses, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2f59b-225">Svcutil.exe를 실행하는 경우 Svcutil.exe에서 WSDL 가져오기 확장을 로드하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-225">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1.  <span data-ttu-id="2f59b-226">Svcutil.exe를는 /SvcutilConfig을 사용 하 여 구성 파일:\<파일 > 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-226">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2.  <span data-ttu-id="2f59b-227">Svcutil.exe와 동일한 디렉터리에 있는 Svcutil.exe.config에 구성 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-227">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="2f59b-228">`UdpBindingElementImporter` 형식은 `IWsdlImportExtension` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-228">The `UdpBindingElementImporter` type implements the `IWsdlImportExtension` interface.</span></span> <span data-ttu-id="2f59b-229">`ImportEndpoint` 메서드는 WSDL 포트로부터 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-229">The `ImportEndpoint` method imports the address from the WSDL port.</span></span>  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="2f59b-230">정책 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-230">Adding Policy Support</span></span>  
 <span data-ttu-id="2f59b-231">사용자 지정 바인딩 요소는 서비스 끝점이 해당 바인딩 요소의 기능을 표현하도록 WSDL 바인딩에서 정책 어설션을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-231">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="2f59b-232">정책 내보내기</span><span class="sxs-lookup"><span data-stu-id="2f59b-232">Policy Export</span></span>  
 <span data-ttu-id="2f59b-233">`UdpTransportBindingElement` 구현 입력 `IPolicyExportExtension` 정책을 내보낼 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-233">The `UdpTransportBindingElement` type implements `IPolicyExportExtension` to add support for exporting policy.</span></span> <span data-ttu-id="2f59b-234">그 결과, `System.ServiceModel.MetadataExporter`는 이를 포함하는 모든 바인딩에 대한 정책 생성에 `UdpTransportBindingElement`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-234">As a result, `System.ServiceModel.MetadataExporter` includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="2f59b-235">`IPolicyExportExtension.ExportPolicy`에서는 멀티캐스트 모드인 경우 UDP용 어설션 및 다른 어설션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-235">In `IPolicyExportExtension.ExportPolicy`, we add an assertion for UDP and another assertion if we are in multicast mode.</span></span> <span data-ttu-id="2f59b-236">이는 멀티캐스트 모드가 통신 스택의 구성 방법에 영향을 주므로 양쪽 모두에서 조정되어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-236">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix, 
        UdpPolicyStrings.MulticastAssertion, 
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="2f59b-237">사용자 지정 전송 바인딩 요소가 주소 지정을 처리하기 때문에 `IPolicyExportExtension`에서의 `UdpTransportBindingElement` 구현 역시 사용 중인 WS-Addressing의 버전을 나타내기 위해 적절한 WS-Addressing 정책 어설션 내보내기를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-237">Because custom transport binding elements are responsible for handling addressing, the `IPolicyExportExtension` implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="2f59b-238">정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="2f59b-238">Policy Import</span></span>  
 <span data-ttu-id="2f59b-239">정책 가져오기 시스템을 확장하려면 Svcutil.exe.config 파일에서처럼 Svcutil.exe의 구성 파일에 다음 구성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-239">To extend the Policy Import system, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2f59b-240">그런 다음 등록된 클래스(`IPolicyImporterExtension`)로부터 `UdpBindingElementImporter`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-240">Then we implement `IPolicyImporterExtension` from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="2f59b-241">`ImportPolicy()`에서는 네임스페이스의 어설션을 검토하면서 전송 생성을 위한 어설션을 처리하고 멀티캐스트인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-241">In `ImportPolicy()`, we look through the assertions in our namespace, and process the ones for generating the transport and check whether it is multicast.</span></span> <span data-ttu-id="2f59b-242">또한 처리하는 어설션을 바인딩 어설션 목록에서 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-242">We also must remove the assertions we handle from the list of binding assertions.</span></span> <span data-ttu-id="2f59b-243">다시 한 번 말하지만 Svcutil.exe를 실행할 때 통합하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-243">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1.  <span data-ttu-id="2f59b-244">Svcutil.exe를는 /SvcutilConfig을 사용 하 여 구성 파일:\<파일 > 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-244">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2.  <span data-ttu-id="2f59b-245">Svcutil.exe와 동일한 디렉터리에 있는 Svcutil.exe.config에 구성 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-245">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
<a name="AddingAStandardBinding"></a>   
## <a name="adding-a-standard-binding"></a><span data-ttu-id="2f59b-246">표준 바인딩 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-246">Adding a Standard Binding</span></span>  
 <span data-ttu-id="2f59b-247">바인딩 요소를 다음 두 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-247">Our binding element can be used in the following two ways:</span></span>  
  
-   <span data-ttu-id="2f59b-248">사용자 지정 바인딩을 통해 사용: 사용자 지정 바인딩에서는 사용자가 임의의 바인딩 요소 집합을 기반으로 직접 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-248">Through a custom binding: A custom binding allows the user to create their own binding based on an arbitrary set of binding elements.</span></span>  
  
-   <span data-ttu-id="2f59b-249">해당 바인딩 요소가 포함된 시스템 제공 바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="2f59b-249">By using a system-provided binding that includes our binding element.</span></span> <span data-ttu-id="2f59b-250">WCF는와 같은 다양 한 시스템 정의 바인딩이 제공 `BasicHttpBinding`, `NetTcpBinding`, 및 `WsHttpBinding`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-250">WCF provides a number of these system-defined bindings, such as `BasicHttpBinding`, `NetTcpBinding`, and `WsHttpBinding`.</span></span> <span data-ttu-id="2f59b-251">이러한 바인딩 각각은 제대로 정의된 프로필에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-251">Each of these bindings is associated with a well-defined profile.</span></span>  
  
 <span data-ttu-id="2f59b-252">샘플에서는 `SampleProfileUdpBinding`에서 파생된 <xref:System.ServiceModel.Channels.Binding>의 프로필 바인딩을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-252">The sample implements profile binding in `SampleProfileUdpBinding`, which derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="2f59b-253">`SampleProfileUdpBinding`은 최대 네 개의 바인딩 요소, 즉 `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` 및 `ReliableSessionBindingElement`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-253">The `SampleProfileUdpBinding` contains up to four binding elements within it: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement`, and `ReliableSessionBindingElement`.</span></span>  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{     
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="2f59b-254">사용자 지정 표준 바인딩 가져오기 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-254">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="2f59b-255">Svcutil.exe 및 `WsdlImporter` 형식은 기본적으로 시스템 정의 바인딩을 인식하고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-255">Svcutil.exe and the `WsdlImporter` type, by default, recognizes and imports system-defined bindings.</span></span> <span data-ttu-id="2f59b-256">그렇지 않을 경우, 해당 바인딩을 `CustomBinding` 인스턴스로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-256">Otherwise, the binding gets imported as a `CustomBinding` instance.</span></span> <span data-ttu-id="2f59b-257">Svcutil.exe 및 `WsdlImporter`를 사용하도록 설정하여 `SampleProfileUdpBinding`을 가져오기 위해 `UdpBindingElementImporter`가 사용자 지정 표준 바인딩 가져오기도 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-257">To enable Svcutil.exe and the `WsdlImporter` to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="2f59b-258">사용자 지정 표준 바인딩 가져오기는 메타데이터로부터 가져온 `ImportEndpoint` 인스턴스를 검사하여 특정 표준 바인딩에 의해 생성되었는지 여부를 확인하기 위해 `IWsdlImportExtension` 인터페이스에 `CustomBinding` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-258">A custom standard binding importer implements the `ImportEndpoint` method on the `IWsdlImportExtension` interface to examine the `CustomBinding` instance imported from metadata to see whether it could have been generated by a specific standard binding.</span></span>  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="2f59b-259">일반적으로 사용자 지정 표준 바인딩 가져오기를 구현하면 가져온 바인딩 요소의 속성을 확인하여 표준 바인딩에 의해 설정될 수 있는 속성만 변경되고, 다른 모든 속성은 기본값인지를 확인하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-259">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="2f59b-260">표준 바인딩 가져오기를 구현하기 위한 기본 전략은 표준 바인딩의 인스턴스를 만들고, 바인딩 요소의 속성을 표준 바인딩이 지원하는 표준 바인딩 인스턴스로 전파하고, 가져온 바인딩 요소를 표준 바인딩의 바인딩 요소와 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-260">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>  
  
<a name="AddingConfigurationSupport"></a>   
## <a name="adding-configuration-support"></a><span data-ttu-id="2f59b-261">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="2f59b-261">Adding Configuration Support</span></span>  
 <span data-ttu-id="2f59b-262">구성을 통해 전송을 노출하려면 두 가지 구성 섹션을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-262">To expose our transport through configuration, we must implement two configuration sections.</span></span> <span data-ttu-id="2f59b-263">첫 번째는 `BindingElementExtensionElement`의 `UdpTransportBindingElement`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-263">The first is a `BindingElementExtensionElement` for `UdpTransportBindingElement`.</span></span> <span data-ttu-id="2f59b-264">이는 `CustomBinding` 구현이 해당 바인딩 요소를 참조하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-264">This is so that `CustomBinding` implementations can reference our binding element.</span></span> <span data-ttu-id="2f59b-265">두 번째는 `Configuration`의 `SampleProfileUdpBinding`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-265">The second is a `Configuration` for our `SampleProfileUdpBinding`.</span></span>  
  
### <a name="binding-element-extension-element"></a><span data-ttu-id="2f59b-266">바인딩 요소 확장명 요소</span><span class="sxs-lookup"><span data-stu-id="2f59b-266">Binding Element Extension Element</span></span>  
 <span data-ttu-id="2f59b-267">`UdpTransportElement` 섹션은 구성 시스템에 `BindingElementExtensionElement`을 노출하는 `UdpTransportBindingElement`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-267">The section `UdpTransportElement` is a `BindingElementExtensionElement` that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="2f59b-268">몇 가지 기본 재정의를 통해 구성 섹션 이름, 바인딩 요소의 형식 및 바인딩 요소를 만드는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-268">With a few basic overrides, we define our configuration section name, the type of our binding element and how to create our binding element.</span></span> <span data-ttu-id="2f59b-269">그러면 다음 코드와 같이 구성 파일에 확장명 섹션을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-269">We can then register our extension section in a configuration file as shown in the following code.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2f59b-270">사용자 지정 바인딩에서는 UDP를 전송으로 사용하기 위해 확장을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-270">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a><span data-ttu-id="2f59b-271">바인딩 섹션</span><span class="sxs-lookup"><span data-stu-id="2f59b-271">Binding Section</span></span>  
 <span data-ttu-id="2f59b-272">`SampleProfileUdpBindingCollectionElement` 섹션은 구성 시스템에 `StandardBindingCollectionElement`을 노출하는 `SampleProfileUdpBinding`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-272">The section `SampleProfileUdpBindingCollectionElement` is a `StandardBindingCollectionElement` that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="2f59b-273">대량의 구현은 `SampleProfileUdpBindingConfigurationElement`로부터 파생되는 `StandardBindingElement`에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-273">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from `StandardBindingElement`.</span></span> <span data-ttu-id="2f59b-274">`SampleProfileUdpBindingConfigurationElement` 에 속성에 해당 하는 속성이 `SampleProfileUdpBinding`, 및 매핑하는 함수가 `ConfigurationElement` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="2f59b-274">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="2f59b-275">마지막으로 다음 샘플 코드와 같이 `OnApplyConfiguration`에서 `SampleProfileUdpBinding` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-275">Finally, override the `OnApplyConfiguration` method in our `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 <span data-ttu-id="2f59b-276">구성 시스템에 이 처리기를 등록하려면 관련 구성 파일에 다음 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-276">To register this handler with the configuration system, we add the following section to the relevant configuration file.</span></span>  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="2f59b-277">이렇게 하면 serviceModel 구성 섹션에서 이 처리기를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-277">It can then be referenced from the serviceModel configuration section.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a><span data-ttu-id="2f59b-278">UDP 테스트 서비스 및 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2f59b-278">The UDP Test Service and Client</span></span>  
 <span data-ttu-id="2f59b-279">이 샘플 전송을 사용하기 위한 테스트 코드는 UdpTestService 및 UdpTestClient 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-279">Test code for using this sample transport is available in the UdpTestService and UdpTestClient directories.</span></span> <span data-ttu-id="2f59b-280">서비스 코드는 두 가지 테스트로 구성됩니다. 하나는 코드에서 바인딩 및 끝점을 설정하고, 다른 하나는 구성을 통해 바인딩 및 끝점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-280">The service code consists of two tests—one test sets up bindings and endpoints from code and the other does it through configuration.</span></span> <span data-ttu-id="2f59b-281">두 테스트 모두 두 개의 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-281">Both tests use two endpoints.</span></span> <span data-ttu-id="2f59b-282">한 끝점을 사용 하 여는 `SampleUdpProfileBinding` 와 [ \<reliableSession >](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 로 설정 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-282">One endpoint uses the `SampleUdpProfileBinding` with [\<reliableSession>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) set to `true`.</span></span> <span data-ttu-id="2f59b-283">다른 끝점은 `UdpTransportBindingElement`가 포함된 사용자 지정 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-283">The other endpoint uses a custom binding with `UdpTransportBindingElement`.</span></span> <span data-ttu-id="2f59b-284">이 사용 하는 `SampleUdpProfileBinding` 와 [ \<reliableSession >](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 로 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-284">This is equivalent to using `SampleUdpProfileBinding` with [\<reliableSession>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) set to `false`.</span></span> <span data-ttu-id="2f59b-285">두 테스트 모두 서비스를 만들고 각 바인딩에 끝점을 추가하며 서비스를 연 다음 서비스를 닫기 전에 사용자가 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-285">Both tests create a service, add an endpoint for each binding, open the service and then wait for the user to hit ENTER before closing the service.</span></span>  
  
 <span data-ttu-id="2f59b-286">서비스 테스트 응용 프로그램을 시작하면 다음과 같이 출력되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-286">When you start the service test application you should see the following output.</span></span>  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 <span data-ttu-id="2f59b-287">그런 다음 게시된 끝점에 대해 테스트 클라이언트 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-287">You can then run the test client application against the published endpoints.</span></span> <span data-ttu-id="2f59b-288">클라이언트 테스트 응용 프로그램은 각 끝점에 대해 클라이언트를 만들고 각 끝점에 5개의 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-288">The client test application creates a client for each endpoint and sends five messages to each endpoint.</span></span> <span data-ttu-id="2f59b-289">클라이언트에 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-289">The following output is on the client.</span></span>  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 <span data-ttu-id="2f59b-290">서비스의 전체 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-290">The following is the full output on the service.</span></span>  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 <span data-ttu-id="2f59b-291">구성을 사용하여 게시된 끝점에 대해 클라이언트 응용 프로그램을 실행하려면 서비스에서 Enter 키를 누른 다음 테스트 클라이언트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-291">To run the client application against endpoints published using configuration, hit ENTER on the service and then run the test client again.</span></span> <span data-ttu-id="2f59b-292">서비스에서 다음과 같이 출력되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-292">You should see the following output on the service.</span></span>  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 <span data-ttu-id="2f59b-293">클라이언트를 다시 실행하면 이전과 동일한 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-293">Running the client again yields the same as the preceding results.</span></span>  
  
 <span data-ttu-id="2f59b-294">Svcutil.exe를 사용하여 클라이언트 코드 및 구성을 다시 생성하려면 서비스 응용 프로그램을 시작한 다음 샘플의 루트 디렉터리에서 다음 Svcutil.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-294">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe from the root directory of the sample.</span></span>  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 <span data-ttu-id="2f59b-295">Svcutil.exe는 `SampleProfileUdpBinding`에 대한 바인딩 확장 구성을 생성하지 않으므로 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-295">Note that Svcutil.exe does not generate the binding extension configuration for the `SampleProfileUdpBinding`, so you must add it manually.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>      
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2f59b-296">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2f59b-296">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2f59b-297">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-297">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="2f59b-298">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-298">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2f59b-299">앞의 "UDP 테스트 서비스 및 클라이언트" 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f59b-299">Refer to the preceding "The UDP Test Service and Client" section.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2f59b-300">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-300">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2f59b-301">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2f59b-301">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2f59b-302">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="2f59b-302">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2f59b-303">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f59b-303">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
