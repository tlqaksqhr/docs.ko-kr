---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: be98c93452c9c7a37ecad5b03f5160ea08f2c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="2c6dc-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="2c6dc-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="2c6dc-103">토큰 처리기의 컬렉션에 대 한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="2c6dc-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-104">\<system.identityModel></span></span>  
<span data-ttu-id="2c6dc-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2c6dc-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2c6dc-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6dc-108">구문</span><span class="sxs-lookup"><span data-stu-id="2c6dc-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c6dc-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c6dc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2c6dc-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c6dc-111">특성</span><span class="sxs-lookup"><span data-stu-id="2c6dc-111">Attributes</span></span>  
  
|<span data-ttu-id="2c6dc-112">특성</span><span class="sxs-lookup"><span data-stu-id="2c6dc-112">Attribute</span></span>|<span data-ttu-id="2c6dc-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c6dc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c6dc-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="2c6dc-114">saveBootstrapContext</span></span>|<span data-ttu-id="2c6dc-115">세션 토큰에 부트스트랩 토큰이 포함할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="2c6dc-116">값 설정할 수도 있습니다 토큰 처리기 컬렉션에 설정 하 여는 `saveBootstrapContext` 특성에 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="2c6dc-117">토큰 처리기 컬렉션에 설정 된 값에는 서비스에 설정 된 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="2c6dc-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="2c6dc-118">maximumClockSkew</span></span>|<span data-ttu-id="2c6dc-119">A <xref:System.TimeSpan> 최대 허용 된 클럭 오차를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="2c6dc-120">로그인 세션의 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 최대 허용 된 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="2c6dc-121">기본값은 5 분 "00: 05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="2c6dc-122">지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값, 참조 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="2c6dc-123">최대 클럭 오차 설정할 수도 있습니다 서비스 수준에서 설정 하 여는 `maximumClockSkew` 특성에 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="2c6dc-124">토큰 처리기 컬렉션에 설정 된 값에는 서비스에 설정 된 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c6dc-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c6dc-125">Child Elements</span></span>  
  
|<span data-ttu-id="2c6dc-126">요소</span><span class="sxs-lookup"><span data-stu-id="2c6dc-126">Element</span></span>|<span data-ttu-id="2c6dc-127">설명</span><span class="sxs-lookup"><span data-stu-id="2c6dc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c6dc-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="2c6dc-129">이 신뢰 당사자의 식별자를 허용 하는 Uri의 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="2c6dc-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-130">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-131">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="2c6dc-132">세션 토큰에서 토큰 재생 검색에 사용 되는 캐시에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="2c6dc-133">서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="2c6dc-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-134">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="2c6dc-136">토큰 처리기 인증서의 유효성을 검사 하기 위해 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="2c6dc-137">서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="2c6dc-138">특정 처리기 자체적인 검사기로 구성 된 경우이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="2c6dc-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-139">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="2c6dc-141">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="2c6dc-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-142">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="2c6dc-144">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="2c6dc-145">발급자 토큰 확인 자가 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="2c6dc-146">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-146">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="2c6dc-148">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="2c6dc-149">서비스 토큰 확인 자가 들어오는 토큰 및 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="2c6dc-150">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-150">Optional.</span></span>|  
|[<span data-ttu-id="2c6dc-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="2c6dc-152">토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="2c6dc-153">서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="2c6dc-154">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c6dc-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c6dc-155">Parent Elements</span></span>  
  
|<span data-ttu-id="2c6dc-156">요소</span><span class="sxs-lookup"><span data-stu-id="2c6dc-156">Element</span></span>|<span data-ttu-id="2c6dc-157">설명</span><span class="sxs-lookup"><span data-stu-id="2c6dc-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c6dc-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="2c6dc-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="2c6dc-159">보안 토큰 처리기에 등록 된 끝점의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6dc-160">설명</span><span class="sxs-lookup"><span data-stu-id="2c6dc-160">Remarks</span></span>  
 <span data-ttu-id="2c6dc-161">이 섹션에서는 속성 값에 대 한는 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="2c6dc-162">서비스에 구성 된이 섹션에 구성 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="2c6dc-163">이러한 설정 중 일부 처리기는 보안 토큰 처리기 컬렉션에 추가 될 때 지정 된 설정으로 재정의할 차례로 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6dc-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c6dc-164">예제</span><span class="sxs-lookup"><span data-stu-id="2c6dc-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
