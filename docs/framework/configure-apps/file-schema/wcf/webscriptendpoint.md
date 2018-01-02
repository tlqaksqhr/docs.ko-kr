---
title: '&lt;webScriptEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 855a0fc0727bf0559b922317d439f7550f18d9ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="60a8c-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="60a8c-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="60a8c-103">이 구성 요소는 고정 되어 있는 표준 끝점을 정의 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩에 자동으로 추가 하는 [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="60a8c-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="60a8c-104">ASP.NET AJAX 응용 프로그램에서 호출되는 서비스를 기록할 때 이 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60a8c-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="60a8c-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="60a8c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="60a8c-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="60a8c-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a8c-107">구문</span><span class="sxs-lookup"><span data-stu-id="60a8c-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60a8c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60a8c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="60a8c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60a8c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60a8c-110">특성</span><span class="sxs-lookup"><span data-stu-id="60a8c-110">Attributes</span></span>  
  
|<span data-ttu-id="60a8c-111">특성</span><span class="sxs-lookup"><span data-stu-id="60a8c-111">Attribute</span></span>|<span data-ttu-id="60a8c-112">설명</span><span class="sxs-lookup"><span data-stu-id="60a8c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60a8c-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="60a8c-113">webEndpointType</span></span>|<span data-ttu-id="60a8c-114">끝점의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="60a8c-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60a8c-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60a8c-115">Child Elements</span></span>  
 <span data-ttu-id="60a8c-116">없음</span><span class="sxs-lookup"><span data-stu-id="60a8c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60a8c-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60a8c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="60a8c-118">요소</span><span class="sxs-lookup"><span data-stu-id="60a8c-118">Element</span></span>|<span data-ttu-id="60a8c-119">설명</span><span class="sxs-lookup"><span data-stu-id="60a8c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60a8c-120">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="60a8c-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="60a8c-121">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="60a8c-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60a8c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60a8c-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
