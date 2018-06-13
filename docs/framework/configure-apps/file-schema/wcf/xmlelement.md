---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 70ff9b93bcd59331c5fa5e66bb51dc4cd1e043ff
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767650"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="a995e-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="a995e-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="a995e-103">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a995e-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="a995e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a995e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a995e-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a995e-105">\<bindings></span></span>  
<span data-ttu-id="a995e-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="a995e-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="a995e-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a995e-107">\<binding></span></span>  
<span data-ttu-id="a995e-108">\<security></span><span class="sxs-lookup"><span data-stu-id="a995e-108">\<security></span></span>  
<span data-ttu-id="a995e-109">\<message></span><span class="sxs-lookup"><span data-stu-id="a995e-109">\<message></span></span>  
<span data-ttu-id="a995e-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="a995e-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a995e-111">구문</span><span class="sxs-lookup"><span data-stu-id="a995e-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a995e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a995e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a995e-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a995e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a995e-114">특성</span><span class="sxs-lookup"><span data-stu-id="a995e-114">Attributes</span></span>  
  
|<span data-ttu-id="a995e-115">특성</span><span class="sxs-lookup"><span data-stu-id="a995e-115">Attribute</span></span>|<span data-ttu-id="a995e-116">설명</span><span class="sxs-lookup"><span data-stu-id="a995e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a995e-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="a995e-117">xmlElement</span></span>|<span data-ttu-id="a995e-118">토큰을 요청할 때 메시지 본문에서 보안 토큰 서비스로 보낼 XML 요소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a995e-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a995e-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a995e-119">Child Elements</span></span>  
 <span data-ttu-id="a995e-120">없음</span><span class="sxs-lookup"><span data-stu-id="a995e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a995e-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a995e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a995e-122">요소</span><span class="sxs-lookup"><span data-stu-id="a995e-122">Element</span></span>|<span data-ttu-id="a995e-123">설명</span><span class="sxs-lookup"><span data-stu-id="a995e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a995e-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a995e-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="a995e-125">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a995e-125">A collection of token request parameters.</span></span> <span data-ttu-id="a995e-126">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a995e-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a995e-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a995e-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="a995e-128">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="a995e-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a995e-129">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="a995e-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a995e-130">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a995e-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a995e-131">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="a995e-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a995e-132">바인딩</span><span class="sxs-lookup"><span data-stu-id="a995e-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
