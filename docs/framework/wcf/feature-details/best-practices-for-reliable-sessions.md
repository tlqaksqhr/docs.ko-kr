---
title: "신뢰할 수 있는 세션을 위한 최선의 방법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6e20b5cf02e7aef31127bb88e27e21965a192a6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="best-practices-for-reliable-sessions"></a><span data-ttu-id="d1c00-102">신뢰할 수 있는 세션을 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="d1c00-102">Best Practices for Reliable Sessions</span></span>

<span data-ttu-id="d1c00-103">이 항목에서는 신뢰할 수 있는 세션에 대 한 모범 사례를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-103">This topic discusses best practices for reliable sessions.</span></span>

## <a name="setting-maxtransferwindowsize"></a><span data-ttu-id="d1c00-104">MaxTransferWindowSize 설정</span><span class="sxs-lookup"><span data-stu-id="d1c00-104">Setting MaxTransferWindowSize</span></span>

<span data-ttu-id="d1c00-105">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 신뢰할 수 있는 세션은 전송 창을 사용하여 클라이언트 및 서비스에서 메시지를 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-105">Reliable sessions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] use a transfer window to hold messages on the client and service.</span></span> <span data-ttu-id="d1c00-106">구성 가능한 속성 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A>는 전송 창이 보관할 수 있는 메시지 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-106">The configurable property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indicates how many messages the transfer window can hold.</span></span>

<span data-ttu-id="d1c00-107">발신자의 경우 전송 창이 승인을; 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다. 수신기에서 서비스에 대해 버퍼링 할 메시지 수 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-107">On the sender, this indicates how many messages the transfer window can hold while waiting for acknowledgements; on the receiver, it indicates how many messages to buffer for the service.</span></span>

<span data-ttu-id="d1c00-108">올바른 크기를 선택 합니다. 네트워크의 효율성과 서비스의 최적 용량에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-108">Choosing the right size impacts the efficiency of the network and the optimal capacity of the service.</span></span> <span data-ttu-id="d1c00-109">다음 섹션에서는이 속성 및 값의 영향에 대 한 값을 선택할 때 고려해 야 할 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-109">The following sections detail what to consider when choosing a value for this property and the impact of the value.</span></span>

<span data-ttu-id="d1c00-110">기본 전송 창 크기는 8 개의 메시지.</span><span class="sxs-lookup"><span data-stu-id="d1c00-110">The default transfer window size is eight messages.</span></span>

### <a name="efficient-use-of-the-network"></a><span data-ttu-id="d1c00-111">네트워크의 효율적인 사용</span><span class="sxs-lookup"><span data-stu-id="d1c00-111">Efficient use of the network</span></span>

<span data-ttu-id="d1c00-112">이 컨텍스트에서 용어 *네트워크* 클라이언트 (발신자)와 서비스 (수신자) 간의 통신의 기본으로 사용 되는 모든 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-112">In this context, the term *network* corresponds to everything used as the basis of communication between a client (sender) and a service (receiver).</span></span> <span data-ttu-id="d1c00-113">여기에 전송 연결 및 모든 중간 매개자 또는 사이는 브리지 SOAP 라우터 또는 HTTP 프록시/방화벽을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-113">This includes the transport connections and any intermediary or bridges in between, including SOAP routers or HTTP proxies/firewalls.</span></span>

<span data-ttu-id="d1c00-114">네트워크를 효율적으로 사용하려면 네트워크 용량을 최대한 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-114">Efficient use of the network ensures that network capacity is fully used.</span></span> <span data-ttu-id="d1c00-115">네트워크를 통해 초당 전송할 수 있는 데이터의 양 (*데이터 속도*) 및 수신자에 게 보낸 사람 으로부터 데이터를 전송 하는 데 걸리는 시간 (*대기 시간*) 영향을 얼마나 효과적으로 네트워크 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-115">Both the amount of data that can be transferred per second over the network (*data rate*) and the time it takes to transfer data from the sender to the receiver (*latency*) impact how effectively the network is utilized.</span></span>

