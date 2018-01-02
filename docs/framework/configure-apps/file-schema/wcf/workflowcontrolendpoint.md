---
title: '&lt;workflowControlEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 443d23a3b0f73d2fd0a08112d51f745d1e1874fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="f8aca-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="f8aca-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="f8aca-103">이 구성 요소는 워크플로 인스턴스의 실행(만들기, 실행, 일시 중단, 종료 등)을 제어하기 위한 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aca-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="f8aca-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f8aca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8aca-105">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="f8aca-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8aca-106">구문</span><span class="sxs-lookup"><span data-stu-id="f8aca-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8aca-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f8aca-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f8aca-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aca-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8aca-109">특성</span><span class="sxs-lookup"><span data-stu-id="f8aca-109">Attributes</span></span>  
  
|<span data-ttu-id="f8aca-110">특성</span><span class="sxs-lookup"><span data-stu-id="f8aca-110">Attribute</span></span>|<span data-ttu-id="f8aca-111">설명</span><span class="sxs-lookup"><span data-stu-id="f8aca-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8aca-112">name</span><span class="sxs-lookup"><span data-stu-id="f8aca-112">name</span></span>|<span data-ttu-id="f8aca-113">표준 끝점의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8aca-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="f8aca-114">이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8aca-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8aca-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f8aca-115">Child Elements</span></span>  
 <span data-ttu-id="f8aca-116">없음</span><span class="sxs-lookup"><span data-stu-id="f8aca-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8aca-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f8aca-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f8aca-118">요소</span><span class="sxs-lookup"><span data-stu-id="f8aca-118">Element</span></span>|<span data-ttu-id="f8aca-119">설명</span><span class="sxs-lookup"><span data-stu-id="f8aca-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8aca-120">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="f8aca-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f8aca-121">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8aca-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8aca-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8aca-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
