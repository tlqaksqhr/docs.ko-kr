---
title: "영속 인스턴스 컨텍스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 540f6b6fe7795eb958afd84695865fd2e4271175
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="durable-instance-context"></a><span data-ttu-id="28050-102">영속 인스턴스 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="28050-102">Durable Instance Context</span></span>
<span data-ttu-id="28050-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 런타임을 사용자 지정하여 영속 인스턴스 컨텍스트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28050-103">This sample demonstrates how to customize the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] runtime to enable durable instance contexts.</span></span> <span data-ttu-id="28050-104">여기서는 SQL Server 2005를 백업 저장소(이 경우 SQL Server 2005 Express)로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-104">It uses SQL Server 2005 as its backing store (SQL Server 2005 Express in this case).</span></span> <span data-ttu-id="28050-105">사용자 지정 저장소 메커니즘에 액세스하는 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-105">However, it also provides a way to access custom storage mechanisms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28050-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="28050-107">이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 채널 계층과 서비스 모델 계층을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-107">This sample involves extending both the channel layer and the service model layer of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="28050-108">따라서 구현 세부 정보를 검토하려면 먼저 기본 개념을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-108">Therefore it is necessary to understand the underlying concepts before going into the implementation details.</span></span>  
  
 <span data-ttu-id="28050-109">영속 인스턴스 컨텍스트는 실제 시나리오에서 매우 자주 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-109">Durable instance contexts can be found in the real world scenarios quite often.</span></span> <span data-ttu-id="28050-110">예를 들어, 장바구니 응용 프로그램에는 중간에 쇼핑을 일시 중지하고 다른 날 계속 진행할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-110">A shopping cart application for example, has the ability to pause shopping halfway through and continue it on another day.</span></span> <span data-ttu-id="28050-111">따라서 다음날 장바구니를 방문하면 원래 컨텍스트가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-111">So that when we visit the shopping cart the next day, our original context is restored.</span></span> <span data-ttu-id="28050-112">서버의 장바구니 응용 프로그램에서는 연결이 끊어진 동안 장바구니 인스턴스를 유지 관리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-112">It is important to note that the shopping cart application (on the server) does not maintain the shopping cart instance while we are disconnected.</span></span> <span data-ttu-id="28050-113">대신 해당 상태를 영속 저장소 매체에 유지하여 복원된 컨텍스트에 새 인스턴스를 생성할 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-113">Instead, it persists its state into a durable storage media and uses it when constructing a new instance for the restored context.</span></span> <span data-ttu-id="28050-114">따라서 동일한 컨텍스트에 대해 제공되는 서비스 인스턴스는 이전 인스턴스와 동일하지 않습니다. 즉, 메모리 주소가 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-114">Therefore the service instance that may service for the same context is not the same as the previous instance (that is, it does not have the same memory address).</span></span>  
  
 <span data-ttu-id="28050-115">영속 인스턴스 컨텍스트는 클라이언트와 서비스 간에 컨텍스트 ID를 교환하는 작은 프로토콜로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-115">Durable instance context is made possible by a small protocol that exchanges a context ID between the client and service.</span></span> <span data-ttu-id="28050-116">이 컨텍스트 ID는 클라이언트에서 만들어 서비스로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-116">This context ID is created on the client and transmitted to the service.</span></span> <span data-ttu-id="28050-117">서비스 인스턴스가 만들어지면 서비스 런타임에서는 이 컨텍스트 ID에 해당하는 지속적인 상태를 영구 저장소(기본적으로 SQL Server 2005 데이터베이스)에서 로드하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-117">When the service instance is created, the service runtime tries to load the persisted state that corresponds to this context ID from a persistent storage (by default it is a SQL Server 2005 database).</span></span> <span data-ttu-id="28050-118">사용 가능한 상태가 없으면 새 인스턴스에 기본 상태가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-118">If no state is available the new instance has its default state.</span></span> <span data-ttu-id="28050-119">서비스 구현에서는 사용자 지정 특성으로 서비스 구현 상태를 변경하는 작업을 표시하여 런타임에서 작업을 호출한 후 서비스 인스턴스를 저장할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-119">The service implementation uses a custom attribute to mark operations that change the state of the service implementation so that the runtime can save the service instance after invoking them.</span></span>  
  
 <span data-ttu-id="28050-120">앞에서 설명한 대로 다음과 같이 간단하게 두 단계를 구분하여 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-120">By the previous description, two steps can easily be distinguished to achieve the goal:</span></span>  
  
1.  <span data-ttu-id="28050-121">네트워크를 통해 컨텍스트 ID를 전달하는 메시지를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-121">Change the message that goes on the wire to carry the context ID.</span></span>  
  
2.  <span data-ttu-id="28050-122">서비스 로컬 동작을 변경하여 사용자 지정 인스턴스 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-122">Change the service local behavior to implement custom instancing logic.</span></span>  
  
 <span data-ttu-id="28050-123">전자는 네트워크의 메시지에 영향을 주므로 사용자 지정 채널로 구현하여 채널 계층에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-123">Because the first one in the list affects the messages on the wire it should be implemented as a custom channel and be hooked up to the channel layer.</span></span> <span data-ttu-id="28050-124">후자는 서비스 로컬 동작에만 영향을 주므로 여러 서비스 확장 지점을 확장하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-124">The latter only affects the service local behavior and therefore can be implemented by extending several service extensibility points.</span></span> <span data-ttu-id="28050-125">다음 단원에서는 각 확장에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-125">In the next few sections, each of these extensions are discussed.</span></span>  
  