<span data-ttu-id="d1c00-116">발신자의 경우 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 속성은 전송 창이 승인을 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-116">On the sender, the property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indicates how many messages its transfer window can hold while waiting for acknowledgements.</span></span> <span data-ttu-id="d1c00-117">네트워크 대기 시간이 깁니다 하 고 응답 보낸 사람 및 효과적인 네트워크 사용률을 보장 하기 위해 전송 창 크기를 증가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-117">If the network latency is high and in order to ensure a responsive sender and effective network utilization, you should increase the transfer window size.</span></span>

<span data-ttu-id="d1c00-118">예를 들어 보낸 사람에 게 데이터 전송 속도 유지 하는 경우에, 대기 시간 수 높은 경우 발신자와 수신자 간에 여러 매개 자가 존재 또는 데이터 손실 매개자 또는 네트워크를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-118">For example even if the sender keeps up with data rate, latency could be high if several intermediaries exist between the sender and receiver or the data must pass through a lossy intermediary or network.</span></span> <span data-ttu-id="d1c00-119">따라서, 발신자는 통신 중에 보낼 새 메시지를 받기 전에 전송 창의 메시지에 대 한 승인을 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-119">Thus, the sender has to wait for acknowledgements for the messages in its transfer window before accepting new messages to send on the wire.</span></span> <span data-ttu-id="d1c00-120">버퍼가 대기 시간이 긴 덜 유효 네트워크 사용률입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-120">The smaller the buffer with high latency, the less effective the network utilization.</span></span> <span data-ttu-id="d1c00-121">반면에 전송 창 크기가 너무 클 서비스 클라이언트에서 보낸 데이터의 높은 속도를 따라가야 하기를 할 수 있으므로 서비스를 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-121">On the other hand, too high a transfer window size may impact the service because the service may need to catch up to the high rate of data sent by the client.</span></span>

### <a name="running-the-service-to-capacity"></a><span data-ttu-id="d1c00-122">용량에 맞게 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="d1c00-122">Running the service to capacity</span></span>

<span data-ttu-id="d1c00-123">네트워크를 효율적으로 사용 하 고, 필요한 만큼도 좋습니다 최적의 용량에 실행 되도록 서비스.</span><span class="sxs-lookup"><span data-stu-id="d1c00-123">As much as the network is used efficiently, ideally you also want the service to run at optimal capacity.</span></span> <span data-ttu-id="d1c00-124">수신자의 전송 창 크기 속성은 수신자가 버퍼링할 수 있는 메시지 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-124">The transfer window size property on the receiver indicates how many messages the receiver can buffer.</span></span> <span data-ttu-id="d1c00-125">이 메시지 버퍼링은 네트워크 흐름 제어에 도움을 줄 뿐만 아니라 서비스를 최대 용량으로 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-125">This message buffering helps not only the network flow control but also enables the service to run to full capacity.</span></span> <span data-ttu-id="d1c00-126">예를 들어 하나의 메시지를 버퍼가 하 고 메시지가 서비스가 처리할 수 있는 것 보다 빨리 도착할 경우, 다음 네트워크 메시지를 삭제 될 수 있습니다 및 용량을 불필요 하 게 또는 미달 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-126">For example if the buffer is one message and messages arrive faster than the service can process them, then the network might drop messages and capacity might be wasted or underutilized.</span></span>

<span data-ttu-id="d1c00-127">동시에 수신 하 고 이전에 수신된 된 메시지를 처리 하는 동안 메시지를 버퍼링 하는 대로 서비스의 가용성을 증가 버퍼를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-127">Using a buffer increases the availability of the service as it concurrently receives and buffers a message while processing the previously received messages.</span></span>

<span data-ttu-id="d1c00-128">동일한를 사용 하는 것이 좋습니다 `MaxTransferWindowSize` 발신자와 수신자 모두에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-128">We recommended that you use the same `MaxTransferWindowSize` on both the sender and receiver.</span></span>

