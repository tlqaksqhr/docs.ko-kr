---
title: "&lt;ws2007HttpBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 78a87add1ed71786dd0e4181c7eeb70e3b63cec1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="fc4b1-102">&lt;ws2007HttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="fc4b1-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="fc4b1-103">사용 하는 보안 설정 나타냅니다는 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="fc4b1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fc4b1-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-105">\<bindings></span></span>  
<span data-ttu-id="fc4b1-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="fc4b1-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-107">\<binding></span></span>  
<span data-ttu-id="fc4b1-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4b1-109">구문</span><span class="sxs-lookup"><span data-stu-id="fc4b1-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc4b1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fc4b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fc4b1-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc4b1-112">특성</span><span class="sxs-lookup"><span data-stu-id="fc4b1-112">Attributes</span></span>  
  
|<span data-ttu-id="fc4b1-113">특성</span><span class="sxs-lookup"><span data-stu-id="fc4b1-113">Attribute</span></span>|<span data-ttu-id="fc4b1-114">설명</span><span class="sxs-lookup"><span data-stu-id="fc4b1-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="fc4b1-115">-선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-115">-   Optional.</span></span> <span data-ttu-id="fc4b1-116">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="fc4b1-117">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="fc4b1-118">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fc4b1-119">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="fc4b1-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="fc4b1-120">값</span><span class="sxs-lookup"><span data-stu-id="fc4b1-120">Value</span></span>|<span data-ttu-id="fc4b1-121">설명</span><span class="sxs-lookup"><span data-stu-id="fc4b1-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="fc4b1-122">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="fc4b1-123">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="fc4b1-124">SSL(Secure Sockets Layer) 인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="fc4b1-125">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="fc4b1-126">클라이언트 인증을 통해 제어 됩니다는 `ClientCredentials` 특성에는 [ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="fc4b1-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="fc4b1-128">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="fc4b1-129">이 모드는 서비스 자격 증명을 out-of-band 클라이언트에서 사용할 수 있는지 여부, 사용할 알고리즘 모음 및 <xref:System.ServiceModel.Security.SecurityMessageProperty>를 통해 메시지 본문에 적용할 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="fc4b1-130">클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="fc4b1-131">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="fc4b1-132">기본적으로 클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc4b1-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fc4b1-133">Child Elements</span></span>  
  
|<span data-ttu-id="fc4b1-134">요소</span><span class="sxs-lookup"><span data-stu-id="fc4b1-134">Element</span></span>|<span data-ttu-id="fc4b1-135">설명</span><span class="sxs-lookup"><span data-stu-id="fc4b1-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc4b1-136">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="fc4b1-137">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-137">Defines the transport security settings.</span></span> <span data-ttu-id="fc4b1-138">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="fc4b1-139">이 설정은 모드를 Transport로 설정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="fc4b1-140">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="fc4b1-141">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-141">Defines the security settings for the message.</span></span> <span data-ttu-id="fc4b1-142">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="fc4b1-143">이 설정은 모드를 Transport로 설정한 경우에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc4b1-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fc4b1-144">Parent Elements</span></span>  
  
|<span data-ttu-id="fc4b1-145">요소</span><span class="sxs-lookup"><span data-stu-id="fc4b1-145">Element</span></span>|<span data-ttu-id="fc4b1-146">설명</span><span class="sxs-lookup"><span data-stu-id="fc4b1-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc4b1-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="fc4b1-148">HTTP 전송 응용 프로그램에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc4b1-149">설명</span><span class="sxs-lookup"><span data-stu-id="fc4b1-149">Remarks</span></span>  
 <span data-ttu-id="fc4b1-150">이 요소는 WS-* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-150">This element is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="fc4b1-151">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4b1-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4b1-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc4b1-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="fc4b1-153">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fc4b1-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fc4b1-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="fc4b1-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fc4b1-155">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="fc4b1-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fc4b1-156">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="fc4b1-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fc4b1-157">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fc4b1-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
