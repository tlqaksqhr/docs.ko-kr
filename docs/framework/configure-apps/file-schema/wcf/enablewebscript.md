---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b14923c1b9a80bcd1c47db0e4fad6a6224b95329
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751898"
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="39cb9-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="39cb9-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="39cb9-103">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 끝점 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39cb9-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="39cb9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="39cb9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="39cb9-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="39cb9-105">\<behaviors></span></span>  
<span data-ttu-id="39cb9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="39cb9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="39cb9-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="39cb9-107">\<behavior></span></span>  
<span data-ttu-id="39cb9-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="39cb9-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39cb9-109">구문</span><span class="sxs-lookup"><span data-stu-id="39cb9-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39cb9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="39cb9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="39cb9-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39cb9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39cb9-112">특성</span><span class="sxs-lookup"><span data-stu-id="39cb9-112">Attributes</span></span>  
 <span data-ttu-id="39cb9-113">없음</span><span class="sxs-lookup"><span data-stu-id="39cb9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39cb9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="39cb9-114">Child Elements</span></span>  
 <span data-ttu-id="39cb9-115">없음</span><span class="sxs-lookup"><span data-stu-id="39cb9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39cb9-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="39cb9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="39cb9-117">요소</span><span class="sxs-lookup"><span data-stu-id="39cb9-117">Element</span></span>|<span data-ttu-id="39cb9-118">설명</span><span class="sxs-lookup"><span data-stu-id="39cb9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39cb9-119">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="39cb9-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="39cb9-120">끝점 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39cb9-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39cb9-121">설명</span><span class="sxs-lookup"><span data-stu-id="39cb9-121">Remarks</span></span>  
 <span data-ttu-id="39cb9-122">이 문제는 사용 하 여 함께 사용 해야는 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩 또는 [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="39cb9-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="39cb9-123">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39cb9-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cb9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39cb9-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="39cb9-125">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="39cb9-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="39cb9-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="39cb9-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