### <a name="enabling-flow-control"></a><span data-ttu-id="d1c00-129">흐름 제어 사용</span><span class="sxs-lookup"><span data-stu-id="d1c00-129">Enabling flow control</span></span>

<span data-ttu-id="d1c00-130">*흐름 제어* 는 발신자와 수신자에 맞춰 서로, 메시지를 사용 하 고 작업을 수행 하는, 즉 보장 하는 메커니즘은 생성 하는 가능한 한 빨리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-130">*Flow control* is a mechanism that ensures that the sender and receiver keep pace with each other, that is, the messages are consumed and acted upon as fast as they're produced.</span></span> <span data-ttu-id="d1c00-131">클라이언트 및 서비스의 전송 창 크기는 발신자와 수신자가 적절한 동기화 창 내에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-131">The transfer window size on the client and service ensures that the sender and receiver are within a reasonable window of synchronization.</span></span>

<span data-ttu-id="d1c00-132">속성을 설정 하는 것이 좋습니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> 를 `true` 간의 신뢰할 수 있는 세션을 사용 중인 경우는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-132">We highly recommended that you set the property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> to `true` when you're using a reliable session between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>

## <a name="setting-maxpendingchannels"></a><span data-ttu-id="d1c00-133">MaxPendingChannels 설정</span><span class="sxs-lookup"><span data-stu-id="d1c00-133">Setting MaxPendingChannels</span></span>

<span data-ttu-id="d1c00-134">하지만 다른 클라이언트의 신뢰할 수 있는 세션 통신 하는 서비스를 작성할 때 여러 클라이언트가 동시에 서비스에 신뢰할 수 있는 세션을 설정 하는 것이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-134">When writing a service that enables reliable session communication from different clients, it's possible to have many clients establish a reliable session to the service at the same time.</span></span> <span data-ttu-id="d1c00-135">이 경우 서비스 응답은 `MaxPendingChannels` 속성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-135">The response of the service in these situations depends on the `MaxPendingChannels` property.</span></span>

<span data-ttu-id="d1c00-136">발신자가 수신자에 대해 신뢰할 수 있는 세션 채널을 만드는 경우 발신자와 수신자 간의 핸드셰이크에서 신뢰할 수 있는 세션이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-136">When the sender creates a reliable session channel to a receiver, a handshake between them establishes a reliable session.</span></span> <span data-ttu-id="d1c00-137">신뢰할 수 있는 세션이 설정된 후 채널은 서비스에서 허용할 수 있도록 보류 중인 채널 큐에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-137">After the reliable session is established, the channel is put in a pending channel queue for acceptance by the service.</span></span> <span data-ttu-id="d1c00-138">`MaxPendingChannels` 속성은 이 상태에 있을 수 있는 채널 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-138">The `MaxPendingChannels` property indicates how many channels can be in this state.</span></span>

<span data-ttu-id="d1c00-139">더 이상 추가 채널을 받을 수 없는 상태 서비스에 대 한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-139">It's possible for the service to be in a state where it can't accept more channels.</span></span> <span data-ttu-id="d1c00-140">큐가 가득 신뢰할 수 있는 세션 설정 시도가 거부 되 고 클라이언트가 다시 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-140">If the queue is full, an attempt to establish a reliable session is rejected, and the client must retry.</span></span>

<span data-ttu-id="d1c00-141">더 긴 시간에 대 한 큐에 보류 중인 채널 큐에 남을 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-141">It's also possible that the pending channels in the queue remain in the queue for a longer duration.</span></span> <span data-ttu-id="d1c00-142">한편, 신뢰할 수 있는 세션에는 비활성 시간 제한을 발생할 수 있습니다, 채널이 faulted 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-142">In the meantime, an inactivity timeout on the reliable session may occur, causing the channel to transition to a faulted state.</span></span>

