---
title: 신뢰할 수 있는 세션 개요
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 1c5344c2804cf4c17fdc46a7fea5a4a360122b6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497080"
---
# <a name="reliable-sessions-overview"></a><span data-ttu-id="25ec3-102">신뢰할 수 있는 세션 개요</span><span class="sxs-lookup"><span data-stu-id="25ec3-102">Reliable Sessions Overview</span></span>

<span data-ttu-id="25ec3-103">Windows Communication Foundation (WCF) SOAP 신뢰할 수 있는 메시징은 SOAP 끝점 사이 종단 간 메시지 전송 안전성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-103">Windows Communication Foundation (WCF) SOAP reliable messaging provides end-to-end message transfer reliability between SOAP endpoints.</span></span> <span data-ttu-id="25ec3-104">전송 오류 및 SOAP 메시지 수준 오류를 극복하여 신뢰할 수 없는 네트워크에서 이를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-104">It does this on networks that are unreliable by overcoming transport failures and SOAP message-level failures.</span></span> <span data-ttu-id="25ec3-105">특히 SOAP 또는 전송 매개자를 통해 보낸 메시지에 대해 세션 기반, 단일 및 필요에 따라 순서가 지정된 배달을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-105">In particular, it provides session-based, single, and (optionally) ordered delivery for messages sent across SOAP or transport intermediaries.</span></span> <span data-ttu-id="25ec3-106">세션 기반 배달은 선택적 메시지 순서 지정 된 세션에서 메시지를 그룹화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-106">Session-based delivery provides for grouping messages in a session with optional ordering of the messages.</span></span>

<span data-ttu-id="25ec3-107">이 항목에서는 신뢰할 수 있는 세션을 어떻게 설명 및 사용 방법과 시기에 보안을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-107">This topic describes reliable sessions, how and when to use them, and how to secure them.</span></span>

## <a name="wcf-reliable-sessions"></a><span data-ttu-id="25ec3-108">WCF 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="25ec3-108">WCF reliable sessions</span></span>

<span data-ttu-id="25ec3-109">WCF 신뢰할 수 있는 세션은 Ws-reliablemessaging 프로토콜에 정의 된 대로 메시징 신뢰할 수 있는 soap는 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-109">WCF reliable sessions is an implementation of SOAP reliable messaging as defined by the WS-ReliableMessaging protocol.</span></span>

<span data-ttu-id="25ec3-110">WCF SOAP 신뢰할 수 있는 메시징은 메시징 끝점을 분리 하는 매개 자의 형식이 나 개수에 관계 없이 두 개의 끝점 사이 종단 간 신뢰할 수 있는 세션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-110">WCF SOAP reliable messaging provides an end-to-end reliable session between two endpoints, regardless of the number or type of intermediaries that separate the messaging endpoints.</span></span> <span data-ttu-id="25ec3-111">여기에 포함 됩니다 (예: HTTP 프록시) SOAP을 사용 하지 않는 전송 매개자 또는 끝점 간의 메시지 흐름에 필요한 SOAP (예를 들어 SOAP 기반 라우터나 브리지)를 사용 하는 매개자입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-111">This includes any transport intermediaries that don't use SOAP (for example, HTTP proxies) or intermediaries that use SOAP (for example, SOAP-based routers or bridges) that are required for messages to flow between the endpoints.</span></span> <span data-ttu-id="25ec3-112">신뢰할 수 있는 세션 채널은 지원 *대화형* 통신 이러한 채널에 의해 연결 된 서비스가 동시에 실행 하 고 짧은 대기 시간 조건, 즉,에서 메시지를 교환 하 고 처리할 내에서 상대적으로 짧은 있도록 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-112">A reliable session channel supports *interactive* communication so that the services connected by such a channel run concurrently and exchange and process messages under conditions of low latency, that is, within relatively short intervals of time.</span></span> <span data-ttu-id="25ec3-113">이 결합 서로 격리 안 함 이므로 이러한 구성 요소가 함께 진행 되거나 함께 실패를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-113">This coupling means that these components make progress together or fail together, so there's no isolation provided between them.</span></span>

