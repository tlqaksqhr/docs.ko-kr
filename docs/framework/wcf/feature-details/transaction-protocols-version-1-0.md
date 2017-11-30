---
title: "트랜잭션 프로토콜 버전 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95bf16a4e243d82b9b8fe83b306284335ae0bd16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="b0a59-102">트랜잭션 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="b0a59-102">Transaction Protocols version 1.0</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="b0a59-103"> 버전 1은 WS-Atomic Transaction 및 WS-Coordination 프로토콜의 버전 1.0을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-103"> version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b0a59-104">버전 1.1에서 참조 [트랜잭션 프로토콜](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-104"> version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="b0a59-105">사양/문서</span><span class="sxs-lookup"><span data-stu-id="b0a59-105">Specification/Document</span></span>|<span data-ttu-id="b0a59-106">링크</span><span class="sxs-lookup"><span data-stu-id="b0a59-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b0a59-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="b0a59-107">WS-Coordination</span></span>|<span data-ttu-id="b0a59-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span><span class="sxs-lookup"><span data-stu-id="b0a59-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span></span>|  
|<span data-ttu-id="b0a59-109">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="b0a59-109">WS-AtomicTransaction</span></span>|<span data-ttu-id="b0a59-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span><span class="sxs-lookup"><span data-stu-id="b0a59-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span></span>|  
  
 <span data-ttu-id="b0a59-111">이러한 프로토콜 사양에서의 상호 운용성은 응용 프로그램 간 및 트랜잭션 관리자 간 이렇게 두 가지 수준에서 필요합니다(다음 그림 참조)</span><span class="sxs-lookup"><span data-stu-id="b0a59-111">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="b0a59-112">사양은 두 가지 수준의 상호 운용성을 위한 메시지 형식 및 메시지 교환을 상세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-112">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="b0a59-113">응용 프로그램 간의 교환을 위한 보안, 안정성 및 인코딩은 일반적인 응용 프로그램 교환을 위해 수행되는 것과 같은 방식으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-113">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="b0a59-114">그러나 트랜잭션 관리자 간의 상호 운용성을 위해서는 특정한 바인딩에 대한 동의가 필요합니다. 이러한 부분은 일반적으로 사용자가 구성하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-114">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="b0a59-115">이 항목에서는 WS-AT(WS-Atomic Transaction) 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-115">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="b0a59-116">이 문서에서 설명하는 방식은 IBM, IONA, Sun Microsystems 등에서 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-116">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="b0a59-117">다음 그림에서는 두 개의 트랜잭션 관리자(트랜잭션 관리자 1, 트랜잭션 관리자 2)와 두 개의 응용 프로그램(응용 프로그램 1, 응용 프로그램 2) 간의 상호 운용성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-117">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2.</span></span>  
  
 <span data-ttu-id="b0a59-118">![트랜잭션 프로토콜](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "했지만")</span><span class="sxs-lookup"><span data-stu-id="b0a59-118">![Transaction Protocols](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")</span></span>  
  
 <span data-ttu-id="b0a59-119">한 명의 개시자(I)와 한 명의 참가자(P)가 있는 일반적인 WS-Coordination/WS-Atomic Transaction 시나리오를 예로 들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-119">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="b0a59-120">개시자와 참가자는 둘 다 트랜잭션 관리자(각각 ITM과 PTM)를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-120">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="b0a59-121">이 항목에서는 2단계 커밋을 2PC라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-121">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0a59-122">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="b0a59-122">1. CreateCoordinationContext</span></span>|<span data-ttu-id="b0a59-123">12. 응용 프로그램 메시지 응답</span><span class="sxs-lookup"><span data-stu-id="b0a59-123">12. Application Message Response</span></span>|  
|<span data-ttu-id="b0a59-124">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-124">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="b0a59-125">13. 커밋(완료)</span><span class="sxs-lookup"><span data-stu-id="b0a59-125">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="b0a59-126">3. 등록(완료)</span><span class="sxs-lookup"><span data-stu-id="b0a59-126">3. Register (Completion)</span></span>|<span data-ttu-id="b0a59-127">14. 준비(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-127">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="b0a59-128">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-128">4. RegisterResponse</span></span>|<span data-ttu-id="b0a59-129">15. 준비(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-129">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="b0a59-130">5. 응용 프로그램 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-130">5. Application Message</span></span>|<span data-ttu-id="b0a59-131">16. 준비됨(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-131">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="b0a59-132">6. CreateCoordinationContext와 Context</span><span class="sxs-lookup"><span data-stu-id="b0a59-132">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="b0a59-133">17. 준비됨(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-133">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="b0a59-134">7. 등록(지속적)</span><span class="sxs-lookup"><span data-stu-id="b0a59-134">7. Register (Durable)</span></span>|<span data-ttu-id="b0a59-135">18. 커밋됨(완료)</span><span class="sxs-lookup"><span data-stu-id="b0a59-135">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="b0a59-136">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-136">8. RegisterResponse</span></span>|<span data-ttu-id="b0a59-137">19. 커밋(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-137">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="b0a59-138">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-138">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="b0a59-139">20. 커밋(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-139">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="b0a59-140">10. 등록(지속적)</span><span class="sxs-lookup"><span data-stu-id="b0a59-140">10. Register (Durable)</span></span>|<span data-ttu-id="b0a59-141">21. 커밋됨(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-141">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="b0a59-142">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-142">11. RegisterResponse</span></span>|<span data-ttu-id="b0a59-143">22. 커밋됨(2PC)</span><span class="sxs-lookup"><span data-stu-id="b0a59-143">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="b0a59-144">이 문서에서는 WS-AtomicTransaction 사양과 보안의 조합에 대해 설명하고, 트랜잭션 관리자 간 통신을 위해 사용하는 보안이 설정된 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-144">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="b0a59-145">이 문서에서 설명하는 방식은 WS-AT 및 WS-Coordination의 다른 구현과 함께 성공적으로 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-145">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="b0a59-146">그림과 표에서는 보안의 관점에서 메시지에 대한 4가지 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-146">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
-   <span data-ttu-id="b0a59-147">활성화 메시지(CreateCoordinationContext 및 CreateCoordinationContextResponse)</span><span class="sxs-lookup"><span data-stu-id="b0a59-147">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
-   <span data-ttu-id="b0a59-148">등록 메시지(Register 및 RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="b0a59-148">Registration messages (Register and RegisterResponse)</span></span>  
  
-   <span data-ttu-id="b0a59-149">프로토콜 메시지(준비, 롤백, 커밋, 중단 등)</span><span class="sxs-lookup"><span data-stu-id="b0a59-149">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
-   <span data-ttu-id="b0a59-150">응용 프로그램 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-150">Application messages.</span></span>  
  
 <span data-ttu-id="b0a59-151">처음 세 개의 메시지 클래스는 트랜잭션 관리자 메시지로 간주되며, 해당 바인딩 구성은 이 항목의 뒷부분에 있는 "응용 프로그램 메시지 교환"에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-151">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="b0a59-152">네 번째 메시지는 응용 프로그램 간 메시지이며, 이 항목의 뒷부분에 있는 "메시지 예제" 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-152">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="b0a59-153">이 단원에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이러한 클래스 각각에 대해 사용하는 프로토콜 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-153">This section describes the protocol bindings used for each of these classes by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="b0a59-154">다음 XML 네임스페이스 및 관련 접두사는 이 문서 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-154">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="b0a59-155">접두사</span><span class="sxs-lookup"><span data-stu-id="b0a59-155">Prefix</span></span>|<span data-ttu-id="b0a59-156">네임스페이스 URI</span><span class="sxs-lookup"><span data-stu-id="b0a59-156">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="b0a59-157">s11</span><span class="sxs-lookup"><span data-stu-id="b0a59-157">s11</span></span>|<span data-ttu-id="b0a59-158">http://schemas.xmlsoap.org/soap/envelope</span><span class="sxs-lookup"><span data-stu-id="b0a59-158">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="b0a59-159">wsa</span><span class="sxs-lookup"><span data-stu-id="b0a59-159">wsa</span></span>|<span data-ttu-id="b0a59-160">http://www.w3.org/2004/08/addressing</span><span class="sxs-lookup"><span data-stu-id="b0a59-160">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="b0a59-161">wscoor</span><span class="sxs-lookup"><span data-stu-id="b0a59-161">wscoor</span></span>|<span data-ttu-id="b0a59-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span><span class="sxs-lookup"><span data-stu-id="b0a59-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span></span>|  
|<span data-ttu-id="b0a59-163">wsat</span><span class="sxs-lookup"><span data-stu-id="b0a59-163">wsat</span></span>|<span data-ttu-id="b0a59-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span><span class="sxs-lookup"><span data-stu-id="b0a59-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span></span>|  
|<span data-ttu-id="b0a59-165">t</span><span class="sxs-lookup"><span data-stu-id="b0a59-165">t</span></span>|<span data-ttu-id="b0a59-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span><span class="sxs-lookup"><span data-stu-id="b0a59-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span></span>|  
|<span data-ttu-id="b0a59-167">o</span><span class="sxs-lookup"><span data-stu-id="b0a59-167">o</span></span>|<span data-ttu-id="b0a59-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="b0a59-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="b0a59-169">xsd</span><span class="sxs-lookup"><span data-stu-id="b0a59-169">xsd</span></span>|<span data-ttu-id="b0a59-170">http://www.w3.org/2001/XMLSchema</span><span class="sxs-lookup"><span data-stu-id="b0a59-170">http://www.w3.org/2001/XMLSchema</span></span>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="b0a59-171">트랜잭션 관리자 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0a59-171">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="b0a59-172">R1001: 트랜잭션 관리자는 WS-Atomic Transaction 및 WS-Coordination 메시지 교환을 위해 SOAP 1.1과 WS-Addressing 2004/08을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-172">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="b0a59-173">응용 프로그램 메시지는 이러한 바인딩에 제한되지 않으며, 이에 대해서는 나중에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-173">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="b0a59-174">트랜잭션 관리자 HTTPS 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0a59-174">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="b0a59-175">트랜잭션 관리자 HTTPS 바인딩은 전송 보안에만 전적으로 의존하여 보안을 수행하며, 트랜잭션 트리에 있는 각 발신자-수신자 쌍 간의 신뢰를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-175">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="b0a59-176">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-176">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="b0a59-177">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-177">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="b0a59-178">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-178">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
-   <span data-ttu-id="b0a59-179">R1111: 연결을 통해 표시되는 X.509 인증서에는 원래 컴퓨터의 FQDN(정규화된 도메인 이름)과 일치하는 주체 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-179">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
-   <span data-ttu-id="b0a59-180">B1112: DNS는 X.509 주체 이름을 확인한 시스템에서 각 발신자-수신자 쌍 간에 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-180">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="b0a59-181">바인딩 구성 활성화 및 등록</span><span class="sxs-lookup"><span data-stu-id="b0a59-181">Activation and Registration Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b0a59-182">에는 HTTPS를 통한 상관 관계와 함께 요청/회신 이중 바인딩이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-182"> requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="b0a59-183">요청/회신 메시지 교환 패턴의 상관 관계 및 설명에 대한 자세한 내용은 8단원 WS-Atomic Transaction을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0a59-183">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="b0a59-184">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-184">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b0a59-185">에서는 HTTPS를 통해 단방향(데이터그램) 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-185"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="b0a59-186">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-186">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="b0a59-187">B2131: 구현에서 지원 해야 `wsa:ReferenceParameters` 의 상관 관계를 달성 하기 위해 Ws-addressing에서 설명 된 대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 2PC 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-187">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="b0a59-188">트랜잭션 관리자가 혼합된 보안 바인딩</span><span class="sxs-lookup"><span data-stu-id="b0a59-188">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="b0a59-189">이 바인딩 id 설정 목적 Ws-coordination 발급 토큰 모델과 함께 사용 하 여 전송 보안을 하는 대체 (혼합된 모드).</span><span class="sxs-lookup"><span data-stu-id="b0a59-189">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="b0a59-190">두 바인딩 간에 다른 요소는 활성화와 등록뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-190">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="b0a59-191">HTTPS 전송 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-191">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="b0a59-192">X.509 인증서는 트랜잭션 관리자 ID를 설정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-192">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="b0a59-193">클라이언트/서버 인증이 필요하며, 클라이언트/서버 권한 부여는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-193">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="b0a59-194">활성화 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-194">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="b0a59-195">활성화 메시지는 일반적으로 응용 프로그램과 해당 로컬 트랜잭션 관리자 간에 발생하기 때문에 대개 상호 운용성에 관여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-195">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="b0a59-196">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이중 HTTPS 바인딩을 사용 하 여 (에 설명 된 [메시징 프로토콜](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) 활성화 메시지에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-196">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="b0a59-197">요청 및 회신 메시지는 WS-Addressing 2004/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-197">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="b0a59-198">8단원 WS-Atomic Transaction 사양에서는 상관 관계 및 메시지 교환 패턴에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-198">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
-   <span data-ttu-id="b0a59-199">R1222: 코디네이터는 `CreateCoordinationContext`를 수신하는 즉시 연관된 비밀 `SecurityContextToken`로 `STx`을 발급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-199">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="b0a59-200">이 토큰은 WS-Trust 사양을 따르는 `t:IssuedTokens` 헤더의 내부로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-200">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
-   <span data-ttu-id="b0a59-201">R1223: 기존 코디네이션 컨텍스트 내에서 활성화가 수행되면 기존 컨텍스트와 연관된 `t:IssuedTokens`과 함께 `SecurityContextToken` 헤더가 `CreateCoordinationContext` 메시지에서 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-201">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="b0a59-202">새 `t:IssuedTokens` 에 나가는 연결에 대 한 헤더를 생성 해야 `wscoor:CreateCoordinationContextResponse` 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-202">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="b0a59-203">등록 메시지 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-203">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="b0a59-204">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이중 HTTPS 바인딩을 사용 하 여 (에 설명 된 [메시징 프로토콜](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="b0a59-204">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="b0a59-205">요청 및 회신 메시지는 WS-Addressing 2004/08을 사용하여 상호 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-205">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="b0a59-206">8단원 WS-AtomicTransaction에서는 메시지 교환 패턴의 상관 관계 및 설명에 대해 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-206">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="b0a59-207">R1232: 나가는 `wscoor:Register` 메시지를 사용 해야 합니다는 `IssuedTokenOverTransport` 에 설명 된 인증 모드 [보안 프로토콜](../../../../docs/framework/wcf/feature-details/security-protocols.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-207">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="b0a59-208">`wsse:Timestamp` 요소를 사용 하 여 서명 해야 합니다는 `SecurityContextToken``STx` 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-208">The `wsse:Timestamp` element must be signed using the `SecurityContextToken``STx` issued.</span></span> <span data-ttu-id="b0a59-209">이 서명은 특정 트랜잭션과 연관된 토큰을 소유했음을 나타내며, 트랜잭션에 등록된 참가자를 인증하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-209">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="b0a59-210">RegistrationResponse 메시지는 HTTPS를 통해 다시 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-210">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="b0a59-211">2PC 프로토콜 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b0a59-211">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b0a59-212">에서는 HTTPS를 통해 단방향(데이터그램) 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-212"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="b0a59-213">메시지 간의 상관 관계는 구현 정보로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-213">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="b0a59-214">B2131: 구현에서 지원 해야 `wsa:ReferenceParameters` 의 상관 관계를 달성 하기 위해 Ws-addressing에서 설명 된 대로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 2PC 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-214">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="b0a59-215">응용 프로그램 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="b0a59-215">Application Message Exchange</span></span>  
 <span data-ttu-id="b0a59-216">바인딩이 다음 보안 요구 사항을 만족하는 경우, 응용 프로그램에서는 응용 프로그램 간 메시지에 대해 특정 바인딩을 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-216">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
-   <span data-ttu-id="b0a59-217">R2001: 응용 프로그램 간 메시지는 메시지의 헤더에서 `t:IssuedTokens`와 함께 `CoordinationContext` 헤더를 이동시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-217">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
-   <span data-ttu-id="b0a59-218">R2002: `t:IssuedToken`의 무결성 및 기밀성이 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-218">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="b0a59-219">`CoordinationContext` 헤더에는 `wscoor:Identifier`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-219">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="b0a59-220">`xsd:AnyURI`를 정의하면 절대 URI와 상대 URI를 모두 사용할 수 있지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 절대 URI인 `wscoor:Identifiers`만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-220">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="b0a59-221">`wscoor:Identifier`의 `wscoor:CoordinationContext`가 상대 URI이면 트랜잭션 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-221">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="b0a59-222">메시지 예제</span><span class="sxs-lookup"><span data-stu-id="b0a59-222">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="b0a59-223">CreateCoordinationContext 요청/응답 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-223">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="b0a59-224">다음 메시지는 요청/응답 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-224">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="b0a59-225">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="b0a59-225">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="b0a59-226">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="b0a59-226">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="b0a59-227">등록 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-227">Registration Messages</span></span>  
 <span data-ttu-id="b0a59-228">다음 메시지는 등록 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-228">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="b0a59-229">레지스터</span><span class="sxs-lookup"><span data-stu-id="b0a59-229">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="b0a59-230">응답 등록</span><span class="sxs-lookup"><span data-stu-id="b0a59-230">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="b0a59-231">2단계 커밋 프로토콜 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-231">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="b0a59-232">다음 메시지는 2PC(2단계 커밋) 프로토콜과 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-232">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="b0a59-233">커밋</span><span class="sxs-lookup"><span data-stu-id="b0a59-233">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="b0a59-234">응용 프로그램 메시지</span><span class="sxs-lookup"><span data-stu-id="b0a59-234">Application Messages</span></span>  
 <span data-ttu-id="b0a59-235">다음 메시지는 응용 프로그램 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a59-235">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="b0a59-236">응용 프로그램 메시지-요청</span><span class="sxs-lookup"><span data-stu-id="b0a59-236">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
