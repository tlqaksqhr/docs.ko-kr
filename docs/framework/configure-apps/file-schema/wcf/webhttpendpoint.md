---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 46691a36b62898583132b5668b06de5659926d66
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="b23c6-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="b23c6-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="b23c6-103">이 구성 요소는 고정 되어 있는 표준 끝점을 정의 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩에 자동으로 추가 하는 [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="b23c6-104">REST 서비스를 작성할 때는 이 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="b23c6-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b23c6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b23c6-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="b23c6-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b23c6-107">구문</span><span class="sxs-lookup"><span data-stu-id="b23c6-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b23c6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b23c6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b23c6-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b23c6-110">특성</span><span class="sxs-lookup"><span data-stu-id="b23c6-110">Attributes</span></span>  
  
|<span data-ttu-id="b23c6-111">특성</span><span class="sxs-lookup"><span data-stu-id="b23c6-111">Attribute</span></span>|<span data-ttu-id="b23c6-112">설명</span><span class="sxs-lookup"><span data-stu-id="b23c6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b23c6-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="b23c6-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="b23c6-114">자동 서식 선택을 사용하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="b23c6-115">자동 서식 선택을 사용하면 인프라에서 요청 메시지의 `Accept` 헤더를 구문 분석하여 가장 적합한 응답 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="b23c6-116">`Accept` 헤더에서 적합한 응답 형식을 지정하지 않는 경우 인프라에서 요청 메시지의 `Content-Type`이나 작업의 기본 응답 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="b23c6-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="b23c6-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="b23c6-118">나가는 응답의 기본 형식을 지정하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="b23c6-119">이 특성은 <xref:System.ServiceModel.Web.WebMessageFormat> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="b23c6-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="b23c6-120">helpEnabled</span></span>|<span data-ttu-id="b23c6-121">끝점에 대해 HTTP 도움말 페이지가 사용되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="b23c6-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="b23c6-122">webEndpointType</span></span>|<span data-ttu-id="b23c6-123">끝점의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b23c6-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b23c6-124">Child Elements</span></span>  
 <span data-ttu-id="b23c6-125">없음</span><span class="sxs-lookup"><span data-stu-id="b23c6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b23c6-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b23c6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b23c6-127">요소</span><span class="sxs-lookup"><span data-stu-id="b23c6-127">Element</span></span>|<span data-ttu-id="b23c6-128">설명</span><span class="sxs-lookup"><span data-stu-id="b23c6-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b23c6-129">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="b23c6-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b23c6-130">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b23c6-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b23c6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b23c6-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