## <a name="durable-instancecontext-channel"></a><span data-ttu-id="28050-126">영속 InstanceContext 채널</span><span class="sxs-lookup"><span data-stu-id="28050-126">Durable InstanceContext Channel</span></span>  
 <span data-ttu-id="28050-127">먼저 채널 계층 확장을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-127">The first thing to look at is a channel layer extension.</span></span> <span data-ttu-id="28050-128">사용자 지정 채널을 기록하는 첫 단계는 채널의 통신 구조를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-128">The first step in writing a custom channel is to decide the communication structure of the channel.</span></span> <span data-ttu-id="28050-129">새로운 유선 프로토콜을 사용할 경우 채널은 채널 스택의 다른 모든 채널과 함께 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-129">As a new wire protocol is being introduced the channel should work with almost any other channel in the channel stack.</span></span> <span data-ttu-id="28050-130">따라서 모든 메시지 교환 패턴을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-130">Therefore it should support all the message exchange patterns.</span></span> <span data-ttu-id="28050-131">그러나 채널의 핵심 기능은 통신 구조와 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-131">However, the core functionality of the channel is the same regardless of its communication structure.</span></span> <span data-ttu-id="28050-132">즉, 클라이언트에서는 메시지에 컨텍스트 ID를 쓰고 서버에서는 메시지로부터 이 컨텍스트 ID를 읽어 상위 수준으로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-132">More specifically, from the client it should write the context ID to the messages and from the service it should read this context ID from the messages and pass it to the upper levels.</span></span> <span data-ttu-id="28050-133">따라서 모든 영속 인스턴스 컨텍스트 채널 구현에서 추상 기본 클래스 역할을 하는 `DurableInstanceContextChannelBase` 클래스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="28050-133">Because of that, a `DurableInstanceContextChannelBase` class is created that acts as the abstract base class for all durable instance context channel implementations.</span></span> <span data-ttu-id="28050-134">이 클래스에는 메시지에서 컨텍스트 정보를 적용하고 읽는 일반적인 상태 컴퓨터 관리 기능과 보호된 멤버 두 개가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-134">This class contains the common state machine management functions and two protected members to apply and read the context information to and from messages.</span></span>  
  
```  
class DurableInstanceContextChannelBase  
{  
  //…  
  protected void ApplyContext(Message message)  
  {  
    //…              
  }  
  protected string ReadContextId(Message message)  
  {  
    //…              
  }  
}  
```  
  
 <span data-ttu-id="28050-135">이러한 두 메서드는 `IContextManager` 구현을 사용하여 메시지에서 컨텍스트 ID를 쓰고 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-135">These two methods make use of `IContextManager` implementations to write and read the context ID to or from the message.</span></span> <span data-ttu-id="28050-136">`IContextManager`는 모든 컨텍스트 관리자에 대해 계약을 정의하는 데 사용되는 사용자 지정 인터페이스입니다. 채널에는 사용자 지정 SOAP 헤더나 HTTP 쿠키 헤더의 컨텍스트 ID를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-136">(`IContextManager` is a custom interface used to define the contract for all context managers.) The channel can either include the context ID in a custom SOAP header or in a HTTP cookie header.</span></span> <span data-ttu-id="28050-137">각 컨텍스트 관리자 구현은 모든 컨텍스트 관리자의 공통 기능이 포함된 `ContextManagerBase` 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-137">Each context manager implementation inherits from the `ContextManagerBase` class that contains the common functionality for all context managers.</span></span> <span data-ttu-id="28050-138">이 클래스의 `GetContextId` 메서드는 클라이언트에서 컨텍스트 ID를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-138">The `GetContextId` method in this class is used to originate the context ID from the client.</span></span> <span data-ttu-id="28050-139">컨텍스트 ID를 처음으로 가져오면 이 메서드는 원격 끝점 주소로 이름이 생성되는 텍스트 파일에 컨텍스트 ID를 저장합니다. 일반적인 URI에서 잘못된 파일 이름 문자는 @ 문자로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="28050-139">When a context ID is originated for the first time, this method saves it into a text file whose name is constructed by the remote endpoint address (the invalid file name characters in the typical URIs are replaced with @ characters).</span></span>  
  
 <span data-ttu-id="28050-140">나중에 동일한 원격 끝점에 컨텍스트 ID가 필요하면 적합한 파일이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-140">Later when the context ID is required for the same remote endpoint, it checks whether an appropriate file exists.</span></span> <span data-ttu-id="28050-141">파일이 있으면 컨텍스트 ID를 읽어 반환하고,</span><span class="sxs-lookup"><span data-stu-id="28050-141">If it does, it reads the context ID and returns.</span></span> <span data-ttu-id="28050-142">그렇지 않으면 새로 생성한 컨텍스트 ID를 반환하여 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-142">Otherwise it returns a newly generated context ID and saves it to a file.</span></span> <span data-ttu-id="28050-143">기본 구성을 사용할 경우 이러한 파일은 현재 사용자의 temp 디렉터리의 ContextStore라는 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-143">With the default configuration, these files are placed in a directory called ContextStore, which resides in the current user’s temp directory.</span></span> <span data-ttu-id="28050-144">그러나 이 위치는 바인딩 요소를 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-144">However this location is configurable using the binding element.</span></span>  
  
 <span data-ttu-id="28050-145">컨텍스트 ID를 전송하는 데 사용되는 메커니즘은 구성 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-145">The mechanism used to transport the context ID is configurable.</span></span> <span data-ttu-id="28050-146">이 메커니즘은 HTTP 쿠키 헤더 또는 사용자 지정 SOAP 헤더에 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-146">It could be either written to the HTTP cookie header or to a custom SOAP header.</span></span> <span data-ttu-id="28050-147">사용자 지정 SOAP 헤더 접근 방식에서는 HTTP가 아닌 프로토콜(예: TCP 또는 명명된 파이프)과 함께 이 프로토콜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-147">The custom SOAP header approach makes it possible to use this protocol with non-HTTP protocols (for example, TCP or Named Pipes).</span></span> <span data-ttu-id="28050-148">`MessageHeaderContextManager`와 `HttpCookieContextManager`라는 클래스에서 이 두 옵션을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-148">There are two classes, namely `MessageHeaderContextManager` and `HttpCookieContextManager`, which implement these two options.</span></span>  
  
 <span data-ttu-id="28050-149">두 클래스 모두 컨텍스트 ID를 메시지에 적절하게 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-149">Both of them write the context ID to the message appropriately.</span></span> <span data-ttu-id="28050-150">예를 들어, `MessageHeaderContextManager` 클래스는 `WriteContext` 메서드의 SOAP 헤더에 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-150">For example, the `MessageHeaderContextManager` class writes it to a SOAP header in the `WriteContext` method.</span></span>  
  
