---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 646833f277c3ef4675a835ca0af3daf647e01224
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="b8673-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="b8673-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="b8673-103">토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b8673-104">발급자 토큰 확인 자가 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b8673-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b8673-105">\<system.identityModel></span></span>  
<span data-ttu-id="b8673-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8673-106">\<identityConfiguration></span></span>  
<span data-ttu-id="b8673-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b8673-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b8673-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b8673-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b8673-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b8673-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8673-110">구문</span><span class="sxs-lookup"><span data-stu-id="b8673-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8673-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8673-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b8673-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8673-113">특성</span><span class="sxs-lookup"><span data-stu-id="b8673-113">Attributes</span></span>  
  
|<span data-ttu-id="b8673-114">특성</span><span class="sxs-lookup"><span data-stu-id="b8673-114">Attribute</span></span>|<span data-ttu-id="b8673-115">설명</span><span class="sxs-lookup"><span data-stu-id="b8673-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8673-116">type</span><span class="sxs-lookup"><span data-stu-id="b8673-116">type</span></span>|<span data-ttu-id="b8673-117">발급자 토큰 확인 자가 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b8673-118">중 하나 여야 합니다는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스 또는 형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b8673-119">필수.</span><span class="sxs-lookup"><span data-stu-id="b8673-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8673-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8673-120">Child Elements</span></span>  
 <span data-ttu-id="b8673-121">없음</span><span class="sxs-lookup"><span data-stu-id="b8673-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8673-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8673-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b8673-123">요소</span><span class="sxs-lookup"><span data-stu-id="b8673-123">Element</span></span>|<span data-ttu-id="b8673-124">설명</span><span class="sxs-lookup"><span data-stu-id="b8673-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8673-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b8673-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b8673-126">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8673-127">설명</span><span class="sxs-lookup"><span data-stu-id="b8673-127">Remarks</span></span>  
 <span data-ttu-id="b8673-128">발급자 토큰 확인 자가 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b8673-129">서명을 확인 하는 중에 사용 되는 암호화 관련 자료를 검색 하는 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b8673-130">지정 해야 합니다는 `type` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="b8673-131">지정 된 형식의 수 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 또는 사용자 지정 형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b8673-132">일부 토큰 처리기에는 구성에서 발급자 토큰 확인자 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b8673-133">개별 토큰 처리기의 설정을 재정의 보안 토큰 처리기 컬렉션에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8673-134">지정 하는 `<issuerTokenResolver>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b8673-135">설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8673-136">예제</span><span class="sxs-lookup"><span data-stu-id="b8673-136">Example</span></span>  
 <span data-ttu-id="b8673-137">다음 XML에서 파생 되는 사용자 지정 클래스를 기반으로 하는 발급자 토큰 확인자에 대 한 구성을 보여 줍니다 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b8673-138">토큰 확인 자가 사용자 지정 구성 요소에서 초기화 된 대상 그룹 키 쌍의 사전 유지 관리 (`<AddAudienceKeyPair>`) 클래스에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b8673-139">클래스 재정의 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 이 요소를 처리 하기 위해 메서드.</span><span class="sxs-lookup"><span data-stu-id="b8673-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b8673-140">재정의 다음 예에서 같습니다. 그러나 간단히 하기 위해 호출 하는 메서드 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8673-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b8673-141">전체 예제를 참조 하십시오.는 `CustomToken` 샘플.</span><span class="sxs-lookup"><span data-stu-id="b8673-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b8673-142">예제</span><span class="sxs-lookup"><span data-stu-id="b8673-142">Example</span></span>  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8673-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8673-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