<span data-ttu-id="25ec3-114">신뢰할 수 있는 세션에서는 다음 두 가지 유형의 오류를 마스킹합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-114">A reliable session masks two kinds of failures:</span></span>

- <span data-ttu-id="25ec3-115">손실되거나 중복된 메시지 및 보낸 순서와 다른 순서로 도착한 메시지를 포함하는 SOAP 메시지 수준 오류</span><span class="sxs-lookup"><span data-stu-id="25ec3-115">SOAP message-level failures, which includes lost or duplicated messages and messages that arrive in a different order from the order in which they were sent.</span></span>

- <span data-ttu-id="25ec3-116">전송 오류</span><span class="sxs-lookup"><span data-stu-id="25ec3-116">Transport failures.</span></span>

<span data-ttu-id="25ec3-117">신뢰할 수 있는 세션은 WS-ReliableMessaging 프로토콜 및 내장 메모리 전송 창을 구현하여 SOAP 메시지 수준 오류를 마스킹하고 전송 오류가 발생할 경우 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-117">A reliable session implements the WS-ReliableMessaging protocol and an in-memory transfer window to mask SOAP message-level failures and re-establishes connections in the case of transport failures.</span></span>

<span data-ttu-id="25ec3-118">신뢰할 수 있는 세션은 TCP가 IP 패킷에 대해 제공하는 SOAP 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-118">A reliable session provides for SOAP messages what TCP provides for IP packets.</span></span> <span data-ttu-id="25ec3-119">TCP 소켓 연결은 노드 간에 IP 패킷에 대한 단수형의 순서가 지정된 전송을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-119">A TCP socket connection provides a singular, in-order transfer of IP packets between nodes.</span></span> <span data-ttu-id="25ec3-120">신뢰할 수 있는 채널은 신뢰할 수 있는 전송과 동일한 유형을 제공하지만 다음과 같은 방법에서 TCP 소켓 안정성이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-120">The reliable channel provides the same type of reliable transfer, but it differs from TCP socket reliability in the following ways:</span></span>

- <span data-ttu-id="25ec3-121">안정성은 임의 크기 패킷(바이트)이 아닌 SOAP 메시지 수준에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-121">The reliability is at the SOAP message level, not for an arbitrarily sized packet of bytes.</span></span>

- <span data-ttu-id="25ec3-122">안정성은 TCP 통한 전송에 대 한 뿐 아니라의 전송 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-122">The reliability is transport-neutral, not just for transfer over TCP.</span></span>

- <span data-ttu-id="25ec3-123">안정성 특정 전송 세션 (예: TCP 연결이 제공 세션)에 연결 되지 및 צ ְ ײ 여러 전송 세션 동시에 또는 순차적으로 신뢰할 수 있는 세션의 수명 동안 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-123">The reliability isn't tied to a particular transport session (for example, the session a TCP connection provides) and can use multiple transport sessions concurrently or sequentially over the lifetime of the reliable session.</span></span>

- <span data-ttu-id="25ec3-124">신뢰할 수 있는 세션은 SOAP 끝점 간의 연결에 필요한 전송 연결 수에 관계없이 발신자 및 수신자 SOAP 끝점 사이에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-124">The reliable session is between the sender and receiver SOAP endpoints, regardless of the number of transport connections required for connectivity between them.</span></span> <span data-ttu-id="25ec3-125">즉, TCP 안정성은 전송 연결 끝나는, 신뢰할 수 있는 세션은 종단 간 안정성을 제공 하지만 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-125">In short, TCP reliability ends where the transport connection ends, while a reliable session provides end-to-end reliability.</span></span>

## <a name="reliable-sessions-and-bindings"></a><span data-ttu-id="25ec3-126">신뢰할 수 있는 세션 및 바인딩</span><span class="sxs-lookup"><span data-stu-id="25ec3-126">Reliable sessions and bindings</span></span>

