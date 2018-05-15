---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b53b7cc3ce812b72830c0ad83c5cc2b42bfc25a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="8c1ca-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="8c1ca-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="8c1ca-103">이 구성 요소는 고정 되어 있는 표준 끝점을 정의 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩에 자동으로 추가 하는 [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1ca-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="8c1ca-104">ASP.NET AJAX 응용 프로그램에서 호출되는 서비스를 기록할 때 이 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1ca-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="8c1ca-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c1ca-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c1ca-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="8c1ca-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c1ca-107">구문</span><span class="sxs-lookup"><span data-stu-id="8c1ca-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c1ca-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c1ca-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c1ca-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1ca-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c1ca-110">특성</span><span class="sxs-lookup"><span data-stu-id="8c1ca-110">Attributes</span></span>  
  
|<span data-ttu-id="8c1ca-111">특성</span><span class="sxs-lookup"><span data-stu-id="8c1ca-111">Attribute</span></span>|<span data-ttu-id="8c1ca-112">설명</span><span class="sxs-lookup"><span data-stu-id="8c1ca-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c1ca-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8c1ca-113">webEndpointType</span></span>|<span data-ttu-id="8c1ca-114">끝점의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1ca-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c1ca-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c1ca-115">Child Elements</span></span>  
 <span data-ttu-id="8c1ca-116">없음</span><span class="sxs-lookup"><span data-stu-id="8c1ca-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c1ca-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c1ca-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8c1ca-118">요소</span><span class="sxs-lookup"><span data-stu-id="8c1ca-118">Element</span></span>|<span data-ttu-id="8c1ca-119">설명</span><span class="sxs-lookup"><span data-stu-id="8c1ca-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c1ca-120">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="8c1ca-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8c1ca-121">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1ca-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c1ca-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c1ca-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
