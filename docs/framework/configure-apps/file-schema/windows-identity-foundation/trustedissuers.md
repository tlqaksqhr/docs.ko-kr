---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="f8473-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="f8473-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="f8473-103">구성 기반 발급자 이름 레지스트리에서 사용 하는 신뢰할 수 있는 발급자 인증서 목록 구성 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="f8473-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="f8473-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f8473-104">\<system.identityModel></span></span>  
<span data-ttu-id="f8473-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f8473-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f8473-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f8473-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f8473-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f8473-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f8473-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="f8473-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="f8473-109">\<r s ></span><span class="sxs-lookup"><span data-stu-id="f8473-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8473-110">구문</span><span class="sxs-lookup"><span data-stu-id="f8473-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8473-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f8473-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f8473-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8473-113">특성</span><span class="sxs-lookup"><span data-stu-id="f8473-113">Attributes</span></span>  
 <span data-ttu-id="f8473-114">없음</span><span class="sxs-lookup"><span data-stu-id="f8473-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f8473-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f8473-115">Child Elements</span></span>  
  
|<span data-ttu-id="f8473-116">요소</span><span class="sxs-lookup"><span data-stu-id="f8473-116">Element</span></span>|<span data-ttu-id="f8473-117">설명</span><span class="sxs-lookup"><span data-stu-id="f8473-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="f8473-118">신뢰할 수 있는 발급자의 컬렉션에 인증서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="f8473-119">인증서가 지정 된는 `thumbprint` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="f8473-120">이 특성은 필수 이며 인증서 지 문의 ASN.1 인코딩 폼을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="f8473-121">`name` 특성은 선택적 이며 인증서에 대 한 이름을 지정 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="f8473-122">모든 인증서에서 신뢰할 수 있는 발급자의 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="f8473-123">신뢰할 수 있는 발급자의 컬렉션에서 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="f8473-124">인증서가 지정 된는 `thumbprint` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="f8473-125">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8473-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f8473-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f8473-127">요소</span><span class="sxs-lookup"><span data-stu-id="f8473-127">Element</span></span>|<span data-ttu-id="f8473-128">설명</span><span class="sxs-lookup"><span data-stu-id="f8473-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8473-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="f8473-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="f8473-130">발급자 이름 레지스트리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-130">Configures the issuer name registry.</span></span> <span data-ttu-id="f8473-131">**중요:** 는 `type` 특성의는 `<issuerNameRegistry>` 요소를 참조 해야 합니다는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 에 대 한 클래스는 `<trustedIssuers>` 요소 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8473-132">설명</span><span class="sxs-lookup"><span data-stu-id="f8473-132">Remarks</span></span>  
 <span data-ttu-id="f8473-133">Windows Identity Foundation (WIF)의 단일 구현이 제공는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 기본적으로 클래스는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="f8473-134">구성 발급자 이름 레지스트리 구성에서 로드 된 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="f8473-135">목록은 X.509 인증서의 발급자에 의해 생성 되는 토큰의 서명을 확인 하는 데 필요한 각 발급자 이름을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="f8473-136">신뢰할 수 있는 발급자 인증서 목록 아래에 지정 된 된 `<trustedIssuers>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="f8473-137">목록의 각 요소는 니모닉 발급자 이름을 해당 발급자에 의해 생성 되는 토큰의 서명을 확인 하는 데 필요한 X.509 인증서와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="f8473-138">신뢰할 수 있는 인증서는 인증서 지 문의 폼 인코딩된 ASN.1를 사용 하 여 지정 및 사용 하 여 컬렉션에 추가 됩니다 `<add>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="f8473-139">선택을 취소 하거나 발급자 (인증서)를 사용 하 여 목록에서 제거할 수는 `<clear>` 및 `<remove>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="f8473-140">`type` 특성의는 `<issuerNameRegistry>` 요소를 참조 해야 합니다는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 에 대 한 클래스는 `<trustedIssuers>` 요소 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8473-141">예제</span><span class="sxs-lookup"><span data-stu-id="f8473-141">Example</span></span>  
 <span data-ttu-id="f8473-142">다음 XML 기반 구성 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8473-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8473-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8473-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
