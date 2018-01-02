---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b46df4f069259ae4bb2d2769e20c6ad9e6090c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="78990-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="78990-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="78990-103">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78990-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="78990-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="78990-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="78990-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="78990-105">\<behaviors></span></span>  
<span data-ttu-id="78990-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="78990-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="78990-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="78990-107">\<behavior></span></span>  
<span data-ttu-id="78990-108">\<a g e r ></span><span class="sxs-lookup"><span data-stu-id="78990-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78990-109">구문</span><span class="sxs-lookup"><span data-stu-id="78990-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78990-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78990-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78990-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78990-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78990-112">특성</span><span class="sxs-lookup"><span data-stu-id="78990-112">Attributes</span></span>  
  
|<span data-ttu-id="78990-113">특성</span><span class="sxs-lookup"><span data-stu-id="78990-113">Attribute</span></span>|<span data-ttu-id="78990-114">설명</span><span class="sxs-lookup"><span data-stu-id="78990-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78990-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="78990-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="78990-116">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="78990-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78990-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78990-117">Child Elements</span></span>  
 <span data-ttu-id="78990-118">없음</span><span class="sxs-lookup"><span data-stu-id="78990-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78990-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78990-119">Parent Elements</span></span>  
  
|<span data-ttu-id="78990-120">요소</span><span class="sxs-lookup"><span data-stu-id="78990-120">Element</span></span>|<span data-ttu-id="78990-121">설명</span><span class="sxs-lookup"><span data-stu-id="78990-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78990-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="78990-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="78990-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78990-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78990-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78990-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
