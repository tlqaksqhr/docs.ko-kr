---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 61b128d5856fd8e35516949b637177dc38a17164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="340c6-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="340c6-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="340c6-103">사용자 지정 쿠키 처리기 유형을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="340c6-104">이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Custom"입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="340c6-105">사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="340c6-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="340c6-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="340c6-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="340c6-107">\<federationConfiguration></span></span>  
<span data-ttu-id="340c6-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="340c6-108">\<cookieHandler></span></span>  
<span data-ttu-id="340c6-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="340c6-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340c6-110">구문</span><span class="sxs-lookup"><span data-stu-id="340c6-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="340c6-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="340c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="340c6-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="340c6-113">특성</span><span class="sxs-lookup"><span data-stu-id="340c6-113">Attributes</span></span>  
  
|<span data-ttu-id="340c6-114">특성</span><span class="sxs-lookup"><span data-stu-id="340c6-114">Attribute</span></span>|<span data-ttu-id="340c6-115">설명</span><span class="sxs-lookup"><span data-stu-id="340c6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="340c6-116">type</span><span class="sxs-lookup"><span data-stu-id="340c6-116">type</span></span>|<span data-ttu-id="340c6-117">파생 되는 사용자 지정 형식을 지정 된 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="340c6-118">지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="340c6-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="340c6-119">Child Elements</span></span>  
 <span data-ttu-id="340c6-120">없음</span><span class="sxs-lookup"><span data-stu-id="340c6-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="340c6-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="340c6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="340c6-122">요소</span><span class="sxs-lookup"><span data-stu-id="340c6-122">Element</span></span>|<span data-ttu-id="340c6-123">설명</span><span class="sxs-lookup"><span data-stu-id="340c6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="340c6-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="340c6-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="340c6-125">구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="340c6-126">설명</span><span class="sxs-lookup"><span data-stu-id="340c6-126">Remarks</span></span>  
 <span data-ttu-id="340c6-127">사용자 지정 쿠키 처리기를 설정 하 여 지정 되는 경우는 `mode` 특성의는 `<cookieHandler>` 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 하는 "Custom"으로 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="340c6-128">이 요소 수 없습니다 될 때 지정 되는 `mode` 특성은 "이 Chunked" 또는 "Default"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="340c6-129">사용자 지정 쿠키 처리기에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="340c6-130">`<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="340c6-131">예</span><span class="sxs-lookup"><span data-stu-id="340c6-131">Example</span></span>  
 <span data-ttu-id="340c6-132">다음 예제에서는 구성 유형의 사용자 지정 쿠키 처리기 사용 하 여 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="340c6-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="340c6-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340c6-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