```  
public override void WriteContext(Message message)  
{  
  string contextId = this.GetContextId();  
  
  MessageHeader contextHeader =  
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,  
      DurableInstanceContextUtility.HeaderNamespace,  
      contextId,   
      true);  
  
  message.Headers.Add(contextHeader);  
}   
```  
  
 <span data-ttu-id="28050-151">`ApplyContext` 클래스의 `ReadContextId` 및 `DurableInstanceContextChannelBase` 메서드는 각각 `IContextManager.ReadContext` 및 `IContextManager.WriteContext`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-151">Both the `ApplyContext` and `ReadContextId` methods in the `DurableInstanceContextChannelBase` class invoke the `IContextManager.ReadContext` and `IContextManager.WriteContext`, respectively.</span></span> <span data-ttu-id="28050-152">그러나 `DurableInstanceContextChannelBase` 클래스로 이러한 컨텍스트 관리자를 직접 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-152">However, these context managers are not directly created by the `DurableInstanceContextChannelBase` class.</span></span> <span data-ttu-id="28050-153">대신 `ContextManagerFactory` 클래스를 사용하여 해당 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-153">Instead it uses the `ContextManagerFactory` class to do that job.</span></span>  
  
```  
IContextManager contextManager =  
                ContextManagerFactory.CreateContextManager(contextType,   
                this.contextStoreLocation,   
                this.endpointAddress);  
```  
  
 <span data-ttu-id="28050-154">`ApplyContext` 메서드는 보내는 채널에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-154">The `ApplyContext` method is invoked by the sending channels.</span></span> <span data-ttu-id="28050-155">이 메서드는 나가는 메시지에 컨텍스트 ID를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-155">It injects the context ID to the outgoing messages.</span></span> <span data-ttu-id="28050-156">`ReadContextId` 메서드는 받는 채널에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-156">The `ReadContextId` method is invoked by the receiving channels.</span></span> <span data-ttu-id="28050-157">이 메서드를 사용하면 들어오는 메시지에서 컨텍스트 ID를 사용할 수 있고 `Properties` 클래스의 `Message` 컬렉션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-157">This method ensures that the context ID is available in the incoming messages and adds it to the `Properties` collection of the `Message` class.</span></span> <span data-ttu-id="28050-158">또한 컨텍스트 ID를 읽는 데 오류가 발생하면 `CommunicationException`이 throw되어 채널이 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-158">It also throws a `CommunicationException` in case of a failure to read the context ID and thus causes the channel to be aborted.</span></span>  
  
```  
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);  
```  
  
 <span data-ttu-id="28050-159">계속하려면 `Properties` 클래스에서 `Message` 컬렉션을 사용하는 방법을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-159">Before proceeding, it is important to understand the usage of the `Properties` collection in the `Message` class.</span></span> <span data-ttu-id="28050-160">일반적으로 이 `Properties` 컬렉션은 채널 계층의 하위 수준에서 상위 수준으로 데이터를 전달할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-160">Typically, this `Properties` collection is used when passing data from lower to the upper levels from the channel layer.</span></span> <span data-ttu-id="28050-161">이렇게 하면 프로토콜 정보에 관계없이 일관된 방식으로 상위 수준에 원하는 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-161">This way the desired data can be provided to the upper levels in a consistent manner regardless of the protocol details.</span></span> <span data-ttu-id="28050-162">즉, 채널 계층에서 SOAP 헤더나 HTTP 쿠키 헤더로 컨텍스트 ID를 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-162">In other words, the channel layer can send and receive the context ID either as a SOAP header or a HTTP cookie header.</span></span> <span data-ttu-id="28050-163">그러나 채널 계층을 통해 `Properties` 컬렉션에서 이 정보를 사용할 수 있으므로 상위 수준에서는 해당 정보에 대해 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-163">But it is not necessary for the upper levels to know about these details because the channel layer makes this information available in the `Properties` collection.</span></span>  
  
 <span data-ttu-id="28050-164">이제 `DurableInstanceContextChannelBase` 클래스를 사용하여 필요한 인터페이스 10개(IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel)를 모두 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-164">Now with the `DurableInstanceContextChannelBase` class in place all ten of the necessary interfaces (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) must be implemented.</span></span> <span data-ttu-id="28050-165">이러한 인터페이스는 사용 가능한 모든 메시지 교환 패턴(데이터그램, 단방향, 이중 및 세션 변형)과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-165">They resemble every available message exchange pattern (datagram, simplex, duplex and their sessionful variants).</span></span> <span data-ttu-id="28050-166">이러한 구현은 각각 앞에서 설명한 기본 클래스를 상속하고 `ApplyContext`와 `ReadContexId`를 적절하게 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-166">Each of these implementations inherit the base class previously described and calls `ApplyContext` and `ReadContexId` appropriately.</span></span> <span data-ttu-id="28050-167">예를 들어, IOutputChannel 인터페이스를 구현하는 `DurableInstanceContextOutputChannel`은 메시지를 보내는 각 메서드에서 `ApplyContext` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-167">For example, `DurableInstanceContextOutputChannel` - which implements the IOutputChannel interface - calls the `ApplyContext` method from each method that sends the messages.</span></span>  
  
