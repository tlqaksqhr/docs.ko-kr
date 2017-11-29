---
title: "보안 프로토콜 버전 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f40c79ad1a6eedc2b1de4dffa9de5b48aeb8e6f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="dd734-102">보안 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="dd734-103">Web Services Security 프로토콜은 모든 기존 엔터프라이즈 메시징 보안 요구 사항을 포함하는 Web Services Security 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="dd734-104">이 단원에서는 다음 Web Services Security 프로토콜에 대한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 버전 1.0 세부 정보(<xref:System.ServiceModel.Channels.SecurityBindingElement>에서 구현)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-104">This section describes the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="dd734-105">사양/문서</span><span class="sxs-lookup"><span data-stu-id="dd734-105">Specification/Document</span></span>|<span data-ttu-id="dd734-106">링크</span><span class="sxs-lookup"><span data-stu-id="dd734-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="dd734-107">WSS: SOAP Message Security 1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-107">WSS: SOAP Message Security 1.0</span></span>|<span data-ttu-id="dd734-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span></span>|  
|<span data-ttu-id="dd734-109">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-109">WSS: Username Token Profile 1.0</span></span>|<span data-ttu-id="dd734-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="dd734-111">WSS: X509 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-111">WSS: X509 Token Profile 1.0</span></span>|<span data-ttu-id="dd734-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="dd734-113">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-113">WSS: SAML 1.1 Token Profile 1.0</span></span>|<span data-ttu-id="dd734-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="dd734-115">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-115">WSS: SOAP Message Security 1.1</span></span>|<span data-ttu-id="dd734-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span></span>|  
|<span data-ttu-id="dd734-117">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-117">WSS Username Token Profile 1.1</span></span>|<span data-ttu-id="dd734-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="dd734-119">WSS: X.509 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-119">WSS: X.509 Token Profile 1.1</span></span>|<span data-ttu-id="dd734-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span></span>|  
|<span data-ttu-id="dd734-121">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-121">WSS: Kerberos Token Profile 1.1</span></span>|<span data-ttu-id="dd734-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span></span>|  
|<span data-ttu-id="dd734-123">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-123">WSS: SAML 1.1 Token Profile 1.1</span></span>|<span data-ttu-id="dd734-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="dd734-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span></span>|  
|<span data-ttu-id="dd734-125">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="dd734-125">WS-Secure Conversation</span></span>|<span data-ttu-id="dd734-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span><span class="sxs-lookup"><span data-stu-id="dd734-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span></span>|  
|<span data-ttu-id="dd734-127">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="dd734-127">WS-Trust</span></span>|<span data-ttu-id="dd734-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span><span class="sxs-lookup"><span data-stu-id="dd734-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span></span>|  
|<span data-ttu-id="dd734-129">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="dd734-129">Application Note:</span></span><br /><br /> <span data-ttu-id="dd734-130">WS-Trust for TLS Handshake 사용</span><span class="sxs-lookup"><span data-stu-id="dd734-130">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="dd734-131">게시 예정</span><span class="sxs-lookup"><span data-stu-id="dd734-131">To be published</span></span>|  
|<span data-ttu-id="dd734-132">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="dd734-132">Application Note:</span></span><br /><br /> <span data-ttu-id="dd734-133">WS-Trust for SPNEGO 사용</span><span class="sxs-lookup"><span data-stu-id="dd734-133">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="dd734-134">게시 예정</span><span class="sxs-lookup"><span data-stu-id="dd734-134">To be published</span></span>|  
|<span data-ttu-id="dd734-135">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="dd734-135">Application Note:</span></span><br /><br /> <span data-ttu-id="dd734-136">Web Services Addressing 끝점 참조 및 ID</span><span class="sxs-lookup"><span data-stu-id="dd734-136">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="dd734-137">게시 예정</span><span class="sxs-lookup"><span data-stu-id="dd734-137">To be published</span></span>|  
|<span data-ttu-id="dd734-138">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="dd734-138">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="dd734-139">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="dd734-139">(2005/07)</span></span>|<span data-ttu-id="dd734-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span><span class="sxs-lookup"><span data-stu-id="dd734-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span></span><br /><br /> <span data-ttu-id="dd734-141">OASIS WS-SX Technical Committee(http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html)에 제출된 오류에 의해 수정됨</span><span class="sxs-lookup"><span data-stu-id="dd734-141">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-142"> 버전 1에서는 Web Services Security 구성에 기본으로 사용할 수 있는 17가지 인증 모드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-142">, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="dd734-143">각 모드는 다음과 같은 공통 배포 요구 사항에 대해 최적화된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-143">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="dd734-144">클라이언트와 서비스를 인증하는 데 사용되는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="dd734-144">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="dd734-145">메시지 또는 전송 보안 보호 메커니즘</span><span class="sxs-lookup"><span data-stu-id="dd734-145">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="dd734-146">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="dd734-146">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="dd734-147">인증 모드</span><span class="sxs-lookup"><span data-stu-id="dd734-147">Authentication Mode</span></span>|<span data-ttu-id="dd734-148">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="dd734-148">Client Authentication</span></span>|<span data-ttu-id="dd734-149">서버 인증</span><span class="sxs-lookup"><span data-stu-id="dd734-149">Server Authentication</span></span>|<span data-ttu-id="dd734-150">모드</span><span class="sxs-lookup"><span data-stu-id="dd734-150">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="dd734-151">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-151">UserNameOverTransport</span></span>|<span data-ttu-id="dd734-152">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="dd734-152">User name/password</span></span>|<span data-ttu-id="dd734-153">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-153">X509</span></span>|<span data-ttu-id="dd734-154">전송</span><span class="sxs-lookup"><span data-stu-id="dd734-154">Transport</span></span>|  
|<span data-ttu-id="dd734-155">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-155">CertificateOverTransport</span></span>|<span data-ttu-id="dd734-156">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-156">X509</span></span>|<span data-ttu-id="dd734-157">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-157">X509</span></span>|<span data-ttu-id="dd734-158">전송</span><span class="sxs-lookup"><span data-stu-id="dd734-158">Transport</span></span>|  
|<span data-ttu-id="dd734-159">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-159">KerberosOverTransport</span></span>|<span data-ttu-id="dd734-160">Windows</span><span class="sxs-lookup"><span data-stu-id="dd734-160">Windows</span></span>|<span data-ttu-id="dd734-161">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-161">X509</span></span>|<span data-ttu-id="dd734-162">전송</span><span class="sxs-lookup"><span data-stu-id="dd734-162">Transport</span></span>|  
|<span data-ttu-id="dd734-163">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-163">IssuedTokenOverTransport</span></span>|<span data-ttu-id="dd734-164">페더레이션</span><span class="sxs-lookup"><span data-stu-id="dd734-164">Federated</span></span>|<span data-ttu-id="dd734-165">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-165">X509</span></span>|<span data-ttu-id="dd734-166">전송</span><span class="sxs-lookup"><span data-stu-id="dd734-166">Transport</span></span>|  
|<span data-ttu-id="dd734-167">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-167">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="dd734-168">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-168">Windows Sspi Negotiated</span></span>|<span data-ttu-id="dd734-169">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-169">Windows Sspi Negotiated</span></span>|<span data-ttu-id="dd734-170">전송</span><span class="sxs-lookup"><span data-stu-id="dd734-170">Transport</span></span>|  
|<span data-ttu-id="dd734-171">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-171">AnonymousForCertificate</span></span>|<span data-ttu-id="dd734-172">없음</span><span class="sxs-lookup"><span data-stu-id="dd734-172">None</span></span>|<span data-ttu-id="dd734-173">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-173">X509</span></span>|<span data-ttu-id="dd734-174">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-174">Message</span></span>|  
|<span data-ttu-id="dd734-175">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-175">UserNameForCertificate</span></span>|<span data-ttu-id="dd734-176">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="dd734-176">User name/password</span></span>|<span data-ttu-id="dd734-177">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-177">X509</span></span>|<span data-ttu-id="dd734-178">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-178">Message</span></span>|  
|<span data-ttu-id="dd734-179">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-179">MutualCertificate</span></span>|<span data-ttu-id="dd734-180">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-180">X509</span></span>|<span data-ttu-id="dd734-181">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-181">X509</span></span>|<span data-ttu-id="dd734-182">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-182">Message</span></span>|  
|<span data-ttu-id="dd734-183">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="dd734-183">MutualCertificateDuplex</span></span>|<span data-ttu-id="dd734-184">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-184">X509</span></span>|<span data-ttu-id="dd734-185">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-185">X509</span></span>|<span data-ttu-id="dd734-186">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-186">Message</span></span>|  
|<span data-ttu-id="dd734-187">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-187">IssuedTokenForCertificate</span></span>|<span data-ttu-id="dd734-188">페더레이션</span><span class="sxs-lookup"><span data-stu-id="dd734-188">Federated</span></span>|<span data-ttu-id="dd734-189">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-189">X509</span></span>|<span data-ttu-id="dd734-190">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-190">Message</span></span>|  
|<span data-ttu-id="dd734-191">Kerberos</span><span class="sxs-lookup"><span data-stu-id="dd734-191">Kerberos</span></span>|<span data-ttu-id="dd734-192">Windows</span><span class="sxs-lookup"><span data-stu-id="dd734-192">Windows</span></span>|<span data-ttu-id="dd734-193">Windows</span><span class="sxs-lookup"><span data-stu-id="dd734-193">Windows</span></span>|<span data-ttu-id="dd734-194">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-194">Message</span></span>|  
|<span data-ttu-id="dd734-195">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="dd734-195">IssuedToken</span></span>|<span data-ttu-id="dd734-196">페더레이션</span><span class="sxs-lookup"><span data-stu-id="dd734-196">Federated</span></span>|<span data-ttu-id="dd734-197">페더레이션</span><span class="sxs-lookup"><span data-stu-id="dd734-197">Federated</span></span>|<span data-ttu-id="dd734-198">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-198">Message</span></span>|  
|<span data-ttu-id="dd734-199">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-199">SspiNegotiated</span></span>|<span data-ttu-id="dd734-200">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-200">Windows Sspi Negotiated</span></span>|<span data-ttu-id="dd734-201">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-201">Windows Sspi Negotiated</span></span>|<span data-ttu-id="dd734-202">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-202">Message</span></span>|  
|<span data-ttu-id="dd734-203">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-203">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="dd734-204">없음</span><span class="sxs-lookup"><span data-stu-id="dd734-204">None</span></span>|<span data-ttu-id="dd734-205">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-205">X509, TLS-Nego</span></span>|<span data-ttu-id="dd734-206">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-206">Message</span></span>|  
|<span data-ttu-id="dd734-207">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-207">UserNameForSslNegotiated</span></span>|<span data-ttu-id="dd734-208">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="dd734-208">User name/password</span></span>|<span data-ttu-id="dd734-209">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-209">X509, TLS-Nego</span></span>|<span data-ttu-id="dd734-210">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-210">Message</span></span>|  
|<span data-ttu-id="dd734-211">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-211">MutualSslNegotiated</span></span>|<span data-ttu-id="dd734-212">X509</span><span class="sxs-lookup"><span data-stu-id="dd734-212">X509</span></span>|<span data-ttu-id="dd734-213">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-213">X509, TLS-Nego</span></span>|<span data-ttu-id="dd734-214">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-214">Message</span></span>|  
|<span data-ttu-id="dd734-215">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-215">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="dd734-216">페더레이션</span><span class="sxs-lookup"><span data-stu-id="dd734-216">Federated</span></span>|<span data-ttu-id="dd734-217">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="dd734-217">X509, TLS-Nego</span></span>|<span data-ttu-id="dd734-218">메시지</span><span class="sxs-lookup"><span data-stu-id="dd734-218">Message</span></span>|  
  
 <span data-ttu-id="dd734-219">이러한 인증 모드를 사용하는 끝점에서는 WS-SP(WS-SecurityPolicy)를 사용하여 보안 요구 사항을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-219">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="dd734-220">이 문서에서는 각 인증 모드의 보안 헤더 및 인프라 메시지 구조에 대해 설명하고 정책 및 메시지에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-220">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-221">에서는 WS-SecureConversation을 사용하여 응용 프로그램 간의 다중 메시지 교환 보호를 위한 보안 세션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-221"> leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="dd734-222">구현에 대한 자세한 내용은 아래의 "보안 세션"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-222">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="dd734-223">인증 모드 이외에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서명과 암호화 작업의 순서 비교, 알고리즘 모음, 키 파생 서명 확인 등과 같이 대부분의 메시지 보안 기반 인증 모드에 적용되는 공통 보호 메커니즘을 제어하는 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-223">In addition to authentication modes, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="dd734-224">이 문서에서는 다음과 같은 접두사와 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-224">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="dd734-225">접두사</span><span class="sxs-lookup"><span data-stu-id="dd734-225">Prefix</span></span>|<span data-ttu-id="dd734-226">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="dd734-226">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="dd734-227">s</span><span class="sxs-lookup"><span data-stu-id="dd734-227">s</span></span>|<span data-ttu-id="dd734-228">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="dd734-228">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="dd734-229">sp</span><span class="sxs-lookup"><span data-stu-id="dd734-229">sp</span></span>|<span data-ttu-id="dd734-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="dd734-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span></span>|  
