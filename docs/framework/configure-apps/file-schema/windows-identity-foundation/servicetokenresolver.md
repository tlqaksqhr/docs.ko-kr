---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755762"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="3087d-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="3087d-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="3087d-103">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3087d-104">서비스 토큰 확인 자가 들어오는 토큰 및 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="3087d-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3087d-105">\<system.identityModel></span></span>  
<span data-ttu-id="3087d-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3087d-106">\<identityConfiguration></span></span>  
<span data-ttu-id="3087d-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3087d-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3087d-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3087d-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="3087d-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="3087d-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3087d-110">구문</span><span class="sxs-lookup"><span data-stu-id="3087d-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3087d-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3087d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3087d-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3087d-113">특성</span><span class="sxs-lookup"><span data-stu-id="3087d-113">Attributes</span></span>  
  
|<span data-ttu-id="3087d-114">특성</span><span class="sxs-lookup"><span data-stu-id="3087d-114">Attribute</span></span>|<span data-ttu-id="3087d-115">설명</span><span class="sxs-lookup"><span data-stu-id="3087d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3087d-116">type</span><span class="sxs-lookup"><span data-stu-id="3087d-116">type</span></span>|<span data-ttu-id="3087d-117">서비스 토큰 확인 자가 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="3087d-118">중 하나는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 형식 또는 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="3087d-119">지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3087d-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="3087d-120">필수.</span><span class="sxs-lookup"><span data-stu-id="3087d-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3087d-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3087d-121">Child Elements</span></span>  
 <span data-ttu-id="3087d-122">없음</span><span class="sxs-lookup"><span data-stu-id="3087d-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3087d-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3087d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3087d-124">요소</span><span class="sxs-lookup"><span data-stu-id="3087d-124">Element</span></span>|<span data-ttu-id="3087d-125">설명</span><span class="sxs-lookup"><span data-stu-id="3087d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3087d-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3087d-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3087d-127">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3087d-128">설명</span><span class="sxs-lookup"><span data-stu-id="3087d-128">Remarks</span></span>  
 <span data-ttu-id="3087d-129">들어오는 토큰 및 메시지 암호화 토큰을 확인 하려면 서비스 토큰 확인 자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="3087d-130">들어오는 토큰의 암호를 해독 하는 데 사용 해야 하는 키를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="3087d-131">지정 해야 합니다는 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="3087d-132">지정 된 형식의 수 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="3087d-133">일부 토큰 처리기를 사용 하면 구성에서 서비스 토큰 확인자 설정을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="3087d-134">개별 토큰 처리기의 설정을 재정의 보안 토큰 처리기 컬렉션에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3087d-135">지정 하는 `<serviceTokenResolver>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3087d-136">설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3087d-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3087d-137">예제</span><span class="sxs-lookup"><span data-stu-id="3087d-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