```  
public void Send(Message message, TimeSpan timeout)  
{  
    // Apply the context information before sending the message.  
    this.ApplyContext(message);  
    //…  
}   
```  
  
 <span data-ttu-id="28050-168">반면, `DurableInstanceContextInputChannel` 인터페이스를 구현하는 `IInputChannel`은 메시지를 받는 각 메서드에서 `ReadContextId` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-168">On the other hand, `DurableInstanceContextInputChannel` - which implements the `IInputChannel` interface - calls the `ReadContextId` method in each method which receives the messages.</span></span>  
  
```  
public Message Receive(TimeSpan timeout)  
{  
    //…  
      ReadContextId(message);  
      return message;  
}  
```  
  
 <span data-ttu-id="28050-169">이와 달리 다음 채널 구현에서는 메서드 호출을 채널 스택의 아래 채널에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-169">Apart from this, these channel implementations delegate the method invocations to the channel below them in the channel stack.</span></span> <span data-ttu-id="28050-170">그러나 세션 변형에는 세션을 만드는 첫 번째 메시지에 대해서만 컨텍스트 ID를 보내고 읽을 수 있는 기본 논리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-170">However, sessionful variants have a basic logic to make sure that the context ID is sent and is read only for the first message that causes the session to be created.</span></span>  
  
```  
if (isFirstMessage)  
{  
//…  
    this.ApplyContext(message);  
    isFirstMessage = false;  
}  
```  
  
 <span data-ttu-id="28050-171">그런 다음 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클래스와 `DurableInstanceContextBindingElement` 클래스에서 이러한 채널 구현을 `DurableInstanceContextBindingElementSection` 채널 런타임에 적절하게 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-171">These channel implementations are then added to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel runtime by the `DurableInstanceContextBindingElement` class and `DurableInstanceContextBindingElementSection` class appropriately.</span></span> <span data-ttu-id="28050-172">참조는 [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) 채널 바인딩 요소 및 바인딩 요소 섹션에 대 한 자세한 내용은 샘플 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-172">See the [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) channel sample documentation for more details about binding elements and binding element sections.</span></span>  
  
## <a name="service-model-layer-extensions"></a><span data-ttu-id="28050-173">서비스 모델 계층 확장명</span><span class="sxs-lookup"><span data-stu-id="28050-173">Service Model Layer Extensions</span></span>  
 <span data-ttu-id="28050-174">이제 컨텍스트 ID가 채널 계층을 통해 이동했으므로 서비스 동작을 구현하여 인스턴스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-174">Now that the context ID has traveled through the channel layer, the service behavior can be implemented to customize the instantiation.</span></span> <span data-ttu-id="28050-175">이 샘플에서는 저장소 관리자를 사용하여 영구 저장소에서 상태를 로드하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-175">In this sample, a storage manager is used to load and save state from or to the persistent store.</span></span> <span data-ttu-id="28050-176">앞에서 설명한 대로 이 샘플에서는 SQL Server 2005를 백업 저장소로 사용하는 저장소 관리자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-176">As explained previously, this sample provides a storage manager that uses SQL Server 2005 as its backing store.</span></span> <span data-ttu-id="28050-177">그러나 이 확장에 사용자 지정 저장소 메커니즘을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-177">However, it is also possible to add custom storage mechanisms to this extension.</span></span> <span data-ttu-id="28050-178">해당 작업을 수행하기 위해 모든 저장소 관리자에 의해 구현되어야 하는 공용 인터페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-178">To do that a public interface is declared, which must be implemented by all storage managers.</span></span>  
  
```  
public interface IStorageManager  
{  
    object GetInstance(string contextId, Type type);  
    void SaveInstance(string contextId, object state);  
}  
```  
  
 <span data-ttu-id="28050-179">`SqlServerStorageManager` 클래스에는 기본 `IStorageManager` 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-179">The `SqlServerStorageManager` class contains the default `IStorageManager` implementation.</span></span> <span data-ttu-id="28050-180">해당 `SaveInstance` 메서드에서 지정된 개체는 XmlSerializer를 사용하여 serialize되고 SQL Server 데이터베이스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-180">In its `SaveInstance` method the given object is serialized using the XmlSerializer and is saved to the SQL Server database.</span></span>  
  
```  
XmlSerializer serializer = new XmlSerializer(state.GetType());  
string data;  
  
using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))  
{  
    serializer.Serialize(writer, state);  
    data = writer.ToString();  
}  
  
using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
{  
    connection.Open();  
  
    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";  
  
    using (SqlCommand command = new SqlCommand(update, connection))  
    {  
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;  
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;  
  
        int rows = command.ExecuteNonQuery();  
  
        if (rows == 0)  
        {  
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";  
            command.CommandText = insert;  
            command.ExecuteNonQuery();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="28050-181">`GetInstance` 메서드에서는 지정된 컨텍스트 ID에 대해 serialize된 데이터를 읽고 해당 데이터로 생성된 개체를 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-181">In the `GetInstance` method the serialized data is read for a given context ID and the object constructed from it is returned to the caller.</span></span>  
  
```  
object data;  
using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
{  
    connection.Open();  
  
    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";  
    using (SqlCommand command = new SqlCommand(select, connection))  
    {  
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;  
        data = command.ExecuteScalar();  
    }  
}  
  
