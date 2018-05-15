---
title: '&lt;netPeerTcpBinding&gt;의 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: c94336413424542f6fc6c0ef5b400b10ae715cd8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="fcb96-102">&lt;netPeerTcpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="fcb96-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="fcb96-103">전송 수준 보안에 대 한 설정을 사용 하는 경우 지정 된 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="fcb96-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fcb96-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fcb96-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fcb96-105">\<bindings></span></span>  
<span data-ttu-id="fcb96-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="fcb96-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="fcb96-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fcb96-107">\<binding></span></span>  
<span data-ttu-id="fcb96-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fcb96-108">\<security></span></span>  
<span data-ttu-id="fcb96-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="fcb96-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb96-110">구문</span><span class="sxs-lookup"><span data-stu-id="fcb96-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcb96-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fcb96-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fcb96-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcb96-113">특성</span><span class="sxs-lookup"><span data-stu-id="fcb96-113">Attributes</span></span>  
  
|<span data-ttu-id="fcb96-114">특성</span><span class="sxs-lookup"><span data-stu-id="fcb96-114">Attribute</span></span>|<span data-ttu-id="fcb96-115">설명</span><span class="sxs-lookup"><span data-stu-id="fcb96-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcb96-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="fcb96-116">credentialType</span></span>|<span data-ttu-id="fcb96-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-117">Optional.</span></span> <span data-ttu-id="fcb96-118">피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="fcb96-119">이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="fcb96-120">credentialType 특성</span><span class="sxs-lookup"><span data-stu-id="fcb96-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="fcb96-121">값</span><span class="sxs-lookup"><span data-stu-id="fcb96-121">Value</span></span>|<span data-ttu-id="fcb96-122">설명</span><span class="sxs-lookup"><span data-stu-id="fcb96-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fcb96-123">인증서</span><span class="sxs-lookup"><span data-stu-id="fcb96-123">Certificate</span></span>|<span data-ttu-id="fcb96-124">피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="fcb96-125">암호</span><span class="sxs-lookup"><span data-stu-id="fcb96-125">Password</span></span>|<span data-ttu-id="fcb96-126">피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcb96-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fcb96-127">Child Elements</span></span>  
 <span data-ttu-id="fcb96-128">없음</span><span class="sxs-lookup"><span data-stu-id="fcb96-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fcb96-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fcb96-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fcb96-130">요소</span><span class="sxs-lookup"><span data-stu-id="fcb96-130">Element</span></span>|<span data-ttu-id="fcb96-131">설명</span><span class="sxs-lookup"><span data-stu-id="fcb96-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcb96-132">\<security></span><span class="sxs-lookup"><span data-stu-id="fcb96-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="fcb96-133">에 대 한 보안 설정을 정의 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcb96-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcb96-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcb96-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="fcb96-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fcb96-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fcb96-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="fcb96-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fcb96-137">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="fcb96-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fcb96-138">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="fcb96-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fcb96-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="fcb96-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
