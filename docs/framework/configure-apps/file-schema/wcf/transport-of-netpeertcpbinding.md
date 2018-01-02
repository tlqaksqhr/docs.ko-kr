---
title: "&lt;netPeerTcpBinding&gt;의 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3e933e1c3468a09b1d6b089b4abf52dad85017
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="017f4-102">&lt;netPeerTcpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="017f4-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="017f4-103">전송 수준 보안에 대 한 설정을 사용 하는 경우 지정 된 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="017f4-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="017f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="017f4-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="017f4-105">\<bindings></span></span>  
<span data-ttu-id="017f4-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="017f4-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="017f4-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="017f4-107">\<binding></span></span>  
<span data-ttu-id="017f4-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="017f4-108">\<security></span></span>  
<span data-ttu-id="017f4-109">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="017f4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="017f4-110">구문</span><span class="sxs-lookup"><span data-stu-id="017f4-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="017f4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="017f4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="017f4-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="017f4-113">특성</span><span class="sxs-lookup"><span data-stu-id="017f4-113">Attributes</span></span>  
  
|<span data-ttu-id="017f4-114">특성</span><span class="sxs-lookup"><span data-stu-id="017f4-114">Attribute</span></span>|<span data-ttu-id="017f4-115">설명</span><span class="sxs-lookup"><span data-stu-id="017f4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="017f4-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="017f4-116">credentialType</span></span>|<span data-ttu-id="017f4-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-117">Optional.</span></span> <span data-ttu-id="017f4-118">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="017f4-119">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="017f4-120">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="017f4-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="017f4-121">값</span><span class="sxs-lookup"><span data-stu-id="017f4-121">Value</span></span>|<span data-ttu-id="017f4-122">설명</span><span class="sxs-lookup"><span data-stu-id="017f4-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="017f4-123">인증서</span><span class="sxs-lookup"><span data-stu-id="017f4-123">Certificate</span></span>|<span data-ttu-id="017f4-124">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="017f4-125">암호</span><span class="sxs-lookup"><span data-stu-id="017f4-125">Password</span></span>|<span data-ttu-id="017f4-126">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="017f4-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="017f4-127">Child Elements</span></span>  
 <span data-ttu-id="017f4-128">없음</span><span class="sxs-lookup"><span data-stu-id="017f4-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="017f4-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="017f4-129">Parent Elements</span></span>  
  
|<span data-ttu-id="017f4-130">요소</span><span class="sxs-lookup"><span data-stu-id="017f4-130">Element</span></span>|<span data-ttu-id="017f4-131">설명</span><span class="sxs-lookup"><span data-stu-id="017f4-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="017f4-132">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="017f4-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="017f4-133">에 대 한 보안 설정을 정의 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="017f4-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="017f4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="017f4-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="017f4-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="017f4-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="017f4-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="017f4-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="017f4-137">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="017f4-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="017f4-138">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="017f4-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="017f4-139">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="017f4-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
