---
title: 메시지 보안을 사용하여 메시지에 보안 설정
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
caps.latest.revision: 16
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: be9d55e508308f23e70be81ac0d4fe0dfd0ea9cd
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="securing-messages-using-message-security"></a><span data-ttu-id="f4984-102">메시지 보안을 사용하여 메시지에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f4984-102">Securing Messages Using Message Security</span></span>
<span data-ttu-id="f4984-103">이 절에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하는 경우의 <xref:System.ServiceModel.NetMsmqBinding> 메시지 보안에 대해 설명합니다</span><span class="sxs-lookup"><span data-stu-id="f4984-103">This section discusses [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message security when using <xref:System.ServiceModel.NetMsmqBinding>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4984-104">이 항목을 읽기 전에 것이 좋습니다 읽어 [보안 개념](../../../../docs/framework/wcf/feature-details/security-concepts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-104">Before reading through this topic, it is recommended that you read [Security Concepts](../../../../docs/framework/wcf/feature-details/security-concepts.md).</span></span>  
  
 <span data-ttu-id="f4984-105">다음 그림에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 사용하는 대기 중인 통신의 개념적 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-105">The following illustration provides a conceptual model of queued communication using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="f4984-106">이 그림과 용어는 전송 보안 개념을</span><span class="sxs-lookup"><span data-stu-id="f4984-106">This illustration and terminology are used to explain</span></span>  
  
 <span data-ttu-id="f4984-107">설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-107">transport security concepts.</span></span>  
  
 <span data-ttu-id="f4984-108">![응용 프로그램 다이어그램 큐에 대기](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "분산-큐-그림")</span><span class="sxs-lookup"><span data-stu-id="f4984-108">![Queued Application Diagram](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Queue-Figure")</span></span>  
  
 <span data-ttu-id="f4984-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 대기 중인 메시지를 보내는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지는 MSMQ(Message Queuing) 메시지의 본문으로 첨부됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-109">When sending queued messages using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message is attached as a body of the Message Queuing (MSMQ) message.</span></span> <span data-ttu-id="f4984-110">전송 보안은 MSMQ 메시지 전체를 보호하지만, 메시지(또는 SOAP) 보안은 MSMQ 메시지의 본문만 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-110">While transport security secures the entire MSMQ message, message (or SOAP) security only secures the body of the MSMQ message.</span></span>  
  
 <span data-ttu-id="f4984-111">클라이언트에서 대상 큐의 메시지를 보호하는 전송 보안과 달리, 메시지 보안의 핵심 개념은 클라이언트에서 받는 응용 프로그램(서비스)의 메시지를 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-111">The key concept of message security is that the client secures the message for the receiving application (service), unlike transport security where the client secures the message for the Target Queue.</span></span> <span data-ttu-id="f4984-112">따라서 메시지 보안을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 보호하는 경우에는 MSMQ가 활용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-112">As such, MSMQ plays no part when securing the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message using message security.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f4984-113"> 메시지 보안에서는 인증서 또는 Kerberos 프로토콜 등의 기존 보안 인프라와 통합되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지에 보안 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-113"> message security adds security headers to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message that integrate with existing security infrastructures, such as a certificate or the Kerberos protocol.</span></span>  
  
## <a name="message-credential-type"></a><span data-ttu-id="f4984-114">메시지 자격 증명 형식</span><span class="sxs-lookup"><span data-stu-id="f4984-114">Message Credential Type</span></span>  
 <span data-ttu-id="f4984-115">메시지 보안을 사용하면 서비스 및 클라이언트에서 서로 자격 증명을 제출하여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-115">Using message security, the service and client can present credentials to authenticate each another.</span></span> <span data-ttu-id="f4984-116"><xref:System.ServiceModel.NetMsmqBinding.Security%2A> 모드를 `Message` 또는 `Both`(즉, 전송 보안과 메시지 보안 모두 사용)로 설정하면 메시지 보안을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-116">You can select message security by setting the <xref:System.ServiceModel.NetMsmqBinding.Security%2A> mode to `Message` or `Both` (that is, use both transport security and message security).</span></span>  
  
 <span data-ttu-id="f4984-117">서비스에서 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 속성을 사용하여 클라이언트 인증에 사용되는 자격 증명을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-117">The service can use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to inspect the credential used to authenticate the client.</span></span> <span data-ttu-id="f4984-118">이 방법을 사용하여 서비스에서 구현하는 추가 인증 검사를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-118">This can also be used for further authorization checks that the service chooses to implement.</span></span>  
  
 <span data-ttu-id="f4984-119">이 절에서는 서로 다른 자격 증명 형식과 큐에서 그러한 형식을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-119">This section explains the different credential types and how to use them with queues.</span></span>  
  
### <a name="certificate"></a><span data-ttu-id="f4984-120">인증서</span><span class="sxs-lookup"><span data-stu-id="f4984-120">Certificate</span></span>  
 <span data-ttu-id="f4984-121">Certificate 자격 증명 형식에서는 X.509 인증서를 사용하여 서비스와 클라이언트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-121">The certificate credential type uses an X.509 certificate to identify the service and the client.</span></span>  
  
 <span data-ttu-id="f4984-122">일반적인 시나리오에서 클라이언트와 서비스에는 신뢰할 수 있는 인증 기관의 유효한 인증서가 발급됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-122">In a typical scenario, the client and the service are issued a valid certificate by a trusted certification authority.</span></span> <span data-ttu-id="f4984-123">그런 다음 연결이 설정되고, 클라이언트에서 서비스의 인증서를 통해 서비스의 유효성을 인증하여 서비스 신뢰 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-123">Then the connection is established, the client authenticates the validity of the service using the service's certificate to decide whether it can trust the service.</span></span> <span data-ttu-id="f4984-124">마찬가지로 서비스에서는 클라이언트의 인증서를 사용하여 클라이언트 신뢰를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-124">Similarly, the service uses the client's certificate to validate the client trust.</span></span>  
  
 <span data-ttu-id="f4984-125">연결되지 않은 쿼리의 성질을 생각하면, 클라이언트와 서비스는 동시에 온라인 상태가 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-125">Given the disconnected nature of queues, the client and the service may not be online at the same time.</span></span> <span data-ttu-id="f4984-126">따라서 클라이언트와 서비스는 out-of-band로 인증서를 교환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-126">As such, the client and service have to exchange certificates out-of-band.</span></span> <span data-ttu-id="f4984-127">특히 신뢰할 수 있는 저장소에 서비스의 인증서(인증 기관에 체인으로 연결 가능)를 가지고 있는 클라이언트는 올바른 서비스와 통신하고 있는 것을 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-127">In particular, the client, by virtue of holding the service's certificate (which can be chained to a certification authority) in its trusted store, must trust that it is communicating with the correct service.</span></span> <span data-ttu-id="f4984-128">클라이언트 인증의 경우 서비스에서는 메시지와 함께 첨부된 X.509 인증서를 저장소에 있는 인증서와 비교하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-128">For authenticating the client, the service uses the X.509 certificate attached with the message to matches it with the certificate in its store to verify the authenticity of the client.</span></span> <span data-ttu-id="f4984-129">인증서는 인증 기관에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-129">Again, the certificate must be chained to a certification authority.</span></span>  
  
 <span data-ttu-id="f4984-130">Windows를 실행하는 컴퓨터에서 인증서는 다양한 종류의 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-130">On a computer running Windows, certificates are held in several kinds of stores.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f4984-131"> 다른 저장소 참조 [인증서 저장소](http://go.microsoft.com/fwlink/?LinkId=87787)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-131"> the different stores, see [Certificate stores](http://go.microsoft.com/fwlink/?LinkId=87787).</span></span>  
  
### <a name="windows"></a><span data-ttu-id="f4984-132">Windows</span><span class="sxs-lookup"><span data-stu-id="f4984-132">Windows</span></span>  
 <span data-ttu-id="f4984-133">Windows 메시지 자격 증명 형식에는 Kerberos 프로토콜이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-133">Windows message credential type uses the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="f4984-134">Kerberos 프로토콜은 도메인에서 사용자를 인증하고 인증된 사용자가 도메인에 있는 다른 엔터티와 보안 컨텍스트를 구성할 수 있게 해 주는 보안 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-134">The Kerberos protocol is a security mechanism that authenticates users on a domain and allows the authenticated users to establish secure contexts with other entities on a domain.</span></span>  
  
 <span data-ttu-id="f4984-135">대기 중인 통신에 Kerberos 프로토콜을 사용하는 경우의 문제는 KDC(키 배포 센터)에서 배포하는 클라이언트 ID가 포함된 티켓의 수명이 비교적 짧다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-135">The problem with using the Kerberos protocol for queued communication is that the tickets that contain client identity that the Key Distribution Center (KDC) distributes are relatively short-lived.</span></span> <span data-ttu-id="f4984-136">A *수명* 티켓의 유효성을 나타내는 Kerberos 티켓에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-136">A *lifetime* is associated with the Kerberos ticket that indicates the validity of the ticket.</span></span> <span data-ttu-id="f4984-137">따라서 대기 시간이 긴 경우에는 클라이언트를 인증하는 서비스에서 토큰이 여전히 유효한지 확신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-137">As such, given high latency, you cannot be sure that the token is still valid for the service that authenticates the client.</span></span>  
  
 <span data-ttu-id="f4984-138">이 자격 증명 형식을 사용하는 경우 서비스는 SERVICE 계정에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-138">Note that when using this credential type, the service must be running under the SERVICE account.</span></span>  
  
 <span data-ttu-id="f4984-139">메시지 자격 증명을 선택할 때, 기본적으로 Kerberos 프로토콜이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-139">The Kerberos protocol is used by default when choosing message credential.</span></span> <span data-ttu-id="f4984-140">자세한 내용은 참조 [Kerberos 탐색, Windows 2000에서 분산 보안에 대 한 프로토콜](http://go.microsoft.com/fwlink/?LinkId=87790)합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-140">For more information, see [Exploring Kerberos, the Protocol for Distributed Security in Windows 2000](http://go.microsoft.com/fwlink/?LinkId=87790).</span></span>  
  
### <a name="username-password"></a><span data-ttu-id="f4984-141">Username Password</span><span class="sxs-lookup"><span data-stu-id="f4984-141">Username Password</span></span>  
 <span data-ttu-id="f4984-142">이 속성을 이용하면 메시지의 보안 헤더에 사용자 이름 암호를 사용하여 클라이언트를 서버에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-142">Using this property, the client can authenticate to the server using a username password in the security header of the message.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="f4984-143">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f4984-143">IssuedToken</span></span>  
 <span data-ttu-id="f4984-144">클라이언트에서는 보안 토큰 서비스를 사용하여 서비스에서 클라이언트에 사용할 메시지에 첨부되는 토큰을 발급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-144">The client can use the security token service to issue a token that can then be attached to the message for the service to authenticate the client.</span></span>  
  
## <a name="using-transport-and-message-security"></a><span data-ttu-id="f4984-145">전송 및 메시지 보안 사용</span><span class="sxs-lookup"><span data-stu-id="f4984-145">Using Transport and Message Security</span></span>  
 <span data-ttu-id="f4984-146">전송 보안과 메시지 보안을 모두 사용하는 경우에는 전송과 SOAP 메시지 수준 모두에서 메시지 보호에 사용되는 인증서가 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4984-146">When using both transport security and message security, the certificate used to secure the message both at the transport and the SOAP message level must be the same.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4984-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4984-147">See Also</span></span>  
 [<span data-ttu-id="f4984-148">전송 보안을 사용하여 메시지에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f4984-148">Securing Messages Using Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 [<span data-ttu-id="f4984-149">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="f4984-149">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
 [<span data-ttu-id="f4984-150">보안 개념</span><span class="sxs-lookup"><span data-stu-id="f4984-150">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 [<span data-ttu-id="f4984-151">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f4984-151">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
