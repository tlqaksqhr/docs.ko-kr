---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2226b4f55025c9dec3fdeb4f9b4f51016ffd3e8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="88915-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="88915-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="88915-103">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88915-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="88915-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="88915-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="88915-105">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="88915-105">\<client></span></span>  
<span data-ttu-id="88915-106">\<메타 데이터 ></span><span class="sxs-lookup"><span data-stu-id="88915-106">\<metadata></span></span>  
<span data-ttu-id="88915-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="88915-107">\<policyImporters></span></span>  
<span data-ttu-id="88915-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="88915-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88915-109">구문</span><span class="sxs-lookup"><span data-stu-id="88915-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88915-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88915-110">Attributes and Elements</span></span>  
 <span data-ttu-id="88915-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88915-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88915-112">특성</span><span class="sxs-lookup"><span data-stu-id="88915-112">Attributes</span></span>  
  
|<span data-ttu-id="88915-113">특성</span><span class="sxs-lookup"><span data-stu-id="88915-113">Attribute</span></span>|<span data-ttu-id="88915-114">설명</span><span class="sxs-lookup"><span data-stu-id="88915-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="88915-115">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88915-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88915-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88915-116">Child Elements</span></span>  
 <span data-ttu-id="88915-117">없음</span><span class="sxs-lookup"><span data-stu-id="88915-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88915-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88915-118">Parent Elements</span></span>  
  
|<span data-ttu-id="88915-119">요소</span><span class="sxs-lookup"><span data-stu-id="88915-119">Element</span></span>|<span data-ttu-id="88915-120">설명</span><span class="sxs-lookup"><span data-stu-id="88915-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88915-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="88915-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="88915-122">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88915-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88915-123">설명</span><span class="sxs-lookup"><span data-stu-id="88915-123">Remarks</span></span>  
 <span data-ttu-id="88915-124">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="88915-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88915-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88915-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="88915-126">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="88915-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="88915-127">클라이언트</span><span class="sxs-lookup"><span data-stu-id="88915-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
