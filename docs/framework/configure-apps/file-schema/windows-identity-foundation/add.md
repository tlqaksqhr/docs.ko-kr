---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d863a0fc2b575aceef12370a57f7f7807261cb5a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltaddgt"></a><span data-ttu-id="45c0b-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="45c0b-102">&lt;add&gt;</span></span>
<span data-ttu-id="45c0b-103">토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="45c0b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="45c0b-104">\<system.identityModel></span></span>  
<span data-ttu-id="45c0b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="45c0b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="45c0b-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="45c0b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="45c0b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="45c0b-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c0b-108">구문</span><span class="sxs-lookup"><span data-stu-id="45c0b-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45c0b-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="45c0b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45c0b-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45c0b-111">특성</span><span class="sxs-lookup"><span data-stu-id="45c0b-111">Attributes</span></span>  
  
|<span data-ttu-id="45c0b-112">특성</span><span class="sxs-lookup"><span data-stu-id="45c0b-112">Attribute</span></span>|<span data-ttu-id="45c0b-113">설명</span><span class="sxs-lookup"><span data-stu-id="45c0b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45c0b-114">type</span><span class="sxs-lookup"><span data-stu-id="45c0b-114">type</span></span>|<span data-ttu-id="45c0b-115">추가할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="45c0b-116">지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45c0b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="45c0b-117">Child Elements</span></span>  
  
|<span data-ttu-id="45c0b-118">요소</span><span class="sxs-lookup"><span data-stu-id="45c0b-118">Element</span></span>|<span data-ttu-id="45c0b-119">설명</span><span class="sxs-lookup"><span data-stu-id="45c0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45c0b-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="45c0b-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="45c0b-121">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="45c0b-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="45c0b-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="45c0b-123">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="45c0b-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="45c0b-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="45c0b-125">에 대 한 구성을 제공 된 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="45c0b-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="45c0b-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="45c0b-127">에 대 한 선택적 구성을 제공 된 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스나 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45c0b-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="45c0b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="45c0b-129">요소</span><span class="sxs-lookup"><span data-stu-id="45c0b-129">Element</span></span>|<span data-ttu-id="45c0b-130">설명</span><span class="sxs-lookup"><span data-stu-id="45c0b-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45c0b-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="45c0b-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="45c0b-132">보안 토큰 처리기에 등록 된 끝점의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45c0b-133">설명</span><span class="sxs-lookup"><span data-stu-id="45c0b-133">Remarks</span></span>  
 <span data-ttu-id="45c0b-134">`<add>` 요소 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="45c0b-135">이 처리기 클래스를 통해 참조 되는 여부에 따라 달라는 `type` 특성에는 `<add>` 요소는이 기능에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="45c0b-136">이 기능을 제공 하는 토큰 처리기 클래스를 취하는 생성자를 노출 해야 합니다는 <xref:System.Xml.XmlElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="45c0b-137">이 기능을 제공 않는 몇 가지 기본 제공 보안 토큰 처리기 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="45c0b-138">이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="45c0b-139">토큰 처리기 컬렉션에 지정 된 형식의 단일 처리기만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="45c0b-140">즉, 예를 들어에서 파생 되는 처리기를 추가 하려는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 컬렉션을 먼저 제거 해야는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>는 컬렉션에서 기본적으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="45c0b-141">사용할 수 있습니다는 [ \<제거 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) 컬렉션 또는 사용에서 단일 처리기를 제거 하는 요소는 [ \<지우기 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) 모든 처리기 컬렉션에서 제거할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="45c0b-142">처리기에 지정 된 설정은 아래에 토큰 처리기 컬렉션에 지정 된 해당 설정은 재정의 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 에서 서비스 수준에서 지정 된 및 요소 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c0b-143">예</span><span class="sxs-lookup"><span data-stu-id="45c0b-143">Example</span></span>  
 <span data-ttu-id="45c0b-144">다음 XML에서는 `<add>` 및 `<remove>` 요소를 사용자 지정 세션 토큰 처리기의 기본 세션 토큰 처리기를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="45c0b-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="45c0b-145">XML에서 가져온 것은 `ClaimsAwareWebFarm` 샘플.</span><span class="sxs-lookup"><span data-stu-id="45c0b-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
