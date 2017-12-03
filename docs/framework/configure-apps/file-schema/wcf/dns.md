---
title: '&lt;dns&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6994069ca57a078e3d8236739ecf091d9e179455
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltdnsgt"></a><span data-ttu-id="536a8-102">&lt;dns&gt;</span><span class="sxs-lookup"><span data-stu-id="536a8-102">&lt;dns&gt;</span></span>
<span data-ttu-id="536a8-103">서버에서 사용할 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="536a8-104">서버의 인증서에 같은 값이 있는 DNS가 포함된 경우 이 ID를 X509 인증서 인증 모드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="536a8-105">SPN에 같은 값이 있는 경우 Windows 인증 모드에도 해당 ID를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="536a8-106">요소 값을 설정 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="536a8-107">\<identity ></span><span class="sxs-lookup"><span data-stu-id="536a8-107">\<identity></span></span>  
<span data-ttu-id="536a8-108">\<dns ></span><span class="sxs-lookup"><span data-stu-id="536a8-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536a8-109">구문</span><span class="sxs-lookup"><span data-stu-id="536a8-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="536a8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="536a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="536a8-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="536a8-112">특성</span><span class="sxs-lookup"><span data-stu-id="536a8-112">Attributes</span></span>  
  
|<span data-ttu-id="536a8-113">특성</span><span class="sxs-lookup"><span data-stu-id="536a8-113">Attribute</span></span>|<span data-ttu-id="536a8-114">설명</span><span class="sxs-lookup"><span data-stu-id="536a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="536a8-115">값</span><span class="sxs-lookup"><span data-stu-id="536a8-115">value</span></span>|<span data-ttu-id="536a8-116">인증서의 DNS입니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-116">The DNS of the certificate.</span></span> <span data-ttu-id="536a8-117">DNS는 IP 기반 네트워크에서 컴퓨터를 찾는 데 사용하는 산업 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="536a8-118">사용자가 기억 하기 쉬운 표시 이름와 같은 [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) 또는 [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165)207.46.131.137 같은 숫자 기반 주소 보다 쉽게, 합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="536a8-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="536a8-119">Child Elements</span></span>  
 <span data-ttu-id="536a8-120">없음</span><span class="sxs-lookup"><span data-stu-id="536a8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="536a8-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="536a8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="536a8-122">요소</span><span class="sxs-lookup"><span data-stu-id="536a8-122">Element</span></span>|<span data-ttu-id="536a8-123">설명</span><span class="sxs-lookup"><span data-stu-id="536a8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="536a8-124">\<identity ></span><span class="sxs-lookup"><span data-stu-id="536a8-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="536a8-125">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="536a8-126">예제</span><span class="sxs-lookup"><span data-stu-id="536a8-126">Example</span></span>  
 <span data-ttu-id="536a8-127">다음 구성 코드에서는 서버를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="536a8-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="536a8-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="536a8-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="536a8-129">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="536a8-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="536a8-130">\<identity ></span><span class="sxs-lookup"><span data-stu-id="536a8-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
