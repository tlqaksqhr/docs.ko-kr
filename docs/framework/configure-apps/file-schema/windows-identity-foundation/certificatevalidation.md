---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7a5d31bce5f71e644b40b3aa7e7c0c1c8790cab6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="cc545-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="cc545-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="cc545-103">토큰 처리기 인증서의 유효성을 검사 하기 위해 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="cc545-104">특정 처리기 자체적인 검사기로 구성 된 경우이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="cc545-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="cc545-105">\<system.identityModel></span></span>  
<span data-ttu-id="cc545-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cc545-106">\<identityConfiguration></span></span>  
<span data-ttu-id="cc545-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="cc545-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc545-108">구문</span><span class="sxs-lookup"><span data-stu-id="cc545-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc545-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cc545-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc545-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc545-111">특성</span><span class="sxs-lookup"><span data-stu-id="cc545-111">Attributes</span></span>  
  
|<span data-ttu-id="cc545-112">특성</span><span class="sxs-lookup"><span data-stu-id="cc545-112">Attribute</span></span>|<span data-ttu-id="cc545-113">설명</span><span class="sxs-lookup"><span data-stu-id="cc545-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc545-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="cc545-114">certificateValidationMode</span></span>|<span data-ttu-id="cc545-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cc545-116">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="cc545-117">사용자 지정 유효성 검사기를 지정 하려면이 특성을 "Custom"으로 설정 하 고 사용 하 여 유효성 검사기를 지정 된 [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="cc545-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-118">Optional.</span></span>|  
|<span data-ttu-id="cc545-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="cc545-119">revocationMode</span></span>|<span data-ttu-id="cc545-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> X.509 인증서에 대해 사용 하는 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cc545-121">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-121">The default value is "Online".</span></span> <span data-ttu-id="cc545-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-122">Optional.</span></span>|  
|<span data-ttu-id="cc545-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="cc545-123">trustedStoreLocation</span></span>|<span data-ttu-id="cc545-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="cc545-125">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="cc545-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc545-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cc545-127">Child Elements</span></span>  
  
|<span data-ttu-id="cc545-128">요소</span><span class="sxs-lookup"><span data-stu-id="cc545-128">Element</span></span>|<span data-ttu-id="cc545-129">설명</span><span class="sxs-lookup"><span data-stu-id="cc545-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc545-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="cc545-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="cc545-131">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="cc545-132">이 이와 같은 경우에 사용 되는 `certificateValidationMode` 특성에는 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) "Custom"으로 설정 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc545-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cc545-133">Parent Elements</span></span>  
  
|<span data-ttu-id="cc545-134">요소</span><span class="sxs-lookup"><span data-stu-id="cc545-134">Element</span></span>|<span data-ttu-id="cc545-135">설명</span><span class="sxs-lookup"><span data-stu-id="cc545-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc545-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cc545-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="cc545-137">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="cc545-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cc545-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="cc545-139">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc545-140">설명</span><span class="sxs-lookup"><span data-stu-id="cc545-140">Remarks</span></span>  
 <span data-ttu-id="cc545-141">A `<certificateValidation>` 에서 서비스 수준에서 요소를 지정할 수 있습니다는 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준 아래에 `<securityTokenHandlerConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="cc545-142">서비스에 지정 된 토큰 처리기 컬렉션에 대 한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="cc545-143">일부 토큰 처리기에는 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="cc545-144">서비스 수준에서 및 보안 토큰 처리기 컬렉션에 개별 토큰 처리기의 설정을 지정 된 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cc545-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc545-145">예</span><span class="sxs-lookup"><span data-stu-id="cc545-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
