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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2385b96460e0a3d53efb62054fb7da334ddd2d49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="d709e-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="d709e-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="d709e-103">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d709e-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="d709e-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d709e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d709e-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d709e-105">\<behaviors></span></span>  
<span data-ttu-id="d709e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d709e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d709e-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d709e-107">\<behavior></span></span>  
<span data-ttu-id="d709e-108">\<a g e r ></span><span class="sxs-lookup"><span data-stu-id="d709e-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d709e-109">구문</span><span class="sxs-lookup"><span data-stu-id="d709e-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d709e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d709e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d709e-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d709e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d709e-112">특성</span><span class="sxs-lookup"><span data-stu-id="d709e-112">Attributes</span></span>  
  
|<span data-ttu-id="d709e-113">특성</span><span class="sxs-lookup"><span data-stu-id="d709e-113">Attribute</span></span>|<span data-ttu-id="d709e-114">설명</span><span class="sxs-lookup"><span data-stu-id="d709e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d709e-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="d709e-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="d709e-116">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d709e-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d709e-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d709e-117">Child Elements</span></span>  
 <span data-ttu-id="d709e-118">없음</span><span class="sxs-lookup"><span data-stu-id="d709e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d709e-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d709e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d709e-120">요소</span><span class="sxs-lookup"><span data-stu-id="d709e-120">Element</span></span>|<span data-ttu-id="d709e-121">설명</span><span class="sxs-lookup"><span data-stu-id="d709e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d709e-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d709e-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d709e-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d709e-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d709e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d709e-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
