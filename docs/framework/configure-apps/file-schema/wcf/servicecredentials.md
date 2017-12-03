---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8e2fa4fe72b7b4c2f421aefa566f89492c06457
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="d7889-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="d7889-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="d7889-103">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="d7889-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d7889-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d7889-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7889-105">\<behaviors></span></span>  
<span data-ttu-id="d7889-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d7889-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d7889-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7889-107">\<behavior></span></span>  
<span data-ttu-id="d7889-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d7889-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7889-109">구문</span><span class="sxs-lookup"><span data-stu-id="d7889-109">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">  
   <clientCertificate>  
   </clientCertificate>  
   <issuedTokenAuthentication>  
   </issuedTokenAuthentication>  
   <peer>  
   </peer>  
   <secureConversationAuthentication>  
   </secureConversationAuthentication>  
   <serviceCertificate>  
   </serviceCertificate>  
   <userNameAuthentication>  
   </userNameAuthentication>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</serviceCredentials>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7889-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7889-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d7889-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7889-112">특성</span><span class="sxs-lookup"><span data-stu-id="d7889-112">Attributes</span></span>  
  
|<span data-ttu-id="d7889-113">특성</span><span class="sxs-lookup"><span data-stu-id="d7889-113">Attribute</span></span>|<span data-ttu-id="d7889-114">설명</span><span class="sxs-lookup"><span data-stu-id="d7889-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d7889-115">이 구성 요소의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7889-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7889-116">Child Elements</span></span>  
  
|<span data-ttu-id="d7889-117">요소</span><span class="sxs-lookup"><span data-stu-id="d7889-117">Element</span></span>|<span data-ttu-id="d7889-118">설명</span><span class="sxs-lookup"><span data-stu-id="d7889-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7889-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="d7889-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="d7889-120">클라이언트 인증서가 out-of-band 방식으로 제공될 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="d7889-121">이 요소는 클라이언트 인증서 유효성 검사 설정도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="d7889-122">이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="d7889-123">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="d7889-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="d7889-124">이 서비스에 대해 현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="d7889-125">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="d7889-126">\<피어 ></span><span class="sxs-lookup"><span data-stu-id="d7889-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="d7889-127">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="d7889-128">이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="d7889-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d7889-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="d7889-130">보안 대화에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="d7889-131">이 요소는 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="d7889-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d7889-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="d7889-133">자체 식별을 위해 서비스에서 사용되는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="d7889-134">이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="d7889-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d7889-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="d7889-136">사용자 이름 암호 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="d7889-137">이 요소는 <xref:System.ServiceModel.Configuration.UserNameServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="d7889-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d7889-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="d7889-139">Windows 자격 증명 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="d7889-140">이 요소는 <xref:System.ServiceModel.Configuration.WindowsServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7889-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7889-141">Parent Elements</span></span>  
  
|<span data-ttu-id="d7889-142">요소</span><span class="sxs-lookup"><span data-stu-id="d7889-142">Element</span></span>|<span data-ttu-id="d7889-143">설명</span><span class="sxs-lookup"><span data-stu-id="d7889-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7889-144">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d7889-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d7889-145">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7889-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7889-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7889-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="d7889-147">보안 동작</span><span class="sxs-lookup"><span data-stu-id="d7889-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
