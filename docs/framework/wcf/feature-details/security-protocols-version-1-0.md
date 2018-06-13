---
title: 보안 프로토콜 버전 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 1b1e911b20ac8974dbc8cfa79e03fbd14f9beb17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509179"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="388fc-102">보안 프로토콜 버전 1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="388fc-103">Web Services Security 프로토콜은 모든 기존 엔터프라이즈 메시징 보안 요구 사항을 포함하는 Web Services Security 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="388fc-104">이 섹션에서는 Windows Communication Foundation (WCF) 버전 1.0 세부 정보를 설명 (에서 구현 되는 <xref:System.ServiceModel.Channels.SecurityBindingElement>) 다음 웹 서비스 보안 프로토콜에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="388fc-105">사양/문서</span><span class="sxs-lookup"><span data-stu-id="388fc-105">Specification/Document</span></span>|<span data-ttu-id="388fc-106">링크</span><span class="sxs-lookup"><span data-stu-id="388fc-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="388fc-107">WSS: SOAP Message Security 1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-107">WSS: SOAP Message Security 1.0</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf|  
|<span data-ttu-id="388fc-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-108">WSS: Username Token Profile 1.0</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf|  
|<span data-ttu-id="388fc-109">WSS: X509 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-109">WSS: X509 Token Profile 1.0</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf|  
|<span data-ttu-id="388fc-110">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf|  
|<span data-ttu-id="388fc-111">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-111">WSS: SOAP Message Security 1.1</span></span>|http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf|  
|<span data-ttu-id="388fc-112">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-112">WSS Username Token Profile 1.1</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf|  
|<span data-ttu-id="388fc-113">WSS: X.509 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-113">WSS: X.509 Token Profile 1.1</span></span>|http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf|  
|<span data-ttu-id="388fc-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-114">WSS: Kerberos Token Profile 1.1</span></span>|http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf|  
|<span data-ttu-id="388fc-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf|  
|<span data-ttu-id="388fc-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="388fc-116">WS-Secure Conversation</span></span>|http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/|  
|<span data-ttu-id="388fc-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="388fc-117">WS-Trust</span></span>|http://msdn.microsoft.com/ws/2005/02/ws-trust/|  
|<span data-ttu-id="388fc-118">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="388fc-118">Application Note:</span></span><br /><br /> <span data-ttu-id="388fc-119">WS-Trust for TLS Handshake 사용</span><span class="sxs-lookup"><span data-stu-id="388fc-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="388fc-120">게시 예정</span><span class="sxs-lookup"><span data-stu-id="388fc-120">To be published</span></span>|  
|<span data-ttu-id="388fc-121">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="388fc-121">Application Note:</span></span><br /><br /> <span data-ttu-id="388fc-122">WS-Trust for SPNEGO 사용</span><span class="sxs-lookup"><span data-stu-id="388fc-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="388fc-123">게시 예정</span><span class="sxs-lookup"><span data-stu-id="388fc-123">To be published</span></span>|  
|<span data-ttu-id="388fc-124">응용 프로그램 참고:</span><span class="sxs-lookup"><span data-stu-id="388fc-124">Application Note:</span></span><br /><br /> <span data-ttu-id="388fc-125">Web Services Addressing 끝점 참조 및 ID</span><span class="sxs-lookup"><span data-stu-id="388fc-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="388fc-126">게시 예정</span><span class="sxs-lookup"><span data-stu-id="388fc-126">To be published</span></span>|  
|<span data-ttu-id="388fc-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="388fc-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="388fc-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="388fc-128">(2005/07)</span></span>|http://msdn.microsoft.com/ws/2005/07/ws-security-policy/<br /><br /> <span data-ttu-id="388fc-129">OASIS WS-SX Technical Committee에 제출 된 오류 수정 됨 http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span><span class="sxs-lookup"><span data-stu-id="388fc-129">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 <span data-ttu-id="388fc-130">WCF, 버전 1에서는 Web services security 구성에 대 한 기준으로 사용할 수 있는 17 가지 인증 모드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="388fc-131">각 모드는 다음과 같은 공통 배포 요구 사항에 대해 최적화된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="388fc-132">클라이언트와 서비스를 인증하는 데 사용되는 자격 증명</span><span class="sxs-lookup"><span data-stu-id="388fc-132">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="388fc-133">메시지 또는 전송 보안 보호 메커니즘</span><span class="sxs-lookup"><span data-stu-id="388fc-133">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="388fc-134">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="388fc-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="388fc-135">인증 모드</span><span class="sxs-lookup"><span data-stu-id="388fc-135">Authentication Mode</span></span>|<span data-ttu-id="388fc-136">클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="388fc-136">Client Authentication</span></span>|<span data-ttu-id="388fc-137">서버 인증</span><span class="sxs-lookup"><span data-stu-id="388fc-137">Server Authentication</span></span>|<span data-ttu-id="388fc-138">모드</span><span class="sxs-lookup"><span data-stu-id="388fc-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="388fc-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-139">UserNameOverTransport</span></span>|<span data-ttu-id="388fc-140">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="388fc-140">User name/password</span></span>|<span data-ttu-id="388fc-141">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-141">X509</span></span>|<span data-ttu-id="388fc-142">전송</span><span class="sxs-lookup"><span data-stu-id="388fc-142">Transport</span></span>|  
|<span data-ttu-id="388fc-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-143">CertificateOverTransport</span></span>|<span data-ttu-id="388fc-144">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-144">X509</span></span>|<span data-ttu-id="388fc-145">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-145">X509</span></span>|<span data-ttu-id="388fc-146">전송</span><span class="sxs-lookup"><span data-stu-id="388fc-146">Transport</span></span>|  
|<span data-ttu-id="388fc-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-147">KerberosOverTransport</span></span>|<span data-ttu-id="388fc-148">Windows</span><span class="sxs-lookup"><span data-stu-id="388fc-148">Windows</span></span>|<span data-ttu-id="388fc-149">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-149">X509</span></span>|<span data-ttu-id="388fc-150">전송</span><span class="sxs-lookup"><span data-stu-id="388fc-150">Transport</span></span>|  
|<span data-ttu-id="388fc-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="388fc-152">페더레이션</span><span class="sxs-lookup"><span data-stu-id="388fc-152">Federated</span></span>|<span data-ttu-id="388fc-153">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-153">X509</span></span>|<span data-ttu-id="388fc-154">전송</span><span class="sxs-lookup"><span data-stu-id="388fc-154">Transport</span></span>|  
|<span data-ttu-id="388fc-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="388fc-156">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="388fc-157">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="388fc-158">전송</span><span class="sxs-lookup"><span data-stu-id="388fc-158">Transport</span></span>|  
|<span data-ttu-id="388fc-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-159">AnonymousForCertificate</span></span>|<span data-ttu-id="388fc-160">없음</span><span class="sxs-lookup"><span data-stu-id="388fc-160">None</span></span>|<span data-ttu-id="388fc-161">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-161">X509</span></span>|<span data-ttu-id="388fc-162">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-162">Message</span></span>|  
|<span data-ttu-id="388fc-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-163">UserNameForCertificate</span></span>|<span data-ttu-id="388fc-164">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="388fc-164">User name/password</span></span>|<span data-ttu-id="388fc-165">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-165">X509</span></span>|<span data-ttu-id="388fc-166">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-166">Message</span></span>|  
|<span data-ttu-id="388fc-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-167">MutualCertificate</span></span>|<span data-ttu-id="388fc-168">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-168">X509</span></span>|<span data-ttu-id="388fc-169">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-169">X509</span></span>|<span data-ttu-id="388fc-170">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-170">Message</span></span>|  
|<span data-ttu-id="388fc-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="388fc-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="388fc-172">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-172">X509</span></span>|<span data-ttu-id="388fc-173">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-173">X509</span></span>|<span data-ttu-id="388fc-174">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-174">Message</span></span>|  
|<span data-ttu-id="388fc-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="388fc-176">페더레이션</span><span class="sxs-lookup"><span data-stu-id="388fc-176">Federated</span></span>|<span data-ttu-id="388fc-177">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-177">X509</span></span>|<span data-ttu-id="388fc-178">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-178">Message</span></span>|  
|<span data-ttu-id="388fc-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="388fc-179">Kerberos</span></span>|<span data-ttu-id="388fc-180">Windows</span><span class="sxs-lookup"><span data-stu-id="388fc-180">Windows</span></span>|<span data-ttu-id="388fc-181">Windows</span><span class="sxs-lookup"><span data-stu-id="388fc-181">Windows</span></span>|<span data-ttu-id="388fc-182">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-182">Message</span></span>|  
|<span data-ttu-id="388fc-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="388fc-183">IssuedToken</span></span>|<span data-ttu-id="388fc-184">페더레이션</span><span class="sxs-lookup"><span data-stu-id="388fc-184">Federated</span></span>|<span data-ttu-id="388fc-185">페더레이션</span><span class="sxs-lookup"><span data-stu-id="388fc-185">Federated</span></span>|<span data-ttu-id="388fc-186">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-186">Message</span></span>|  
|<span data-ttu-id="388fc-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-187">SspiNegotiated</span></span>|<span data-ttu-id="388fc-188">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="388fc-189">Windows SSPI 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="388fc-190">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-190">Message</span></span>|  
|<span data-ttu-id="388fc-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="388fc-192">없음</span><span class="sxs-lookup"><span data-stu-id="388fc-192">None</span></span>|<span data-ttu-id="388fc-193">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-193">X509, TLS-Nego</span></span>|<span data-ttu-id="388fc-194">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-194">Message</span></span>|  
|<span data-ttu-id="388fc-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="388fc-196">사용자 이름/암호</span><span class="sxs-lookup"><span data-stu-id="388fc-196">User name/password</span></span>|<span data-ttu-id="388fc-197">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-197">X509, TLS-Nego</span></span>|<span data-ttu-id="388fc-198">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-198">Message</span></span>|  
|<span data-ttu-id="388fc-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-199">MutualSslNegotiated</span></span>|<span data-ttu-id="388fc-200">X509</span><span class="sxs-lookup"><span data-stu-id="388fc-200">X509</span></span>|<span data-ttu-id="388fc-201">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-201">X509, TLS-Nego</span></span>|<span data-ttu-id="388fc-202">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-202">Message</span></span>|  
|<span data-ttu-id="388fc-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="388fc-204">페더레이션</span><span class="sxs-lookup"><span data-stu-id="388fc-204">Federated</span></span>|<span data-ttu-id="388fc-205">X509, TLS 협상</span><span class="sxs-lookup"><span data-stu-id="388fc-205">X509, TLS-Nego</span></span>|<span data-ttu-id="388fc-206">메시지</span><span class="sxs-lookup"><span data-stu-id="388fc-206">Message</span></span>|  
  
 <span data-ttu-id="388fc-207">이러한 인증 모드를 사용하는 끝점에서는 WS-SP(WS-SecurityPolicy)를 사용하여 보안 요구 사항을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="388fc-208">이 문서에서는 각 인증 모드의 보안 헤더 및 인프라 메시지 구조에 대해 설명하고 정책 및 메시지에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="388fc-209">WCF 응용 프로그램 간의 다중 메시지 교환을 보호 해 보안 세션 지원을 제공할 수 Ws-secureconversation을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="388fc-210">구현에 대한 자세한 내용은 아래의 "보안 세션"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="388fc-211">인증 모드 이외에 WCF는 예를 들어 대부분의 메시지 보안 기반 인증 모드에 적용 되는 공통 보호 메커니즘을 제어 하는 설정을 제공: 서명 및 암호화 작업, 알고리즘 모음, 키 파생의 순서 및 서명 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="388fc-212">이 문서에서는 다음과 같은 접두사와 네임스페이스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="388fc-213">접두사</span><span class="sxs-lookup"><span data-stu-id="388fc-213">Prefix</span></span>|<span data-ttu-id="388fc-214">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="388fc-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="388fc-215">s</span><span class="sxs-lookup"><span data-stu-id="388fc-215">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="388fc-216">sp</span><span class="sxs-lookup"><span data-stu-id="388fc-216">sp</span></span>|http://schemas.xmlsoap.org/ws/2005/07/securitypolicy|  