<span data-ttu-id="25ec3-127">앞서 언급 했 듯이 신뢰할 수 있는 세션은 전송 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-127">As mentioned earlier, a reliable session is transport neutral.</span></span> <span data-ttu-id="25ec3-128">또한, 요청-회신 또는 이중과 같은 여러 메시지 교환 패턴을 통해 신뢰할 수 있는 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-128">Also, you can establish a reliable session over many message exchange patterns, such as request-reply or duplex.</span></span> <span data-ttu-id="25ec3-129">WCF 신뢰할 수 있는 세션 바인딩 집합의 속성으로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-129">A WCF reliable session is exposed as a property of a set of bindings.</span></span>

<span data-ttu-id="25ec3-130">사용 하는 끝점에서 신뢰할 수 있는 세션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-130">Use a reliable session on endpoints that use:</span></span>

- <span data-ttu-id="25ec3-131">HTTP 기반 전송 표준 바인딩:</span><span class="sxs-lookup"><span data-stu-id="25ec3-131">HTTP-based transport standard bindings:</span></span>

  - <span data-ttu-id="25ec3-132">`WsHttpBinding` 및 요청-회신 또는 단방향 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-132">`WsHttpBinding` and expose request-reply or one-way contracts.</span></span>

  - <span data-ttu-id="25ec3-133">요청-회신 또는 간단한 단방향 서비스 계약을 통해 신뢰할 수 있는 세션을 사용할 때</span><span class="sxs-lookup"><span data-stu-id="25ec3-133">When using reliable session over a request-reply or simple one-way service contract.</span></span>

  - <span data-ttu-id="25ec3-134">`WsDualHttpBinding` 및 이중, 요청-회신 또는 단방향 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-134">`WsDualHttpBinding` and expose duplex, request-reply, or one-way contracts.</span></span>

  - <span data-ttu-id="25ec3-135">`WsFederationHttpBinding` 및 요청-회신 또는 단방향 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-135">`WsFederationHttpBinding` and expose request-reply or one-way contracts.</span></span>

- <span data-ttu-id="25ec3-136">TCP 기반 전송 표준 바인딩:</span><span class="sxs-lookup"><span data-stu-id="25ec3-136">TCP-based transport standard bindings:</span></span>

  - <span data-ttu-id="25ec3-137">`NetTcpBinding` 및 이중, 요청-회신 또는 단방향 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-137">`NetTcpBinding` and expose duplex, request reply, or one-way contracts.</span></span>

<span data-ttu-id="25ec3-138">에 다른 모든 바인딩에서 신뢰할 수 있는 세션을 사용 하 여 HTTPS와 같은 사용자 지정 바인딩을 만들어야만 (문제에 대 한 자세한 내용은 참조 <a href="#reliable-sessions-and-security">신뢰할 수 있는 세션 및 보안</a>) 또는 명명된 된 파이프 바인딩의 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-138">Use a reliable session on any other bindings by creating a custom binding, such as HTTPS (for more information about issues, see <a href="#reliable-sessions-and-security">Reliable sessions and security</a>) or a named pipe binding.</span></span>

<span data-ttu-id="25ec3-139">다른 기본 채널 형식에 신뢰할 수 있는 세션 누적 할 수 있습니다 하 고 결과적으로 신뢰할 수 있는 세션 채널 모양이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-139">You can stack a reliable session on different underlying channel types, and the resulting reliable session channel shape varies.</span></span> <span data-ttu-id="25ec3-140">클라이언트와 서버 모두에서 지원 되는 신뢰할 수 있는 세션 채널의 유형을 사용 하는 기본 채널 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-140">On both the client and the server, the type of reliable session channel supported depends on the type of underlying channel used.</span></span> <span data-ttu-id="25ec3-141">다음 표에서는 기본 채널 형식의 기능으로서 클라이언트에서 지원되는 세션 채널 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-141">The following table lists the types of session channels supported on the client as a function of the underlying channel type.</span></span>

