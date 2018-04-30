---
title: Windows 인증 오류 디버깅
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
- WCF, Windows authentication
ms.assetid: 181be4bd-79b1-4a66-aee2-931887a6d7cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 39c033d45488b827a4aee7439904db8094795db4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="debugging-windows-authentication-errors"></a><span data-ttu-id="87117-102">Windows 인증 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="87117-102">Debugging Windows Authentication Errors</span></span>
<span data-ttu-id="87117-103">Windows 인증을 보안 메커니즘으로 사용하면 SSPI(보안 지원 공급자 인터페이스)에서 보안 프로세스를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-103">When using Windows authentication as a security mechanism, the Security Support Provider Interface (SSPI) handles security processes.</span></span> <span data-ttu-id="87117-104">SSPI 계층에 보안 오류가 발생하면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-104">When security errors occur at the SSPI layer, they are surfaced by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="87117-105">이 항목에서는 오류 진단에 도움이 되는 프레임워크 및 일련의 질문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-105">This topic provides a framework and set of questions to help diagnose the errors.</span></span>  
  
 <span data-ttu-id="87117-106">Kerberos 프로토콜의 개요를 참조 하십시오. [Kerberos 설명](http://go.microsoft.com/fwlink/?LinkID=86946)SSPI의 개요를 참조 하세요. [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941)합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-106">For an overview of the Kerberos protocol, see [Kerberos Explained](http://go.microsoft.com/fwlink/?LinkID=86946); for an overview of SSPI, see [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941).</span></span>  
  
 <span data-ttu-id="87117-107">Windows 인증을 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 일반적으로 사용 하 여는 *Negotiate* 공급자 SSP (Security Support), 클라이언트와 서비스 간의 Kerberos 상호 인증을 수행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-107">For Windows authentication, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] typically uses the *Negotiate* Security Support Provider (SSP), which performs Kerberos mutual authentication between the client and service.</span></span> <span data-ttu-id="87117-108">Kerberos 프로토콜을 사용할 수 없는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 기본적으로 NTLM(NT LAN Manager)으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-108">If the Kerberos protocol is not available, by default [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] falls back to NT LAN Manager (NTLM).</span></span> <span data-ttu-id="87117-109">그러나 Kerberos 프로토콜만 사용하고 Kerberos를 사용할 수 없는 경우 예외를 throw하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-109">However, you can configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use only the Kerberos protocol (and to throw an exception if Kerberos is not available).</span></span> <span data-ttu-id="87117-110">또한 제한된 형식의 Kerberos 프로토콜을 사용하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-110">You can also configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use restricted forms of the Kerberos protocol.</span></span>  
  
## <a name="debugging-methodology"></a><span data-ttu-id="87117-111">디버깅 방법</span><span class="sxs-lookup"><span data-stu-id="87117-111">Debugging Methodology</span></span>  
 <span data-ttu-id="87117-112">기본 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-112">The basic method is as follows:</span></span>  
  
1.  <span data-ttu-id="87117-113">Windows 인증 사용 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-113">Determine whether you are using Windows authentication.</span></span> <span data-ttu-id="87117-114">다른 스키마를 사용할 경우 이 항목이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-114">If you are using any other scheme, this topic does not apply.</span></span>  
  
2.  <span data-ttu-id="87117-115">Windows 인증을 사용하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성에서 Kerberos를 직접 사용할지 또는 협상을 통해 사용할지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-115">If you are sure you are using Windows authentication, determine whether your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration uses Kerberos direct or Negotiate.</span></span>  
  
3.  <span data-ttu-id="87117-116">구성에서 Kerberos 프로토콜을 사용할지 또는 NTLM을 사용할지 결정한 다음에는 올바른 컨텍스트에서 오류 메시지를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-116">Once you have determined whether your configuration is using the Kerberos protocol or NTLM, you can understand error messages in the correct context.</span></span>  
  
### <a name="availability-of-the-kerberos-protocol-and-ntlm"></a><span data-ttu-id="87117-117">Kerberos 프로토콜 및 NTLM 사용 가능성</span><span class="sxs-lookup"><span data-stu-id="87117-117">Availability of the Kerberos Protocol and NTLM</span></span>  
 <span data-ttu-id="87117-118">Kerberos SSP에는 Kerberos KDC(키 배포 센터) 역할을 하는 도메인 컨트롤러가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-118">The Kerberos SSP requires a domain controller to act as the Kerberos Key Distribution Center (KDC).</span></span> <span data-ttu-id="87117-119">Kerberos 프로토콜은 클라이언트와 서비스 둘 다에서 도메인 ID를 사용하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-119">The Kerberos protocol is available only when both the client and service are using domain identities.</span></span> <span data-ttu-id="87117-120">다음 표에 요약된 것처럼 다른 계정 조합의 경우 NTLM이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-120">In other account combinations, NTLM is used, as summarized in the following table.</span></span>  
  
 <span data-ttu-id="87117-121">표 머리글에는 서버에서 사용할 수 있는 계정 형식이 표시되어 있으며,</span><span class="sxs-lookup"><span data-stu-id="87117-121">The table headers show possible account types used by the server.</span></span> <span data-ttu-id="87117-122">왼쪽 열에는 클라이언트에서 사용할 수 있는 계정 형식이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-122">The left column shows possible account types used by the client.</span></span>  
  
||<span data-ttu-id="87117-123">로컬 사용자</span><span class="sxs-lookup"><span data-stu-id="87117-123">Local User</span></span>|<span data-ttu-id="87117-124">로컬 시스템</span><span class="sxs-lookup"><span data-stu-id="87117-124">Local System</span></span>|<span data-ttu-id="87117-125">도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="87117-125">Domain User</span></span>|<span data-ttu-id="87117-126">도메인 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="87117-126">Domain Machine</span></span>|  
|-|----------------|------------------|-----------------|--------------------|  
|<span data-ttu-id="87117-127">로컬 사용자</span><span class="sxs-lookup"><span data-stu-id="87117-127">Local User</span></span>|<span data-ttu-id="87117-128">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-128">NTLM</span></span>|<span data-ttu-id="87117-129">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-129">NTLM</span></span>|<span data-ttu-id="87117-130">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-130">NTLM</span></span>|<span data-ttu-id="87117-131">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-131">NTLM</span></span>|  
|<span data-ttu-id="87117-132">로컬 시스템</span><span class="sxs-lookup"><span data-stu-id="87117-132">Local System</span></span>|<span data-ttu-id="87117-133">익명 NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-133">Anonymous NTLM</span></span>|<span data-ttu-id="87117-134">익명 NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-134">Anonymous NTLM</span></span>|<span data-ttu-id="87117-135">익명 NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-135">Anonymous NTLM</span></span>|<span data-ttu-id="87117-136">익명 NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-136">Anonymous NTLM</span></span>|  
|<span data-ttu-id="87117-137">도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="87117-137">Domain User</span></span>|<span data-ttu-id="87117-138">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-138">NTLM</span></span>|<span data-ttu-id="87117-139">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-139">NTLM</span></span>|<span data-ttu-id="87117-140">Kerberos</span><span class="sxs-lookup"><span data-stu-id="87117-140">Kerberos</span></span>|<span data-ttu-id="87117-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="87117-141">Kerberos</span></span>|  
|<span data-ttu-id="87117-142">도메인 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="87117-142">Domain Machine</span></span>|<span data-ttu-id="87117-143">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-143">NTLM</span></span>|<span data-ttu-id="87117-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="87117-144">NTLM</span></span>|<span data-ttu-id="87117-145">Kerberos</span><span class="sxs-lookup"><span data-stu-id="87117-145">Kerberos</span></span>|<span data-ttu-id="87117-146">Kerberos</span><span class="sxs-lookup"><span data-stu-id="87117-146">Kerberos</span></span>|  
  
 <span data-ttu-id="87117-147">특히 네 가지 계정 형식에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-147">Specifically, the four account types include:</span></span>  
  
-   <span data-ttu-id="87117-148">로컬 사용자: 시스템 전용 사용자 프로필.</span><span class="sxs-lookup"><span data-stu-id="87117-148">Local User: Machine-only user profile.</span></span> <span data-ttu-id="87117-149">예를 들면 `MachineName\Administrator` 또는 `MachineName\ProfileName` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-149">For example: `MachineName\Administrator` or `MachineName\ProfileName`.</span></span>  
  
-   <span data-ttu-id="87117-150">로컬 시스템: 도메인에 연결되지 않은 컴퓨터의 기본 제공 계정인 SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="87117-150">Local System: The built-in account SYSTEM on a machine that is not joined to a domain.</span></span>  
  
-   <span data-ttu-id="87117-151">도메인 사용자: Windows 도메인의 사용자 계정.</span><span class="sxs-lookup"><span data-stu-id="87117-151">Domain User: A user account on a Windows domain.</span></span> <span data-ttu-id="87117-152">예: `DomainName\ProfileName`</span><span class="sxs-lookup"><span data-stu-id="87117-152">For example: `DomainName\ProfileName`.</span></span>  
  
-   <span data-ttu-id="87117-153">도메인 컴퓨터: Windows 도메인에 연결된 컴퓨터에서 실행 중인 컴퓨터 ID가 있는 프로세스.</span><span class="sxs-lookup"><span data-stu-id="87117-153">Domain Machine: A process with machine identity running on a machine joined to a Windows domain.</span></span> <span data-ttu-id="87117-154">예: `MachineName\Network Service`</span><span class="sxs-lookup"><span data-stu-id="87117-154">For example: `MachineName\Network Service`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87117-155">서비스 자격 증명은 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 클래스의 <xref:System.ServiceModel.ServiceHost> 메서드가 호출될 때 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-155">The service credential is captured when the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method of the <xref:System.ServiceModel.ServiceHost> class is called.</span></span> <span data-ttu-id="87117-156">클라이언트 자격 증명은 클라이언트가 메시지를 보낼 때마다 읽어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="87117-156">The client credential is read whenever the client sends a message.</span></span>  
  
## <a name="common-windows-authentication-problems"></a><span data-ttu-id="87117-157">일반적인 Windows 인증 문제</span><span class="sxs-lookup"><span data-stu-id="87117-157">Common Windows Authentication Problems</span></span>  
 <span data-ttu-id="87117-158">이 단원에서는 몇 가지 일반적인 Windows 인증 문제와 그 해결 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-158">This section discusses some common Windows authentication problems and possible remedies.</span></span>  
  
### <a name="kerberos-protocol"></a><span data-ttu-id="87117-159">Kerberos 프로토콜</span><span class="sxs-lookup"><span data-stu-id="87117-159">Kerberos Protocol</span></span>  
  
#### <a name="spnupn-problems-with-the-kerberos-protocol"></a><span data-ttu-id="87117-160">Kerberos 프로토콜에 대한 SPN/UPN 문제</span><span class="sxs-lookup"><span data-stu-id="87117-160">SPN/UPN Problems with the Kerberos Protocol</span></span>  
 <span data-ttu-id="87117-161">Windows 인증을 사용할 때 Kerberos 프로토콜을 사용하거나 SSPI 협상을 수행하는 경우, 클라이언트 끝점에 사용되는 URL은 서비스 URL 내에 있는 서비스 호스트의 정규화된 도메인 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-161">When using Windows authentication, and the Kerberos protocol is used or negotiated by SSPI, the URL the client endpoint uses must include the fully qualified domain name of the service's host inside the service URL.</span></span> <span data-ttu-id="87117-162">이 가정 아래에 있는 서비스를 실행 하 여 가장 일반적으로 수행 되는 Active Directory 도메인에 컴퓨터 추가 될 때 만들어지는 컴퓨터 (기본값) 서비스 사용자 이름 (SPN) 키에 대 한 액세스 서비스가 실행 중인 계정에는 네트워크 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-162">This assumes that the account under which the service is running has access to the machine (default) service principal name (SPN) key that is created when the computer is added to the Active Directory domain, which is most commonly done by running the service under the Network Service account.</span></span> <span data-ttu-id="87117-163">서비스에 시스템 SPN 키에 대한 액세스 권한이 없는 경우 클라이언트의 끝점 ID로 서비스가 실행 중인 계정의 올바른 SPN 또는 UPN(User Principal Name)을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-163">If the service does not have access to the machine SPN key, you must supply the correct SPN or user principal name (UPN) of the account under which the service is running in the client's endpoint identity.</span></span> <span data-ttu-id="87117-164">방법에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SPN 및 UPN을 사용 하 여 참조 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-164">For more information about how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] works with SPN and UPN, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="87117-165">웹 팜 또는 웹 가든과 같은 부하 분산 시나리오에서는 각 응용 프로그램에 대해 고유한 계정을 정의하고, 해당 계정에 SPN을 할당하고, 응용 프로그램의 모든 서비스가 해당 계정으로 실행되도록 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-165">In load-balancing scenarios, such as Web farms or Web gardens, a common practice is to define a unique account for each application, assign an SPN to that account, and ensure that all of the application's services run in that account.</span></span>  
  
 <span data-ttu-id="87117-166">서비스 계정에 대한 SPN을 얻으려면 Active Directory 도메인 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-166">To obtain an SPN for your service's account, you need to be an Active Directory domain administrator.</span></span> <span data-ttu-id="87117-167">자세한 내용은 참조 [Windows Kerberos 기술 자료에 대 한](http://go.microsoft.com/fwlink/?LinkID=88330)합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-167">For more information, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkID=88330).</span></span>  
  