|<span data-ttu-id="388fc-217">a</span><span class="sxs-lookup"><span data-stu-id="388fc-217">a</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="388fc-218">wsse</span><span class="sxs-lookup"><span data-stu-id="388fc-218">wsse</span></span>|<span data-ttu-id="388fc-219">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="388fc-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="388fc-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="388fc-220">wsse11</span></span>|<span data-ttu-id="388fc-221">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="388fc-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="388fc-222">wsu</span><span class="sxs-lookup"><span data-stu-id="388fc-222">wsu</span></span>|<span data-ttu-id="388fc-223">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="388fc-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="388fc-224">ds</span><span class="sxs-lookup"><span data-stu-id="388fc-224">ds</span></span>|<span data-ttu-id="388fc-225">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="388fc-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="388fc-226">wst</span><span class="sxs-lookup"><span data-stu-id="388fc-226">wst</span></span>|<span data-ttu-id="388fc-227">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="388fc-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="388fc-228">wssc</span><span class="sxs-lookup"><span data-stu-id="388fc-228">wssc</span></span>|<span data-ttu-id="388fc-229">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="388fc-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="388fc-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="388fc-230">wsaw</span></span>|<span data-ttu-id="388fc-231">TBD - WS-Addressing 정책 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="388fc-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="388fc-232">wsp</span><span class="sxs-lookup"><span data-stu-id="388fc-232">wsp</span></span>|http://schemas.xmlsoap.org/ws/2004/09/policy|  
|<span data-ttu-id="388fc-233">mssp</span><span class="sxs-lookup"><span data-stu-id="388fc-233">mssp</span></span>|http://schemas.microsoft.com/ws/2005/07/securitypolicy|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="388fc-234">1. 토큰 프로필</span><span class="sxs-lookup"><span data-stu-id="388fc-234">1. Token Profiles</span></span>  
 <span data-ttu-id="388fc-235">Web Services Security 사양에서는 자격 증명을 보안 토큰으로서 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="388fc-236">WCF에서는 다음과 같은 토큰 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="388fc-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="388fc-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="388fc-238">WCF에는 다음과 같은 제약 조건이 있는 UsernameToken10 및 UsernameToken11 프로필 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="388fc-239">UsernameToken\Password 요소의 R1101 PasswordType 특성은 생략되거나 그 값이 #PasswordText(기본값)여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="388fc-240">확장성을 사용하여 #PasswordDigest를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="388fc-241">#PasswordDigest가 보안 암호 보호 메커니즘으로 잘못 인식되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="388fc-242">그러나 #PasswordDigest는 UsernameToken 암호화를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="388fc-243">#PasswordDigest의 주요 목표는 재생 공격을 방지하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="388fc-244">WCF 인증 모드에서는 메시지 서명을 사용 하 여 재생 공격 위협은 완화 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="388fc-245">B1102 WCF 하지는 usernametoken Nonce 및 Created 하위 요소를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="388fc-246">이러한 하위 요소는 재생 검색을 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="388fc-247">WCF는 메시지 서명을 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="388fc-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1(UsernameToken11)에서는 암호로부터 키 파생 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="388fc-249">B1103 UsernameToken 암호는 키 파생에 사용할 수 없으므로 암호화 작업에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="388fc-250">설명: 암호는 일반적으로 암호화 작업에 사용하기에 너무 약합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="388fc-251">1.2 X509 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="388fc-252">WCF는에서는 X509v3 인증서를 자격 증명 형식 지원를 다음과 같은 제약 조건이 있는 X509TokenProfile1.0 및 X509TokenProfile1.1 따라가는입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="388fc-253">R1201 BinarySecurityToken 요소의 ValueType 특성은 X509v3 인증서를 포함할 경우 #X509v3 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="388fc-254">또한 WSS X509 Token Profile 1.0 및 1.1은 #X509PKIPathv1 및 #PKCS7을 값 형식으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="388fc-255">WCF에는 이러한 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="388fc-256">R1202 SKI(SubjectKeyIdentifier) 확장이 X509 인증서에 있으면 토큰에 대한 외부 참조로 wsse:KeyIdentifier를 사용해야 합니다. 이 때 ValueType 특성은 #X509SubjectKeyIdentifier이고 해당 내용에 base64 인코딩된 인증서 SKI 확장명 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="388fc-257">SKI 참조는 널리 구현되고 있으며 상호 운용성이 높은 외부 참조 형식으로 인정받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="388fc-258">R1203 X509 보안 토큰에 대한 외부 참조에는 ds:X509IssuerSerial을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="388fc-259">R1204 X509TokenProfile1.1이 사용 중인 경우 X509 보안 토큰에 대한 외부 참조에는 WS-Security 1.1을 통해 추가된 지문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="388fc-260">WCF는에서는 X509IssuerSerial을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="388fc-261">그러나 X509IssuerSerial와 상호 운용성 문제는: WCF 문자열로 사용 하 여 X509IssuerSerial의 두 값을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="388fc-262">따라서 주체 이름 구성 요소를 다시 정렬 하 고 인증서에 대 한 참조를 WCF 서비스에 보내는, 하는 경우이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="388fc-263">1.3 Kerberos 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="388fc-264">WCF에서는 다음과 같은 제약 조건으로 Windows 인증을 위해 KerberosTokenProfile1.1를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="388fc-265">R1301 Kerberos Token은 GSS_API 및 Kerberos 사양에 정의된 GSS 래핑된 Kerberos v4 AP_REQ 값을 사용하고, 값이 #GSS_Kerberosv5_AP_REQ인 ValueType 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="388fc-266">WCF에서는 GSS 래핑된 Kerberos AP-REQ를 하지는 완전 AP-요구 사항</span><span class="sxs-lookup"><span data-stu-id="388fc-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="388fc-267">이는 최선의 보안 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="388fc-268">1.4 SAML v1.1 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="388fc-269">WCF는 SAML v1.1 토큰 용 WSS SAML Token profiles 1.0 및 1.1을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="388fc-270">또한 다른 버전의 SAML 토큰 형식을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="388fc-271">1.5 보안 컨텍스트 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="388fc-272">WCF 보안 컨텍스트 토큰 (SCT) Ws-securecoversation에 도입 된 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="388fc-273">SCT는 아래에 설명하는 이진 협상 프로토콜 TLS 및 SSPI를 비롯하여 SecureConversation에 설정된 보안 컨텍스트를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="388fc-274">2. 일반 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="388fc-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="388fc-275">2.1 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="388fc-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="388fc-276">타임스탬프 표시 여부는 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 클래스의 <xref:System.ServiceModel.Channels.SecurityBindingElement> 속성을 사용하여 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="388fc-277">WCF에서는 wsse와 wsse: timestamp를 항상 serialize: 생성 및 wsse: Expires 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="388fc-278">wsse:TimeStamp는 서명이 사용될 경우 항상 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="388fc-279">2.2 보호 순서</span><span class="sxs-lookup"><span data-stu-id="388fc-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="388fc-280">WCF는 메시지 보호 순서가 "서명한 하기 전에 암호화" 및 "서명 전 암호화" (Security Policy 1.1)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="388fc-281">WS-Security 1.1 서명 확인 메커니즘을 사용하지 않을 경우 서명 전 암호화로 보호된 메시지는 서명 대체 공격에 취약하고, 암호화된 내용에 대한 서명으로 인해 감사를 수행하기 더 어려워지므로 "암호화 전 서명"을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="388fc-282">2.3 서명 보호</span><span class="sxs-lookup"><span data-stu-id="388fc-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="388fc-283">서명 전 암호화를 사용할 경우, 특히 사용자 지정 토큰을 weak 키 자료와 함께 사용하는 경우에는 암호화된 내용이나 서명 키를 추측하기 위한 무차별 키 대입 공격을 방지해 서명을 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="388fc-284">2.4 알고리즘 모음</span><span class="sxs-lookup"><span data-stu-id="388fc-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="388fc-285">WCF는 Security Policy 1.1에 나열 된 모든 알고리즘 모음을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="388fc-286">2.5 키 파생</span><span class="sxs-lookup"><span data-stu-id="388fc-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="388fc-287">WCF는 Ws-secureconversation에 설명 된 대로 "대칭 키에 대 한 키 파생"을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="388fc-288">2.6 서명 확인</span><span class="sxs-lookup"><span data-stu-id="388fc-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="388fc-289">서명 확인을 사용하여 중개자의 공격으로부터 서명 집합을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="388fc-290">2.7 보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="388fc-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="388fc-291">각 인증 모드에서는 보안 헤더에 대한 특정 레이아웃에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="388fc-292">보안 헤더 내의 요소는 일부 순서가 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="388fc-293">보안 헤더 자식 요소의 순서를 지정하기 위해 WS-Security 정책에서는 다음과 같은 보안 헤더 레이아웃 모드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="388fc-294">Strict</span><span class="sxs-lookup"><span data-stu-id="388fc-294">Strict</span></span>|<span data-ttu-id="388fc-295">"사용 전 선언"의 일반 원칙에 따라 보안 정책 7.7.1 단원에 설명된 번호가 매겨진 레이아웃 규칙을 따르는 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="388fc-296">Lax</span><span class="sxs-lookup"><span data-stu-id="388fc-296">Lax</span></span>|<span data-ttu-id="388fc-297">WSS: SOAP 메시지 보안에 따른 순서로 보안 헤더에 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="388fc-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="388fc-298">LaxTimestampFirst</span></span>|<span data-ttu-id="388fc-299">보안 헤더의 첫 번째 항목이 wsse:Timestamp여야 한다는 점을 제외하고 Lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="388fc-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="388fc-300">LaxTimestampLast</span></span>|<span data-ttu-id="388fc-301">보안 헤더의 마지막 항목이 wsse:Timestamp여야 한다는 점을 제외하고 lax와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="388fc-302">WCF 보안 헤더 레이아웃에 대 한 모든 4 가지 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="388fc-303">아래에 설명된 인증 모드에 대한 보안 헤더 구조 및 메시지 예제에서는 "Strict" 모드를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="388fc-304">2. 일반 메시지 보안 매개 변수</span><span class="sxs-lookup"><span data-stu-id="388fc-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="388fc-305">이 단원에서는 클라이언트와 서비스 간에 교환되는 메시지의 보안 헤더 구조를 보여 주는 예제와 함께 각 인증 모드에 대한 예제 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="388fc-306">6.1 전송 보호</span><span class="sxs-lookup"><span data-stu-id="388fc-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="388fc-307">WCF 보안 전송을 사용 하 여; 메시지를 보호 하는 다섯 가지 인증 모드를 제공 합니다. UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport 및 SspiNegotiatedOverTransport 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="388fc-308">이러한 인증 모드는 SecurityPolicy에 설명된 전송 바인딩을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="388fc-309">UserNameOverTransport 인증 모드의 경우 UsernameToken이 서명된 지원 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="388fc-310">다른 인증 모드의 경우 토큰이 서명된 보증 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="388fc-311">보안 헤더 레이아웃에 대해서는 SecurityPolicy의 부록 C.1.2 및 C.1.3에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="388fc-312">다음 예제 보안 헤더에서는 지정된 인증 모드에 대한 Strict 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="388fc-313">모든 경우의 토큰에 대한 "파생 키" 속성 값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="388fc-314">전송 바인딩의 다양한 속성 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="388fc-315">타임스탬프: true</span><span class="sxs-lookup"><span data-stu-id="388fc-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="388fc-316">보안 헤더 레이아웃: Strict</span><span class="sxs-lookup"><span data-stu-id="388fc-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="388fc-317">알고리즘 모음: Basic256</span><span class="sxs-lookup"><span data-stu-id="388fc-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="388fc-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="388fc-319">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="388fc-320">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="388fc-321">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="388fc-322">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-322">Policy</span></span>  
  
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
  
 <span data-ttu-id="388fc-323">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="388fc-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="388fc-324">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-324">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-325">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="388fc-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="388fc-327">이 인증 모드에서 클라이언트는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="388fc-328">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="388fc-329">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="388fc-330">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-330">Policy</span></span>  
  
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
  
 <span data-ttu-id="388fc-331">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="388fc-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="388fc-332">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-332">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-333">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="388fc-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="388fc-335">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS(보안 토큰 서비스)에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="388fc-336">발급된 토큰은 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="388fc-337">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="388fc-338">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="388fc-339">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-339">Policy</span></span>  
  
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
  
 <span data-ttu-id="388fc-340">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="388fc-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="388fc-341">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-341">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-342">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="388fc-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="388fc-344">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="388fc-345">Kerberos 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="388fc-346">서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="388fc-347">바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="388fc-348">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-348">Policy</span></span>  
  
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
  
 <span data-ttu-id="388fc-349">보안 헤더 레이아웃</span><span class="sxs-lookup"><span data-stu-id="388fc-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="388fc-350">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-350">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-351">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="388fc-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="388fc-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="388fc-353">이 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="388fc-354">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="388fc-355">결과 SCT는 항상 개시자로부터 수신자로 전송되는 보증 지원 토큰으로 SOAP 계층에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="388fc-356">서비스는 전송 계층에서 X.509 인증서를 사용하여 추가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="388fc-357">사용되는 바인딩은 전송 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-357">The binding used is a transport binding.</span></span> <span data-ttu-id="388fc-358">"SPNEGO" (협상) WCF Ws-trust와 함께 SSPI 이진 협상 프로토콜을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="388fc-359">이 단원의 보안 헤더 예제는 SPNEGO 핸드셰이크를 통해 SCT를 설정한 경우의 보안 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="388fc-360">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-360">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="388fc-361">보안 헤더 예제</span><span class="sxs-lookup"><span data-stu-id="388fc-361">Security Header Examples</span></span>  
 <span data-ttu-id="388fc-362">WS-Trust 이진 협상을 사용하여 SPNEGO 핸드셰이크를 통해 보안 컨텍스트 토큰을 설정한 경우, 응용 프로그램 메시지에 다음과 같은 구조의 보안 헤더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="388fc-363">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-363">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-364">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="388fc-365">6.2 X.509 인증서를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="388fc-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="388fc-366">이 단원에서는 MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate 및 IssuedTokenForCertificate 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="388fc-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="388fc-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="388fc-368">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="388fc-369">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="388fc-370">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="388fc-371">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="388fc-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="388fc-372">수신자 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="388fc-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="388fc-373">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-374">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-375">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-376">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-377">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-377">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-378">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-379">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-379">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-380">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-380">Response</span></span>  
  
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
  
 <span data-ttu-id="388fc-381">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="388fc-382">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-382">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-383">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-383">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="388fc-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="388fc-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="388fc-385">이 인증 모드에서 클라이언트는 SOAP 계층에 개시자 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="388fc-386">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="388fc-387">사용되는 바인딩은 다음과 같은 속성 값을 가진 비대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="388fc-388">개시자 토큰: 포함 모드가 …/IncludeToken/AlwaysToRecipient로 설정된 클라이언트의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="388fc-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="388fc-389">수신자 토큰: 포함 모드가 …/IncludeToken/AlwaysToInitiator로 설정된 서버의 X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="388fc-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="388fc-390">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-391">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-392">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-393">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-394">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-394">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-395">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-396">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="388fc-396">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-397">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-398">요청 및 응답</span><span class="sxs-lookup"><span data-stu-id="388fc-398">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="388fc-399">6.2.3 X.509 서비스 인증에서 SymmetricBinding 사용</span><span class="sxs-lookup"><span data-stu-id="388fc-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="388fc-400">"WSS10"에서는 X509 토큰 사용 시나리오를 제한적으로 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="388fc-401">예를 들어, 서비스 X509 토큰만 사용하여 메시지에 대한 서명 및 암호화 보호를 제공할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="388fc-402">"WSS11"에서는 EncryptedKey를 대칭 토큰으로 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="388fc-403">이제 요청 메시지 보호와 응답 메시지 보호에 서비스의 X.509 인증서에 대해 암호화된 임시 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="388fc-404">아래 6.4 단원에 설명된 인증 모드에서는 이 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="388fc-405">WS-SecurityPolicy에서는 Service X509 토큰을 보호 토큰으로 사용하여 SymmetricBinding을 통해 이 패턴을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="388fc-406">AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 및 IssuedTokenForCertificate 인증 모드는 모두 다음 속성 값을 가진 비슷한 sp:SymmetricBinding 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="388fc-407">보호 토큰: 포함 모드가 …/IncludeToken/Never로 설정된 서버의 X509 인증서</span><span class="sxs-lookup"><span data-stu-id="388fc-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="388fc-408">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-409">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-410">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-411">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-412">위의 인증 모드는 사용하는 지원 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="388fc-413">AnonymousForCertificate의 경우 토큰이 없으며, MutualCertificate WSS 1.1의 경우 클라이언트의 X509 인증서를 보증 지원 토큰으로 사용하고, UserNameForCertificate의 경우 사용자 이름 토큰을 서명된 지원 토큰으로 사용하고, IssuedTokenForCertificate의 경우 발급된 토큰을 보증 지원 토큰으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="388fc-414">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-414">Policy</span></span>  
  
 <span data-ttu-id="388fc-415">대칭 바인딩</span><span class="sxs-lookup"><span data-stu-id="388fc-415">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="388fc-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="388fc-417">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="388fc-418">사용되는 바인딩은 6.4.2에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="388fc-419">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-419">Policy</span></span>  
  
 <span data-ttu-id="388fc-420">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-421">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-422">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-422">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-423">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-423">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-424">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-425">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-425">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-426">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-426">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="388fc-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="388fc-428">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="388fc-429">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="388fc-430">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="388fc-431">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-431">Policy</span></span>  
  
 <span data-ttu-id="388fc-432">바인딩에 대한 자세한 내용은 위 6.2.3의 "정책"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="388fc-433">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-433">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-434">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-435">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-435">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-436">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-436">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-437">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-438">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-438">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-439">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-439">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="388fc-440">6.2.6 MutualCertificate(WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="388fc-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="388fc-441">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="388fc-442">서비스도 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="388fc-443">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="388fc-444">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-444">Policy</span></span>  
  
 <span data-ttu-id="388fc-445">바인딩에 대한 자세한 내용은 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="388fc-446">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-446">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-447">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-448">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-448">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-449">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-449">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-450">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-451">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-451">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-452">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-452">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="388fc-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="388fc-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="388fc-454">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="388fc-455">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="388fc-456">서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="388fc-457">사용되는 바인딩은 서비스의 공개 키로 암호화되고 클라이언트에서 생성한 키를 보호 토큰으로 사용하는 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="388fc-458">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-458">Policy</span></span>  
  
 <span data-ttu-id="388fc-459">바인딩에 대한 자세한 내용은 위 6.2.3의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="388fc-460">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-460">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-461">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-462">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-462">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-463">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-463">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-464">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-465">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-465">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-466">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-466">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="388fc-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="388fc-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="388fc-468">이 인증 모드에서 클라이언트는 Kerberos 티켓을 사용하여 서비스를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="388fc-469">동일한 티켓에서 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="388fc-470">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="388fc-471">보호 토큰: 포함 모드가 .../IncludeToken/Once로 설정된 Kerberos 티켓</span><span class="sxs-lookup"><span data-stu-id="388fc-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="388fc-472">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-473">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-474">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-475">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-476">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-476">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-477">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-478">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-478">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-479">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-479">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-480">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-481">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="388fc-482">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="388fc-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="388fc-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="388fc-484">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="388fc-485">서비스가 클라이언트에 인증되지 않습니다. 대신 STS에서 공유 키를 발급된 토큰의 일부로 암호화하여 서비스에서만 키를 해독할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="388fc-486">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="388fc-487">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="388fc-488">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-489">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-490">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-491">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-492">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-492">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-493">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-494">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-494">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-495">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-495">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-496">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-497">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-497">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-498">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-498">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="388fc-499">6.5 SslNegotiated를 사용하여 서비스 인증</span><span class="sxs-lookup"><span data-stu-id="388fc-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="388fc-500">이 단원에서는 보호 토큰이 WS-T(WS-Trust) RST/RSTR 메시지를 통해 TLS 프로토콜을 실행하여 그 키 값이 협상되는 WS-SC(WS-SecureConversation)별 보안 컨텍스트 토큰인 대칭 바인딩을 사용하는 인증 모드 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="388fc-501">WS-Trust를 사용하는 TLS 핸드셰이크 구현에 대한 자세한 내용은 TLSNEGO를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="388fc-502">여기의 메시지 예제에서는 연결된 보안 컨텍스트가 있는 SCT가 핸드셰이크를 통해 이미 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="388fc-503">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="388fc-504">보호 토큰: 포함 모드가 .../IncludeToken/Never로 설정된 SslContextToken</span><span class="sxs-lookup"><span data-stu-id="388fc-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="388fc-505">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-506">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-507">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-508">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="388fc-509">6.5.1 SslNegotiated 서비스 인증 정책</span><span class="sxs-lookup"><span data-stu-id="388fc-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="388fc-510">이 단원의 모든 인증 모드에 대한 정책은 비슷하며 사용되는 특정 서명된 지원 토큰과 보증 토큰만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="388fc-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="388fc-512">이 인증 모드에서 클라이언트는 비대칭이고, 서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="388fc-513">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="388fc-514">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-514">Policy</span></span>  
  
 <span data-ttu-id="388fc-515">바인딩에 대한 자세한 내용은 위 6.5.1의 정책을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-516">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-517">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-517">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-518">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-518">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-519">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-520">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-520">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-521">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-521">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="388fc-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="388fc-523">이 인증 모드에서 클라이언트는 SOAP 계층에 서명된 지원 토큰으로 표시되는 사용자 이름 토큰을 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="388fc-524">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="388fc-525">사용되는 바인딩은 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="388fc-526">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-526">Policy</span></span>  
  
 <span data-ttu-id="388fc-527">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="388fc-528">서명된 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-528">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-529">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-530">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-530">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-531">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-531">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-532">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-533">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-533">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-534">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-534">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="388fc-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="388fc-536">이 인증 모드에서 클라이언트는 서비스를 인증하지 않고 대신 STS에서 발급한 토큰을 제공하고 공유 키에 대해 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="388fc-537">발급된 토큰은 SOAP 계층에 보증 지원 토큰으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="388fc-538">서비스는 X.509 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="388fc-539">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="388fc-540">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-540">Policy</span></span>  
  
 <span data-ttu-id="388fc-541">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="388fc-542">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-542">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-543">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-544">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-544">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-545">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-545">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-546">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-547">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-547">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-548">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-548">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="388fc-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="388fc-550">이 인증 모드에서 클라이언트 및 서비스는 X.509 인증서를 사용하여 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="388fc-551">사용되는 바인딩은 위 6.5.1에 설명된 것처럼 대칭 바인딩 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="388fc-552">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-552">Policy</span></span>  
  
 <span data-ttu-id="388fc-553">바인딩에 대한 자세한 내용은 위 6.5.1 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388fc-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="388fc-554">보증 지원 토큰</span><span class="sxs-lookup"><span data-stu-id="388fc-554">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-555">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-556">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-556">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-557">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-557">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-558">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-559">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-559">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-560">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-560">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="388fc-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="388fc-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="388fc-562">이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="388fc-563">가능하면 Kerberos를 사용하고, 그렇지 않으면 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="388fc-564">사용되는 바인딩은 다음과 같은 속성을 가진 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="388fc-565">보호 토큰: 포함 모드가 .../IncludeToken/AlwaysToRecipient로 설정된 SpnegoContextToken</span><span class="sxs-lookup"><span data-stu-id="388fc-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="388fc-566">토큰 보호: False</span><span class="sxs-lookup"><span data-stu-id="388fc-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="388fc-567">전체 헤더 및 본문 서명: True</span><span class="sxs-lookup"><span data-stu-id="388fc-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="388fc-568">보호 순서: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="388fc-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="388fc-569">서명 암호화: True</span><span class="sxs-lookup"><span data-stu-id="388fc-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="388fc-570">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-570">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-571">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-572">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-572">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-573">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-573">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-574">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-575">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-575">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-576">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-576">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="388fc-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="388fc-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="388fc-578">사용되는 바인딩은 보호 토큰이 WS-SC(WS-SecureConversation)별 SCT인 대칭 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="388fc-579">SCT는 그 자체가 협상 프로토콜을 사용하는 대칭 바인딩인 중첩 바인딩에 따라 WS-Trust(WS-Trust) 또는 WS-SC(WS-SecureConversation)를 사용하여 협상됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="388fc-580">협상 프로토콜은 가능하면 Kerberos를 사용하여 클라이언트 및 서버 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="388fc-581">Kerberos를 사용할 수 없는 경우 NTLM으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="388fc-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="388fc-582">정책</span><span class="sxs-lookup"><span data-stu-id="388fc-582">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="388fc-583">보안 헤더 예: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="388fc-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="388fc-584">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-584">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-585">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-585">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="388fc-586">보안 헤더 예: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="388fc-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="388fc-587">요청</span><span class="sxs-lookup"><span data-stu-id="388fc-587">Request</span></span>  
  
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
  
 <span data-ttu-id="388fc-588">응답</span><span class="sxs-lookup"><span data-stu-id="388fc-588">Response</span></span>  
  
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
