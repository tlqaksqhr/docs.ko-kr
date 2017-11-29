---
title: "&lt;scopedCertificates&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8ebcc5f640a585022c924994409dacbb06a08e47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltscopedcertificatesgt-element"></a><span data-ttu-id="3c4eb-102">&lt;scopedCertificates&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-102">&lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="3c4eb-103">인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="3c4eb-104">이 컬렉션은 일반적으로 연합 시나리오에서 보안 토큰 서비스에 대한 서비스 인증서를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="3c4eb-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c4eb-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-106">\<behaviors></span></span>  
<span data-ttu-id="3c4eb-107">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="3c4eb-107">endpointBehaviors section</span></span>  
<span data-ttu-id="3c4eb-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-108">\<behavior></span></span>  
<span data-ttu-id="3c4eb-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-109">\<clientCredentials></span></span>  
<span data-ttu-id="3c4eb-110">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-110">\<serviceCertificate></span></span>  
<span data-ttu-id="3c4eb-111">\<scopedCertificates > 요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="3c4eb-112">\<추가 > 요소에 대 한 \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4eb-113">구문</span><span class="sxs-lookup"><span data-stu-id="3c4eb-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c4eb-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3c4eb-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c4eb-116">특성</span><span class="sxs-lookup"><span data-stu-id="3c4eb-116">Attributes</span></span>  
 <span data-ttu-id="3c4eb-117">없음</span><span class="sxs-lookup"><span data-stu-id="3c4eb-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c4eb-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-118">Child Elements</span></span>  
  
|<span data-ttu-id="3c4eb-119">요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-119">Element</span></span>|<span data-ttu-id="3c4eb-120">설명</span><span class="sxs-lookup"><span data-stu-id="3c4eb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c4eb-121">\<add></span><span class="sxs-lookup"><span data-stu-id="3c4eb-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="3c4eb-122">범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c4eb-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3c4eb-124">요소</span><span class="sxs-lookup"><span data-stu-id="3c4eb-124">Element</span></span>|<span data-ttu-id="3c4eb-125">설명</span><span class="sxs-lookup"><span data-stu-id="3c4eb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c4eb-126">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3c4eb-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="3c4eb-127">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c4eb-128">설명</span><span class="sxs-lookup"><span data-stu-id="3c4eb-128">Remarks</span></span>  
 <span data-ttu-id="3c4eb-129">이 컬렉션을 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="3c4eb-130">이는 클라이언트가 중간 보안 토큰 서비스뿐 아니라 끝 서비스 등의 여러 서비스와 통신할 수 있는 발급된 토큰 시나리오에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="3c4eb-131">인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="3c4eb-132">바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="3c4eb-133">자세한 내용은의 "범위가 지정 된 인증서" 섹션을 참조 하십시오. [하는 방법: 페더레이션 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c4eb-134">예제</span><span class="sxs-lookup"><span data-stu-id="3c4eb-134">Example</span></span>  
 <span data-ttu-id="3c4eb-135">다음 예제에서는 해당 도메인 이름이 www.contoso.com인 끝점과 HTTP 프로토콜을 통해 통신할 때 클라이언트가 사용할 서비스 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4eb-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is http://www.contoso.com over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c4eb-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c4eb-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="3c4eb-137">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="3c4eb-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="3c4eb-138">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="3c4eb-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="3c4eb-139">\<add></span><span class="sxs-lookup"><span data-stu-id="3c4eb-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [<span data-ttu-id="3c4eb-140">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3c4eb-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="3c4eb-141">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3c4eb-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
