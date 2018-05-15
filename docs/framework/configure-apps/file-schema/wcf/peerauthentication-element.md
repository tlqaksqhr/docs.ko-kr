---
title: '&lt;peerAuthentication&gt; 요소'
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: db544b1bbf46d0656b763d5be769d9521a299f1a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="ae36c-102">&lt;peerAuthentication&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="ae36c-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="ae36c-103">피어 투 피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="ae36c-104">피어 투 피어 프로그래밍에 대 한 자세한 내용은 참조 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="ae36c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae36c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae36c-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ae36c-106">\<behaviors></span></span>  
<span data-ttu-id="ae36c-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ae36c-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="ae36c-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ae36c-108">\<behavior></span></span>  
<span data-ttu-id="ae36c-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ae36c-109">\<clientCredentials></span></span>  
<span data-ttu-id="ae36c-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="ae36c-110">\<peer></span></span>  
<span data-ttu-id="ae36c-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="ae36c-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae36c-112">구문</span><span class="sxs-lookup"><span data-stu-id="ae36c-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae36c-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ae36c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ae36c-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae36c-115">특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-115">Attributes</span></span>  
  
|<span data-ttu-id="ae36c-116">특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-116">Attribute</span></span>|<span data-ttu-id="ae36c-117">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="ae36c-118">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-118">Optional string.</span></span> <span data-ttu-id="ae36c-119">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ae36c-120">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="ae36c-121">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-121">Optional enumeration.</span></span> <span data-ttu-id="ae36c-122">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="ae36c-123">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="ae36c-124">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="ae36c-125">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-125">Optional enumeration.</span></span> <span data-ttu-id="ae36c-126">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="ae36c-127">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ae36c-128">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-128">Optional enumeration.</span></span> <span data-ttu-id="ae36c-129">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ae36c-130">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="ae36c-131">에 대해 유효성 검사가 수행 되는 **신뢰할 수 있는 사용자** 지정한 저장소 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="ae36c-132">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="ae36c-133">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="ae36c-134">값</span><span class="sxs-lookup"><span data-stu-id="ae36c-134">Value</span></span>|<span data-ttu-id="ae36c-135">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae36c-136">문자열</span><span class="sxs-lookup"><span data-stu-id="ae36c-136">String</span></span>|<span data-ttu-id="ae36c-137">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="ae36c-138">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="ae36c-139">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="ae36c-140">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="ae36c-141">값</span><span class="sxs-lookup"><span data-stu-id="ae36c-141">Value</span></span>|<span data-ttu-id="ae36c-142">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae36c-143">열거형</span><span class="sxs-lookup"><span data-stu-id="ae36c-143">Enumeration</span></span>|<span data-ttu-id="ae36c-144">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="ae36c-145">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="ae36c-146">자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="ae36c-147">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="ae36c-148">값</span><span class="sxs-lookup"><span data-stu-id="ae36c-148">Value</span></span>|<span data-ttu-id="ae36c-149">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae36c-150">열거형</span><span class="sxs-lookup"><span data-stu-id="ae36c-150">Enumeration</span></span>|<span data-ttu-id="ae36c-151">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="ae36c-152">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="ae36c-153">자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="ae36c-154">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="ae36c-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="ae36c-155">값</span><span class="sxs-lookup"><span data-stu-id="ae36c-155">Value</span></span>|<span data-ttu-id="ae36c-156">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae36c-157">열거형</span><span class="sxs-lookup"><span data-stu-id="ae36c-157">Enumeration</span></span>|<span data-ttu-id="ae36c-158">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ae36c-159">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="ae36c-160">시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="ae36c-161">사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae36c-162">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ae36c-162">Child Elements</span></span>  
 <span data-ttu-id="ae36c-163">없음</span><span class="sxs-lookup"><span data-stu-id="ae36c-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae36c-164">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ae36c-164">Parent Elements</span></span>  
  
|<span data-ttu-id="ae36c-165">요소</span><span class="sxs-lookup"><span data-stu-id="ae36c-165">Element</span></span>|<span data-ttu-id="ae36c-166">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae36c-167">\<peer></span><span class="sxs-lookup"><span data-stu-id="ae36c-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="ae36c-168">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae36c-169">설명</span><span class="sxs-lookup"><span data-stu-id="ae36c-169">Remarks</span></span>  
 <span data-ttu-id="ae36c-170">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="ae36c-171">이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="ae36c-172">새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="ae36c-173">원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="ae36c-174">메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae36c-175">예제</span><span class="sxs-lookup"><span data-stu-id="ae36c-175">Example</span></span>  
 <span data-ttu-id="ae36c-176">다음 코드에서는 인증서 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae36c-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae36c-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae36c-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="ae36c-178">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="ae36c-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ae36c-179">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="ae36c-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ae36c-180">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="ae36c-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ae36c-181">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="ae36c-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ae36c-182">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="ae36c-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
