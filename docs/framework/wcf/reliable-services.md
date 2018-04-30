---
title: 신뢰할 수 있는 서비스
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9cbaef77f4dce609d36ba4b679d8c569b648fa5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="reliable-services"></a><span data-ttu-id="3563d-102">신뢰할 수 있는 서비스</span><span class="sxs-lookup"><span data-stu-id="3563d-102">Reliable Services</span></span>
<span data-ttu-id="3563d-103">큐 및 신뢰할 수 있는 세션은 신뢰할 수 있는 메시징을 구현하는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-103">Queues and reliable sessions are the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] features that implement reliable messaging.</span></span> <span data-ttu-id="3563d-104">이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 신뢰할 수 있는 메시징 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-104">This topic explains the reliable messaging features of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="3563d-105">*신뢰할 수 있는 메시징* 방법 신뢰할 수 있는 메시징 소스는 (라는 *소스*) 메시지를 안정적으로 신뢰할 수 있는 메시징 대상 전송 (라는 *대상*).</span><span class="sxs-lookup"><span data-stu-id="3563d-105">*Reliable messaging* is how a reliable messaging source (called the *source*) transfers messages reliably to a reliable messaging destination (called the *destination*).</span></span>  
  
 <span data-ttu-id="3563d-106">신뢰할 수 있는 메시징에서는 다음 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-106">Reliable messaging performs the following functions:</span></span>  
  
-   <span data-ttu-id="3563d-107">메시지 전송 또는 전송 실패와 상관없이 소스에서 대상으로 보낸 메시지에 대한 보증을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-107">Transfers assurances for messages sent from a source to a destination regardless of message transfer or transport failures.</span></span>  
  
