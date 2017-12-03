---
title: "&lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23f56c85f4fbea7eb1ccc41a7b520b2166158fbc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicecertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="5e0f3-102">&lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="5e0f3-102">&lt;serviceCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="5e0f3-103">메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
 <span data-ttu-id="5e0f3-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e0f3-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-105">\<behaviors></span></span>  
<span data-ttu-id="5e0f3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5e0f3-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-107">\<behavior></span></span>  
<span data-ttu-id="5e0f3-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5e0f3-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0f3-110">구문</span><span class="sxs-lookup"><span data-stu-id="5e0f3-110">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e0f3-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5e0f3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5e0f3-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e0f3-113">특성</span><span class="sxs-lookup"><span data-stu-id="5e0f3-113">Attributes</span></span>  
  
|<span data-ttu-id="5e0f3-114">특성</span><span class="sxs-lookup"><span data-stu-id="5e0f3-114">Attribute</span></span>|<span data-ttu-id="5e0f3-115">설명</span><span class="sxs-lookup"><span data-stu-id="5e0f3-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="5e0f3-116">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="5e0f3-117">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-117">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="5e0f3-118">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="5e0f3-119">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-119">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="5e0f3-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e0f3-121">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="5e0f3-122">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="5e0f3-123">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-123">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="5e0f3-124">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-124">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="5e0f3-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e0f3-126">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-126">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="5e0f3-127">-AuthRoot: 인증서 저장소 공급 업체 Ca (인증 기관)입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-127">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="5e0f3-128">-CertificatAuthority: 중개 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-128">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="5e0f3-129">-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-129">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="5e0f3-130">-인증서 저장소 my: 개인 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-130">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="5e0f3-131">-Root: 신뢰할 수 있는 루트 Ca (인증 기관)에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-131">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="5e0f3-132">-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-132">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="5e0f3-133">-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-133">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="5e0f3-134">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-134">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="5e0f3-135">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-135">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="5e0f3-136">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-136">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e0f3-137">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="5e0f3-137">-   FindByThumbprint</span></span><br /><span data-ttu-id="5e0f3-138">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="5e0f3-138">-   FindBySubjectName</span></span><br /><span data-ttu-id="5e0f3-139">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5e0f3-139">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="5e0f3-140">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="5e0f3-140">-   FindByIssuerName</span></span><br /><span data-ttu-id="5e0f3-141">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5e0f3-141">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="5e0f3-142">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="5e0f3-142">-   FindBySerialNumber</span></span><br /><span data-ttu-id="5e0f3-143">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="5e0f3-143">-   FindByTimeValid</span></span><br /><span data-ttu-id="5e0f3-144">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="5e0f3-144">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="5e0f3-145">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="5e0f3-145">-   FindByTemplateName</span></span><br /><span data-ttu-id="5e0f3-146">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="5e0f3-146">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="5e0f3-147">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="5e0f3-147">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="5e0f3-148">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="5e0f3-148">-   FindByExtension</span></span><br /><span data-ttu-id="5e0f3-149">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="5e0f3-149">-   FindByKeyUsage</span></span><br /><span data-ttu-id="5e0f3-150">-Findbysubjectkeyidentifier가</span><span class="sxs-lookup"><span data-stu-id="5e0f3-150">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="5e0f3-151">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-151">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="5e0f3-152">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-152">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e0f3-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5e0f3-153">Child Elements</span></span>  
 <span data-ttu-id="5e0f3-154">없음</span><span class="sxs-lookup"><span data-stu-id="5e0f3-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e0f3-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5e0f3-155">Parent Elements</span></span>  
  
|<span data-ttu-id="5e0f3-156">요소</span><span class="sxs-lookup"><span data-stu-id="5e0f3-156">Element</span></span>|<span data-ttu-id="5e0f3-157">설명</span><span class="sxs-lookup"><span data-stu-id="5e0f3-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e0f3-158">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5e0f3-158">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="5e0f3-159">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-159">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e0f3-160">설명</span><span class="sxs-lookup"><span data-stu-id="5e0f3-160">Remarks</span></span>  
 <span data-ttu-id="5e0f3-161">이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-161">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="5e0f3-162">주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-162">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="5e0f3-163">이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `x509FindType`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-163">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="5e0f3-164">참조 된 요소를 사용 하 여 [하는 방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0f3-164"> using the element, see [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0f3-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e0f3-165">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>  
 [<span data-ttu-id="5e0f3-166">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="5e0f3-166">How to: Specify Client Credential Values</span></span>](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [<span data-ttu-id="5e0f3-167">보안 동작</span><span class="sxs-lookup"><span data-stu-id="5e0f3-167">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
