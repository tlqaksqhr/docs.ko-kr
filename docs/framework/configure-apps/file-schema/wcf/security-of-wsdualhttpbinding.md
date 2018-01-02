---
title: "&lt;wsDualHttpBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4b90bd304ef8d87593c5b78febc0182c8fa2f091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="b5a2b-102">&lt;wsDualHttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="b5a2b-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="b5a2b-103">보안 기능을 정의 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="b5a2b-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5a2b-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-105">\<bindings></span></span>  
<span data-ttu-id="b5a2b-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="b5a2b-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-107">\<binding></span></span>  
<span data-ttu-id="b5a2b-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a2b-109">구문</span><span class="sxs-lookup"><span data-stu-id="b5a2b-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5a2b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b5a2b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5a2b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5a2b-112">특성</span><span class="sxs-lookup"><span data-stu-id="b5a2b-112">Attributes</span></span>  
  
|<span data-ttu-id="b5a2b-113">특성</span><span class="sxs-lookup"><span data-stu-id="b5a2b-113">Attribute</span></span>|<span data-ttu-id="b5a2b-114">설명</span><span class="sxs-lookup"><span data-stu-id="b5a2b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5a2b-115">모드</span><span class="sxs-lookup"><span data-stu-id="b5a2b-115">mode</span></span>|<span data-ttu-id="b5a2b-116">-선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-116">-   Optional.</span></span> <span data-ttu-id="b5a2b-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b5a2b-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-118">The default value is `Message`.</span></span> <span data-ttu-id="b5a2b-119">이 특성은 <xref:System.ServiceModel.WSDualHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b5a2b-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="b5a2b-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="b5a2b-121">값</span><span class="sxs-lookup"><span data-stu-id="b5a2b-121">Value</span></span>|<span data-ttu-id="b5a2b-122">설명</span><span class="sxs-lookup"><span data-stu-id="b5a2b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b5a2b-123">없음</span><span class="sxs-lookup"><span data-stu-id="b5a2b-123">None</span></span>|<span data-ttu-id="b5a2b-124">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-124">Security is disabled.</span></span>|  
|<span data-ttu-id="b5a2b-125">메시지</span><span class="sxs-lookup"><span data-stu-id="b5a2b-125">Message</span></span>|<span data-ttu-id="b5a2b-126">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5a2b-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b5a2b-127">Child Elements</span></span>  
  
|<span data-ttu-id="b5a2b-128">요소</span><span class="sxs-lookup"><span data-stu-id="b5a2b-128">Element</span></span>|<span data-ttu-id="b5a2b-129">설명</span><span class="sxs-lookup"><span data-stu-id="b5a2b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a2b-130">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="b5a2b-131">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b5a2b-132">이 요소는 <xref:System.ServiceModel.MessageSecurityOverHttp> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5a2b-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b5a2b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b5a2b-134">요소</span><span class="sxs-lookup"><span data-stu-id="b5a2b-134">Element</span></span>|<span data-ttu-id="b5a2b-135">설명</span><span class="sxs-lookup"><span data-stu-id="b5a2b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a2b-136">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b5a2b-137">모든 바인딩 기능을 정의 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5a2b-138">설명</span><span class="sxs-lookup"><span data-stu-id="b5a2b-138">Remarks</span></span>  
 <span data-ttu-id="b5a2b-139">이중 바인딩은 클라이언트의 IP 주소를 서비스에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="b5a2b-140">클라이언트는 보안을 사용하여 신뢰하는 서비스에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5a2b-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a2b-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5a2b-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="b5a2b-142">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b5a2b-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b5a2b-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="b5a2b-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b5a2b-144">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b5a2b-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b5a2b-145">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b5a2b-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b5a2b-146">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5a2b-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
