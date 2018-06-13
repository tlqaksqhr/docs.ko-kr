---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754956"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="80e46-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="80e46-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="80e46-103">들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80e46-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="80e46-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="80e46-104">\<system.identityModel></span></span>  
<span data-ttu-id="80e46-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="80e46-105">\<identityConfiguration></span></span>  
<span data-ttu-id="80e46-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="80e46-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80e46-107">구문</span><span class="sxs-lookup"><span data-stu-id="80e46-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80e46-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80e46-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80e46-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80e46-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80e46-110">특성</span><span class="sxs-lookup"><span data-stu-id="80e46-110">Attributes</span></span>  
 <span data-ttu-id="80e46-111">없음</span><span class="sxs-lookup"><span data-stu-id="80e46-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80e46-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80e46-112">Child Elements</span></span>  
  
|<span data-ttu-id="80e46-113">요소</span><span class="sxs-lookup"><span data-stu-id="80e46-113">Element</span></span>|<span data-ttu-id="80e46-114">설명</span><span class="sxs-lookup"><span data-stu-id="80e46-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80e46-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="80e46-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="80e46-116">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80e46-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80e46-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80e46-117">Parent Elements</span></span>  
  
|<span data-ttu-id="80e46-118">요소</span><span class="sxs-lookup"><span data-stu-id="80e46-118">Element</span></span>|<span data-ttu-id="80e46-119">설명</span><span class="sxs-lookup"><span data-stu-id="80e46-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80e46-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="80e46-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="80e46-121">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80e46-121">Specifies service-level identity settings.</span></span>|
