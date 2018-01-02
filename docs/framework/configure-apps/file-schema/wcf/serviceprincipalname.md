---
title: "&lt;서비스 사용자 이름&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f9b4ec506097cf010af78b3504def08102e0774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="e2596-102">&lt;서비스 사용자 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="e2596-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="e2596-103">SPN(서비스 사용자 이름)으로 서비스 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="e2596-104">SPN을 설정 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="e2596-105">\<identity ></span><span class="sxs-lookup"><span data-stu-id="e2596-105">\<identity></span></span>  
<span data-ttu-id="e2596-106">\<서비스 사용자 이름 ></span><span class="sxs-lookup"><span data-stu-id="e2596-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2596-107">구문</span><span class="sxs-lookup"><span data-stu-id="e2596-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2596-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e2596-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2596-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2596-110">특성</span><span class="sxs-lookup"><span data-stu-id="e2596-110">Attributes</span></span>  
  
|<span data-ttu-id="e2596-111">특성</span><span class="sxs-lookup"><span data-stu-id="e2596-111">Attribute</span></span>|<span data-ttu-id="e2596-112">설명</span><span class="sxs-lookup"><span data-stu-id="e2596-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2596-113">값</span><span class="sxs-lookup"><span data-stu-id="e2596-113">value</span></span>|<span data-ttu-id="e2596-114">클라이언트에서 서비스의 인스턴스를 고유하게 식별하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="e2596-115">포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="e2596-116">클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2596-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e2596-117">Child Elements</span></span>  
 <span data-ttu-id="e2596-118">없음</span><span class="sxs-lookup"><span data-stu-id="e2596-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2596-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e2596-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e2596-120">요소</span><span class="sxs-lookup"><span data-stu-id="e2596-120">Element</span></span>|<span data-ttu-id="e2596-121">설명</span><span class="sxs-lookup"><span data-stu-id="e2596-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2596-122">\<identity ></span><span class="sxs-lookup"><span data-stu-id="e2596-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e2596-123">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2596-124">설명</span><span class="sxs-lookup"><span data-stu-id="e2596-124">Remarks</span></span>  
 <span data-ttu-id="e2596-125">이 ID를 가진 끝점과 연결되는 보안 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트는 이 끝점에 대해 SSPI 인증을 수행할 때 SPN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2596-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2596-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2596-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="e2596-127">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="e2596-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e2596-128">\<identity ></span><span class="sxs-lookup"><span data-stu-id="e2596-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
