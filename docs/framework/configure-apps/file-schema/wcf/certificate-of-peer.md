---
title: "&lt;peer&gt;의 &lt;certificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f46ebab92cbca616b06db5be6dc155a44558aa7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="67e48-102">&lt;peer&gt;의 &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="67e48-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="67e48-103">피어에서 사용하는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="67e48-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="67e48-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="67e48-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="67e48-105">\<behaviors></span></span>  
<span data-ttu-id="67e48-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="67e48-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="67e48-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="67e48-107">\<behavior></span></span>  
<span data-ttu-id="67e48-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="67e48-108">\<serviceCredentials></span></span>  
<span data-ttu-id="67e48-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="67e48-109">\<peer></span></span>  
<span data-ttu-id="67e48-110">\<인증서 ></span><span class="sxs-lookup"><span data-stu-id="67e48-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e48-111">구문</span><span class="sxs-lookup"><span data-stu-id="67e48-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67e48-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="67e48-112">Attributes and Elements</span></span>  
 <span data-ttu-id="67e48-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67e48-114">특성</span><span class="sxs-lookup"><span data-stu-id="67e48-114">Attributes</span></span>  
  
|<span data-ttu-id="67e48-115">특성</span><span class="sxs-lookup"><span data-stu-id="67e48-115">Attribute</span></span>|<span data-ttu-id="67e48-116">설명</span><span class="sxs-lookup"><span data-stu-id="67e48-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="67e48-117">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="67e48-118">이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="67e48-119">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="67e48-120">클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="67e48-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="67e48-122">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="67e48-123">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="67e48-124">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="67e48-125">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="67e48-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="67e48-127">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="67e48-128">-AuthRoot: 인증서 저장소에서 타사 인증 기관 (Ca)입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="67e48-129">-CertificateAuthority: 중개 ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="67e48-130">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="67e48-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="67e48-131">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="67e48-132">-Root: 신뢰할 수 있는 루트 인증 기관 (Ca)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="67e48-133">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="67e48-134">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="67e48-135">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="67e48-136">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="67e48-137">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="67e48-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="67e48-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="67e48-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="67e48-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="67e48-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="67e48-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="67e48-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="67e48-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="67e48-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="67e48-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="67e48-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="67e48-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="67e48-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="67e48-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="67e48-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="67e48-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="67e48-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="67e48-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="67e48-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="67e48-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="67e48-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="67e48-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="67e48-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="67e48-149">-   FindByExtension</span></span><br /><span data-ttu-id="67e48-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="67e48-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="67e48-151">-Findbysubjectkeyidentifier가</span><span class="sxs-lookup"><span data-stu-id="67e48-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="67e48-152">`findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="67e48-153">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67e48-154">자식 요소</span><span class="sxs-lookup"><span data-stu-id="67e48-154">Child Elements</span></span>  
 <span data-ttu-id="67e48-155">없음</span><span class="sxs-lookup"><span data-stu-id="67e48-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67e48-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="67e48-156">Parent Elements</span></span>  
  
|<span data-ttu-id="67e48-157">요소</span><span class="sxs-lookup"><span data-stu-id="67e48-157">Element</span></span>|<span data-ttu-id="67e48-158">설명</span><span class="sxs-lookup"><span data-stu-id="67e48-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67e48-159">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="67e48-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="67e48-160">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e48-161">설명</span><span class="sxs-lookup"><span data-stu-id="67e48-161">Remarks</span></span>  
 <span data-ttu-id="67e48-162">이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 `X509Certificate2` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="67e48-163">피어 투 피어 프로그래밍에 대 한 자세한 내용은 참조 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67e48-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e48-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67e48-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="67e48-165">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="67e48-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="67e48-166">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="67e48-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="67e48-167">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="67e48-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="67e48-168">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="67e48-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="67e48-169">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="67e48-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="67e48-170">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="67e48-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