if (data != null)  
{  
    XmlSerializer serializer = new XmlSerializer(type);  
    using (StringReader reader = new StringReader((string)data))  
    {  
        object instance = serializer.Deserialize(reader);  
        return instance;  
    }  
}  
```  
  
 <span data-ttu-id="28050-182">이러한 저장소 관리자의 사용자는 해당 관리자를 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-182">Users of these storage managers are not supposed to instantiate them directly.</span></span> <span data-ttu-id="28050-183">따라서 저장소 관리자 생성 정보에서 추출한 `StorageManagerFactory` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-183">They use the `StorageManagerFactory` class, which abstracts from the storage manager creation details.</span></span> <span data-ttu-id="28050-184">이 클래스에는 지정된 저장소 관리자 형식의 인스턴스를 만드는 정적 멤버인 `GetStorageManager`가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-184">This class has one static member, `GetStorageManager`, which creates an instance of a given storage manager type.</span></span> <span data-ttu-id="28050-185">형식 매개 변수가 `null`이면 이 메서드는 기본 `SqlServerStorageManager` 클래스의 인스턴스를 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-185">If the type parameter is `null`, this method creates an instance of the default `SqlServerStorageManager` class and returns it.</span></span> <span data-ttu-id="28050-186">또한 지정된 형식의 유효성을 검사하여 `IStorageManager` 인터페이스가 구현되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-186">It also validates the given type to make sure that it implements the `IStorageManager` interface.</span></span>  
  
```  
public static IStorageManager GetStorageManager(Type storageManagerType)  
{  
IStorageManager storageManager = null;  
  
if (storageManagerType == null)  
{  
    return new SqlServerStorageManager();  
}  
else  
{  
    object obj = Activator.CreateInstance(storageManagerType);  
  
    // Throw if the specified storage manager type does not  
    // implement IStorageManager.  
    if (obj is IStorageManager)  
    {  
        storageManager = (IStorageManager)obj;  
    }  
    else  
    {  
        throw new InvalidOperationException(  
                  ResourceHelper.GetString("ExInvalidStorageManager"));  
    }  
  
    return storageManager;  
}                  
}   
```  
  
 <span data-ttu-id="28050-187">영구 저장소에서 인터페이스를 읽고 쓰는 데 필요한 인프라를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-187">The necessary infrastructure to read and write instances from the persistent storage is implemented.</span></span> <span data-ttu-id="28050-188">이제 서비스 동작을 변경하는 데 필요한 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-188">Now the necessary steps to change the service behavior have to be taken.</span></span>  
  
 <span data-ttu-id="28050-189">이 프로세스의 첫 번째 단계로 채널 계층을 통해 현재 InstanceContext에 도달한 컨텍스트 ID를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-189">As the first step of this process we have to save the context ID, which came through the channel layer to the current InstanceContext.</span></span> <span data-ttu-id="28050-190">InstanceContext는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 디스패처와 서비스 인스턴스 간의 링크 역할을 하는 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-190">InstanceContext is a runtime component that acts as the link between the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dispatcher and the service instance.</span></span> <span data-ttu-id="28050-191">이 구성 요소를 사용하면 서비스 인스턴스에 추가 상태 및 동작을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-191">It can be used to provide additional state and behavior to the service instance.</span></span> <span data-ttu-id="28050-192">세션 통신에서는 첫 번째 메시지에 대해서만 컨텍스트 ID를 전송하기 때문에 이 구성 요소가 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-192">This is essential because in sessionful communication the context ID is sent only with the first message.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="28050-193">에서는 확장 가능한 개체 패턴을 사용하여 새 상태 및 동작을 추가함으로써 InstanceContext 런타임 구성 요소를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-193"> allows extending its InstanceContext runtime component by adding a new state and behavior using its extensible object pattern.</span></span> <span data-ttu-id="28050-194">확장 가능한 개체 패턴은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 새 기능으로 기존 런타임 클래스를 확장하거나 개체에 새 상태 기능을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-194">The extensible object pattern is used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="28050-195">세 가지 인터페이스가 있습니다 확장명 가능한 개체 패턴에 IExtensibleObject의\<T >, IExtension\<T >, 및 i e x\<T >:</span><span class="sxs-lookup"><span data-stu-id="28050-195">There are three interfaces in the extensible object pattern - IExtensibleObject\<T>, IExtension\<T>, and IExtensionCollection\<T>:</span></span>  
  
-   <span data-ttu-id="28050-196">IExtensibleObject\<T > 인터페이스의 기능을 사용자 지정 확장을 허용 하는 개체에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-196">The IExtensibleObject\<T> interface is implemented by objects that allow extensions that customize their functionality.</span></span>  
  
-   <span data-ttu-id="28050-197">IExtension\<T > 인터페이스 화 형식의 클래스 확장인 개체에 의해 구현 됩니다</span><span class="sxs-lookup"><span data-stu-id="28050-197">The IExtension\<T> interface is implemented by objects that are extensions of classes of type T.</span></span>  
  
-   <span data-ttu-id="28050-198">i e x\<T > 인터페이스는 형식별으로 IExtensions를 검색할 수 있는 IExtensions의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-198">The IExtensionCollection\<T> interface is a collection of IExtensions that allows for retrieving IExtensions by their type.</span></span>  
  
 <span data-ttu-id="28050-199">따라서 IExtension 인터페이스를 구현하고 필요한 상태를 정의하는 InstanceContextExtension 클래스를 만들어 컨텍스트 ID를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-199">Therefore an InstanceContextExtension class should be created that implements the IExtension interface and defines the required state to save the context ID.</span></span> <span data-ttu-id="28050-200">이 클래스는 사용할 저장소 관리자를 보유하는 상태도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-200">This class also provides the state to hold the storage manager being used.</span></span> <span data-ttu-id="28050-201">새 상태가 저장된 다음에는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-201">Once the new state is saved, it should not be possible to modify it.</span></span> <span data-ttu-id="28050-202">따라서 상태가 생성되어 인스턴스에 제공되고 저장된 다음에는 읽기 전용 속성으로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-202">Therefore the state is provided and saved to the instance at the time it is being constructed and then only accessible using read-only properties.</span></span>  
  
```  
// Constructor  
public DurableInstanceContextExtension(string contextId,   
            IStorageManager storageManager)  
{  
    this.contextId = contextId;  
    this.storageManager = storageManager;              
}  
  
