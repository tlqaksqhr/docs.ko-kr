---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 3b58214a1fd7a50fb1a9ab3dfee0a14870f8a476
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="db5bc-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="db5bc-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="db5bc-103">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="db5bc-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="db5bc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="db5bc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="db5bc-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="db5bc-105">\<behaviors></span></span>  
<span data-ttu-id="db5bc-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="db5bc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="db5bc-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="db5bc-107">\<behavior></span></span>  
<span data-ttu-id="db5bc-108">\<a g e r ></span><span class="sxs-lookup"><span data-stu-id="db5bc-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db5bc-109">구문</span><span class="sxs-lookup"><span data-stu-id="db5bc-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db5bc-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="db5bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db5bc-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="db5bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db5bc-112">특성</span><span class="sxs-lookup"><span data-stu-id="db5bc-112">Attributes</span></span>  
  
|<span data-ttu-id="db5bc-113">특성</span><span class="sxs-lookup"><span data-stu-id="db5bc-113">Attribute</span></span>|<span data-ttu-id="db5bc-114">설명</span><span class="sxs-lookup"><span data-stu-id="db5bc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db5bc-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="db5bc-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="db5bc-116">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="db5bc-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db5bc-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="db5bc-117">Child Elements</span></span>  
 <span data-ttu-id="db5bc-118">없음</span><span class="sxs-lookup"><span data-stu-id="db5bc-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db5bc-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="db5bc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="db5bc-120">요소</span><span class="sxs-lookup"><span data-stu-id="db5bc-120">Element</span></span>|<span data-ttu-id="db5bc-121">설명</span><span class="sxs-lookup"><span data-stu-id="db5bc-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db5bc-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="db5bc-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="db5bc-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db5bc-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db5bc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db5bc-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
