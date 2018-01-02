---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34bfaeb563bd4979bf29a5e45a60730eb38700b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="ee66b-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="ee66b-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="ee66b-103">클라이언트에서 인증할 서비스의 UPN(User Principal Name)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="ee66b-104">UPN을 설정 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="ee66b-105">\<identity ></span><span class="sxs-lookup"><span data-stu-id="ee66b-105">\<identity></span></span>  
<span data-ttu-id="ee66b-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="ee66b-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee66b-107">구문</span><span class="sxs-lookup"><span data-stu-id="ee66b-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee66b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee66b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ee66b-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee66b-110">특성</span><span class="sxs-lookup"><span data-stu-id="ee66b-110">Attributes</span></span>  
  
|<span data-ttu-id="ee66b-111">특성</span><span class="sxs-lookup"><span data-stu-id="ee66b-111">Attribute</span></span>|<span data-ttu-id="ee66b-112">설명</span><span class="sxs-lookup"><span data-stu-id="ee66b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee66b-113">값</span><span class="sxs-lookup"><span data-stu-id="ee66b-113">value</span></span>|<span data-ttu-id="ee66b-114">사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="ee66b-115">Windows 도메인에 로그온하는 표준 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="ee66b-116">형식은: someone@example.com (경우와 전자 메일 주소).</span><span class="sxs-lookup"><span data-stu-id="ee66b-116">The format is: someone@example.com (as for an e-mail address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee66b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee66b-117">Child Elements</span></span>  
 <span data-ttu-id="ee66b-118">없음</span><span class="sxs-lookup"><span data-stu-id="ee66b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee66b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee66b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee66b-120">요소</span><span class="sxs-lookup"><span data-stu-id="ee66b-120">Element</span></span>|<span data-ttu-id="ee66b-121">설명</span><span class="sxs-lookup"><span data-stu-id="ee66b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee66b-122">\<identity ></span><span class="sxs-lookup"><span data-stu-id="ee66b-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ee66b-123">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee66b-124">설명</span><span class="sxs-lookup"><span data-stu-id="ee66b-124">Remarks</span></span>  
 <span data-ttu-id="ee66b-125">이 ID를 가진 끝점과 연결되는 보안 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트는 이 끝점에 대해 SSPI 인증을 사용할 때 UPN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee66b-126">예</span><span class="sxs-lookup"><span data-stu-id="ee66b-126">Example</span></span>  
 <span data-ttu-id="ee66b-127">다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee66b-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee66b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee66b-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="ee66b-129">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="ee66b-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="ee66b-130">\<identity ></span><span class="sxs-lookup"><span data-stu-id="ee66b-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
