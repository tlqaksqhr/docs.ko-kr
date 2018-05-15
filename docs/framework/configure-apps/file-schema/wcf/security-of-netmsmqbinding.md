---
title: '&lt;netMsmqBinding&gt;의 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0ed1021bdc45d0d64a20ff19410ad56e0d304ed3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="f6977-102">&lt;netMsmqBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="f6977-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="f6977-103">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="f6977-104">이 클래스는 전송 또는 SOAP 보안의 사용 여부 그리고 보안이 사용된다면 어떤 인증 모드 및 보호 수준을 사용하는지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="f6977-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f6977-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6977-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="f6977-106">\<bindings></span></span>  
<span data-ttu-id="f6977-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="f6977-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="f6977-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="f6977-108">\<binding></span></span>  
<span data-ttu-id="f6977-109">\<security></span><span class="sxs-lookup"><span data-stu-id="f6977-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6977-110">구문</span><span class="sxs-lookup"><span data-stu-id="f6977-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6977-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f6977-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f6977-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6977-113">특성</span><span class="sxs-lookup"><span data-stu-id="f6977-113">Attributes</span></span>  
  
|<span data-ttu-id="f6977-114">특성</span><span class="sxs-lookup"><span data-stu-id="f6977-114">Attribute</span></span>|<span data-ttu-id="f6977-115">설명</span><span class="sxs-lookup"><span data-stu-id="f6977-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6977-116">모드</span><span class="sxs-lookup"><span data-stu-id="f6977-116">mode</span></span>|<span data-ttu-id="f6977-117">무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="f6977-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f6977-119">-None: 보안이 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-119">-   None: This disables security.</span></span><br /><span data-ttu-id="f6977-120">-Transport: 보호 및 인증이 전송에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="f6977-121">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="f6977-122">응용 프로그램 및 큐 관리자 간에는 제공되는 보안이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="f6977-123">기존 Msmq 응용 프로그램이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="f6977-124">-메시지: 종단 간 응용 프로그램 보안을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="f6977-125">전송 계층에는 제공되는 보안이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="f6977-126">이는 다른 표준 바인딩에 의해 제공되는 보안과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="f6977-127">-Both: 전송 및 SOAP 메시징 계층 모두에 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="f6977-128">두 수준 모두에서 동일한 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="f6977-129">기본값은 Transport입니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-129">The default value is Transport.</span></span> <span data-ttu-id="f6977-130">이 특성은 <xref:System.ServiceModel.NetMsmqSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6977-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f6977-131">Child Elements</span></span>  
  
|<span data-ttu-id="f6977-132">요소</span><span class="sxs-lookup"><span data-stu-id="f6977-132">Element</span></span>|<span data-ttu-id="f6977-133">설명</span><span class="sxs-lookup"><span data-stu-id="f6977-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6977-134">\<message></span><span class="sxs-lookup"><span data-stu-id="f6977-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="f6977-135">SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="f6977-136">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="f6977-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="f6977-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="f6977-138">MSMQ 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="f6977-139">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f6977-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6977-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f6977-140">Parent Elements</span></span>  
  
|<span data-ttu-id="f6977-141">요소</span><span class="sxs-lookup"><span data-stu-id="f6977-141">Element</span></span>|<span data-ttu-id="f6977-142">설명</span><span class="sxs-lookup"><span data-stu-id="f6977-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6977-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="f6977-143">binding</span></span>|<span data-ttu-id="f6977-144">바인딩 요소는 [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f6977-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6977-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6977-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="f6977-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f6977-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f6977-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="f6977-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f6977-148">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="f6977-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f6977-149">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f6977-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f6977-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="f6977-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="f6977-151">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="f6977-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