| <span data-ttu-id="25ec3-142">지원 되는 신뢰할 수 있는 세션 채널 형식입니다.&#8224;</span><span class="sxs-lookup"><span data-stu-id="25ec3-142">Supported reliable session channel types&#8224;</span></span> | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | <span data-ttu-id="25ec3-143">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-143">Yes</span></span>               | <span data-ttu-id="25ec3-144">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-144">Yes</span></span>                      | <span data-ttu-id="25ec3-145">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-145">Yes</span></span>              | <span data-ttu-id="25ec3-146">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-146">Yes</span></span>                     |
| `IRequestSessionChannel`                        | <span data-ttu-id="25ec3-147">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-147">Yes</span></span>               | <span data-ttu-id="25ec3-148">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-148">Yes</span></span>                      | <span data-ttu-id="25ec3-149">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-149">No</span></span>               | <span data-ttu-id="25ec3-150">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-150">No</span></span>                      |
| `IDuplexSessionChannel`                         | <span data-ttu-id="25ec3-151">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-151">No</span></span>                | <span data-ttu-id="25ec3-152">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-152">No</span></span>                       | <span data-ttu-id="25ec3-153">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-153">Yes</span></span>              | <span data-ttu-id="25ec3-154">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-154">Yes</span></span>                     |

<span data-ttu-id="25ec3-155">&#8224;지원 되는 채널 형식은 원본에 대해 사용할 수 있는 값 `TChannel` 매개 변수 값으로 전달 되는 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> 메서드.</span><span class="sxs-lookup"><span data-stu-id="25ec3-155">&#8224;The supported channel types are the values available for the generic `TChannel` parameter value that is passed into the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> method.</span></span>

<span data-ttu-id="25ec3-156">다음 표에서는 기본 채널 형식의 기능으로서 서버에서 지원되는 세션 채널 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-156">The following table lists the types of session channels supported on the server as a function of the underlying channel type.</span></span>

| <span data-ttu-id="25ec3-157">지원 되는 신뢰할 수 있는 세션 채널 형식입니다.&#8225;</span><span class="sxs-lookup"><span data-stu-id="25ec3-157">Supported reliable session channel types&#8225;</span></span> | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | <span data-ttu-id="25ec3-158">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-158">Yes</span></span>             | <span data-ttu-id="25ec3-159">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-159">Yes</span></span>                    | <span data-ttu-id="25ec3-160">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-160">Yes</span></span>              | <span data-ttu-id="25ec3-161">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-161">Yes</span></span>                     |
| `IReplySessionChannel`                          | <span data-ttu-id="25ec3-162">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-162">Yes</span></span>             | <span data-ttu-id="25ec3-163">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-163">Yes</span></span>                    | <span data-ttu-id="25ec3-164">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-164">No</span></span>               | <span data-ttu-id="25ec3-165">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-165">No</span></span>                      |
| `IDuplexSessionChannel`                         | <span data-ttu-id="25ec3-166">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-166">No</span></span>              | <span data-ttu-id="25ec3-167">아니요</span><span class="sxs-lookup"><span data-stu-id="25ec3-167">No</span></span>                     | <span data-ttu-id="25ec3-168">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-168">Yes</span></span>              | <span data-ttu-id="25ec3-169">예</span><span class="sxs-lookup"><span data-stu-id="25ec3-169">Yes</span></span>                     |

<span data-ttu-id="25ec3-170">&#8225;지원 되는 채널 형식은 원본에 대해 사용할 수 있는 값 `TChannel` 매개 변수 값으로 전달 되는 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> 메서드.</span><span class="sxs-lookup"><span data-stu-id="25ec3-170">&#8225;The supported channel types are the values available for the generic `TChannel` parameter value that is passed into the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> method.</span></span>

