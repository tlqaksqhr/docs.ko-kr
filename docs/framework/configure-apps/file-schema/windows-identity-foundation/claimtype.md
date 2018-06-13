---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767429"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="ae9f4-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="ae9f4-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="ae9f4-103">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="ae9f4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ae9f4-104">\<system.identityModel></span></span>  
<span data-ttu-id="ae9f4-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ae9f4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ae9f4-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="ae9f4-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="ae9f4-107">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="ae9f4-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9f4-108">구문</span><span class="sxs-lookup"><span data-stu-id="ae9f4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae9f4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ae9f4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ae9f4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae9f4-111">특성</span><span class="sxs-lookup"><span data-stu-id="ae9f4-111">Attributes</span></span>  
  
|<span data-ttu-id="ae9f4-112">특성</span><span class="sxs-lookup"><span data-stu-id="ae9f4-112">Attribute</span></span>|<span data-ttu-id="ae9f4-113">설명</span><span class="sxs-lookup"><span data-stu-id="ae9f4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae9f4-114">type</span><span class="sxs-lookup"><span data-stu-id="ae9f4-114">type</span></span>|<span data-ttu-id="ae9f4-115">클레임 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-115">The claim type.</span></span> <span data-ttu-id="ae9f4-116">일반적으로 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-116">Typically a URI.</span></span> <span data-ttu-id="ae9f4-117">필수.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-117">Required.</span></span>|  
|<span data-ttu-id="ae9f4-118">선택적</span><span class="sxs-lookup"><span data-stu-id="ae9f4-118">optional</span></span>|<span data-ttu-id="ae9f4-119">클레임 유형 선택 사항 인지를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="ae9f4-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae9f4-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ae9f4-121">Child Elements</span></span>  
 <span data-ttu-id="ae9f4-122">없음</span><span class="sxs-lookup"><span data-stu-id="ae9f4-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae9f4-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ae9f4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ae9f4-124">요소</span><span class="sxs-lookup"><span data-stu-id="ae9f4-124">Element</span></span>|<span data-ttu-id="ae9f4-125">설명</span><span class="sxs-lookup"><span data-stu-id="ae9f4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae9f4-126">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="ae9f4-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="ae9f4-127">들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-127">Specifies the set of required claims for incoming security tokens.</span></span>|
