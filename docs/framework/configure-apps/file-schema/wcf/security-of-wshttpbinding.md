---
title: '&lt;wsHttpBinding&gt;의 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 836e920ef7c95d4a7a2b752c2f76f29d8c880e7c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750468"
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="4de80-102">&lt;wsHttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="4de80-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="4de80-103">보안 기능을 나타내는 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="4de80-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4de80-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4de80-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4de80-105">\<bindings></span></span>  
<span data-ttu-id="4de80-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4de80-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="4de80-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4de80-107">\<binding></span></span>  
<span data-ttu-id="4de80-108">\<security></span><span class="sxs-lookup"><span data-stu-id="4de80-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de80-109">구문</span><span class="sxs-lookup"><span data-stu-id="4de80-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4de80-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4de80-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4de80-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4de80-112">특성</span><span class="sxs-lookup"><span data-stu-id="4de80-112">Attributes</span></span>  
  
|<span data-ttu-id="4de80-113">특성</span><span class="sxs-lookup"><span data-stu-id="4de80-113">Attribute</span></span>|<span data-ttu-id="4de80-114">설명</span><span class="sxs-lookup"><span data-stu-id="4de80-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4de80-115">모드</span><span class="sxs-lookup"><span data-stu-id="4de80-115">mode</span></span>|<span data-ttu-id="4de80-116">-선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-116">-   Optional.</span></span> <span data-ttu-id="4de80-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="4de80-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-118">The default is `Message`.</span></span><br /><span data-ttu-id="4de80-119">-이 특성은 형식 <xref:System.ServiceModel.SecurityMode>합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4de80-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="4de80-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="4de80-121">값</span><span class="sxs-lookup"><span data-stu-id="4de80-121">Value</span></span>|<span data-ttu-id="4de80-122">설명</span><span class="sxs-lookup"><span data-stu-id="4de80-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4de80-123">없음</span><span class="sxs-lookup"><span data-stu-id="4de80-123">None</span></span>|<span data-ttu-id="4de80-124">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-124">Security is disabled.</span></span>|  
|<span data-ttu-id="4de80-125">전송</span><span class="sxs-lookup"><span data-stu-id="4de80-125">Transport</span></span>|<span data-ttu-id="4de80-126">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="4de80-127">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="4de80-128">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="4de80-129">클라이언트 인증은 `ClientCredentials`의</span><span class="sxs-lookup"><span data-stu-id="4de80-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="4de80-130">[ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="4de80-131">메시지</span><span class="sxs-lookup"><span data-stu-id="4de80-131">Message</span></span>|<span data-ttu-id="4de80-132">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="4de80-133">기본적으로 SOAP 본문은 암호화 및 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="4de80-134">이 모드는 서비스 자격 증명을 클라이언트에서 out of band 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 그리고 Security.Message 속성을 통해 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="4de80-135">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="4de80-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="4de80-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="4de80-137">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="4de80-138">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4de80-139">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4de80-139">Child Elements</span></span>  
  
|<span data-ttu-id="4de80-140">요소</span><span class="sxs-lookup"><span data-stu-id="4de80-140">Element</span></span>|<span data-ttu-id="4de80-141">설명</span><span class="sxs-lookup"><span data-stu-id="4de80-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4de80-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="4de80-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="4de80-143">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-143">Defines the transport security settings.</span></span> <span data-ttu-id="4de80-144">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="4de80-145">\<message></span><span class="sxs-lookup"><span data-stu-id="4de80-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="4de80-146">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-146">Defines the security settings for the message.</span></span> <span data-ttu-id="4de80-147">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4de80-148">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4de80-148">Parent Elements</span></span>  
  
|<span data-ttu-id="4de80-149">요소</span><span class="sxs-lookup"><span data-stu-id="4de80-149">Element</span></span>|<span data-ttu-id="4de80-150">설명</span><span class="sxs-lookup"><span data-stu-id="4de80-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4de80-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4de80-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="4de80-152">HTTP 전송 응용 프로그램에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4de80-153">설명</span><span class="sxs-lookup"><span data-stu-id="4de80-153">Remarks</span></span>  
 <span data-ttu-id="4de80-154">WSHttpBinding 클래스는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="4de80-155">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="4de80-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de80-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4de80-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="4de80-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="4de80-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4de80-158">바인딩</span><span class="sxs-lookup"><span data-stu-id="4de80-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4de80-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="4de80-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4de80-160">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4de80-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4de80-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="4de80-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