// Read only properties  
public string ContextId  
{  
    get { return this.contextId; }  
}  
  
public IStorageManager StorageManager  
{  
    get { return this.storageManager; }              
}   
```  
  
 <span data-ttu-id="28050-203">InstanceContextInitializer 클래스는 IInstanceContextInitializer 인터페이스를 구현하고 생성되는 InstanceContext의 Extensions 컬렉션에 인스턴스 컨텍스트 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-203">The InstanceContextInitializer class implements the IInstanceContextInitializer interface and adds the instance context extension to the Extensions collection of the InstanceContext being constructed.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
    string contextId =   
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];  
  
    DurableInstanceContextExtension extension =  
                new DurableInstanceContextExtension(contextId,   
                     storageManager);  
    instanceContext.Extensions.Add(extension);  
}  
```  
  
 <span data-ttu-id="28050-204">앞에서 설명한 대로 `Properties` 클래스의 `Message` 컬렉션에서 컨텍스트 ID를 읽고 확장 클래스의 생성자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-204">As described earlier the context ID is read from the `Properties` collection of the `Message` class and passed to the constructor of the extension class.</span></span> <span data-ttu-id="28050-205">이 샘플에서는 계층 간에 일관된 방식으로 정보를 교환할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28050-205">This demonstrates how information can be exchanged between the layers in a consistent manner.</span></span>  
  
 <span data-ttu-id="28050-206">다음으로 중요한 단계는 서비스 인스턴스 생성 프로세스를 재정의하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-206">The next important step is overriding the service instance creation process.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="28050-207">에서는 사용자 지정 인스턴스 동작을 구현하고 IInstanceProvider 인터페이스를 사용하여 런타임에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-207"> allows implementing custom instantiation behaviors and hooking them up to the runtime using the IInstanceProvider interface.</span></span> <span data-ttu-id="28050-208">이 작업을 수행하기 위해 새 `InstanceProvider` 클래스가 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-208">The new `InstanceProvider` class is implemented to do that job.</span></span> <span data-ttu-id="28050-209">생성자에는 인스턴스 공급자에 필요한 서비스 유형이 허용되며,</span><span class="sxs-lookup"><span data-stu-id="28050-209">In the constructor the service type expected from the instance provider is accepted.</span></span> <span data-ttu-id="28050-210">이 서비스 유형은 나중에 새 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-210">Later this is used to create new instances.</span></span> <span data-ttu-id="28050-211">`GetInstance` 구현에서는 지속적인 인스턴스를 찾는 저장소 관리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28050-211">In the `GetInstance` implementation an instance of a storage manager is created looking for a persisted instance.</span></span> <span data-ttu-id="28050-212">이 구현에서 `null`을 반환하면 서비스 유형의 새 인스턴스가 인스턴스화되어 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-212">If it returns `null` then a new instance of the service type is instantiated and returned to the caller.</span></span>  
  
```  
public object GetInstance(InstanceContext instanceContext, Message message)  
{  
    object instance = null;  
  
    DurableInstanceContextExtension extension =  
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();  
  
    string contextId = extension.ContextId;  
    IStorageManager storageManager = extension.StorageManager;              
  
    instance = storageManager.GetInstance(contextId, serviceType);          
  
    if (instance == null)  
    {  
        instance = Activator.CreateInstance(serviceType);  
    }  
  
    return instance;  
}  
```  
  
 <span data-ttu-id="28050-213">다음으로 중요한 단계는 `InstanceContextExtension`, `InstanceContextInitializer` 및 `InstanceProvider` 클래스를 서비스 모델 런타임에 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-213">The next important step is to install the `InstanceContextExtension`, `InstanceContextInitializer` and `InstanceProvider` classes into the service model runtime.</span></span> <span data-ttu-id="28050-214">사용자 지정 특성을 사용하면 서비스 구현 클래스를 표시하여 동작을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-214">A custom attribute could be used to mark the service implementation classes to install the behavior.</span></span> <span data-ttu-id="28050-215">`DurableInstanceContextAttribute`에는 이 특성의 구현이 포함되어 있으며 `IServiceBehavior` 인터페이스를 구현하여 전체 서비스 런타임을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-215">The `DurableInstanceContextAttribute` contains the implementation for this attribute and it implements the `IServiceBehavior` interface to extend the entire service runtime.</span></span>  
  
 <span data-ttu-id="28050-216">이 클래스에는 사용할 저장소 관리자의 형식을 허용하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-216">This class has a property that accepts the type of the storage manager to be used.</span></span> <span data-ttu-id="28050-217">이렇게 하면 구현을 통해 사용자가 고유한 `IStorageManager` 구현을 이 특성의 매개 변수로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-217">In this way the implementation enables the users to specify their own `IStorageManager` implementation as parameter of this attribute.</span></span>  
  
 <span data-ttu-id="28050-218">`ApplyDispatchBehavior` 구현에서는 현재 `InstanceContextMode` 특성의 `ServiceBehavior`를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-218">In the `ApplyDispatchBehavior` implementation the `InstanceContextMode` of the current `ServiceBehavior` attribute is being verified.</span></span> <span data-ttu-id="28050-219">이 속성을 Singleton으로 설정하면 영속 인스턴스를 사용할 수 없으며 `InvalidOperationException`이 throw되어 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="28050-219">If this property is set to Singleton, enabling durable instancing is not possible and an `InvalidOperationException` is thrown to notify the host.</span></span>  
  
