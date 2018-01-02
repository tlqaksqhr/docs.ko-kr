---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ae572ff3a8a2335a4259bdce2af5f6922fb0596f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="93af3-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="93af3-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="93af3-103">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="93af3-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="93af3-104">\<system.identityModel></span></span>  
<span data-ttu-id="93af3-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="93af3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="93af3-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="93af3-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="93af3-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="93af3-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93af3-108">구문</span><span class="sxs-lookup"><span data-stu-id="93af3-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93af3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="93af3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93af3-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93af3-111">특성</span><span class="sxs-lookup"><span data-stu-id="93af3-111">Attributes</span></span>  
  
|<span data-ttu-id="93af3-112">특성</span><span class="sxs-lookup"><span data-stu-id="93af3-112">Attribute</span></span>|<span data-ttu-id="93af3-113">설명</span><span class="sxs-lookup"><span data-stu-id="93af3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93af3-114">type</span><span class="sxs-lookup"><span data-stu-id="93af3-114">type</span></span>|<span data-ttu-id="93af3-115">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-115">The claim type.</span></span> <span data-ttu-id="93af3-116">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-116">Typically a URI.</span></span> <span data-ttu-id="93af3-117">필수.</span><span class="sxs-lookup"><span data-stu-id="93af3-117">Required.</span></span>|  
|<span data-ttu-id="93af3-118">선택적</span><span class="sxs-lookup"><span data-stu-id="93af3-118">optional</span></span>|<span data-ttu-id="93af3-119">클레임 유형 선택 사항 인지를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="93af3-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93af3-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93af3-121">Child Elements</span></span>  
 <span data-ttu-id="93af3-122">없음</span><span class="sxs-lookup"><span data-stu-id="93af3-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93af3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93af3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="93af3-124">요소</span><span class="sxs-lookup"><span data-stu-id="93af3-124">Element</span></span>|<span data-ttu-id="93af3-125">설명</span><span class="sxs-lookup"><span data-stu-id="93af3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93af3-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="93af3-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="93af3-127">들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93af3-127">Specifies the set of required claims for incoming security tokens.</span></span>|
