---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 103ee50e86a809ee4a5e36451fd9e6b99fc3bb2c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="ace27-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="ace27-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="ace27-103">피어 노드에서 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="ace27-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ace27-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ace27-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ace27-105">\<behaviors></span></span>  
<span data-ttu-id="ace27-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ace27-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ace27-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ace27-107">\<behavior></span></span>  
<span data-ttu-id="ace27-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="ace27-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ace27-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="ace27-109">\<peer></span></span>  
<span data-ttu-id="ace27-110">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ace27-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace27-111">구문</span><span class="sxs-lookup"><span data-stu-id="ace27-111">Syntax</span></span>  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ace27-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ace27-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ace27-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ace27-114">특성</span><span class="sxs-lookup"><span data-stu-id="ace27-114">Attributes</span></span>  
  
|<span data-ttu-id="ace27-115">특성</span><span class="sxs-lookup"><span data-stu-id="ace27-115">Attribute</span></span>|<span data-ttu-id="ace27-116">설명</span><span class="sxs-lookup"><span data-stu-id="ace27-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="ace27-117">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-117">Optional enumeration.</span></span> <span data-ttu-id="ace27-118">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="ace27-119">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="ace27-120">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="ace27-121">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-121">Optional string.</span></span> <span data-ttu-id="ace27-122">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ace27-123">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="ace27-124">이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="ace27-125">에서는 신뢰할 수 있는 사용자의 저장소를 대상으로 피어 인증서를 확인하는 기본 피어 인증서 유효성 검사기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="ace27-126">이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="ace27-127">사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="ace27-128">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-128">Optional enumeration.</span></span> <span data-ttu-id="ace27-129">인증서 해지 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="ace27-130">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="ace27-131">시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="ace27-132">이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="ace27-133">이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ace27-134">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-134">Optional enumeration.</span></span> <span data-ttu-id="ace27-135">피어 인증서의 유효성이 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 보안 시스템에 의해 확인되는, 신뢰할 수 있는 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="ace27-136">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ace27-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ace27-137">Child Elements</span></span>  
 <span data-ttu-id="ace27-138">없음</span><span class="sxs-lookup"><span data-stu-id="ace27-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ace27-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ace27-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ace27-140">요소</span><span class="sxs-lookup"><span data-stu-id="ace27-140">Element</span></span>|<span data-ttu-id="ace27-141">설명</span><span class="sxs-lookup"><span data-stu-id="ace27-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ace27-142">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="ace27-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="ace27-143">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace27-144">설명</span><span class="sxs-lookup"><span data-stu-id="ace27-144">Remarks</span></span>  
 <span data-ttu-id="ace27-145">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="ace27-146">이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="ace27-147">새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="ace27-148">원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="ace27-149">메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ace27-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace27-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ace27-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="ace27-151">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="ace27-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ace27-152">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="ace27-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ace27-153">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="ace27-153">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ace27-154">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="ace27-154">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ace27-155">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="ace27-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
