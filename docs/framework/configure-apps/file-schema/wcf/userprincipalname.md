---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 1bb0c8ac4cbe11cdfa31beb16b00b3863acabf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358679"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="8c773-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="8c773-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="8c773-103">클라이언트에서 인증할 서비스의 UPN(User Principal Name)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="8c773-104">UPN을 설정 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="8c773-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c773-105">\<identity></span></span>  
<span data-ttu-id="8c773-106">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="8c773-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c773-107">구문</span><span class="sxs-lookup"><span data-stu-id="8c773-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c773-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c773-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c773-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c773-110">특성</span><span class="sxs-lookup"><span data-stu-id="8c773-110">Attributes</span></span>  
  
|<span data-ttu-id="8c773-111">특성</span><span class="sxs-lookup"><span data-stu-id="8c773-111">Attribute</span></span>|<span data-ttu-id="8c773-112">설명</span><span class="sxs-lookup"><span data-stu-id="8c773-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c773-113">값</span><span class="sxs-lookup"><span data-stu-id="8c773-113">value</span></span>|<span data-ttu-id="8c773-114">사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="8c773-115">Windows 도메인에 로그온하는 표준 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="8c773-116">형식은: someone@example.com (경우와 전자 메일 주소).</span><span class="sxs-lookup"><span data-stu-id="8c773-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c773-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c773-117">Child Elements</span></span>  
 <span data-ttu-id="8c773-118">없음</span><span class="sxs-lookup"><span data-stu-id="8c773-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c773-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c773-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8c773-120">요소</span><span class="sxs-lookup"><span data-stu-id="8c773-120">Element</span></span>|<span data-ttu-id="8c773-121">설명</span><span class="sxs-lookup"><span data-stu-id="8c773-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c773-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c773-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8c773-123">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c773-124">설명</span><span class="sxs-lookup"><span data-stu-id="8c773-124">Remarks</span></span>  
 <span data-ttu-id="8c773-125">이 id 가진 끝점과 연결 하는 보안 Windows Communication Foundation (WCF) 클라이언트 끝점과 SSPI 인증을 수행할 때 UPN을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c773-126">예제</span><span class="sxs-lookup"><span data-stu-id="8c773-126">Example</span></span>  
 <span data-ttu-id="8c773-127">다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c773-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c773-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c773-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="8c773-129">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="8c773-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8c773-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c773-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