<span data-ttu-id="d1c00-143">동시에 여러 클라이언트가 서비스를 제공 하는 서비스를 작성할 때 사용자의 요구에 적합 한 값을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-143">When writing a service that services multiple clients simultaneously, you should set a value that's suitable for your needs.</span></span> <span data-ttu-id="d1c00-144">에 대 한 값을 너무 높게 설정 된 `MaxPendingChannels` 속성 작업 집합에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-144">Setting too high a value for the `MaxPendingChannels` property impacts your working set.</span></span>

<span data-ttu-id="d1c00-145">에 대 한 기본값 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> 4 개의 채널 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-145">The default value for <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> is four channels.</span></span>

## <a name="reliable-sessions-and-hosting"></a><span data-ttu-id="d1c00-146">신뢰할 수 있는 세션 및 호스팅</span><span class="sxs-lookup"><span data-stu-id="d1c00-146">Reliable sessions and hosting</span></span>

<span data-ttu-id="d1c00-147">다음과 같은 중요 한 고려 사항을 염두에서에 둬야 해야, 웹 신뢰할 수 있는 세션을 사용 하는 서비스를 호스팅 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d1c00-147">When web hosting a service that uses reliable sessions, you should keep the following important considerations in mind:</span></span>

- <span data-ttu-id="d1c00-148">신뢰할 수 있는 세션은 상태 저장 세션이며 상태는 AppDomain에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-148">Reliable sessions are stateful, and state is maintained in the AppDomain.</span></span> <span data-ttu-id="d1c00-149">따라서 신뢰할 수 있는 세션의 일부인 모든 메시지는 동일한 AppDomain에서 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-149">This means that all messages that are part of a reliable session must be processed in the same AppDomain.</span></span> <span data-ttu-id="d1c00-150">팜 또는 가든의 크기는 노드가 하나 보다 큰 웹 팜 및 웹 가든이 제약이 조건을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-150">Web farms and web gardens where the size of the farm or garden is greater than one node can't guarantee this constraint.</span></span>

- <span data-ttu-id="d1c00-151">이중 HTTP 채널을 사용 하 여 신뢰할 수 있는 세션 (예: 사용 `WsDualHttpBinding`) 두 HTTP 연결에서 클라이언트의 경우 보다 더 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-151">Reliable sessions using dual HTTP channels (for example, using `WsDualHttpBinding`) can require more than the default of two HTTP connections per-client.</span></span> <span data-ttu-id="d1c00-152">즉, 동시 응용 프로그램 및 프로토콜 메시지가 주어진된 시간에 각 방식으로 전송 될 수 있으므로 신뢰할 수 있는 이중 세션 최대 두 개의 연결이 각 방법 마다 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-152">This means a duplex reliable session can require up to two connections each way because concurrent application and protocol messages may be transferring each way at any given time.</span></span> <span data-ttu-id="d1c00-153">서비스의 메시지 교환 패턴에 따라 특정 조건에서 이중 HTTP 및 신뢰할 수 있는 세션을 사용 하는 웹 호스팅 서비스에 교착 상태가 발생할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-153">Under certain conditions depending on the message exchange pattern of the service, this means that it's possible to deadlock a web-hosted service using dual HTTP and reliable sessions.</span></span> <span data-ttu-id="d1c00-154">클라이언트당 허용 가능한 HTTP 연결 수를 늘리려면 다음 관련 구성 파일을 추가 합니다 (예를 들어 *web.config* 해당 서비스의):</span><span class="sxs-lookup"><span data-stu-id="d1c00-154">To increase the number of allowable HTTP connections per client, add the following to the relevant configuration file (for example, *web.config* of the service in question):</span></span>

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  <span data-ttu-id="d1c00-155">값은 `maxconnection` 특성은 필요한 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-155">The value of the `maxconnection` attribute is the number of connections needed.</span></span> <span data-ttu-id="d1c00-156">이 경우 최소값에 대 한 연결 4 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1c00-156">The minimum in this case should be four connections.</span></span>