#### <a name="kerberos-protocol-direct-requires-the-service-to-run-under-a-domain-machine-account"></a><span data-ttu-id="87117-168">Kerberos 프로토콜을 직접 사용하려면 도메인 컴퓨터 계정으로 서비스 실행이 필요</span><span class="sxs-lookup"><span data-stu-id="87117-168">Kerberos Protocol Direct Requires the Service to Run Under a Domain Machine Account</span></span>  
 <span data-ttu-id="87117-169">이는 다음 코드처럼 `ClientCredentialType` 속성이 `Windows`로 설정되고, <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> 속성이 `false`로 설정된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-169">This occurs when the `ClientCredentialType` property is set to `Windows` and the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> property is set to `false`, as shown in the following code.</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#1)]
 [!code-vb[C_DebuggingWindowsAuth#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#1)]  
  
 <span data-ttu-id="87117-170">이 문제를 해결하려면 도메인과 연결된 컴퓨터에서 Network Service 등의 도메인 컴퓨터 계정을 사용하여 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-170">To remedy, run the service using a Domain Machine account, such as Network Service, on a domain joined machine.</span></span>  
  
### <a name="delegation-requires-credential-negotiation"></a><span data-ttu-id="87117-171">위임에 자격 증명 협상 필요</span><span class="sxs-lookup"><span data-stu-id="87117-171">Delegation Requires Credential Negotiation</span></span>  
 <span data-ttu-id="87117-172">Kerberos 인증 프로토콜을 위임과 함께 사용하려면 자격 증명 협상이 포함된 Kerberos 프로토콜("multi-leg" 또는 "multi-step" Kerberos라고 함)을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-172">To use the Kerberos authentication protocol with delegation, you must implement the Kerberos protocol with credential negotiation (sometimes called "multi-leg" or "multi-step" Kerberos).</span></span> <span data-ttu-id="87117-173">자격 증명 협상이 포함되지 않은 Kerberos 프로토콜("one-shot" 또는 "single-leg" Kerberos라고도 함)을 구현하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-173">If you implement Kerberos authentication without credential negotiation (sometimes called "one-shot" or "single-leg" Kerberos), an exception will be thrown.</span></span>  
  
 <span data-ttu-id="87117-174">자격 증명 협상이 포함된 Kerberos 프로토콜을 구현하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-174">To implement Kerberos with credential negotiation, do the following steps:</span></span>  
  
1.  <span data-ttu-id="87117-175"><xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>을 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>으로 설정하여 위임을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-175">Implement delegation by setting <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> to <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span>  
  
2.  <span data-ttu-id="87117-176">SSPI 협상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-176">Require SSPI negotiation:</span></span>  
  
    1.  <span data-ttu-id="87117-177">표준 바인딩을 사용하는 경우 `NegotiateServiceCredential` 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-177">If you are using standard bindings, set the `NegotiateServiceCredential` property to `true`.</span></span>  
  
    2.  <span data-ttu-id="87117-178">사용자 지정 바인딩을 사용하는 경우 `AuthenticationMode` 요소의 `Security` 속성을 `SspiNegotiated`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-178">If you are using custom bindings, set the `AuthenticationMode` attribute of the `Security` element to `SspiNegotiated`.</span></span>  
  
3.  <span data-ttu-id="87117-179">NTLM 사용을 허용하지 않고 Kerberos를 사용하려면 SSPI 협상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-179">Require the SSPI negotiation to use Kerberos by disallowing the use of NTLM:</span></span>  
  
    1.  <span data-ttu-id="87117-180">`ChannelFactory.Credentials.Windows.AllowNtlm = false` 문과 함께 코드에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-180">Do this in code, with the following statement: `ChannelFactory.Credentials.Windows.AllowNtlm = false`</span></span>  
  
    2.  <span data-ttu-id="87117-181">`allowNtlm` 특성을 `false`로 설정하여 구성 파일에서 이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-181">Or you can do this in the configuration file by setting the `allowNtlm` attribute to `false`.</span></span> <span data-ttu-id="87117-182">이 특성에 포함 되어는 [ \<windows >](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-182">This attribute is contained in the [\<windows>](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md).</span></span>  
  
### <a name="ntlm-protocol"></a><span data-ttu-id="87117-183">NTLM 프로토콜</span><span class="sxs-lookup"><span data-stu-id="87117-183">NTLM Protocol</span></span>  
  
#### <a name="negotiate-ssp-falls-back-to-ntlm-but-ntlm-is-disabled"></a><span data-ttu-id="87117-184">협상 SSP가 NTLM으로 대체되어도 NTLM을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="87117-184">Negotiate SSP Falls Back to NTLM, but NTLM Is Disabled</span></span>  
 <span data-ttu-id="87117-185"><xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> 속성이 `false`로 설정되어 있어 NTLM이 사용될 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-185">The <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> property is set to `false`, which causes [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="87117-186">이 속성을 `false`로 설정하면 유선을 통해 NTLM 자격 증명을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-186">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>  
  
 <span data-ttu-id="87117-187">다음은 NTLM으로 대체되지 않도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87117-187">The following shows how to disable fallback to NTLM.</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#4)]
 [!code-vb[C_DebuggingWindowsAuth#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#4)]  
  
#### <a name="ntlm-logon-fails"></a><span data-ttu-id="87117-188">NTLM 로그온 실패</span><span class="sxs-lookup"><span data-stu-id="87117-188">NTLM Logon Fails</span></span>  
 <span data-ttu-id="87117-189">클라이언트 자격 증명이 서비스에 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-189">The client credentials are not valid on the service.</span></span> <span data-ttu-id="87117-190">사용자 이름과 암호를 올바르게 설정했는지, 서비스를 실행하는 컴퓨터에서 인식하는 계정과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-190">Check that the user name and password are correctly set and correspond to an account that is known to the computer where the service is running.</span></span> <span data-ttu-id="87117-191">NTLM에서는 서비스의 컴퓨터에 로그온하기 위해 지정된 자격 증명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-191">NTLM uses the specified credentials to log on to the service's computer.</span></span> <span data-ttu-id="87117-192">클라이언트를 실행하는 컴퓨터에서 유효한 자격 증명이라도 서비스의 컴퓨터에서 유효하지 않으면 로그온이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-192">While the credentials may be valid on the computer where the client is running, this logon will fail if the credentials are not valid on the service's computer.</span></span>  
  
#### <a name="anonymous-ntlm-logon-occurs-but-anonymous-logons-are-disabled-by-default"></a><span data-ttu-id="87117-193">익명 NTLM 로그온을 수행해도 기본적으로 익명 로그온을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="87117-193">Anonymous NTLM Logon Occurs, but Anonymous Logons Are Disabled by Default</span></span>  
 <span data-ttu-id="87117-194">클라이언트를 만들 때 다음 예제에서처럼 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 속성이 <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>로 설정되지만 기본적으로 서버에서 익명 로그온을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-194">When creating a client, the <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property is set to <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, as shown in the following example, but by default the server disallows anonymous logons.</span></span> <span data-ttu-id="87117-195">이는 <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A> 클래스의 <xref:System.ServiceModel.Security.WindowsServiceCredential> 속성의 기본값이 `false`로 설정되기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-195">This occurs because the default value of the <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A> property of the <xref:System.ServiceModel.Security.WindowsServiceCredential> class is `false`.</span></span>  
  
 <span data-ttu-id="87117-196">다음 클라이언트 코드에서는 익명 로그온을 사용하도록 설정합니다. 기본 속성은 `Identification`입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-196">The following client code attempts to enable anonymous logons (note that the default property is `Identification`).</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#5)]
 [!code-vb[C_DebuggingWindowsAuth#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#5)]  
  
 <span data-ttu-id="87117-197">다음 서비스 코드에서는 서버에서 익명 로그온을 사용하도록 기본값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-197">The following service code changes the default to enable anonymous logons by the server.</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#6)]
 [!code-vb[C_DebuggingWindowsAuth#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#6)]  
  
 <span data-ttu-id="87117-198">가장에 대 한 자세한 내용은 참조 [위임 및 가장](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-198">For more information about impersonation, see [Delegation and Impersonation](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
 <span data-ttu-id="87117-199">또는 기본 제공 계정인 SYSTEM을 사용하여 클라이언트를 Windows 서비스로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-199">Alternatively, the client is running as a Windows service, using the built-in account SYSTEM.</span></span>  
  
### <a name="other-problems"></a><span data-ttu-id="87117-200">기타 문제</span><span class="sxs-lookup"><span data-stu-id="87117-200">Other Problems</span></span>  
  
#### <a name="client-credentials-are-not-set-correctly"></a><span data-ttu-id="87117-201">클라이언트 자격 증명이 올바르게 설정되지 않음</span><span class="sxs-lookup"><span data-stu-id="87117-201">Client Credentials Are Not Set Correctly</span></span>  
 <span data-ttu-id="87117-202">Windows 인증에서는 <xref:System.ServiceModel.Security.WindowsClientCredential>을 사용하지 않고, <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성에서 반환된 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential> 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87117-202">Windows authentication uses the <xref:System.ServiceModel.Security.WindowsClientCredential> instance returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class, not the <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>.</span></span> <span data-ttu-id="87117-203">다음은 잘못된 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-203">The following shows an incorrect example.</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#2)]
 [!code-vb[C_DebuggingWindowsAuth#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#2)]  
  
 <span data-ttu-id="87117-204">다음은 올바른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="87117-204">The following shows the correct example.</span></span>  
  
 [!code-csharp[C_DebuggingWindowsAuth#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#3)]
 [!code-vb[C_DebuggingWindowsAuth#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#3)]  
  
#### <a name="sspi-is-not-available"></a><span data-ttu-id="87117-205">SSPI를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="87117-205">SSPI Is Not Available</span></span>  
 <span data-ttu-id="87117-206">다음 운영 체제 서버로 사용 될 때 Windows 인증을 지원 하지 않습니다: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]Home edition.</span><span class="sxs-lookup"><span data-stu-id="87117-206">The following operating systems do not support Windows authentication when used as a server: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition, and [!INCLUDE[wv](../../../../includes/wv-md.md)]Home editions.</span></span>  
  
#### <a name="developing-and-deploying-with-different-identities"></a><span data-ttu-id="87117-207">다른 ID로 개발 및 배포</span><span class="sxs-lookup"><span data-stu-id="87117-207">Developing and Deploying with Different Identities</span></span>  
 <span data-ttu-id="87117-208">응용 프로그램을 한 컴퓨터에서 개발하여 다른 컴퓨터에 배포하고 서로 다른 계정 형식을 사용하여 각 컴퓨터에서 인증을 수행하면 동작이 동일하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-208">If you develop your application on one machine, and deploy on another, and use different account types to authenticate on each machine, you may experience different behavior.</span></span> <span data-ttu-id="87117-209">예를 들어 `SSPI Negotiated` 인증 모드를 사용하여 Windows XP Pro 컴퓨터에서 응용 프로그램을 개발할 경우</span><span class="sxs-lookup"><span data-stu-id="87117-209">For example, suppose you develop your application on a Windows XP Pro machine using the `SSPI Negotiated` authentication mode.</span></span> <span data-ttu-id="87117-210">로컬 사용자 계정을 사용하여 인증하면 NTLM 프로토콜이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87117-210">If you use a local user account to authenticate with, then NTLM protocol will be used.</span></span> <span data-ttu-id="87117-211">응용 프로그램 개발을 마친 후 도메인 계정으로 실행되는 Windows Server 2003 컴퓨터에 해당 서비스를 배포하면</span><span class="sxs-lookup"><span data-stu-id="87117-211">Once the application is developed, you deploy the service to a Windows Server 2003 machine where it runs under a domain account.</span></span> <span data-ttu-id="87117-212">클라이언트에서는 Kerberos 및 도메인 컨트롤러를 사용할 것이므로 해당 서비스를 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87117-212">At this point the client will not be able to authenticate the service because it will be using Kerberos and a domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87117-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87117-213">See Also</span></span>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 [<span data-ttu-id="87117-214">위임 및 가장</span><span class="sxs-lookup"><span data-stu-id="87117-214">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [<span data-ttu-id="87117-215">지원되지 않는 시나리오</span><span class="sxs-lookup"><span data-stu-id="87117-215">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
