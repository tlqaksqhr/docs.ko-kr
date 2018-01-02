---
title: "&lt;peerTransport&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="a60d1-102">&lt;peerTransport&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="a60d1-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="a60d1-103">메시지 전송에 사용되는 인증 형식 및 보안을 비롯하여 피어 채널과 연결된 보안 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="a60d1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a60d1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a60d1-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a60d1-105">\<bindings></span></span>  
<span data-ttu-id="a60d1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a60d1-106">\<customBinding></span></span>  
<span data-ttu-id="a60d1-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a60d1-107">\<binding></span></span>  
<span data-ttu-id="a60d1-108">\<r t ></span><span class="sxs-lookup"><span data-stu-id="a60d1-108">\<peerTransport></span></span>  
<span data-ttu-id="a60d1-109">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="a60d1-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a60d1-110">구문</span><span class="sxs-lookup"><span data-stu-id="a60d1-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a60d1-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a60d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a60d1-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a60d1-113">특성</span><span class="sxs-lookup"><span data-stu-id="a60d1-113">Attributes</span></span>  
  
|<span data-ttu-id="a60d1-114">특성</span><span class="sxs-lookup"><span data-stu-id="a60d1-114">Attribute</span></span>|<span data-ttu-id="a60d1-115">설명</span><span class="sxs-lookup"><span data-stu-id="a60d1-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="a60d1-116">적용할 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="a60d1-117">기본값은 Message입니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-117">The default value is Message.</span></span> <span data-ttu-id="a60d1-118">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a60d1-119">mode 특성</span><span class="sxs-lookup"><span data-stu-id="a60d1-119">mode Attribute</span></span>  
  
|<span data-ttu-id="a60d1-120">값</span><span class="sxs-lookup"><span data-stu-id="a60d1-120">Value</span></span>|<span data-ttu-id="a60d1-121">설명</span><span class="sxs-lookup"><span data-stu-id="a60d1-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="a60d1-122">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="a60d1-123">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="a60d1-124">SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="a60d1-125">HTTPS는 인증 및 기밀성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="a60d1-126">SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a60d1-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a60d1-127">Child Elements</span></span>  
  
|<span data-ttu-id="a60d1-128">요소</span><span class="sxs-lookup"><span data-stu-id="a60d1-128">Element</span></span>|<span data-ttu-id="a60d1-129">설명</span><span class="sxs-lookup"><span data-stu-id="a60d1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a60d1-130">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="a60d1-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="a60d1-131">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="a60d1-132">이 요소에는 서비스와 상호 작용할 때 사용되는 자격 증명을 지정하는 `clientCredentialType` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="a60d1-133">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="a60d1-134">이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a60d1-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a60d1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a60d1-136">요소</span><span class="sxs-lookup"><span data-stu-id="a60d1-136">Element</span></span>|<span data-ttu-id="a60d1-137">설명</span><span class="sxs-lookup"><span data-stu-id="a60d1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a60d1-138">\<r t ></span><span class="sxs-lookup"><span data-stu-id="a60d1-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="a60d1-139">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a60d1-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a60d1-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a60d1-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a60d1-141">전송 보안</span><span class="sxs-lookup"><span data-stu-id="a60d1-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="a60d1-142">전송</span><span class="sxs-lookup"><span data-stu-id="a60d1-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="a60d1-143">전송 선택</span><span class="sxs-lookup"><span data-stu-id="a60d1-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="a60d1-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="a60d1-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a60d1-145">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="a60d1-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a60d1-146">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="a60d1-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a60d1-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a60d1-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
