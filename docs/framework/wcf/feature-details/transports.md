---
title: "Windows Communication Foundation의 전송"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9275f1812111365ed6b0fb3be6957cd9ca883fdf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="68691-102">Windows Communication Foundation의 전송</span><span class="sxs-lookup"><span data-stu-id="68691-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="68691-103">전송 계층은 채널 스택의 최하위 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68691-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="68691-104">HTTP, HTTPS, TCP 및 명명된 파이프가 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 사용되는 기본 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="68691-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="68691-105">이 단원의 항목에서는 이러한 전송 중에서 특정 전송을 선택하여 구성하고 조정 속성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="68691-106">에는 다른 추가 전송도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="68691-106"> includes additional transports.</span></span> <span data-ttu-id="68691-107">메시지 큐 (MSMQ) 전송에 대 한 정보를 참조 하십시오. [큐 및 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="68691-108">피어-투-피어 전송에 대 한 정보를 참조 하십시오. [피어 투 피어 네트워킹](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68691-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="68691-109">In This Section</span></span>  
 [<span data-ttu-id="68691-110">전송 선택</span><span class="sxs-lookup"><span data-stu-id="68691-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="68691-111">세 가지 기본 전송과 그 중 하나를 선택하기 위해 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="68691-112">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="68691-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="68691-113">메시지 인코딩 바인딩 요소를 선택할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="68691-114">스트리밍 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="68691-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="68691-115">스트리밍을 수행하도록 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="68691-116">HTTP 및 HTTPS 구성</span><span class="sxs-lookup"><span data-stu-id="68691-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="68691-117">HTTP 및 HTTPS 전송 바인딩 요소를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="68691-118">방법: WCF URL 예약을 제한 된 예약으로 대체</span><span class="sxs-lookup"><span data-stu-id="68691-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="68691-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 제한 예약을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="68691-120">전송 할당량</span><span class="sxs-lookup"><span data-stu-id="68691-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="68691-121">전송 계층에 사용할 수 있는 할당량을 설정할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="68691-122">Nat 및 방화벽 작업</span><span class="sxs-lookup"><span data-stu-id="68691-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="68691-123">방화벽을 사용하여 메시지를 주고 받을 경우 또는 NAT(Network Address Translation)를 사용할 경우 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="68691-124">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="68691-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="68691-125">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 Net.TCP 포트 공유 구성 요소를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68691-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="68691-126">참조</span><span class="sxs-lookup"><span data-stu-id="68691-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="68691-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="68691-127">Related Sections</span></span>  
 [<span data-ttu-id="68691-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="68691-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="68691-129">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="68691-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
