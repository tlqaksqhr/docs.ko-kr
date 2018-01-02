---
title: "&lt;certificate&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc971cae9c09a75c43f568ccbf1b4608704be30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="2b6d0-102">&lt;certificate&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="2b6d0-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="2b6d0-103">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="2b6d0-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2b6d0-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-105">\<behaviors></span></span>  
<span data-ttu-id="2b6d0-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2b6d0-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-107">\<behavior></span></span>  
<span data-ttu-id="2b6d0-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-108">\<clientCredentials></span></span>  
<span data-ttu-id="2b6d0-109">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-109">\<peer></span></span>  
<span data-ttu-id="2b6d0-110">\<인증서 ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6d0-111">구문</span><span class="sxs-lookup"><span data-stu-id="2b6d0-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b6d0-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2b6d0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2b6d0-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b6d0-114">특성</span><span class="sxs-lookup"><span data-stu-id="2b6d0-114">Attributes</span></span>  
  
|<span data-ttu-id="2b6d0-115">특성</span><span class="sxs-lookup"><span data-stu-id="2b6d0-115">Attribute</span></span>|<span data-ttu-id="2b6d0-116">설명</span><span class="sxs-lookup"><span data-stu-id="2b6d0-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="2b6d0-117">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="2b6d0-118">이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="2b6d0-119">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="2b6d0-120">클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="2b6d0-121">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2b6d0-122">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="2b6d0-123">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="2b6d0-124">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="2b6d0-125">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="2b6d0-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2b6d0-127">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="2b6d0-128">-AuthRoot: 인증서 저장소 공급 업체 Ca (인증 기관)입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="2b6d0-129">-CertificateAuthority: 중개 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="2b6d0-130">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="2b6d0-131">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="2b6d0-132">-Root: 신뢰할 수 있는 루트 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="2b6d0-133">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="2b6d0-134">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="2b6d0-135">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="2b6d0-136">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="2b6d0-137">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2b6d0-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="2b6d0-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="2b6d0-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="2b6d0-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="2b6d0-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="2b6d0-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="2b6d0-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="2b6d0-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="2b6d0-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="2b6d0-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="2b6d0-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="2b6d0-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="2b6d0-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="2b6d0-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="2b6d0-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="2b6d0-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="2b6d0-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="2b6d0-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="2b6d0-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="2b6d0-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="2b6d0-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="2b6d0-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="2b6d0-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="2b6d0-149">-   FindByExtension</span></span><br /><span data-ttu-id="2b6d0-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="2b6d0-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="2b6d0-151">-Findbysubjectkeyidentifier가</span><span class="sxs-lookup"><span data-stu-id="2b6d0-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="2b6d0-152">`findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="2b6d0-153">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b6d0-154">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2b6d0-154">Child Elements</span></span>  
 <span data-ttu-id="2b6d0-155">없음</span><span class="sxs-lookup"><span data-stu-id="2b6d0-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b6d0-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2b6d0-156">Parent Elements</span></span>  
  
|<span data-ttu-id="2b6d0-157">요소</span><span class="sxs-lookup"><span data-stu-id="2b6d0-157">Element</span></span>|<span data-ttu-id="2b6d0-158">설명</span><span class="sxs-lookup"><span data-stu-id="2b6d0-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b6d0-159">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="2b6d0-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="2b6d0-160">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b6d0-161">설명</span><span class="sxs-lookup"><span data-stu-id="2b6d0-161">Remarks</span></span>  
 <span data-ttu-id="2b6d0-162">이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 X509Certificate2 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="2b6d0-163">피어 투 피어 프로그래밍에 대 한 자세한 내용은 참조 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b6d0-164">예</span><span class="sxs-lookup"><span data-stu-id="2b6d0-164">Example</span></span>  
 <span data-ttu-id="2b6d0-165">다음 코드에서는 피어 투 피어 시나리오에서 사용된 인증서를 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6d0-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b6d0-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b6d0-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [<span data-ttu-id="2b6d0-167">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="2b6d0-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="2b6d0-168">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="2b6d0-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="2b6d0-169">피어 채널 메시지 인증</span><span class="sxs-lookup"><span data-stu-id="2b6d0-169">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="2b6d0-170">피어 채널 사용자 지정 인증</span><span class="sxs-lookup"><span data-stu-id="2b6d0-170">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="2b6d0-171">피어 채널 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="2b6d0-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
