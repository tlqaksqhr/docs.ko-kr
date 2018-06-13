---
title: '&lt;ws2007HttpBinding&gt;의 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 3be9d4e64e63b32156cb64257f5bed8230cee3aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350948"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="1e70a-102">&lt;ws2007HttpBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="1e70a-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="1e70a-103">HTTP 전송의 인증 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="1e70a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1e70a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1e70a-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="1e70a-105">\<bindings></span></span>  
<span data-ttu-id="1e70a-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="1e70a-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="1e70a-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="1e70a-107">\<binding></span></span>  
<span data-ttu-id="1e70a-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1e70a-108">\<security></span></span>  
<span data-ttu-id="1e70a-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="1e70a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e70a-110">구문</span><span class="sxs-lookup"><span data-stu-id="1e70a-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="1e70a-111">형식</span><span class="sxs-lookup"><span data-stu-id="1e70a-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e70a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e70a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1e70a-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e70a-114">특성</span><span class="sxs-lookup"><span data-stu-id="1e70a-114">Attributes</span></span>  
  
|<span data-ttu-id="1e70a-115">특성</span><span class="sxs-lookup"><span data-stu-id="1e70a-115">Attribute</span></span>|<span data-ttu-id="1e70a-116">설명</span><span class="sxs-lookup"><span data-stu-id="1e70a-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="1e70a-117">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="1e70a-118">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="1e70a-119">클라이언트를 도메인 프록시에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="1e70a-120">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="1e70a-121">다이제스트 또는 기본 인증을 위한 인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="1e70a-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1e70a-123">인증 영역은 최소한, 인증을 수행하는 호스트의 이름을 지정하며,</span><span class="sxs-lookup"><span data-stu-id="1e70a-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="1e70a-124">액세스 권한을 가진 사용자 컬렉션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="1e70a-125">사용자는 여러 개의 사용자 이름 및 암호 중에서 사용할 수 있는 하나를 알아내기 위해 인증 영역을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="1e70a-126">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="1e70a-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1e70a-127">값</span><span class="sxs-lookup"><span data-stu-id="1e70a-127">Value</span></span>|<span data-ttu-id="1e70a-128">설명</span><span class="sxs-lookup"><span data-stu-id="1e70a-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e70a-129">없음</span><span class="sxs-lookup"><span data-stu-id="1e70a-129">None</span></span>|<span data-ttu-id="1e70a-130">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-130">Security is disabled.</span></span>|  
|<span data-ttu-id="1e70a-131">Basic</span><span class="sxs-lookup"><span data-stu-id="1e70a-131">Basic</span></span>|<span data-ttu-id="1e70a-132">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1e70a-133">Digest</span><span class="sxs-lookup"><span data-stu-id="1e70a-133">Digest</span></span>|<span data-ttu-id="1e70a-134">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1e70a-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1e70a-135">Ntlm</span></span>|<span data-ttu-id="1e70a-136">Windows 도메인에 대한 대체(fallback)로 NTLM 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1e70a-137">Windows</span><span class="sxs-lookup"><span data-stu-id="1e70a-137">Windows</span></span>|<span data-ttu-id="1e70a-138">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1e70a-139">인증서</span><span class="sxs-lookup"><span data-stu-id="1e70a-139">Certificate</span></span>|<span data-ttu-id="1e70a-140">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="1e70a-141">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="1e70a-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1e70a-142">값</span><span class="sxs-lookup"><span data-stu-id="1e70a-142">Value</span></span>|<span data-ttu-id="1e70a-143">설명</span><span class="sxs-lookup"><span data-stu-id="1e70a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e70a-144">없음</span><span class="sxs-lookup"><span data-stu-id="1e70a-144">None</span></span>|<span data-ttu-id="1e70a-145">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-145">Security is disabled.</span></span>|  
|<span data-ttu-id="1e70a-146">Basic</span><span class="sxs-lookup"><span data-stu-id="1e70a-146">Basic</span></span>|<span data-ttu-id="1e70a-147">기본 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1e70a-148">Digest</span><span class="sxs-lookup"><span data-stu-id="1e70a-148">Digest</span></span>|<span data-ttu-id="1e70a-149">다이제스트 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1e70a-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1e70a-150">Ntlm</span></span>|<span data-ttu-id="1e70a-151">Windows 도메인에 대한 대체(fallback)로 NTLM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1e70a-152">Windows</span><span class="sxs-lookup"><span data-stu-id="1e70a-152">Windows</span></span>|<span data-ttu-id="1e70a-153">Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1e70a-154">인증서</span><span class="sxs-lookup"><span data-stu-id="1e70a-154">Certificate</span></span>|<span data-ttu-id="1e70a-155">X.509 인증서를 사용하여 클라이언트를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e70a-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e70a-156">Child Elements</span></span>  
 <span data-ttu-id="1e70a-157">없음</span><span class="sxs-lookup"><span data-stu-id="1e70a-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e70a-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e70a-158">Parent Elements</span></span>  
  
|<span data-ttu-id="1e70a-159">요소</span><span class="sxs-lookup"><span data-stu-id="1e70a-159">Element</span></span>|<span data-ttu-id="1e70a-160">설명</span><span class="sxs-lookup"><span data-stu-id="1e70a-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e70a-161">\<security></span><span class="sxs-lookup"><span data-stu-id="1e70a-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="1e70a-162">보안 기능을 나타내는 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e70a-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e70a-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e70a-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="1e70a-164">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="1e70a-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1e70a-165">바인딩</span><span class="sxs-lookup"><span data-stu-id="1e70a-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1e70a-166">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="1e70a-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1e70a-167">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1e70a-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1e70a-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e70a-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
