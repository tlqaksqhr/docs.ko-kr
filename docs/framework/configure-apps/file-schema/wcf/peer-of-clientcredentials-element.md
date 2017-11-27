---
title: "&lt;clientCredentials&gt; 요소의 &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f26321afdbe53c4ab3750eae4a7a730bcb5ae4e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="d25fe-102">&lt;clientCredentials&gt; 요소의 &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="d25fe-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="d25fe-103">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="d25fe-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d25fe-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d25fe-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d25fe-105">\<behaviors></span></span>  
<span data-ttu-id="d25fe-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d25fe-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d25fe-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d25fe-107">\<behavior></span></span>  
<span data-ttu-id="d25fe-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="d25fe-108">\<clientCredentials></span></span>  
<span data-ttu-id="d25fe-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="d25fe-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25fe-110">구문</span><span class="sxs-lookup"><span data-stu-id="d25fe-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d25fe-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d25fe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d25fe-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d25fe-113">특성</span><span class="sxs-lookup"><span data-stu-id="d25fe-113">Attributes</span></span>  
 <span data-ttu-id="d25fe-114">없음</span><span class="sxs-lookup"><span data-stu-id="d25fe-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d25fe-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d25fe-115">Child Elements</span></span>  
  
|<span data-ttu-id="d25fe-116">요소</span><span class="sxs-lookup"><span data-stu-id="d25fe-116">Element</span></span>|<span data-ttu-id="d25fe-117">설명</span><span class="sxs-lookup"><span data-stu-id="d25fe-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d25fe-118">\<인증서 ></span><span class="sxs-lookup"><span data-stu-id="d25fe-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="d25fe-119">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="d25fe-120">입니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-120">.</span></span>|  
|[<span data-ttu-id="d25fe-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d25fe-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="d25fe-122">피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="d25fe-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d25fe-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="d25fe-124">메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d25fe-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d25fe-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d25fe-126">요소</span><span class="sxs-lookup"><span data-stu-id="d25fe-126">Element</span></span>|<span data-ttu-id="d25fe-127">설명</span><span class="sxs-lookup"><span data-stu-id="d25fe-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d25fe-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="d25fe-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="d25fe-129">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d25fe-130">설명</span><span class="sxs-lookup"><span data-stu-id="d25fe-130">Remarks</span></span>  
 <span data-ttu-id="d25fe-131">이 구성 요소는 피어 노드가 메시에서 다른 노드로부터 인증을 얻는 데 사용하는 자격 증명과 피어 노드가 다른 피어 노드를 인증하는 데 사용하는 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="d25fe-132">자세한 내용은 참조 [피어 채널 메시지 인증](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) 및 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d25fe-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25fe-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d25fe-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="d25fe-134">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="d25fe-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="d25fe-135">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d25fe-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="d25fe-136">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="d25fe-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="d25fe-137">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="d25fe-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="d25fe-138">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="d25fe-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="d25fe-139">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d25fe-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
