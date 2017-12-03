---
title: "&lt;netTcpBinding&gt;의 &lt;message&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f589dea8cace4a049c701cd00fd9a62d40fcf219
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagegt-element-of-ltnettcpbindinggt"></a><span data-ttu-id="308fb-102">&lt;netTcpBinding&gt;의 &lt;message&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="308fb-102">&lt;message&gt; element of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="308fb-103">구성 된 끝점에 대 한 메시지 수준 보안 요구 사항 형식을 정의 하는 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="308fb-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="308fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="308fb-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="308fb-105">\<bindings></span></span>  
<span data-ttu-id="308fb-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="308fb-106">\<netTcpBinding></span></span>  
<span data-ttu-id="308fb-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="308fb-107">\<binding></span></span>  
<span data-ttu-id="308fb-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="308fb-108">\<security></span></span>  
<span data-ttu-id="308fb-109">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="308fb-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="308fb-110">구문</span><span class="sxs-lookup"><span data-stu-id="308fb-110">Syntax</span></span>  
  
```xml  
<message   
      algorithmSuite=System.Servicemodel.Security.SecurityAlgorithmsuite  
    clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="308fb-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="308fb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="308fb-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="308fb-113">특성</span><span class="sxs-lookup"><span data-stu-id="308fb-113">Attributes</span></span>  
  
|<span data-ttu-id="308fb-114">특성</span><span class="sxs-lookup"><span data-stu-id="308fb-114">Attribute</span></span>|<span data-ttu-id="308fb-115">설명</span><span class="sxs-lookup"><span data-stu-id="308fb-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="308fb-116">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-116">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="308fb-117">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-117">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="308fb-118">이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-118">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="308fb-119">다음 표에서는 가능한 값이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-119">Possible values are shown in the following table.</span></span> <span data-ttu-id="308fb-120">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="308fb-121">서비스 바인딩에서 기본값과 같지 않은 `algorithmSuite` 값을 지정하는 경우 Svcutil.exe을 사용하여 구성 파일을 생성하면 파일이 제대로 생성되지 않으므로 구성 파일을 수동으로 편집하여 이 특성을 원하는 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-121">If the service binding specifies an `algorithmSuite` value that is not equal to the default, and you generate the configuration file using Svcutil.exe, then it is not generated correctly, and you must manually edit the configuration file to set this attribute to the desired value.</span></span>|  
|`clientCredentialType`|<span data-ttu-id="308fb-122">메시지 기반 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-122">Specifies the type of credential to be used when performing client authentication using Message-based security.</span></span> <span data-ttu-id="308fb-123">다음 표에서는 가능한 값이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-123">Possible values are shown in the following table.</span></span> <span data-ttu-id="308fb-124">기본값은 `UserName`입니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-124">The default value is `UserName`.</span></span> <span data-ttu-id="308fb-125">이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-125">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="308fb-126">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="308fb-126">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="308fb-127">값</span><span class="sxs-lookup"><span data-stu-id="308fb-127">Value</span></span>|<span data-ttu-id="308fb-128">설명</span><span class="sxs-lookup"><span data-stu-id="308fb-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="308fb-129">Basic128</span><span class="sxs-lookup"><span data-stu-id="308fb-129">Basic128</span></span>|<span data-ttu-id="308fb-130">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-130">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-131">Basic192</span><span class="sxs-lookup"><span data-stu-id="308fb-131">Basic192</span></span>|<span data-ttu-id="308fb-132">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-132">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-133">Basic256</span><span class="sxs-lookup"><span data-stu-id="308fb-133">Basic256</span></span>|<span data-ttu-id="308fb-134">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-134">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-135">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-135">Basic256Rsa15</span></span>|<span data-ttu-id="308fb-136">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-136">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-137">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-137">Basic192Rsa15</span></span>|<span data-ttu-id="308fb-138">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-138">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-139">TripleDes</span><span class="sxs-lookup"><span data-stu-id="308fb-139">TripleDes</span></span>|<span data-ttu-id="308fb-140">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-140">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-141">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-141">Basic128Rsa15</span></span>|<span data-ttu-id="308fb-142">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-142">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-143">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-143">TripleDesRsa15</span></span>|<span data-ttu-id="308fb-144">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-144">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-145">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="308fb-145">Basic128Sha256</span></span>|<span data-ttu-id="308fb-146">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-146">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-147">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="308fb-147">Basic192Sha256</span></span>|<span data-ttu-id="308fb-148">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-148">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-149">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="308fb-149">Basic256Sha256</span></span>|<span data-ttu-id="308fb-150">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-150">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-151">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="308fb-151">TripleDesSha256</span></span>|<span data-ttu-id="308fb-152">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-152">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="308fb-153">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-153">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="308fb-154">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-154">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-155">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-155">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="308fb-156">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-157">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-157">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="308fb-158">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="308fb-159">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="308fb-159">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="308fb-160">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="308fb-161">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="308fb-161">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="308fb-162">값</span><span class="sxs-lookup"><span data-stu-id="308fb-162">Value</span></span>|<span data-ttu-id="308fb-163">설명</span><span class="sxs-lookup"><span data-stu-id="308fb-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="308fb-164">없음</span><span class="sxs-lookup"><span data-stu-id="308fb-164">None</span></span>|<span data-ttu-id="308fb-165">이를 통해 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-165">This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="308fb-166">서비스 쪽에서는 서비스가 클라이언트 자격 증명을 요구하지 않음을 의미하고</span><span class="sxs-lookup"><span data-stu-id="308fb-166">On the service, this indicates that the service does not require any client credential.</span></span> <span data-ttu-id="308fb-167">클라이언트 쪽에서는 클라이언트가 클라이언트 자격 증명을 제공하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-167">On the client, this indicates that the client does not provide any client credential.</span></span>|  
|<span data-ttu-id="308fb-168">Windows</span><span class="sxs-lookup"><span data-stu-id="308fb-168">Windows</span></span>|<span data-ttu-id="308fb-169">Windows 자격 증명의 인증된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-169">Allows the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span>|  
|<span data-ttu-id="308fb-170">UserName</span><span class="sxs-lookup"><span data-stu-id="308fb-170">UserName</span></span>|<span data-ttu-id="308fb-171">서비스에서 UserName 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-171">Allows the service to require that the client be authenticated using a UserName credential.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="308fb-172">는 암호 다이제스트를 보내거나 암호를 사용하여 키를 파생하고 메시지 보안에 이러한 키를 사용하는 것을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-172"> does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="308fb-173">따라서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 UserName 자격 증명을 사용할 때 전송에 보안을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-173">As such, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport is secured when using UserName credentials.</span></span> <span data-ttu-id="308fb-174">이 자격 증명 모드에서는 상호 운용이 가능한 교환 또는 `negotiateServiceCredential` 특성을 기반으로 하는 상호 운용이 불가능한 협상이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-174">This credential mode results in either an interoperable exchange or a non-interoperable negotiation based on the `negotiateServiceCredential` attribute.</span></span>|  
|<span data-ttu-id="308fb-175">인증서</span><span class="sxs-lookup"><span data-stu-id="308fb-175">Certificate</span></span>|<span data-ttu-id="308fb-176">서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-176">Allows the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="308fb-177">메시지 보안 모드가 사용되고 `negotiateServiceCredential` 특성이 `false`로 설정되면 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-177">If message security mode is used and the `negotiateServiceCredential` attribute is set to `false`, the client must be provisioned with the service certificate.</span></span>|  
|<span data-ttu-id="308fb-178">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="308fb-178">IssuedToken</span></span>|<span data-ttu-id="308fb-179">일반적으로 STS(보안 토큰 서비스)에서 발급하는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-179">Specifies a custom token, usually issued by a Security Token Service (STS).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="308fb-180">자식 요소</span><span class="sxs-lookup"><span data-stu-id="308fb-180">Child Elements</span></span>  
 <span data-ttu-id="308fb-181">없음</span><span class="sxs-lookup"><span data-stu-id="308fb-181">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="308fb-182">부모 요소</span><span class="sxs-lookup"><span data-stu-id="308fb-182">Parent Elements</span></span>  
  
|<span data-ttu-id="308fb-183">요소</span><span class="sxs-lookup"><span data-stu-id="308fb-183">Element</span></span>|<span data-ttu-id="308fb-184">설명</span><span class="sxs-lookup"><span data-stu-id="308fb-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="308fb-185">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="308fb-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="308fb-186"><xref:System.ServiceModel.Configuration.NetTcpBindingElement>의 보안 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-186">Defines the security capabilities for the <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="308fb-187">설명</span><span class="sxs-lookup"><span data-stu-id="308fb-187">Remarks</span></span>  
 <span data-ttu-id="308fb-188">Message는 SOAP 메시지 무결성 및 기밀성과 통신 피어의 상호 인증을 위해 메시지 수준 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-188">Message uses message-level security for the integrity and confidentiality of the SOAP message, and for mutual authentication of the communication peers.</span></span> <span data-ttu-id="308fb-189">바인딩에서 이 보안 모드를 선택하면 채널 스택이 메시지 보안 바인딩 요소로 구성되고 SOAP 메시지가 WS-Security* 표준에 따라 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="308fb-189">If this security mode is selected on a binding, the channel stack is configured with message security binding elements and the SOAP messages are secured in compliance with WS-Security* standards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308fb-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="308fb-190">See Also</span></span>  
 <xref:System.ServiceModel.MessageSecurityOverTcp>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="308fb-191">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="308fb-191">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="308fb-192">바인딩</span><span class="sxs-lookup"><span data-stu-id="308fb-192">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="308fb-193">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="308fb-193">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="308fb-194">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="308fb-194">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="308fb-195">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="308fb-195">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
