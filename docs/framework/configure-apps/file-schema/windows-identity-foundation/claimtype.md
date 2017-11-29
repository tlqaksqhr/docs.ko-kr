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
ms.openlocfilehash: c4ee8833578b082f25c427b13d77072d1954197f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="572b0-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="572b0-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="572b0-103">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="572b0-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="572b0-104">\<system.identityModel></span></span>  
<span data-ttu-id="572b0-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="572b0-105">\<identityConfiguration></span></span>  
<span data-ttu-id="572b0-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="572b0-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="572b0-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="572b0-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572b0-108">구문</span><span class="sxs-lookup"><span data-stu-id="572b0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="572b0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="572b0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="572b0-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="572b0-111">특성</span><span class="sxs-lookup"><span data-stu-id="572b0-111">Attributes</span></span>  
  
|<span data-ttu-id="572b0-112">특성</span><span class="sxs-lookup"><span data-stu-id="572b0-112">Attribute</span></span>|<span data-ttu-id="572b0-113">설명</span><span class="sxs-lookup"><span data-stu-id="572b0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="572b0-114">type</span><span class="sxs-lookup"><span data-stu-id="572b0-114">type</span></span>|<span data-ttu-id="572b0-115">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-115">The claim type.</span></span> <span data-ttu-id="572b0-116">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-116">Typically a URI.</span></span> <span data-ttu-id="572b0-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="572b0-117">Required.</span></span>|  
|<span data-ttu-id="572b0-118">선택적</span><span class="sxs-lookup"><span data-stu-id="572b0-118">optional</span></span>|<span data-ttu-id="572b0-119">클레임 유형 선택 사항 인지를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="572b0-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="572b0-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="572b0-121">Child Elements</span></span>  
 <span data-ttu-id="572b0-122">없음</span><span class="sxs-lookup"><span data-stu-id="572b0-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="572b0-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="572b0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="572b0-124">요소</span><span class="sxs-lookup"><span data-stu-id="572b0-124">Element</span></span>|<span data-ttu-id="572b0-125">설명</span><span class="sxs-lookup"><span data-stu-id="572b0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="572b0-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="572b0-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="572b0-127">들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="572b0-127">Specifies the set of required claims for incoming security tokens.</span></span>|
