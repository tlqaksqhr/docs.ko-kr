---
title: '&lt;rsa&gt;'
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: dbeb08e6475d4825ad442b0b264e9003bb6fc53d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltrsagt"></a><span data-ttu-id="0bcfd-102">&lt;rsa&gt;</span><span class="sxs-lookup"><span data-stu-id="0bcfd-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="0bcfd-103">이 ID를 가진 끝점과 연결되는 보안 WCF 클라이언트는 서버가 나타내는 클레임 중에 이 ID 생성에 사용된 RSA 공개 키가 포함된 클레임이 있음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="0bcfd-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="0bcfd-104">\<identity></span></span>  
<span data-ttu-id="0bcfd-105">\<rsa ></span><span class="sxs-lookup"><span data-stu-id="0bcfd-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bcfd-106">구문</span><span class="sxs-lookup"><span data-stu-id="0bcfd-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bcfd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0bcfd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0bcfd-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bcfd-109">특성</span><span class="sxs-lookup"><span data-stu-id="0bcfd-109">Attributes</span></span>  
  
|<span data-ttu-id="0bcfd-110">특성</span><span class="sxs-lookup"><span data-stu-id="0bcfd-110">Attribute</span></span>|<span data-ttu-id="0bcfd-111">설명</span><span class="sxs-lookup"><span data-stu-id="0bcfd-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bcfd-112">값</span><span class="sxs-lookup"><span data-stu-id="0bcfd-112">value</span></span>|<span data-ttu-id="0bcfd-113">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-113">Optional String.</span></span> <span data-ttu-id="0bcfd-114">클라이언트에서 비교할 RSA 공개 키 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bcfd-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0bcfd-115">Child Elements</span></span>  
 <span data-ttu-id="0bcfd-116">없음</span><span class="sxs-lookup"><span data-stu-id="0bcfd-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bcfd-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0bcfd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0bcfd-118">요소</span><span class="sxs-lookup"><span data-stu-id="0bcfd-118">Element</span></span>|<span data-ttu-id="0bcfd-119">설명</span><span class="sxs-lookup"><span data-stu-id="0bcfd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bcfd-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="0bcfd-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0bcfd-121">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bcfd-122">설명</span><span class="sxs-lookup"><span data-stu-id="0bcfd-122">Remarks</span></span>  
 <span data-ttu-id="0bcfd-123">RSA 검사를 사용하면 RSA 키 또는 생성된 고유 RSA 키 값에 따라 하나의 인증서만 사용하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="0bcfd-124">이렇게 하면 RSA 키 값이 변경된 경우 기존 클라이언트와 작동하지 않는 서비스 대신 특정 RSA 키에 대한 인증을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="0bcfd-125">유효성을 검사할 서비스를 클라이언트 id를 사용 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bcfd-126">예제</span><span class="sxs-lookup"><span data-stu-id="0bcfd-126">Example</span></span>  
 <span data-ttu-id="0bcfd-127">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 공개 키 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcfd-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bcfd-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bcfd-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="0bcfd-129">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="0bcfd-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="0bcfd-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="0bcfd-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
