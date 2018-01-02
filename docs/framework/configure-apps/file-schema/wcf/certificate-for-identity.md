---
title: "&lt;identity&gt;에 대한 &lt;certificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c1fb253ed166b4e8106f68bf2782cf215541294
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="cec0b-102">&lt;identity&gt;에 대한 &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="cec0b-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="cec0b-103">클라이언트에 서버의 유효성을 검사하는 데 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="cec0b-104">요소 값을 설정 하는 방법에 대 한 자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="cec0b-105">\<identity ></span><span class="sxs-lookup"><span data-stu-id="cec0b-105">\<identity></span></span>  
<span data-ttu-id="cec0b-106">\<인증서 ></span><span class="sxs-lookup"><span data-stu-id="cec0b-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec0b-107">구문</span><span class="sxs-lookup"><span data-stu-id="cec0b-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cec0b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cec0b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cec0b-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cec0b-110">특성</span><span class="sxs-lookup"><span data-stu-id="cec0b-110">Attributes</span></span>  
  
|<span data-ttu-id="cec0b-111">특성</span><span class="sxs-lookup"><span data-stu-id="cec0b-111">Attribute</span></span>|<span data-ttu-id="cec0b-112">설명</span><span class="sxs-lookup"><span data-stu-id="cec0b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cec0b-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="cec0b-113">encodedValue</span></span>|<span data-ttu-id="cec0b-114">인증서의 Base64 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cec0b-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cec0b-115">Child Elements</span></span>  
 <span data-ttu-id="cec0b-116">없음</span><span class="sxs-lookup"><span data-stu-id="cec0b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cec0b-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cec0b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cec0b-118">요소</span><span class="sxs-lookup"><span data-stu-id="cec0b-118">Element</span></span>|<span data-ttu-id="cec0b-119">설명</span><span class="sxs-lookup"><span data-stu-id="cec0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cec0b-120">\<identity ></span><span class="sxs-lookup"><span data-stu-id="cec0b-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="cec0b-121">클라이언트에서 인증할 서비스의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cec0b-122">예</span><span class="sxs-lookup"><span data-stu-id="cec0b-122">Example</span></span>  
 <span data-ttu-id="cec0b-123">다음 코드에서는 클라이언트에 서버의 유효성을 검사하는 데 사용되는 인코딩된 인증서 표현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cec0b-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cec0b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cec0b-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="cec0b-125">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="cec0b-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="cec0b-126">\<identity ></span><span class="sxs-lookup"><span data-stu-id="cec0b-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