## <a name="reliable-sessions-and-security"></a><span data-ttu-id="25ec3-171">신뢰할 수 있는 세션 및 보안</span><span class="sxs-lookup"><span data-stu-id="25ec3-171">Reliable sessions and security</span></span>

<span data-ttu-id="25ec3-172">신뢰할 수 있는 세션을 보안 하는 것이 중요 통신 당사자 (서비스 및 클라이언트)에 인증 되 고 세션에서 교환 되는 메시지 변조 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-172">Securing a reliable session is important to ensure that the communicating parties (service and client) are authenticated and that the messages exchanged in the session aren't tampered with.</span></span> <span data-ttu-id="25ec3-173">또한이 각 개별 신뢰할 수 있는 세션의 무결성을 보장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-173">Furthermore, it's important to ensure the integrity of each individual reliable session.</span></span> <span data-ttu-id="25ec3-174">신뢰할 수 있는 세션에 표시 하 고 보안 세션 채널에 의해 관리 되는 보안 컨텍스트에 바인딩하여 보안을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-174">A reliable session is secured by binding it to a security context that's represented and managed by a security session channel.</span></span> <span data-ttu-id="25ec3-175">보안 채널은 보안 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-175">The security channel provides a security session.</span></span> <span data-ttu-id="25ec3-176">세션 설정 동안 교환된 보안 토큰은 신뢰할 수 있는 세션의 메시지 보안을 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-176">Security tokens exchanged during the session establishment are then used to secure the messages in the reliable session.</span></span>

<span data-ttu-id="25ec3-177">신뢰할 수 있는 세션이 통해 경우 TCP 세션이 신뢰할 수 있는 세션에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-177">When a reliable session is over TCP-S, the TCP session is tied to the reliable session.</span></span> <span data-ttu-id="25ec3-178">따라서 전송 보안을 보안 신뢰할 수 있는 세션에 연결 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-178">Therefore, transport security ensures that security is also tied to the reliable session.</span></span> <span data-ttu-id="25ec3-179">이 경우 연결 재설정이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-179">In this case, connection re-establishment is turned off.</span></span>

<span data-ttu-id="25ec3-180">HTTPS를 사용하는 경우에만 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-180">The only exception is when using HTTPS.</span></span> <span data-ttu-id="25ec3-181">(SECURE Sockets Layer) 세션은 신뢰할 수 있는 세션에 바인딩되어 있지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-181">The Secure Sockets Layer (SSL) session isn't bound to the reliable session.</span></span> <span data-ttu-id="25ec3-182">이 인해 위협이 보안 컨텍스트 (SSL 세션)을 공유 하는 세션; 서로 간에 보호 되지 않습니다 때문에 이 하거나 응용 프로그램에 따라 실제 위협이 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-182">This imposes a threat because sessions that are sharing a security context (the SSL session) aren't protected from each other; this might or might not be a real threat depending on the application.</span></span>

## <a name="using-reliable-sessions"></a><span data-ttu-id="25ec3-183">신뢰할 수 있는 세션을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="25ec3-183">Using reliable sessions</span></span>

<span data-ttu-id="25ec3-184">WCF 신뢰할 수 있는 세션을 사용 하려면 신뢰할 수 있는 세션을 지 원하는 바인딩으로 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-184">To use WCF reliable sessions, create an endpoint with a binding that supports a reliable session.</span></span> <span data-ttu-id="25ec3-185">WCF 신뢰할 수 있는 세션을 제공 하는 시스템 제공 바인딩 중 하나 사용 하 여 사용할 수 없거나이 작업을 수행 하는 사용자 고유의 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-185">Use one of the system-provided bindings that WCF provides with the reliable session enabled or create your own custom binding that does this.</span></span>

<span data-ttu-id="25ec3-186">기본적으로 신뢰할 수 있는 세션을 지원하고 사용하도록 설정하는 시스템 정의 바인딩은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-186">The system-defined bindings that support and enable a reliable session by default include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

