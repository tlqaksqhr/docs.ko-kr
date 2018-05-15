---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="d20c5-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="d20c5-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="d20c5-103">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="d20c5-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d20c5-104">\<system.identityModel></span></span>  
<span data-ttu-id="d20c5-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d20c5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d20c5-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d20c5-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d20c5-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d20c5-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d20c5-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="d20c5-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d20c5-109">구문</span><span class="sxs-lookup"><span data-stu-id="d20c5-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d20c5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d20c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d20c5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d20c5-112">특성</span><span class="sxs-lookup"><span data-stu-id="d20c5-112">Attributes</span></span>  
  
|<span data-ttu-id="d20c5-113">특성</span><span class="sxs-lookup"><span data-stu-id="d20c5-113">Attribute</span></span>|<span data-ttu-id="d20c5-114">설명</span><span class="sxs-lookup"><span data-stu-id="d20c5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d20c5-115">type</span><span class="sxs-lookup"><span data-stu-id="d20c5-115">type</span></span>|<span data-ttu-id="d20c5-116">파생 되는 형식을 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d20c5-117">사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d20c5-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d20c5-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d20c5-118">Child Elements</span></span>  
  
|<span data-ttu-id="d20c5-119">요소</span><span class="sxs-lookup"><span data-stu-id="d20c5-119">Element</span></span>|<span data-ttu-id="d20c5-120">설명</span><span class="sxs-lookup"><span data-stu-id="d20c5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d20c5-121">\<r s ></span><span class="sxs-lookup"><span data-stu-id="d20c5-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="d20c5-122">경우는 `type` 특성 지정 구성 기반 발급자 이름 레지스트리 (의 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="d20c5-123">[ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소 표시 되려면 `<add>`, `<clear>`, 또는 `<remove>` 자식 요소로 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d20c5-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d20c5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d20c5-125">요소</span><span class="sxs-lookup"><span data-stu-id="d20c5-125">Element</span></span>|<span data-ttu-id="d20c5-126">설명</span><span class="sxs-lookup"><span data-stu-id="d20c5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d20c5-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d20c5-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d20c5-128">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d20c5-129">설명</span><span class="sxs-lookup"><span data-stu-id="d20c5-129">Remarks</span></span>  
 <span data-ttu-id="d20c5-130">모든 발급자 토큰 발급자 이름 레지스트리를 사용 하 여 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="d20c5-131">이것은 개체에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d20c5-132">발급자 이름 레지스트리 해당 발급자에 의해 생성 되는 토큰의 서명을 확인 하는 데 필요한 암호화 자료에 니모닉 이름을 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="d20c5-133">발급자 이름 레지스트리 신뢰 당사자 (RP) 응용 프로그램에서 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="d20c5-134">사용 하 여 지정 된 발급자 이름 레지스트리 형식은 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="d20c5-135">`<issuerNameRegistry>` 요소는 지정된 된 형식에 대 한 구성 정보를 제공 하는 하나 이상의 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="d20c5-136">재정의 하 여 이러한 하위 요소를 처리 하는 논리를 제공 하는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d20c5-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="d20c5-137">WIF 형식을 제공 하는 단일 발급자 이름 레지스트리 기본적으로 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d20c5-138">이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="d20c5-139">자식 구성 요소 필요 `<trustedIssuers>`에서 신뢰할 수 있는 발급자 인증서 컬렉션에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="d20c5-140">ASN.1를 사용 하 여 인증서 지 문의 폼 인코딩 및 추가 또는 사용 하 여 컬렉션에서 제거할 지정 된 인증서를 신뢰할 수 있는 `<add>`, `<clear>`, 또는 `<remove>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d20c5-141">`<issuerNameRegistry>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d20c5-142">지정 하는 `<issuerNameRegistry>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d20c5-143">설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d20c5-144">예제</span><span class="sxs-lookup"><span data-stu-id="d20c5-144">Example</span></span>  
 <span data-ttu-id="d20c5-145">다음 XML 기반 구성 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d20c5-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d20c5-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d20c5-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
