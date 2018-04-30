---
title: '&lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16c5c065e805cb672f85dd9ff28f5b5d82d1ffba
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="ltservicecertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="0c2b1-102">&lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="0c2b1-102">&lt;serviceCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="0c2b1-103">메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
 <span data-ttu-id="0c2b1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c2b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c2b1-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0c2b1-105">\<behaviors></span></span>  
<span data-ttu-id="0c2b1-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c2b1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0c2b1-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0c2b1-107">\<behavior></span></span>  
<span data-ttu-id="0c2b1-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0c2b1-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0c2b1-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0c2b1-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c2b1-110">구문</span><span class="sxs-lookup"><span data-stu-id="0c2b1-110">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c2b1-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c2b1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0c2b1-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c2b1-113">특성</span><span class="sxs-lookup"><span data-stu-id="0c2b1-113">Attributes</span></span>  
  
|<span data-ttu-id="0c2b1-114">특성</span><span class="sxs-lookup"><span data-stu-id="0c2b1-114">Attribute</span></span>|<span data-ttu-id="0c2b1-115">설명</span><span class="sxs-lookup"><span data-stu-id="0c2b1-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="0c2b1-116">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0c2b1-117">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-117">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="0c2b1-118">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="0c2b1-119">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-119">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="0c2b1-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c2b1-121">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="0c2b1-122">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="0c2b1-123">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-123">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="0c2b1-124">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-124">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="0c2b1-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c2b1-126">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-126">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="0c2b1-127">-AuthRoot: 인증서 저장소 공급 업체 Ca (인증 기관)입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-127">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="0c2b1-128">-CertificatAuthority: 중개 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-128">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="0c2b1-129">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-129">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="0c2b1-130">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-130">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="0c2b1-131">-Root: 신뢰할 수 있는 루트 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-131">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="0c2b1-132">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-132">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="0c2b1-133">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-133">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="0c2b1-134">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-134">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="0c2b1-135">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-135">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="0c2b1-136">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-136">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c2b1-137">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="0c2b1-137">-   FindByThumbprint</span></span><br /><span data-ttu-id="0c2b1-138">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="0c2b1-138">-   FindBySubjectName</span></span><br /><span data-ttu-id="0c2b1-139">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0c2b1-139">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="0c2b1-140">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="0c2b1-140">-   FindByIssuerName</span></span><br /><span data-ttu-id="0c2b1-141">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="0c2b1-141">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="0c2b1-142">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="0c2b1-142">-   FindBySerialNumber</span></span><br /><span data-ttu-id="0c2b1-143">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="0c2b1-143">-   FindByTimeValid</span></span><br /><span data-ttu-id="0c2b1-144">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="0c2b1-144">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="0c2b1-145">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="0c2b1-145">-   FindByTemplateName</span></span><br /><span data-ttu-id="0c2b1-146">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="0c2b1-146">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="0c2b1-147">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="0c2b1-147">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="0c2b1-148">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="0c2b1-148">-   FindByExtension</span></span><br /><span data-ttu-id="0c2b1-149">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-149">-   FindByKeyUsage</span></span><br /><span data-ttu-id="0c2b1-150">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="0c2b1-150">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="0c2b1-151">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-151">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="0c2b1-152">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-152">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c2b1-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c2b1-153">Child Elements</span></span>  
 <span data-ttu-id="0c2b1-154">없음</span><span class="sxs-lookup"><span data-stu-id="0c2b1-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c2b1-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c2b1-155">Parent Elements</span></span>  
  
|<span data-ttu-id="0c2b1-156">요소</span><span class="sxs-lookup"><span data-stu-id="0c2b1-156">Element</span></span>|<span data-ttu-id="0c2b1-157">설명</span><span class="sxs-lookup"><span data-stu-id="0c2b1-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c2b1-158">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0c2b1-158">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="0c2b1-159">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-159">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c2b1-160">설명</span><span class="sxs-lookup"><span data-stu-id="0c2b1-160">Remarks</span></span>  
 <span data-ttu-id="0c2b1-161">이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-161">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="0c2b1-162">주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-162">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="0c2b1-163">이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `x509FindType`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-163">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 <span data-ttu-id="0c2b1-164">요소를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b1-164">For more information about using the element, see [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2b1-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c2b1-165">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>  
 [<span data-ttu-id="0c2b1-166">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="0c2b1-166">How to: Specify Client Credential Values</span></span>](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [<span data-ttu-id="0c2b1-167">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0c2b1-167">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