<span data-ttu-id="25ec3-187">옵션으로 신뢰할 수 있는 세션을 지원 하지만 기본적으로 사용 하지 않는 시스템 제공 바인딩은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-187">The system-provided bindings that support a reliable session as an option but don't enable one by default include:</span></span>

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

<span data-ttu-id="25ec3-188">사용자 지정 바인딩을 만드는 방법의 예제를 보려면 [하는 방법: HTTPS로 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-188">For an example of how to create a custom binding, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

<span data-ttu-id="25ec3-189">신뢰할 수 있는 세션을 지 원하는 WCF 바인딩에의 논의 알려면 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-189">For a discussion of WCF bindings that support reliable sessions, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>

## <a name="when-to-use-reliable-sessions"></a><span data-ttu-id="25ec3-190">신뢰할 수 있는 세션을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="25ec3-190">When to use reliable sessions</span></span>

<span data-ttu-id="25ec3-191">응용 프로그램에서 신뢰할 수 있는 세션을 사용 하는 경우를 이해 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-191">It's important to understand when to use reliable sessions in your application.</span></span> <span data-ttu-id="25ec3-192">WCF 활성화 되어 작동 동시에 끝점 간에 신뢰할 수 있는 세션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-192">WCF supports reliable sessions between endpoints that are active and alive at the same time.</span></span> <span data-ttu-id="25ec3-193">응용 프로그램 끝점 중 하나에 필요한 시간 동안 사용할 수 없게 다음 큐를 사용 하 여 안정성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-193">If your application requires one of the endpoints be unavailable for a duration of time, then use queues to achieve reliability.</span></span>

<span data-ttu-id="25ec3-194">이 시나리오에서 TCP를 통해 연결 된 두 개의 끝점을 필요한 경우 TCP 신뢰할 수 있는 메시지 교환을 제공 하기에 충분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-194">If the scenario requires two endpoints connected over TCP, then TCP may be sufficient to provide reliable message exchanges.</span></span> <span data-ttu-id="25ec3-195">TCP를 사용 하면 신뢰할 수 있는 세션을 사용할 필요가 없습니다 되지만 패킷이 순서와 한 번만 도착 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-195">Although, it isn't necessary to use a reliable session, since TCP ensures that the packets arrive in order and only once.</span></span>

<span data-ttu-id="25ec3-196">시나리오는 다음과 같은 특징이 있으면, 다음 심각 하 게 고려해 야 신뢰할 수 있는 세션을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ec3-196">If your scenario has any of the following characteristics, then you must seriously consider using a reliable session.</span></span>

- <span data-ttu-id="25ec3-197">SOAP 라우터와 같은 SOAP 매개자</span><span class="sxs-lookup"><span data-stu-id="25ec3-197">SOAP intermediaries, such as SOAP routers</span></span>

- <span data-ttu-id="25ec3-198">프록시 매개자 또는 전송 브리지</span><span class="sxs-lookup"><span data-stu-id="25ec3-198">Proxy intermediaries or transport bridges</span></span>

- <span data-ttu-id="25ec3-199">일시적인 연결</span><span class="sxs-lookup"><span data-stu-id="25ec3-199">Intermittent connectivity</span></span>

- <span data-ttu-id="25ec3-200">HTTP 통한 세션</span><span class="sxs-lookup"><span data-stu-id="25ec3-200">Sessions over HTTP</span></span>

## <a name="see-also"></a><span data-ttu-id="25ec3-201">참고자료</span><span class="sxs-lookup"><span data-stu-id="25ec3-201">See also</span></span>

<span data-ttu-id="25ec3-202">[바인딩을 사용 하 여 서비스 및 클라이언트 구성](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md) </span><span class="sxs-lookup"><span data-stu-id="25ec3-202">[Using Bindings to Configure Services and Clients](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md) </span></span>  
[<span data-ttu-id="25ec3-203">WS 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="25ec3-203">WS Reliable Session</span></span>](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