```  
ServiceBehaviorAttribute serviceBehavior =  
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();  
  
if (serviceBehavior != null &&  
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)  
{  
    throw new InvalidOperationException(  
       ResourceHelper.GetString("ExSingeltonInstancingNotSupported"));  
}  
```  
  
 <span data-ttu-id="28050-220">그런 다음 저장소 관리자, 인스턴스 컨텍스트 이니셜라이저 및 인스턴스 공급자의 인스턴스가 생성되고 모든 끝점에 대해 만들어진 `DispatchRuntime`에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-220">After this the instances of the storage manager, instance context initializer, and the instance provider are created and installed in the `DispatchRuntime` created for every endpoint.</span></span>  
  
```  
IStorageManager storageManager =   
    StorageManagerFactory.GetStorageManager(storageManagerType);  
  
InstanceContextInitializer contextInitializer =  
    new InstanceContextInitializer(storageManager);  
  
InstanceProvider instanceProvider =  
    new InstanceProvider(description.ServiceType);  
  
foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
{  
    ChannelDispatcher cd = cdb as ChannelDispatcher;  
  
    if (cd != null)  
    {  
        foreach (EndpointDispatcher ed in cd.Endpoints)  
        {  
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);  
            ed.DispatchRuntime.InstanceProvider = instanceProvider;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="28050-221">지금까지의 내용을 요약하면 이 샘플에서는 사용자 지정 컨텍스트 ID 교환을 위해 사용자 지정 유선 프로토콜을 사용하는 채널을 생성하고 기본 인스턴스 동작을 덮어써서 영구 저장소에서 인스턴스를 로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-221">In summary so far, this sample has produced a channel that enabled the custom wire protocol for custom context ID exchange and it also overwrites the default instancing behavior to load the instances from the persistent storage.</span></span>  
  
 <span data-ttu-id="28050-222">이제 서비스 인스턴스를 영구 저장소에 저장하는 방법만 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-222">What is left is a way to save the service instance to the persistent storage.</span></span> <span data-ttu-id="28050-223">앞에서 설명한 대로 상태를 저장하는 데 필요한 기능은 `IStorageManager`에 이미 구현되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-223">As discussed previously, there is already the required functionality to save the state in an `IStorageManager` implementation.</span></span> <span data-ttu-id="28050-224">이제 이 기능을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임과 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-224">We now must integrate this with the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime.</span></span> <span data-ttu-id="28050-225">서비스 구현 클래스의 메서드에 적용할 수 있는 또 다른 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-225">Another attribute is required that is applicable to the methods in the service implementation class.</span></span> <span data-ttu-id="28050-226">이 특성은 서비스 인스턴스의 상태를 변경하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-226">This attribute is supposed to be applied to the methods that change the state of the service instance.</span></span>  
  
 <span data-ttu-id="28050-227">`SaveStateAttribute` 클래스가 이 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-227">The `SaveStateAttribute` class implements this functionality.</span></span> <span data-ttu-id="28050-228">또한 `IOperationBehavior` 클래스를 구현하여 각 작업에 대해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-228">It also implements `IOperationBehavior` class to modify the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime for each operation.</span></span> <span data-ttu-id="28050-229">이 특성으로 메서드를 표시하면 적절한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]이 생성되는 동안 `ApplyBehavior` 런타임에서 `DispatchOperation` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-229">When a method is marked with this attribute, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime invokes the `ApplyBehavior` method while the appropriate `DispatchOperation` is being constructed.</span></span> <span data-ttu-id="28050-230">이 메서드 구현에는 다음과 같은 코드가 한 줄 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-230">In this method implementation there is single line of code:</span></span>  
  
```  
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);  
```  
  
 <span data-ttu-id="28050-231">이 명령은 `OperationInvoker` 형식의 인스턴스를 만들어 생성할 `Invoker`의 `DispatchOperation` 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-231">This instruction creates an instance of `OperationInvoker` type and assigns it to the `Invoker` property of the `DispatchOperation` being constructed.</span></span> <span data-ttu-id="28050-232">`OperationInvoker` 클래스는 `DispatchOperation`에 대해 생성된 기본 작업 호출자의 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="28050-232">The `OperationInvoker` class is a wrapper for the default operation invoker created for the `DispatchOperation`.</span></span> <span data-ttu-id="28050-233">이 클래스는 `IOperationInvoker` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-233">This class implements the `IOperationInvoker` interface.</span></span> <span data-ttu-id="28050-234">`Invoke` 메서드 구현에서 실제 메서드 호출은 내부 작업 호출자에게 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-234">In the `Invoke` method implementation the actual method invocation is delegated to the inner operation invoker.</span></span> <span data-ttu-id="28050-235">그러나 결과를 반환하기 전에 `InstanceContext`의 저장소 관리자를 사용하여 서비스 인스턴스를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-235">However, before returning the results the storage manager in the `InstanceContext` is used to save the service instance.</span></span>  
  
```  
object result = innerOperationInvoker.Invoke(instance,  
    inputs, out outputs);  
  
// Save the instance using the storage manager saved in the   
// current InstanceContext.  
InstanceContextExtension extension =  
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();  
  
extension.StorageManager.SaveInstance(extension.ContextId, instance);  
return result;  
```  
  
## <a name="using-the-extension"></a><span data-ttu-id="28050-236">확장 사용</span><span class="sxs-lookup"><span data-stu-id="28050-236">Using the Extension</span></span>  
 <span data-ttu-id="28050-237">채널 계층 확장과 서비스 모델 계층 확장이 모두 수행되어 이제 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-237">Both the channel layer and service model layer extensions are done and they can now be used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span> <span data-ttu-id="28050-238">서비스는 사용자 지정 바인딩을 사용하여 채널 스택에 채널을 추가한 다음 적절한 특성으로 서비스 구현 클래스를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-238">Services have to add the channel into the channel stack using a custom binding and then mark the service implementation classes with the appropriate attributes.</span></span>  
  
```  
[DurableInstanceContext]  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class ShoppingCart : IShoppingCart  
{  
//…  
     [SaveState]  
     public int AddItem(string item)  
     {  
         //…  
     }  
//…  
 }  
