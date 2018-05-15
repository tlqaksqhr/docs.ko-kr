---
title: '&lt;ws2007FederationHttpBinding&gt;의 &lt;security&gt; 요소'
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5f1a7d0ed1bffe2ca2da9318eef700b1d4924c22
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="92990-102">&lt;ws2007FederationHttpBinding&gt;의 &lt;security&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="92990-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="92990-103">보안 설정을 정의 [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92990-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="92990-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92990-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="92990-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="92990-105">\<bindings></span></span>  
<span data-ttu-id="92990-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="92990-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="92990-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="92990-107">\<binding></span></span>  
<span data-ttu-id="92990-108">\<security></span><span class="sxs-lookup"><span data-stu-id="92990-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92990-109">구문</span><span class="sxs-lookup"><span data-stu-id="92990-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92990-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="92990-110">Attributes and Elements</span></span>  
 <span data-ttu-id="92990-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92990-112">특성</span><span class="sxs-lookup"><span data-stu-id="92990-112">Attributes</span></span>  
  
|<span data-ttu-id="92990-113">특성</span><span class="sxs-lookup"><span data-stu-id="92990-113">Attribute</span></span>|<span data-ttu-id="92990-114">설명</span><span class="sxs-lookup"><span data-stu-id="92990-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="92990-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="92990-115">Optional.</span></span> <span data-ttu-id="92990-116">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="92990-117">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="92990-117">The default value is `Message`.</span></span> <span data-ttu-id="92990-118">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="92990-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="92990-119">mode 특성</span><span class="sxs-lookup"><span data-stu-id="92990-119">mode Attribute</span></span>  
  
|<span data-ttu-id="92990-120">값</span><span class="sxs-lookup"><span data-stu-id="92990-120">Value</span></span>|<span data-ttu-id="92990-121">설명</span><span class="sxs-lookup"><span data-stu-id="92990-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="92990-122">없음</span><span class="sxs-lookup"><span data-stu-id="92990-122">None</span></span>|<span data-ttu-id="92990-123">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92990-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="92990-124">메시지</span><span class="sxs-lookup"><span data-stu-id="92990-124">Message</span></span>|<span data-ttu-id="92990-125">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="92990-126">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="92990-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="92990-127">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="92990-128">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="92990-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="92990-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="92990-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="92990-130">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="92990-131">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="92990-132">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="92990-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92990-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="92990-133">Child Elements</span></span>  
  
|<span data-ttu-id="92990-134">요소</span><span class="sxs-lookup"><span data-stu-id="92990-134">Element</span></span>|<span data-ttu-id="92990-135">설명</span><span class="sxs-lookup"><span data-stu-id="92990-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92990-136">\<message></span><span class="sxs-lookup"><span data-stu-id="92990-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="92990-137">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="92990-138">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="92990-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92990-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="92990-139">Parent Elements</span></span>  
  
|<span data-ttu-id="92990-140">요소</span><span class="sxs-lookup"><span data-stu-id="92990-140">Element</span></span>|<span data-ttu-id="92990-141">설명</span><span class="sxs-lookup"><span data-stu-id="92990-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92990-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="92990-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="92990-143">모든 바인딩 기능을 정의 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92990-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92990-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92990-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="92990-145">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="92990-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="92990-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="92990-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="92990-147">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="92990-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="92990-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="92990-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="92990-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="92990-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="92990-150">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="92990-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="92990-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="92990-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
