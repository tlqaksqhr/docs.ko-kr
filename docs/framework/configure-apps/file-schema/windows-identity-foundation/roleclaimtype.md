---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 909df1bd6054d9737f91c30c3c6b2d68b932281c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="ccb0e-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="ccb0e-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="ccb0e-103">역할 유형 클레임의 컬렉션에서 정의 하는 클레임 유형을 지정 <xref:System.Security.Claims.ClaimsIdentity> 에서 반환 된 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 토큰 처리기의 메서드.</span><span class="sxs-lookup"><span data-stu-id="ccb0e-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="ccb0e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ccb0e-104">\<system.identityModel></span></span>  
<span data-ttu-id="ccb0e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ccb0e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ccb0e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ccb0e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ccb0e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ccb0e-107">\<add></span></span>  
<span data-ttu-id="ccb0e-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="ccb0e-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="ccb0e-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="ccb0e-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb0e-110">구문</span><span class="sxs-lookup"><span data-stu-id="ccb0e-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccb0e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ccb0e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ccb0e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb0e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccb0e-113">특성</span><span class="sxs-lookup"><span data-stu-id="ccb0e-113">Attributes</span></span>  
  
|<span data-ttu-id="ccb0e-114">특성</span><span class="sxs-lookup"><span data-stu-id="ccb0e-114">Attribute</span></span>|<span data-ttu-id="ccb0e-115">설명</span><span class="sxs-lookup"><span data-stu-id="ccb0e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccb0e-116">값</span><span class="sxs-lookup"><span data-stu-id="ccb0e-116">value</span></span>|<span data-ttu-id="ccb0e-117">역할 클레임 형식에 대해 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb0e-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccb0e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ccb0e-118">Child Elements</span></span>  
 <span data-ttu-id="ccb0e-119">없음</span><span class="sxs-lookup"><span data-stu-id="ccb0e-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccb0e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ccb0e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ccb0e-121">요소</span><span class="sxs-lookup"><span data-stu-id="ccb0e-121">Element</span></span>|<span data-ttu-id="ccb0e-122">설명</span><span class="sxs-lookup"><span data-stu-id="ccb0e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccb0e-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="ccb0e-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="ccb0e-124">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb0e-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccb0e-125">설명</span><span class="sxs-lookup"><span data-stu-id="ccb0e-125">Remarks</span></span>  
 <span data-ttu-id="ccb0e-126">`<roleClaimType>` 요소 집합에서 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> 속성 때는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccb0e-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb0e-127">예제</span><span class="sxs-lookup"><span data-stu-id="ccb0e-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccb0e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccb0e-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
