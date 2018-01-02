---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713c1c260f36d6d980903cce1ebcc9c5648116c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="e9e35-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e9e35-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="e9e35-103">이 구성 요소는 고정 IMetadataExchange 계약을 사용하여 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="e9e35-104">모든 메타데이터 교환 끝점이 IMetadataExchange를 계약으로 지정하므로 고유의 끝점을 정의하는 대신 이 표준 지점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="e9e35-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e9e35-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9e35-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="e9e35-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9e35-107">구문</span><span class="sxs-lookup"><span data-stu-id="e9e35-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9e35-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9e35-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e9e35-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9e35-110">특성</span><span class="sxs-lookup"><span data-stu-id="e9e35-110">Attributes</span></span>  
  
|<span data-ttu-id="e9e35-111">특성</span><span class="sxs-lookup"><span data-stu-id="e9e35-111">Attribute</span></span>|<span data-ttu-id="e9e35-112">설명</span><span class="sxs-lookup"><span data-stu-id="e9e35-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9e35-113">name</span><span class="sxs-lookup"><span data-stu-id="e9e35-113">name</span></span>|<span data-ttu-id="e9e35-114">표준 끝점의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="e9e35-115">이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9e35-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9e35-116">Child Elements</span></span>  
 <span data-ttu-id="e9e35-117">없음</span><span class="sxs-lookup"><span data-stu-id="e9e35-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9e35-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9e35-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e9e35-119">요소</span><span class="sxs-lookup"><span data-stu-id="e9e35-119">Element</span></span>|<span data-ttu-id="e9e35-120">설명</span><span class="sxs-lookup"><span data-stu-id="e9e35-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9e35-121">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="e9e35-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e9e35-122">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e35-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