```  
  
 <span data-ttu-id="28050-239">클라이언트 응용 프로그램에서는 사용자 지정 바인딩을 사용하여 채널 스택에 DurableInstanceContextChannel을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-239">Client applications must add the DurableInstanceContextChannel into the channel stack using a custom binding.</span></span> <span data-ttu-id="28050-240">구성 파일에서 선언적으로 채널을 구성하려면 바인딩 요소 섹션을 바인딩 요소 확장 컬렉션에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-240">To configure the channel declaratively in the configuration file, the binding element section has to be added to the binding element extensions collection.</span></span>  
  
```xml  
<system.serviceModel>  
 <extensions>  
   <bindingElementExtensions>  
     <add name="durableInstanceContext"  
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
   </bindingElementExtensions>  
 </extensions>  
```  
  
 <span data-ttu-id="28050-241">이제 다른 표준 바인딩 요소와 마찬가지로 바인딩 요소를 사용자 지정 바인딩에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-241">Now the binding element can be used with a custom binding just like other standard binding elements:</span></span>  
  
```xml  
<bindings>  
 <customBinding>  
   <binding name="TextOverHttp">  
     <durableInstanceContext contextType="HttpCookie"/>             
     <reliableSession />  
     <textMessageEncoding />  
     <httpTransport />  
   </binding>  
 </customBinding>  
</bindings>  
```  
  
## <a name="conclusion"></a><span data-ttu-id="28050-242">결론</span><span class="sxs-lookup"><span data-stu-id="28050-242">Conclusion</span></span>  
 <span data-ttu-id="28050-243">이 샘플에서는 사용자 지정 프로토콜 채널을 만드는 방법 및 서비스 동작을 사용자 지정하여 사용하는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-243">This sample showed how to create a custom protocol channel and how to customize the service behavior to enable it.</span></span>  
  
 <span data-ttu-id="28050-244">사용자가 구성 섹션을 사용하여 `IStorageManager` 구현을 지정할 수 있도록 하면 확장을 더 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-244">The extension can be further improved by letting users specify the `IStorageManager` implementation using a configuration section.</span></span> <span data-ttu-id="28050-245">이렇게 하면 서비스 코드를 다시 컴파일하지 않고도 백업 저장소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-245">This makes it possible to modify the backing store without recompiling the service code.</span></span>  
  
 <span data-ttu-id="28050-246">또한 인스턴스의 상태를 캡슐화하는 클래스(예: `StateBag`)를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-246">Furthermore you could try to implement a class (for example, `StateBag`), which encapsulates the state of the instance.</span></span> <span data-ttu-id="28050-247">이 클래스는 상태가 변경될 때마다 상태를 유지하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-247">That class is responsible for persisting the state whenever it changes.</span></span> <span data-ttu-id="28050-248">따라서 `SaveState` 특성을 사용하지 않고 유지 작업을 보다 정확하게 수행할 수 있습니다. 예를 들어, 메서드를 호출할 때마다 `SaveState` 특성으로 상태를 저장하는 대신 상태가 실제로 변경될 때 해당 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-248">This way you can avoid using the `SaveState` attribute and perform the persisting work more accurately (for example, you could persist the state when the state is actually changed rather than saving it each time when a method with the `SaveState` attribute is called).</span></span>  
  
 <span data-ttu-id="28050-249">샘플을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="28050-249">When you run the sample, the following output is displayed.</span></span> <span data-ttu-id="28050-250">클라이언트는 장바구니에 항목 두 개를 추가하고 장바구니의 항목 목록을 서비스에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28050-250">The client adds two items to its shopping cart and then gets the list of items in its shopping cart from the service.</span></span> <span data-ttu-id="28050-251">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="28050-251">Press ENTER in each console window to shut down the service and client.</span></span>  
  
```  
Enter the name of the product: apples  
Enter the name of the product: bananas  
  
Shopping cart currently contains the following items.  
apples  
bananas  
Press ENTER to shut down client  
```  
  
> [!NOTE]
>  <span data-ttu-id="28050-252">서비스를 다시 빌드하면 데이터베이스 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="28050-252">Rebuilding the service overwrites the database file.</span></span> <span data-ttu-id="28050-253">샘플을 여러 번 실행하는 동안 상태를 유지하려면 실행할 때마다 샘플을 다시 빌드하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-253">To observe state preserved across multiple runs of the sample, be sure not to rebuild the sample between runs.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="28050-254">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="28050-254">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="28050-255">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-255">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="28050-256">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-256">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="28050-257">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-257">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28050-258">이 샘플을 실행하려면 SQL Server 2005 또는 SQL Express 2005를 실행하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-258">You must be running SQL Server 2005 or SQL Express 2005 to run this sample.</span></span> <span data-ttu-id="28050-259">SQL Server 2005를 실행하고 있는 경우 서비스의 연결 문자열 구성을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-259">If you are running SQL Server 2005, you must modify the configuration of the service's connection string.</span></span> <span data-ttu-id="28050-260">다중 컴퓨터 구성에서 실행하는 경우 SQL Server는 서버 컴퓨터에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28050-260">When running cross-machine, SQL Server is only required on the server machine.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28050-261">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-261">The samples may already be installed on your machine.</span></span> <span data-ttu-id="28050-262">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="28050-262">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="28050-263">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="28050-263">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="28050-264">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28050-264">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`  
  
## <a name="see-also"></a><span data-ttu-id="28050-265">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28050-265">See Also</span></span>
