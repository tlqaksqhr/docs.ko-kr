---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a008919cc068ca5cdd841ec67f1a7194bbffcd8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="93571-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="93571-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="93571-103">메시지 발신자가 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="93571-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93571-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93571-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="93571-105">\<behaviors></span></span>  
<span data-ttu-id="93571-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="93571-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="93571-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="93571-107">\<behavior></span></span>  
<span data-ttu-id="93571-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="93571-108">\<serviceCredentials></span></span>  
<span data-ttu-id="93571-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="93571-109">\<peer></span></span>  
<span data-ttu-id="93571-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="93571-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93571-111">구문</span><span class="sxs-lookup"><span data-stu-id="93571-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93571-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="93571-112">Attributes and Elements</span></span>  
 <span data-ttu-id="93571-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93571-114">특성</span><span class="sxs-lookup"><span data-stu-id="93571-114">Attributes</span></span>  
  
|<span data-ttu-id="93571-115">특성</span><span class="sxs-lookup"><span data-stu-id="93571-115">Attribute</span></span>|<span data-ttu-id="93571-116">설명</span><span class="sxs-lookup"><span data-stu-id="93571-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="93571-117">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-117">Optional enumeration.</span></span> <span data-ttu-id="93571-118">자격 증명의 유효성을 검사하는 데 사용되는 5개 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="93571-119">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="93571-120">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="93571-121">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-121">Optional string.</span></span> <span data-ttu-id="93571-122">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="93571-123">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="93571-124">이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="93571-125">에서는 신뢰할 수 있는 사용자의 저장소를 대상으로 피어 인증서를 확인하는 기본 피어 인증서 유효성 검사기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="93571-126">이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="93571-127">사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93571-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="93571-128">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-128">Optional enumeration.</span></span> <span data-ttu-id="93571-129">인증서 해지 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="93571-130">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="93571-131">시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="93571-132">이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="93571-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="93571-133">이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93571-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="93571-134">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-134">Optional enumeration.</span></span> <span data-ttu-id="93571-135">피어 인증서의 유효성이 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 보안 시스템에 의해 확인되는, 신뢰할 수 있는 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="93571-136">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="93571-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93571-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93571-137">Child Elements</span></span>  
 <span data-ttu-id="93571-138">없음</span><span class="sxs-lookup"><span data-stu-id="93571-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93571-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93571-139">Parent Elements</span></span>  
  
|<span data-ttu-id="93571-140">요소</span><span class="sxs-lookup"><span data-stu-id="93571-140">Element</span></span>|<span data-ttu-id="93571-141">설명</span><span class="sxs-lookup"><span data-stu-id="93571-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93571-142">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="93571-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="93571-143">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93571-144">설명</span><span class="sxs-lookup"><span data-stu-id="93571-144">Remarks</span></span>  
 <span data-ttu-id="93571-145">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="93571-146">제공 하는 인증서를 사용 하 여 각 메시지는 서명 하는 출력 채널에 대해 [ \<인증서 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93571-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="93571-147">모든 메시지는 응용 프로그램에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="93571-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="93571-148">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93571-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93571-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93571-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="93571-150">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="93571-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="93571-151">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="93571-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="93571-152">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="93571-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="93571-153">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="93571-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="93571-154">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="93571-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
