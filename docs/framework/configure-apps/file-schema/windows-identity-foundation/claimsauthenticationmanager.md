---
title: '&lt;claimsAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 48e5be23b196a24a9d3e2a1dc4639d8ca9823660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="b464c-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="b464c-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="b464c-103">들어오는 클레임에 대 한 클레임 인증 관리자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="b464c-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b464c-104">\<system.identityModel></span></span>  
<span data-ttu-id="b464c-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b464c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b464c-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="b464c-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b464c-107">구문</span><span class="sxs-lookup"><span data-stu-id="b464c-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b464c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b464c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b464c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b464c-110">특성</span><span class="sxs-lookup"><span data-stu-id="b464c-110">Attributes</span></span>  
  
|<span data-ttu-id="b464c-111">특성</span><span class="sxs-lookup"><span data-stu-id="b464c-111">Attribute</span></span>|<span data-ttu-id="b464c-112">설명</span><span class="sxs-lookup"><span data-stu-id="b464c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b464c-113">type</span><span class="sxs-lookup"><span data-stu-id="b464c-113">type</span></span>|<span data-ttu-id="b464c-114">파생 되는 사용자 지정 형식을 지정 된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="b464c-115">지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b464c-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b464c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b464c-116">Child Elements</span></span>  
 <span data-ttu-id="b464c-117">없을 경우 없습니다 `type` 특성 또는 경우에는 `type` 특성 참조는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b464c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b464c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b464c-119">요소</span><span class="sxs-lookup"><span data-stu-id="b464c-119">Element</span></span>|<span data-ttu-id="b464c-120">설명</span><span class="sxs-lookup"><span data-stu-id="b464c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b464c-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b464c-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b464c-122">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b464c-123">설명</span><span class="sxs-lookup"><span data-stu-id="b464c-123">Remarks</span></span>  
 <span data-ttu-id="b464c-124">기본 동작을 통해 제공 되는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="b464c-125">되지 않은 경우 `type` 특성이 지정 된 경우는 `type` 특성 지정는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="b464c-126">지정할 수는 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b464c-127">파생된 클래스의 자식 요소를 통해 구성을 지원할 수 있습니다는 `<claimsAuthenticationManager>` 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 메서드 이러한 요소를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b464c-128">디자이너 클래스의 최대는 자식 요소에 대해 정의 된 스키마가입니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="b464c-129">`<claimsAuthenticationManager>` 요소 집합에서 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b464c-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b464c-130">예제</span><span class="sxs-lookup"><span data-stu-id="b464c-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