|<span data-ttu-id="dd734-231">a</span><span class="sxs-lookup"><span data-stu-id="dd734-231">a</span></span>|<span data-ttu-id="dd734-232">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="dd734-232">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="dd734-233">wsse</span><span class="sxs-lookup"><span data-stu-id="dd734-233">wsse</span></span>|<span data-ttu-id="dd734-234">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="dd734-234">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="dd734-235">wsse11</span><span class="sxs-lookup"><span data-stu-id="dd734-235">wsse11</span></span>|<span data-ttu-id="dd734-236">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="dd734-236">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="dd734-237">wsu</span><span class="sxs-lookup"><span data-stu-id="dd734-237">wsu</span></span>|<span data-ttu-id="dd734-238">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="dd734-238">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="dd734-239">ds</span><span class="sxs-lookup"><span data-stu-id="dd734-239">ds</span></span>|<span data-ttu-id="dd734-240">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="dd734-240">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="dd734-241">wst</span><span class="sxs-lookup"><span data-stu-id="dd734-241">wst</span></span>|<span data-ttu-id="dd734-242">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="dd734-242">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="dd734-243">wssc</span><span class="sxs-lookup"><span data-stu-id="dd734-243">wssc</span></span>|<span data-ttu-id="dd734-244">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="dd734-244">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="dd734-245">wsaw</span><span class="sxs-lookup"><span data-stu-id="dd734-245">wsaw</span></span>|<span data-ttu-id="dd734-246">TBD - WS-Addressing 정책 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="dd734-246">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="dd734-247">wsp</span><span class="sxs-lookup"><span data-stu-id="dd734-247">wsp</span></span>|<span data-ttu-id="dd734-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span><span class="sxs-lookup"><span data-stu-id="dd734-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span></span>|  
|<span data-ttu-id="dd734-249">mssp</span><span class="sxs-lookup"><span data-stu-id="dd734-249">mssp</span></span>|<span data-ttu-id="dd734-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="dd734-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span></span>|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="dd734-251">1. 토큰 프로필</span><span class="sxs-lookup"><span data-stu-id="dd734-251">1. Token Profiles</span></span>  
 <span data-ttu-id="dd734-252">Web Services Security 사양에서는 자격 증명을 보안 토큰으로서 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-252">Web Services Security specifications represent credential as security tokens.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-253">에서는 다음과 같은 토큰 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-253"> supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="dd734-254">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="dd734-254">1.1 UsernameToken</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-255">에서는 UsernameToken10 및 UsernameToken11 프로필을 따르며 다음과 같은 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-255"> follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="dd734-256">UsernameToken\Password 요소의 R1101 PasswordType 특성은 생략되거나 그 값이 #PasswordText(기본값)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-256">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="dd734-257">확장성을 사용하여 #PasswordDigest를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-257">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="dd734-258">#PasswordDigest가 보안 암호 보호 메커니즘으로 잘못 인식되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-258">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="dd734-259">그러나 #PasswordDigest는 UsernameToken 암호화를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-259">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="dd734-260">#PasswordDigest의 주요 목표는 재생 공격을 방지하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-260">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="dd734-261">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인증 모드에서 메시지 서명을 사용하면 재생 공격 위협을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="dd734-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 UsernameToken에 대한 Nonce 및 Created 하위 요소를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="dd734-263">이러한 하위 요소는 재생 검색을 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-263">These sub-elements are intended to help replay detection.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-264">에서는 메시지 서명을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-264"> uses message signatures instead.</span></span>  
  
 <span data-ttu-id="dd734-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1(UsernameToken11)에서는 암호로부터 키 파생 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="dd734-266">B1103 UsernameToken 암호는 키 파생에 사용할 수 없으므로 암호화 작업에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-266">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="dd734-267">설명: 암호는 일반적으로 암호화 작업에 사용하기에 너무 약합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-267">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="dd734-268">1.2 X509 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-268">1.2 X509 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-269">에서는 X509v3 인증서를 자격 증명 형식으로 지원하고 X509TokenProfile1.0 및 X509TokenProfile1.1을 따르며 다음과 같은 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-269"> supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="dd734-270">R1201 BinarySecurityToken 요소의 ValueType 특성은 X509v3 인증서를 포함할 경우 #X509v3 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-270">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="dd734-271">또한 WSS X509 Token Profile 1.0 및 1.1은 #X509PKIPathv1 및 #PKCS7을 값 형식으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-271">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-272">에서는 이러한 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-272"> does not support these types.</span></span>  
  
 <span data-ttu-id="dd734-273">R1202 SKI(SubjectKeyIdentifier) 확장이 X509 인증서에 있으면 토큰에 대한 외부 참조로 wsse:KeyIdentifier를 사용해야 합니다. 이 때 ValueType 특성은 #X509SubjectKeyIdentifier이고 해당 내용에 base64 인코딩된 인증서 SKI 확장 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-273">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="dd734-274">SKI 참조는 널리 구현되고 있으며 상호 운용성이 높은 외부 참조 형식으로 인정받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-274">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="dd734-275">R1203 X509 보안 토큰에 대한 외부 참조에는 ds:X509IssuerSerial을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-275">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="dd734-276">R1204 X509TokenProfile1.1이 사용 중인 경우 X509 보안 토큰에 대한 외부 참조에는 WS-Security 1.1을 통해 추가된 지문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-276">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-277">에서는 X509IssuerSerial을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-277"> supports X509IssuerSerial.</span></span> <span data-ttu-id="dd734-278">그러나 X509IssuerSerial과의 상호 운용성 문제가 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 문자열을 사용하여 X509IssuerSerial의 두 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-278">However There are interoperability issues with X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="dd734-279">따라서 주체 이름 구성 요소를 다시 정렬하고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 인증서에 대한 참조를 보낼 경우 참조를 찾지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-279">Therefore if one reorders components of the Subject Name and sends to an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="dd734-280">1.3 Kerberos 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-280">1.3 Kerberos Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-281">에서는 Windows 인증을 위한 KerberosTokenProfile1.1을 지원하며 다음과 같은 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-281"> supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="dd734-282">R1301 Kerberos Token은 GSS_API 및 Kerberos 사양에 정의된 GSS 래핑된 Kerberos v4 AP_REQ 값을 사용하고, 값이 #GSS_Kerberosv5_AP_REQ인 ValueType 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-282">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-283">에서는 bare AP-REQ가 아니라 GSS 래핑된 Kerberos AP-REQ를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-283"> uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="dd734-284">이는 최선의 보안 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-284">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="dd734-285">1.4 SAML v1.1 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-285">1.4 SAML v1.1 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-286">에서는 SAML v1.1 토큰용 WSS SAML Token profiles 1.0 및 1.1을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-286"> supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="dd734-287">또한 다른 버전의 SAML 토큰 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-287">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="dd734-288">1.5 보안 컨텍스트 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-288">1.5 Security Context Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-289">에서는 SCT(보안 컨텍스트 토큰)가 WS-SecureCoversation에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-289"> supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="dd734-290">SCT는 아래에 설명하는 이진 협상 프로토콜 TLS 및 SSPI를 비롯하여 SecureConversation에 설정된 보안 컨텍스트를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-290">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="dd734-291">2. 일반 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd734-291">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="dd734-292">2.1 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="dd734-292">2.1 TimeStamp</span></span>  
 <span data-ttu-id="dd734-293">타임스탬프 표시 여부는 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 클래스의 <xref:System.ServiceModel.Channels.SecurityBindingElement> 속성을 사용하여 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-293">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-294">에서는 wsse:Created 및 wsse:Expires 필드를 사용하여 wsse:TimeStamp를 항상 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-294"> always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="dd734-295">wsse:TimeStamp는 서명이 사용될 경우 항상 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-295">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="dd734-296">2.2 보호 순서</span><span class="sxs-lookup"><span data-stu-id="dd734-296">2.2 Protection Order</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-297">에서는 "암호화 전 서명" 및 "서명 전 암호화"(Security Policy 1.1)의 두 가지 메시지 보호 순서를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-297"> supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="dd734-298">WS-Security 1.1 서명 확인 메커니즘을 사용하지 않을 경우 서명 전 암호화로 보호된 메시지는 서명 대체 공격에 취약하고, 암호화된 내용에 대한 서명으로 인해 감사를 수행하기 더 어려워지므로 "암호화 전 서명"을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-298">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="dd734-299">2.3 서명 보호</span><span class="sxs-lookup"><span data-stu-id="dd734-299">2.3 Signature Protection</span></span>  
 <span data-ttu-id="dd734-300">서명 전 암호화를 사용할 경우, 특히 사용자 지정 토큰을 weak 키 자료와 함께 사용하는 경우에는 암호화된 내용이나 서명 키를 추측하기 위한 무차별 키 대입 공격을 방지해 서명을 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-300">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="dd734-301">2.4 알고리즘 모음</span><span class="sxs-lookup"><span data-stu-id="dd734-301">2.4 Algorithm Suite</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-302">에서는 Security Policy 1.1에 나열된 모든 알고리즘 모음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-302"> supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="dd734-303">2.5 키 파생</span><span class="sxs-lookup"><span data-stu-id="dd734-303">2.5 Key Derivation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-304">에서는 WS-SecureConversation에서 설명된 대로 "대칭 키에 대한 키 파생"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-304"> uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="dd734-305">2.6 서명 확인</span><span class="sxs-lookup"><span data-stu-id="dd734-305">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="dd734-306">서명 확인을 사용하여 중개자의 공격으로부터 서명 집합을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-306">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="dd734-307">2.7 보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="dd734-307">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="dd734-308">각 인증 모드에서는 보안 헤더에 대한 특정 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-308">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="dd734-309">보안 헤더 내의 요소는 일부 순서가 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-309">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="dd734-310">보안 헤더 자식 요소의 순서를 지정하기 위해 WS-Security 정책에서는 다음과 같은 보안 헤더 레이아웃 모드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-310">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd734-311">Strict</span><span class="sxs-lookup"><span data-stu-id="dd734-311">Strict</span></span>|<span data-ttu-id="dd734-312">"사용 전 선언"의 일반 원칙에 따라 보안 정책 7.7.1 단원에 설명된 번호가 매겨진 레이아웃 규칙을 따르는 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-312">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="dd734-313">Lax</span><span class="sxs-lookup"><span data-stu-id="dd734-313">Lax</span></span>|<span data-ttu-id="dd734-314">WSS: SOAP 메시지 보안에 따른 순서로 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-314">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="dd734-315">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="dd734-315">LaxTimestampFirst</span></span>|<span data-ttu-id="dd734-316">보안 헤더의 첫 번째 항목이 wsse:Timestamp여야 한다는 점을 제외하고 Lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-316">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="dd734-317">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="dd734-317">LaxTimestampLast</span></span>|<span data-ttu-id="dd734-318">보안 헤더의 마지막 항목이 wsse:Timestamp여야 한다는 점을 제외하고 lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-318">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-319">에서는 보안 헤더 레이아웃의 네 가지 모드를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-319"> supports all four modes for security header layout.</span></span> <span data-ttu-id="dd734-320">아래에 설명된 인증 모드에 대한 보안 헤더 구조 및 메시지 예제에서는 "Strict" 모드를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-320">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="dd734-321">2. 일반 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd734-321">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="dd734-322">이 단원에서는 클라이언트와 서비스 간에 교환되는 메시지의 보안 헤더 구조를 보여 주는 예제와 함께 각 인증 모드에 대한 예제 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-322">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="dd734-323">6.1 전송 보호</span><span class="sxs-lookup"><span data-stu-id="dd734-323">6.1 Transport Protection</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="dd734-324">에서는 보안 전송을 사용하여 메시지를 보호하는 다섯 가지 인증 모드(UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport, SspiNegotiatedOverTransport)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-324"> provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="dd734-325">이러한 인증 모드는 SecurityPolicy에 설명된 전송 바인딩을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-325">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="dd734-326">UserNameOverTransport 인증 모드의 경우 UsernameToken이 서명된 지원 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-326">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="dd734-327">다른 인증 모드의 경우 토큰이 서명된 보증 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-327">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="dd734-328">보안 헤더 레이아웃에 대해서는 SecurityPolicy의 부록 C.1.2 및 C.1.3에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-328">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="dd734-329">다음 예제 보안 헤더에서는 지정된 인증 모드에 대한 Strict 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-329">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="dd734-330">모든 경우의 토큰에 대한 "파생 키" 속성 값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-330">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="dd734-331">전송 바인딩의 다양한 속성 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-331">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="dd734-332">타임스탬프: true</span><span class="sxs-lookup"><span data-stu-id="dd734-332">Timestamp: true</span></span>  
  
 <span data-ttu-id="dd734-333">보안 헤더 레이아웃: Strict</span><span class="sxs-lookup"><span data-stu-id="dd734-333">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="dd734-334">알고리즘 모음: Basic256</span><span class="sxs-lookup"><span data-stu-id="dd734-334">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="dd734-335">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-335">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="dd734-336">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-336">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="dd734-337">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="dd734-338">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-338">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="dd734-339">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="dd734-340">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="dd734-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="dd734-341">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-341">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-342">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="dd734-343">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-343">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="dd734-344">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-344">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="dd734-345">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="dd734-346">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-346">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="dd734-347">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-347">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="dd734-348">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="dd734-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="dd734-349">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-349">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-350">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-350">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="dd734-351">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-351">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="dd734-352">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS(보안 토큰 서비스)에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-352">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="dd734-353">발급된 토큰은 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-353">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="dd734-354">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-354">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="dd734-355">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-355">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="dd734-356">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-356">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="dd734-357">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="dd734-357">Security Header Layout</span></span>  
  
 <span data-ttu-id="dd734-358">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-358">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-359">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-359">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="dd734-360">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-360">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="dd734-361">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-361">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="dd734-362">Kerberos 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-362">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="dd734-363">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-363">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="dd734-364">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-364">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="dd734-365">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-365">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="dd734-366">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="dd734-366">Security Header Layout</span></span>  
  
 <span data-ttu-id="dd734-367">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-367">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-368">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-368">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="dd734-369">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="dd734-369">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="dd734-370">이 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-370">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="dd734-371">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-371">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="dd734-372">결과 SCT는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-372">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="dd734-373">서비스는 전송 계층에서 X.509 인증서를 사용하여 추가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-373">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="dd734-374">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-374">The binding used is a transport binding.</span></span> <span data-ttu-id="dd734-375">"SPNEGO"(협상)에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 WS-Trust와 함께 SSPI 이진 협상 프로토콜을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-375">"SPNEGO" (negotiation) describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="dd734-376">이 단원의 보안 헤더 예제는 SPNEGO 핸드셰이크를 통해 SCT를 설정한 경우의 보안 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-376">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="dd734-377">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="dd734-378">보안 헤더 예제</span><span class="sxs-lookup"><span data-stu-id="dd734-378">Security Header Examples</span></span>  
 <span data-ttu-id="dd734-379">WS-Trust 이진 협상을 사용하여 SPNEGO 핸드셰이크를 통해 보안 컨텍스트 토큰을 설정한 경우, 응용 프로그램 메시지에 다음과 같은 구조의 보안 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-379">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="dd734-380">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-380">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-381">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="dd734-382">6.2 X.509 인증서를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="dd734-382">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="dd734-383">이 단원에서는 MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate 및 IssuedTokenForCertificate 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-383">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="dd734-384">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="dd734-384">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="dd734-385">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="dd734-386">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="dd734-387">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="dd734-388">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="dd734-388">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="dd734-389">수신자 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="dd734-389">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="dd734-390">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-391">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-392">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-393">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-394">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-395">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-396">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-396">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-397">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-397">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-398">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-398">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="dd734-399">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-399">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-400">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-400">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="dd734-401">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="dd734-401">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="dd734-402">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-402">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="dd734-403">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-403">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="dd734-404">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-404">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="dd734-405">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="dd734-405">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="dd734-406">수신자 토큰: 포함 모드가 …/IncludeToken/AlwaysToInitiator로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="dd734-406">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="dd734-407">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-407">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-408">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-408">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-409">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-409">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-410">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-410">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-411">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-411">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-412">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-412">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-413">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="dd734-413">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-414">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-414">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-415">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="dd734-415">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="dd734-416">6.2.3 X.509 서비스 인증에서 SymmetricBinding 사용</span><span class="sxs-lookup"><span data-stu-id="dd734-416">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="dd734-417">"WSS10"에서는 X509 토큰 사용 시나리오를 제한적으로 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-417">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="dd734-418">예를 들어, 서비스 X509 토큰만 사용하여 메시지에 대한 서명 및 암호화 보호를 제공할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-418">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="dd734-419">"WSS11"에서는 EncryptedKey를 대칭 토큰으로 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-419">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="dd734-420">이제 요청 메시지 보호와 응답 메시지 보호에 서비스의 X.509 인증서에 대해 암호화된 임시 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-420">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="dd734-421">아래 6.4 단원에 설명된 인증 모드에서는 이 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-421">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="dd734-422">WS-SecurityPolicy에서는 Service X509 토큰을 보호 토큰으로 사용하여 SymmetricBinding을 통해 이 패턴을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-422">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="dd734-423">AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 및 IssuedTokenForCertificate 인증 모드는 모두 다음 속성 값을 가진 비슷한 sp:SymmetricBinding 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-423">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="dd734-424">보호 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X509 인증서</span><span class="sxs-lookup"><span data-stu-id="dd734-424">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="dd734-425">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-425">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-426">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-426">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-427">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-427">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-428">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-428">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-429">위의 인증 모드는 사용하는 지원 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-429">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="dd734-430">AnonymousForCertificate의 경우 토큰이 없으며, MutualCertificate WSS 1.1의 경우 클라이언트의 X509 인증서를 보증 지원 토큰으로 사용하고, UserNameForCertificate의 경우 사용자 이름 토큰을 서명된 지원 토큰으로 사용하고, IssuedTokenForCertificate의 경우 발급된 토큰을 보증 지원 토큰으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-430">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="dd734-431">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-431">Policy</span></span>  
  
 <span data-ttu-id="dd734-432">대칭 바인딩</span><span class="sxs-lookup"><span data-stu-id="dd734-432">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="dd734-433">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-433">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="dd734-434">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-434">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="dd734-435">사용되는 바인딩은 6.4.2에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-435">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="dd734-436">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-436">Policy</span></span>  
  
 <span data-ttu-id="dd734-437">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-437">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-438">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-438">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-439">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-439">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-440">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-440">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-441">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-441">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-442">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-442">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-443">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-443">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="dd734-444">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-444">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="dd734-445">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-445">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="dd734-446">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-446">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="dd734-447">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-447">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="dd734-448">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-448">Policy</span></span>  
  
 <span data-ttu-id="dd734-449">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-449">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="dd734-450">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-450">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-451">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-451">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-452">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-452">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-453">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-453">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-454">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-454">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-455">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-455">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-456">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-456">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="dd734-457">6.2.6 MutualCertificate(WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="dd734-457">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="dd734-458">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-458">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="dd734-459">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-459">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="dd734-460">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-460">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="dd734-461">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-461">Policy</span></span>  
  
 <span data-ttu-id="dd734-462">바인딩에 대한 자세한 내용은 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-462">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="dd734-463">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-463">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-464">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-464">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-465">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-466">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-467">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-467">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-468">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-468">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-469">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-469">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="dd734-470">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="dd734-470">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="dd734-471">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-471">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="dd734-472">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-472">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="dd734-473">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-473">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="dd734-474">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-474">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="dd734-475">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-475">Policy</span></span>  
  
 <span data-ttu-id="dd734-476">바인딩에 대한 자세한 내용은 위 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-476">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="dd734-477">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-477">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-478">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-479">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-479">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-480">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-480">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-481">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-481">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-482">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-482">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-483">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-483">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="dd734-484">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="dd734-484">6.3 Kerberos</span></span>  
 <span data-ttu-id="dd734-485">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-485">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="dd734-486">동일한 티켓에서 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-486">That same ticket also provides server authentication.</span></span> <span data-ttu-id="dd734-487">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-487">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="dd734-488">보호 토큰: 포함 모드가 .../IncludeToken/Once로 설정된 Kerberos 티켓</span><span class="sxs-lookup"><span data-stu-id="dd734-488">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="dd734-489">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-490">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-491">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-492">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-493">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-493">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-494">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-495">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-495">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-496">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-496">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-497">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-497">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-498">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-498">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-499">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-499">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="dd734-500">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="dd734-500">6.4 IssuedToken</span></span>  
 <span data-ttu-id="dd734-501">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-501">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="dd734-502">서비스가 클라이언트에 인증되지 않습니다. 대신 STS에서 공유 키를 발급된 토큰의 일부로 암호화하여 서비스에서만 키를 해독할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-502">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="dd734-503">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-503">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="dd734-504">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-504">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="dd734-505">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-506">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-507">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-508">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-508">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-509">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-509">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-510">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-510">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-511">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-511">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-512">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-512">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-513">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-513">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-514">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-514">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-515">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-515">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="dd734-516">6.5 SslNegotiated를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="dd734-516">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="dd734-517">이 단원에서는 보호 토큰이 WS-T(WS-Trust) RST/RSTR 메시지를 통해 TLS 프로토콜을 실행하여 그 키 값이 협상되는 WS-SC(WS-SecureConversation)별 보안 컨텍스트 토큰인 대칭 바인딩을 사용하는 인증 모드 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-517">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="dd734-518">WS-Trust를 사용하는 TLS 핸드셰이크 구현에 대한 자세한 내용은 TLSNEGO를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-518">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="dd734-519">여기의 메시지 예제에서는 연결된 보안 컨텍스트가 있는 SCT가 핸드셰이크를 통해 이미 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-519">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="dd734-520">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-520">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="dd734-521">보호 토큰: 포함 모드가 .../IncludeToken/Never로 설정된 SslContextToken</span><span class="sxs-lookup"><span data-stu-id="dd734-521">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="dd734-522">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-522">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-523">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-523">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-524">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-524">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-525">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-525">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="dd734-526">6.5.1 SslNegotiated 서비스 인증 정책</span><span class="sxs-lookup"><span data-stu-id="dd734-526">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="dd734-527">이 단원의 모든 인증 모드에 대한 정책은 비슷하며 사용되는 특정 서명된 지원 토큰과 보증 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-527">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="dd734-528">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-528">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="dd734-529">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-529">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="dd734-530">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-530">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="dd734-531">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-531">Policy</span></span>  
  
 <span data-ttu-id="dd734-532">바인딩에 대한 자세한 내용은 위 6.5.1의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-532">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-533">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-533">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-534">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-534">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-535">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-535">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-536">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-536">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-537">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-537">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-538">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-538">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="dd734-539">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-539">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="dd734-540">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-540">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="dd734-541">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-541">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="dd734-542">사용되는 바인딩은 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-542">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="dd734-543">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-543">Policy</span></span>  
  
 <span data-ttu-id="dd734-544">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-544">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="dd734-545">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-545">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-546">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-546">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-547">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-547">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-548">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-548">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-549">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-549">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-550">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-550">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-551">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-551">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="dd734-552">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-552">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="dd734-553">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-553">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="dd734-554">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-554">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="dd734-555">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-555">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="dd734-556">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-556">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="dd734-557">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-557">Policy</span></span>  
  
 <span data-ttu-id="dd734-558">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-558">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="dd734-559">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-559">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-560">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-560">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-561">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-561">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-562">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-562">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-563">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-563">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-564">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-564">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-565">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-565">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="dd734-566">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-566">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="dd734-567">이 인증 모드에서 클라이언트 및 서비스는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-567">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="dd734-568">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-568">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="dd734-569">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-569">Policy</span></span>  
  
 <span data-ttu-id="dd734-570">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd734-570">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="dd734-571">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="dd734-571">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-572">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-573">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-573">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-574">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-574">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-575">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-575">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-576">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-576">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-577">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-577">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="dd734-578">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="dd734-578">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="dd734-579">이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-579">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="dd734-580">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-580">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="dd734-581">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-581">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="dd734-582">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 SpnegoContextToken</span><span class="sxs-lookup"><span data-stu-id="dd734-582">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="dd734-583">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="dd734-583">Token Protection: False</span></span>  
  
 <span data-ttu-id="dd734-584">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="dd734-584">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="dd734-585">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="dd734-585">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="dd734-586">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="dd734-586">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="dd734-587">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-587">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-588">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-588">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-589">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-589">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-590">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-590">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-591">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-591">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-592">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-592">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-593">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-593">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="dd734-594">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="dd734-594">6.7 SecureConversation</span></span>  
 <span data-ttu-id="dd734-595">사용되는 바인딩은 보호 토큰이 WS-SC(WS-SecureConversation)별 SCT인 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-595">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="dd734-596">SCT는 그 자체가 협상 프로토콜을 사용하는 대칭 바인딩인 중첩 바인딩에 따라 WS-Trust(WS-Trust) 또는 WS-SC(WS-SecureConversation)를 사용하여 협상됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-596">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="dd734-597">협상 프로토콜은 가능하면 Kerberos를 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-597">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="dd734-598">Kerberos를 사용할 수 없는 경우 NTLM으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd734-598">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="dd734-599">정책</span><span class="sxs-lookup"><span data-stu-id="dd734-599">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="dd734-600">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="dd734-600">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="dd734-601">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-601">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-602">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-602">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="dd734-603">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="dd734-603">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="dd734-604">요청</span><span class="sxs-lookup"><span data-stu-id="dd734-604">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="dd734-605">응답</span><span class="sxs-lookup"><span data-stu-id="dd734-605">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
