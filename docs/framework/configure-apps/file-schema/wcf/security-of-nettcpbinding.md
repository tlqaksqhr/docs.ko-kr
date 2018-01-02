---
title: "&lt;netTcpBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 08e9f1f3b2145d94f491933639211a6eabd3c9fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="19de1-102">&lt;netTcpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="19de1-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="19de1-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="19de1-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="19de1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="19de1-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="19de1-105">\<bindings></span></span>  
<span data-ttu-id="19de1-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="19de1-106">\<netTcpBinding></span></span>  
<span data-ttu-id="19de1-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="19de1-107">\<binding></span></span>  
<span data-ttu-id="19de1-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="19de1-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19de1-109">구문</span><span class="sxs-lookup"><span data-stu-id="19de1-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19de1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19de1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19de1-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19de1-112">특성</span><span class="sxs-lookup"><span data-stu-id="19de1-112">Attributes</span></span>  
  
|<span data-ttu-id="19de1-113">특성</span><span class="sxs-lookup"><span data-stu-id="19de1-113">Attribute</span></span>|<span data-ttu-id="19de1-114">설명</span><span class="sxs-lookup"><span data-stu-id="19de1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19de1-115">모드</span><span class="sxs-lookup"><span data-stu-id="19de1-115">mode</span></span>|<span data-ttu-id="19de1-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-116">Optional.</span></span> <span data-ttu-id="19de1-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="19de1-118">유효한 값이 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-118">Valid values are shown below.</span></span> <span data-ttu-id="19de1-119">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="19de1-120">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="19de1-121">mode 특성</span><span class="sxs-lookup"><span data-stu-id="19de1-121">mode Attribute</span></span>  
  
|<span data-ttu-id="19de1-122">값</span><span class="sxs-lookup"><span data-stu-id="19de1-122">Value</span></span>|<span data-ttu-id="19de1-123">설명</span><span class="sxs-lookup"><span data-stu-id="19de1-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="19de1-124">없음</span><span class="sxs-lookup"><span data-stu-id="19de1-124">None</span></span>|<span data-ttu-id="19de1-125">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-125">Security is disabled.</span></span>|  
|<span data-ttu-id="19de1-126">전송</span><span class="sxs-lookup"><span data-stu-id="19de1-126">Transport</span></span>|<span data-ttu-id="19de1-127">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="19de1-128">서비스는 SSL 인증서로 구성해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="19de1-129">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="19de1-130">메시지</span><span class="sxs-lookup"><span data-stu-id="19de1-130">Message</span></span>|<span data-ttu-id="19de1-131">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="19de1-132">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="19de1-133">이 모드는 서비스 자격 증명을 클라이언트에서 밴드 외 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="19de1-134">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="19de1-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="19de1-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="19de1-136">전송 보안이 메시지 보안과 결합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="19de1-137">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공되며 무결성, 기밀성 및 서버 인증을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="19de1-138">SOAP 메시지 보안에서는 클라이언트 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="19de1-139">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19de1-140">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19de1-140">Child Elements</span></span>  
  
|<span data-ttu-id="19de1-141">요소</span><span class="sxs-lookup"><span data-stu-id="19de1-141">Element</span></span>|<span data-ttu-id="19de1-142">설명</span><span class="sxs-lookup"><span data-stu-id="19de1-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19de1-143">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="19de1-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="19de1-144">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="19de1-145">이 요소는 <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="19de1-146">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="19de1-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="19de1-147">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-147">Defines the security settings for the message.</span></span> <span data-ttu-id="19de1-148">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19de1-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19de1-149">Parent Elements</span></span>  
  
|<span data-ttu-id="19de1-150">요소</span><span class="sxs-lookup"><span data-stu-id="19de1-150">Element</span></span>|<span data-ttu-id="19de1-151">설명</span><span class="sxs-lookup"><span data-stu-id="19de1-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19de1-152">바인딩</span><span class="sxs-lookup"><span data-stu-id="19de1-152">binding</span></span>|<span data-ttu-id="19de1-153">바인딩 요소는 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19de1-154">설명</span><span class="sxs-lookup"><span data-stu-id="19de1-154">Remarks</span></span>  
 <span data-ttu-id="19de1-155">각 표준 바인딩은 전송 보안 요구 사항을 제어하는 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="19de1-156">일반적으로 이러한 매개 변수에는 메시지 수준 보안이 사용되는지 또는 전송 수준 보안이 사용되는지 지정한 보안 모드 및 선택한 클라이언트 자격 증명 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="19de1-157">이러한 매개 변수가 나타내는 선택 옵션에 따라 채널 스택이 해당 보안을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="19de1-158">WCF(Windows Communication Foundation)에서 제공하는 시스템 제공 바인딩은 가장 일반적인 일부 시나리오의 요구 사항을 충족하기 위한 집합입니다</span><span class="sxs-lookup"><span data-stu-id="19de1-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="19de1-159">이러한 각 바인딩을 사용하면 일부 특정 대상 시나리오의 보안 요구 사항을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="19de1-160">이 구성 요소는 `netTcpBinding`의 보안 사양을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="19de1-161">이것은 시스템 간 통신에 적합한 안전하고, 신뢰할 수 있으며, 최적화된 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="19de1-162">기본적으로 메시지 배달을 위한 TCP, 메시지 보안 및 인증을 위한 Windows 보안, 안정성을 위한 WS-Reliable Messaging 및 이진 메시지 인코딩을 지원하는 런타임 통신 스택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="19de1-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19de1-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19de1-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="19de1-164">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="19de1-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="19de1-165">바인딩</span><span class="sxs-lookup"><span data-stu-id="19de1-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="19de1-166">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="19de1-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="19de1-167">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="19de1-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="19de1-168">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="19de1-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
