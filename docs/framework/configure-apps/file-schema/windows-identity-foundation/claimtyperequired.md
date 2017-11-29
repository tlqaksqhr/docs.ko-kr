---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 89d42cba78eb9758d8b3491fd1bd3b25ef168f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="52b05-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="52b05-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="52b05-103">들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52b05-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="52b05-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="52b05-104">\<system.identityModel></span></span>  
<span data-ttu-id="52b05-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="52b05-105">\<identityConfiguration></span></span>  
<span data-ttu-id="52b05-106">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="52b05-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b05-107">구문</span><span class="sxs-lookup"><span data-stu-id="52b05-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52b05-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52b05-108">Attributes and Elements</span></span>  
 <span data-ttu-id="52b05-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52b05-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52b05-110">특성</span><span class="sxs-lookup"><span data-stu-id="52b05-110">Attributes</span></span>  
 <span data-ttu-id="52b05-111">없음</span><span class="sxs-lookup"><span data-stu-id="52b05-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52b05-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52b05-112">Child Elements</span></span>  
  
|<span data-ttu-id="52b05-113">요소</span><span class="sxs-lookup"><span data-stu-id="52b05-113">Element</span></span>|<span data-ttu-id="52b05-114">설명</span><span class="sxs-lookup"><span data-stu-id="52b05-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52b05-115">\<claimType ></span><span class="sxs-lookup"><span data-stu-id="52b05-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="52b05-116">들어오는 보안 토큰에 대 한 단일 옵션 또는 필요한 클레임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52b05-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52b05-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52b05-117">Parent Elements</span></span>  
  
|<span data-ttu-id="52b05-118">요소</span><span class="sxs-lookup"><span data-stu-id="52b05-118">Element</span></span>|<span data-ttu-id="52b05-119">설명</span><span class="sxs-lookup"><span data-stu-id="52b05-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52b05-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="52b05-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="52b05-121">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52b05-121">Specifies service-level identity settings.</span></span>|
