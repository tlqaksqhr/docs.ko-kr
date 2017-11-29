---
title: '&lt;roleClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 8a5de30d60478b6601781ac34fd481a6167462e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="87f1a-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="87f1a-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="87f1a-103">역할 유형 클레임의 컬렉션에서 정의 하는 클레임 유형을 지정 <xref:System.Security.Claims.ClaimsIdentity> 에서 반환 된 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 토큰 처리기의 메서드.</span><span class="sxs-lookup"><span data-stu-id="87f1a-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="87f1a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="87f1a-104">\<system.identityModel></span></span>  
<span data-ttu-id="87f1a-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="87f1a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="87f1a-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="87f1a-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="87f1a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="87f1a-107">\<add></span></span>  
<span data-ttu-id="87f1a-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="87f1a-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="87f1a-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="87f1a-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f1a-110">구문</span><span class="sxs-lookup"><span data-stu-id="87f1a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87f1a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87f1a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="87f1a-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87f1a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87f1a-113">특성</span><span class="sxs-lookup"><span data-stu-id="87f1a-113">Attributes</span></span>  
  
|<span data-ttu-id="87f1a-114">특성</span><span class="sxs-lookup"><span data-stu-id="87f1a-114">Attribute</span></span>|<span data-ttu-id="87f1a-115">설명</span><span class="sxs-lookup"><span data-stu-id="87f1a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87f1a-116">값</span><span class="sxs-lookup"><span data-stu-id="87f1a-116">value</span></span>|<span data-ttu-id="87f1a-117">역할 클레임 형식에 대해 사용할 클레임의 클레임 형식을 나타내는 URI를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="87f1a-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87f1a-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87f1a-118">Child Elements</span></span>  
 <span data-ttu-id="87f1a-119">없음</span><span class="sxs-lookup"><span data-stu-id="87f1a-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87f1a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87f1a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="87f1a-121">요소</span><span class="sxs-lookup"><span data-stu-id="87f1a-121">Element</span></span>|<span data-ttu-id="87f1a-122">설명</span><span class="sxs-lookup"><span data-stu-id="87f1a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87f1a-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="87f1a-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="87f1a-124">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="87f1a-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f1a-125">설명</span><span class="sxs-lookup"><span data-stu-id="87f1a-125">Remarks</span></span>  
 <span data-ttu-id="87f1a-126">`<roleClaimType>` 요소 집합에서 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> 속성 때는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f1a-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87f1a-127">예제</span><span class="sxs-lookup"><span data-stu-id="87f1a-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87f1a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87f1a-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
