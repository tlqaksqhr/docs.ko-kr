---
title: "&lt;webHttpBinding&gt;의 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 44397edf2d2c5e2f99a255789452b08d91484b81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="25efd-102">&lt;webHttpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="25efd-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="25efd-103">HTTP 요청을 수신하도록 구성된 서비스 끝점의 전송 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="25efd-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="25efd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="25efd-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="25efd-105">\<bindings></span></span>  
<span data-ttu-id="25efd-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="25efd-106">\<webHttpBinding></span></span>  
<span data-ttu-id="25efd-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="25efd-107">\<binding></span></span>  
<span data-ttu-id="25efd-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="25efd-108">\<security></span></span>  
<span data-ttu-id="25efd-109">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="25efd-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25efd-110">구문</span><span class="sxs-lookup"><span data-stu-id="25efd-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</WebHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="25efd-111">형식</span><span class="sxs-lookup"><span data-stu-id="25efd-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25efd-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="25efd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="25efd-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25efd-114">특성</span><span class="sxs-lookup"><span data-stu-id="25efd-114">Attributes</span></span>  
  
|<span data-ttu-id="25efd-115">특성</span><span class="sxs-lookup"><span data-stu-id="25efd-115">Attribute</span></span>|<span data-ttu-id="25efd-116">설명</span><span class="sxs-lookup"><span data-stu-id="25efd-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="25efd-117">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="25efd-118">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="25efd-119">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="25efd-120">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="25efd-121">다이제스트 또는 기본 인증을 위한 인증 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="25efd-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="25efd-123">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="25efd-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="25efd-124">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="25efd-125">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="25efd-126">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="25efd-127">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="25efd-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="25efd-128">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="25efd-129">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="25efd-130">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="25efd-131">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="25efd-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="25efd-132">값</span><span class="sxs-lookup"><span data-stu-id="25efd-132">Value</span></span>|<span data-ttu-id="25efd-133">설명</span><span class="sxs-lookup"><span data-stu-id="25efd-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="25efd-134">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="25efd-135">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="25efd-136">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="25efd-137">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="25efd-138">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="25efd-139">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="25efd-140">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="25efd-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="25efd-141">값</span><span class="sxs-lookup"><span data-stu-id="25efd-141">Value</span></span>|<span data-ttu-id="25efd-142">설명</span><span class="sxs-lookup"><span data-stu-id="25efd-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="25efd-143">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="25efd-144">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="25efd-145">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="25efd-146">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="25efd-147">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25efd-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="25efd-148">Child Elements</span></span>  
 <span data-ttu-id="25efd-149">없음</span><span class="sxs-lookup"><span data-stu-id="25efd-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25efd-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="25efd-150">Parent Elements</span></span>  
  
|<span data-ttu-id="25efd-151">요소</span><span class="sxs-lookup"><span data-stu-id="25efd-151">Element</span></span>|<span data-ttu-id="25efd-152">설명</span><span class="sxs-lookup"><span data-stu-id="25efd-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25efd-153">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="25efd-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="25efd-154">보안 기능을 나타내는 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="25efd-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25efd-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25efd-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="25efd-156">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="25efd-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="25efd-157">바인딩</span><span class="sxs-lookup"><span data-stu-id="25efd-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="25efd-158">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="25efd-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="25efd-159">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="25efd-159">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="25efd-160">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="25efd-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="25efd-161">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="25efd-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