-   <span data-ttu-id="3563d-108">소스와 대상을 서로 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-108">Separates the source and the destination from each other.</span></span> <span data-ttu-id="3563d-109">따라서 소스 및 대상의 실패와 복구를 따로 관리할 수 있으며 소스나 대상을 사용할 수 없는 경우라도 메시지를 안전하게 전송 및 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-109">This provides independent failure and recovery of the source and the destination, as well as reliable transfer and delivery of messages, even when the source or destination is unavailable.</span></span>  
  
 <span data-ttu-id="3563d-110">하지만 신뢰할 수 있는 메시징에는 대기 시간이 길다는 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-110">Reliable messaging frequently comes at the cost of high latency.</span></span> <span data-ttu-id="3563d-111">*대기 시간* 메시지가 소스에서 대상까지 도달 하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-111">*Latency* is the time it takes for the message to reach the destination from the source.</span></span> <span data-ttu-id="3563d-112">따라서[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서는 다음과 같은 유형의 신뢰할 수 있는 메시징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-112">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)], therefore, provides the following types of reliable messaging:</span></span>  
  
-   <span data-ttu-id="3563d-113">[신뢰할 수 있는 세션](../../../docs/framework/wcf/feature-details/reliable-sessions.md), 신뢰할 수 있는 전송 대기 시간이 길어진다는 비용 없이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-113">[Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md), which offers reliable transfer without the cost of high latency.</span></span>  
  
-   <span data-ttu-id="3563d-114">[WCF의 큐](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), 신뢰할 수 있는 전송과 원본과 대상 간의 분리가 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-114">[Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), which offers both reliable transfers and separation between the source and the destination.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="3563d-115">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="3563d-115">Reliable Sessions</span></span>  
 <span data-ttu-id="3563d-116">신뢰할 수 있는 세션에서는 메시징 끝점(소스와 대상)을 분리하는 매개자의 형식이나 개수에 상관없이, WS-Reliable Messaging 프로토콜을 사용하여 소스와 대상 간의 안전한 종단 간 메시지 전송을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-116">Reliable sessions provide end-to-end reliable transfer of messages between a source and a destination using the WS-Reliable Messaging protocol, regardless of the number or type of intermediaries that separate the messaging (source and destination) endpoints.</span></span> <span data-ttu-id="3563d-117">여기에는 끝점 간의 메시지 흐름에 필요한, SOAP를 사용하지 않는 전송 매개자(예: HTTP 프록시) 또는 SOAP를 사용하는 매개자(예: SOAP 기반 라우터나 브리지)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-117">This includes any transport intermediaries that do not use SOAP (for example, HTTP proxies) or intermediaries that use SOAP (for example, SOAP-based routers or bridges) that are required for messages to flow between the endpoints.</span></span> <span data-ttu-id="3563d-118">전송에 실패한 경우 신뢰할 수 있는 세션은 메모리 내 전송 창을 사용하여 SOAP 메시지 수준 오류를 마스킹하고 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-118">Reliable sessions use an in-memory transfer window to mask SOAP message-level failures and re-establish connections in the case of transport failures.</span></span>  
  
 <span data-ttu-id="3563d-119">신뢰할 수 있는 세션은 대기 시간이 짧은 안전한 메시지 전송을 제공하며,</span><span class="sxs-lookup"><span data-stu-id="3563d-119">Reliable sessions provide low-latency reliable message transfers.</span></span> <span data-ttu-id="3563d-120">TCP가 IP 브리지를 통해 패킷을 지원하는 것과 같이, 프록시나 매개자를 통해 SOAP 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-120">They provide for SOAP messages over any proxies or intermediaries, equivalent to what TCP provides for packets over IP bridges.</span></span> <span data-ttu-id="3563d-121">신뢰할 수 있는 세션에 대 한 자세한 내용은 참조 [신뢰할 수 있는 세션](../../../docs/framework/wcf/feature-details/reliable-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-121">For more information about reliable sessions, see [Reliable Sessions](../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
### <a name="queues"></a><span data-ttu-id="3563d-122">큐</span><span class="sxs-lookup"><span data-stu-id="3563d-122">Queues</span></span>  
 <span data-ttu-id="3563d-123">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 큐를 사용하면 메시지를 안전하게 전송할 수 있으며 소스와 대상을 분리할 수 있지만 대기 시간이 깁니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-123">Queues in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provide both reliable transfers of messages and separation between sources and destinations at the cost of high latency.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="3563d-124"> 대기 중인 통신은 메시지 큐(MSMQ)의 위에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-124"> queued communication is built on top of Message Queuing (MSMQ).</span></span>  
  
 <span data-ttu-id="3563d-125">MSMQ는 Windows의 선택적 구성 요소로 제공되며</span><span class="sxs-lookup"><span data-stu-id="3563d-125">MSMQ ships as an optional component with Windows.</span></span> <span data-ttu-id="3563d-126">MSMQ 서비스는 Windows 서비스로 실행되고,</span><span class="sxs-lookup"><span data-stu-id="3563d-126">The MSMQ service runs as a Windows Service.</span></span> <span data-ttu-id="3563d-127">소스 대신 전송 큐에서 전송할 메시지를 캡처하여 대상 큐로 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-127">It captures messages for transmission in a transmission queue on behalf of the source and delivers it to a target queue.</span></span> <span data-ttu-id="3563d-128">대상 큐는 대상을 대신해 메시지를 수락하고 나중에 대상에서 메시지를 요청할 때 배달합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-128">The target queue accepts messages on behalf of the destination for later delivery whenever the destination requests messages.</span></span> <span data-ttu-id="3563d-129">MSMQ 관리자는 전송 중에 메시지가 손실되지 않도록 안전한 메시지 전송 프로토콜을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-129">The MSMQ managers implement a reliable message-transfer protocol so that messages are not lost in transmission.</span></span> <span data-ttu-id="3563d-130">이러한 프로토콜에는 네이티브 프로토콜 또는 SRMP(SOAP Reliable Messaging Protocol)라고 하는 SOAP 기반 프로토콜이 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-130">The protocol can be native or a SOAP-based protocol called SOAP Reliable Messaging Protocol (SRMP).</span></span>  
  
 <span data-ttu-id="3563d-131">큐 간의 안전한 메시지 전송과 결합된 분리를 통해, 느슨하게 결합된 응용 프로그램이 안전하게 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-131">The separation, coupled with reliable message transfers between queues, enables applications that are loosely coupled to communicate reliably.</span></span> <span data-ttu-id="3563d-132">신뢰할 수 있는 세션과 달리 소스와 대상은 동시에 실행될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-132">Unlike reliable sessions, the source and destination do not have to be running at the same time.</span></span> <span data-ttu-id="3563d-133">따라서 소스의 메시지 생산율과 대상의 메시지 소비율이 맞지 않을 경우, 큐가 부하 평준화 메커니즘으로 효과적으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-133">This implicitly enables scenarios where queues are, in effect, used as a load-leveling mechanism when the source's rate of message production and the destination's rate of the message consumption do not match.</span></span> <span data-ttu-id="3563d-134">큐에 대 한 자세한 내용은 참조 [WCF의 큐](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3563d-134">For more information about queues, see [Queues in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3563d-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3563d-135">See Also</span></span>  
 [<span data-ttu-id="3563d-136">신뢰할 수 있는 세션 개요</span><span class="sxs-lookup"><span data-stu-id="3563d-136">Reliable Sessions Overview</span></span>](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 [<span data-ttu-id="3563d-137">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="3563d-137">Queuing in WCF</span></span>](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
