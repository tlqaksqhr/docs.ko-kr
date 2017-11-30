---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4ffe9764eb730be4859fb66ae2f0cc845c9404e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="52ba9-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="52ba9-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="52ba9-103">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="52ba9-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="52ba9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="52ba9-104">\<system.identityModel></span></span>  
<span data-ttu-id="52ba9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="52ba9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="52ba9-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="52ba9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="52ba9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="52ba9-107">\<add></span></span>  
<span data-ttu-id="52ba9-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="52ba9-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ba9-109">구문</span><span class="sxs-lookup"><span data-stu-id="52ba9-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52ba9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52ba9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="52ba9-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52ba9-112">특성</span><span class="sxs-lookup"><span data-stu-id="52ba9-112">Attributes</span></span>  
  
|<span data-ttu-id="52ba9-113">특성</span><span class="sxs-lookup"><span data-stu-id="52ba9-113">Attribute</span></span>|<span data-ttu-id="52ba9-114">설명</span><span class="sxs-lookup"><span data-stu-id="52ba9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52ba9-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="52ba9-115">membershipProviderName</span></span>|<span data-ttu-id="52ba9-116">지정 된 <xref:System.Web.Security.MembershipProvider> 하는 보안 토큰 처리기에서 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba9-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52ba9-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52ba9-117">Child Elements</span></span>  
 <span data-ttu-id="52ba9-118">없음</span><span class="sxs-lookup"><span data-stu-id="52ba9-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52ba9-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52ba9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="52ba9-120">요소</span><span class="sxs-lookup"><span data-stu-id="52ba9-120">Element</span></span>|<span data-ttu-id="52ba9-121">설명</span><span class="sxs-lookup"><span data-stu-id="52ba9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ba9-122">\<add></span><span class="sxs-lookup"><span data-stu-id="52ba9-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="52ba9-123">토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52ba9-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ba9-124">설명</span><span class="sxs-lookup"><span data-stu-id="52ba9-124">Remarks</span></span>  
 <span data-ttu-id="52ba9-125">`<userNameSecurityTokenHandlerRequirement>` 요소 집합에서 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> 속성 때는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 개체 구성에서 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ba9-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ba9-126">예제</span><span class="sxs-lookup"><span data-stu-id="52ba9-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
