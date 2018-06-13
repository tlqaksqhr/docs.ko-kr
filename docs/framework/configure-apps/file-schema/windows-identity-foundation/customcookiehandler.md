---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b974767aa86801bff234e200e1fce021bfc422c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755606"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="29d96-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="29d96-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="29d96-103">사용자 지정 쿠키 처리기 유형을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="29d96-104">이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Custom"입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="29d96-105">사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="29d96-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="29d96-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="29d96-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="29d96-107">\<federationConfiguration></span></span>  
<span data-ttu-id="29d96-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="29d96-108">\<cookieHandler></span></span>  
<span data-ttu-id="29d96-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="29d96-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d96-110">구문</span><span class="sxs-lookup"><span data-stu-id="29d96-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29d96-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="29d96-111">Attributes and Elements</span></span>  
 <span data-ttu-id="29d96-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29d96-113">특성</span><span class="sxs-lookup"><span data-stu-id="29d96-113">Attributes</span></span>  
  
|<span data-ttu-id="29d96-114">특성</span><span class="sxs-lookup"><span data-stu-id="29d96-114">Attribute</span></span>|<span data-ttu-id="29d96-115">설명</span><span class="sxs-lookup"><span data-stu-id="29d96-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29d96-116">type</span><span class="sxs-lookup"><span data-stu-id="29d96-116">type</span></span>|<span data-ttu-id="29d96-117">파생 되는 사용자 지정 형식을 지정 된 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="29d96-118">지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29d96-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="29d96-119">Child Elements</span></span>  
 <span data-ttu-id="29d96-120">없음</span><span class="sxs-lookup"><span data-stu-id="29d96-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29d96-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="29d96-121">Parent Elements</span></span>  
  
|<span data-ttu-id="29d96-122">요소</span><span class="sxs-lookup"><span data-stu-id="29d96-122">Element</span></span>|<span data-ttu-id="29d96-123">설명</span><span class="sxs-lookup"><span data-stu-id="29d96-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29d96-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="29d96-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="29d96-125">구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 읽기 및 쓰기 쿠키를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29d96-126">설명</span><span class="sxs-lookup"><span data-stu-id="29d96-126">Remarks</span></span>  
 <span data-ttu-id="29d96-127">사용자 지정 쿠키 처리기를 설정 하 여 지정 되는 경우는 `mode` 특성의는 `<cookieHandler>` 요소를 포함 하 여 사용자 지정 쿠키 처리기의 형식을 지정 해야 하는 "Custom"으로 `<customCookieHandler>` 쿠키 처리기 형식을 참조 하는 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="29d96-128">이 요소 수 없습니다 될 때 지정 되는 `mode` 특성은 "이 Chunked" 또는 "Default"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="29d96-129">사용자 지정 쿠키 처리기에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="29d96-130">`<customCookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.CustomTypeElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29d96-131">예제</span><span class="sxs-lookup"><span data-stu-id="29d96-131">Example</span></span>  
 <span data-ttu-id="29d96-132">다음 예제에서는 구성 유형의 사용자 지정 쿠키 처리기 사용 하 여 SAM `MyNamespace.MyCustomCookieHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="29d96-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29d96-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29d96-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
