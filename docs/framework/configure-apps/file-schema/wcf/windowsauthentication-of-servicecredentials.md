---
title: '&lt;serviceCredentials&gt;의 &lt;windowsAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 9872b1f2520661ff3f31cef94b6822bb345ebfdf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="86a7e-102">&lt;serviceCredentials&gt;의 &lt;windowsAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="86a7e-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="86a7e-103">Windows 서비스 자격 증명의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="86a7e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86a7e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="86a7e-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="86a7e-105">\<behaviors></span></span>  
<span data-ttu-id="86a7e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="86a7e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="86a7e-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="86a7e-107">\<behavior></span></span>  
<span data-ttu-id="86a7e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="86a7e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="86a7e-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="86a7e-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a7e-110">구문</span><span class="sxs-lookup"><span data-stu-id="86a7e-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86a7e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="86a7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="86a7e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86a7e-113">특성</span><span class="sxs-lookup"><span data-stu-id="86a7e-113">Attributes</span></span>  
  
|<span data-ttu-id="86a7e-114">특성</span><span class="sxs-lookup"><span data-stu-id="86a7e-114">Attribute</span></span>|<span data-ttu-id="86a7e-115">설명</span><span class="sxs-lookup"><span data-stu-id="86a7e-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="86a7e-116">시스템의 보안 컨텍스트에 Windows 그룹이 포함되어 있는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="86a7e-117">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="86a7e-118">이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="86a7e-119">사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="86a7e-120">익명의 인증되지 않은 호출자가 허용되는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="86a7e-121">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="86a7e-122">바인딩의 `clientCredentialType` 특성을 `Windows`로 설정하면 익명 호출자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="86a7e-123">즉, 도메인 또는 작업 그룹 인증 호출자가 시스템에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="86a7e-124">이 특성을 사용하여 이 동작을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="86a7e-125">따라서 이 설정을 사용할 때는 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86a7e-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="86a7e-126">Child Elements</span></span>  
 <span data-ttu-id="86a7e-127">없음</span><span class="sxs-lookup"><span data-stu-id="86a7e-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86a7e-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="86a7e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="86a7e-129">요소</span><span class="sxs-lookup"><span data-stu-id="86a7e-129">Element</span></span>|<span data-ttu-id="86a7e-130">설명</span><span class="sxs-lookup"><span data-stu-id="86a7e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86a7e-131">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="86a7e-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="86a7e-132">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86a7e-133">설명</span><span class="sxs-lookup"><span data-stu-id="86a7e-133">Remarks</span></span>  
 <span data-ttu-id="86a7e-134">`allowAnonymousLogons` 특성을 설정하여 익명 Windows 사용자 액세스를 허용할지 여부를 지정하려면 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="86a7e-135">또한 `includeWindowsGroups` 특성을 설정하여 사용자가 속한 그룹 정보를 AuthorizationContext에 포함시킬지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="86a7e-136">`true`(기본 설정)로 설정되면 서비스에서 클라이언트가 속해 있는 Windows 그룹을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a7e-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a7e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86a7e-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
