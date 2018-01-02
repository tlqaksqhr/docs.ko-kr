---
title: "&lt;serviceCredential&gt;의 &lt;secureConversationAuthentication&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f80b0570055edbe15fa467ea83e11aba2b62a8fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="8f9db-102">&lt;serviceCredential&gt;의 &lt;secureConversationAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="8f9db-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="8f9db-103">보안 대화 서비스 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9db-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="8f9db-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8f9db-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f9db-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8f9db-105">\<behaviors></span></span>  
<span data-ttu-id="8f9db-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8f9db-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8f9db-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8f9db-107">\<behavior></span></span>  
<span data-ttu-id="8f9db-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="8f9db-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8f9db-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="8f9db-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9db-110">구문</span><span class="sxs-lookup"><span data-stu-id="8f9db-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f9db-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8f9db-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8f9db-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9db-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f9db-113">특성</span><span class="sxs-lookup"><span data-stu-id="8f9db-113">Attributes</span></span>  
  
|<span data-ttu-id="8f9db-114">특성</span><span class="sxs-lookup"><span data-stu-id="8f9db-114">Attribute</span></span>|<span data-ttu-id="8f9db-115">설명</span><span class="sxs-lookup"><span data-stu-id="8f9db-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="8f9db-116">사용할 <xref:System.ServiceModel.Security.SecurityStateEncoder> 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f9db-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f9db-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f9db-117">Child Elements</span></span>  
 <span data-ttu-id="8f9db-118">없음</span><span class="sxs-lookup"><span data-stu-id="8f9db-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f9db-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f9db-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8f9db-120">요소</span><span class="sxs-lookup"><span data-stu-id="8f9db-120">Element</span></span>|<span data-ttu-id="8f9db-121">설명</span><span class="sxs-lookup"><span data-stu-id="8f9db-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f9db-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="8f9db-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="8f9db-123">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9db-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f9db-124">설명</span><span class="sxs-lookup"><span data-stu-id="8f9db-124">Remarks</span></span>  
 <span data-ttu-id="8f9db-125">SCT(보안 컨텍스트 토큰) 쿠키 serialization을 위한 알려진 클레임 형식 목록과 쿠키 정보를 인코딩 및 보안할 인코더를 지정하려면 이 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f9db-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="8f9db-126">SCT에 대한 자세한 내용은 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f9db-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9db-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f9db-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
