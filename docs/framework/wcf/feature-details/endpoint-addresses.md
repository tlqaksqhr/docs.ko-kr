---
title: "끝점 주소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3231e5b043dd0e65c09f25eed56341e660bf1f87
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-addresses"></a><span data-ttu-id="5d20c-102">끝점 주소</span><span class="sxs-lookup"><span data-stu-id="5d20c-102">Endpoint Addresses</span></span>
<span data-ttu-id="5d20c-103">모든 끝점에는 해당 끝점을 찾아서 식별하는 데 사용되는 연결된 주소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-103">Every endpoint has an address associated with it, which is used to locate and identify the endpoint.</span></span> <span data-ttu-id="5d20c-104">이 주소는 주로 끝점의 위치를 지정하는 URI(Uniform Resource Identifier)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-104">This address consists primarily of a Uniform Resource Identifier (URI), which specifies the location of the endpoint.</span></span> <span data-ttu-id="5d20c-105">끝점 주소는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 프로그래밍 모델에 <xref:System.ServiceModel.EndpointAddress> 클래스로 표시됩니다. 이 클래스에는 한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 선택적 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 속성과 서비스에 연결하는 데 필요한 다른 SOAP 헤더를 정의하는 선택적 <xref:System.ServiceModel.EndpointAddress.Headers%2A> 속성 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-105">The endpoint address is represented in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] programming model by the <xref:System.ServiceModel.EndpointAddress> class, which contains an optional <xref:System.ServiceModel.EndpointAddress.Identity%2A> property that enables the authentication of the endpoint by other endpoints that exchange messages with it, and a set of optional <xref:System.ServiceModel.EndpointAddress.Headers%2A> properties, which define any other SOAP headers required to reach the service.</span></span> <span data-ttu-id="5d20c-106">선택적 헤더는 서비스 끝점을 확인하거나 상호 작용하는 데 필요한 추가적인 자세한 주소 지정 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-106">The optional headers provide additional and more detailed addressing information to identify or interact with the service endpoint.</span></span> <span data-ttu-id="5d20c-107">끝점 주소는 통신 중에 WS-Addressing EPR(끝점 참조)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-107">The address of an endpoint is represented on the wire as a WS-Addressing endpoint reference (EPR).</span></span>  
  
## <a name="uri-structure-of-an-address"></a><span data-ttu-id="5d20c-108">주소의 URI 구조</span><span class="sxs-lookup"><span data-stu-id="5d20c-108">URI Structure of an Address</span></span>  
 <span data-ttu-id="5d20c-109">대부분 전송 주소 URI에는 네 가지 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-109">The address URI for most transports has four parts.</span></span> <span data-ttu-id="5d20c-110">예를 들어 URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint의 네 부분을 다음과 같이 항목화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-110">For example, the four parts of the URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint can be itemized as follows:</span></span>  
  
-   <span data-ttu-id="5d20c-111">스키마: http:</span><span class="sxs-lookup"><span data-stu-id="5d20c-111">Scheme: http:</span></span>  
  
-   <span data-ttu-id="5d20c-112">시스템: www.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5d20c-112">Machine: www.fabrikam.com</span></span>  
  
-   <span data-ttu-id="5d20c-113">(선택적) 포트: 322</span><span class="sxs-lookup"><span data-stu-id="5d20c-113">(optional) Port: 322</span></span>  
  
-   <span data-ttu-id="5d20c-114">경로: /mathservice.svc/secureEndpoint</span><span class="sxs-lookup"><span data-stu-id="5d20c-114">Path: /mathservice.svc/secureEndpoint</span></span>  
  
## <a name="defining-an-address-for-a-service"></a><span data-ttu-id="5d20c-115">서비스에 대한 주소 정의</span><span class="sxs-lookup"><span data-stu-id="5d20c-115">Defining an Address for a Service</span></span>  
 <span data-ttu-id="5d20c-116">서비스의 끝점 주소는 코드를 사용하여 명령적으로 지정하거나 구성을 통해 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-116">The endpoint address for a service can be specified either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="5d20c-117">일반적으로 배포된 서비스의 바인딩과 주소가 서비스를 배포할 때 사용된 바인딩 및 주소와 다르기 때문에 코드로 끝점을 정의하는 것은 효과적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-117">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="5d20c-118">일반적으로 코드 대신 구성을 사용하여 서비스 끝점을 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-118">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="5d20c-119">바인딩 및 주소 지정 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하거나 재배포할 필요 없이 해당 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-119">Keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
### <a name="defining-an-address-in-configuration"></a><span data-ttu-id="5d20c-120">구성에서 주소 정의</span><span class="sxs-lookup"><span data-stu-id="5d20c-120">Defining an Address in Configuration</span></span>  
 <span data-ttu-id="5d20c-121">사용 하 여 구성 파일에서 끝점을 정의 하는 [ \<끝점 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-121">To define an endpoint in a configuration file, use the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="5d20c-122">자세한 내용 및 예제 참조 [끝점 주소 지정](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-122">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="defining-an-address-in-code"></a><span data-ttu-id="5d20c-123">코드에서 주소 정의</span><span class="sxs-lookup"><span data-stu-id="5d20c-123">Defining an Address in Code</span></span>  
 <span data-ttu-id="5d20c-124">끝점 주소는 <xref:System.ServiceModel.EndpointAddress> 클래스를 사용하여 코드에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-124">An endpoint address can be created in code with the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="5d20c-125">자세한 내용 및 예제 참조 [끝점 주소 지정](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-125">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="endpoints-in-wsdl"></a><span data-ttu-id="5d20c-126">WSDL의 끝점</span><span class="sxs-lookup"><span data-stu-id="5d20c-126">Endpoints in WSDL</span></span>  
 <span data-ttu-id="5d20c-127">끝점 주소는 해당 끝점의 `wsdl:port` 요소 내에 있는 WS-Addressing EPR 요소로 WSDL에서 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-127">An endpoint address can also be represented in WSDL as a WS-Addressing EPR element inside the corresponding endpoint's `wsdl:port` element.</span></span> <span data-ttu-id="5d20c-128">EPR에는 끝점 주소와 주소 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-128">The EPR contains the endpoint's address as well as any address properties.</span></span> <span data-ttu-id="5d20c-129">자세한 내용 및 예제 참조 [끝점 주소 지정](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-129">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a><span data-ttu-id="5d20c-130">여러 IIS 바인딩 지원.NET framework 3.5</span><span class="sxs-lookup"><span data-stu-id="5d20c-130">Multiple IIS Binding Support in .NET Framework 3.5</span></span>  
 <span data-ttu-id="5d20c-131">인터넷 서비스 공급자는 사이트 밀도를 높이고 총 소유 비용을 줄이기 위해 종종 같은 서버 및 사이트에서 여러 응용 프로그램을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-131">Internet service providers often host many applications on the same server and site to increase the site density and lower total cost of ownership.</span></span> <span data-ttu-id="5d20c-132">이러한 응용 프로그램은 일반적으로 다른 기본 주소로 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-132">These applications are typically bound to different base addresses.</span></span> <span data-ttu-id="5d20c-133">IIS(인터넷 정보 서비스) 웹 사이트에 여러 개의 응용 프로그램이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-133">An Internet Information Services (IIS) Web site can contain multiple applications.</span></span> <span data-ttu-id="5d20c-134">하나 이상의 IIS 바인딩을 통해 한 사이트의 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-134">The applications in a site can be accessed through one or more IIS bindings.</span></span>  
  
 <span data-ttu-id="5d20c-135">IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-135">IIS bindings provide two pieces of information: a binding protocol, and binding information.</span></span> <span data-ttu-id="5d20c-136">바인딩 프로토콜은 통신이 이루어지는 스키마를 정의하며, 바인딩 정보는 사이트에 액세스하는 데 사용되는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-136">The binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span>  
  
 <span data-ttu-id="5d20c-137">다음 예제에서는 IIS 바인딩에 나타낼 수 있는 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-137">The following example shows the components that can be present in an IIS binding:</span></span>  
  
-   <span data-ttu-id="5d20c-138">바인딩 프로토콜: HTTP</span><span class="sxs-lookup"><span data-stu-id="5d20c-138">Binding protocol: HTTP</span></span>  
  
-   <span data-ttu-id="5d20c-139">바인딩 정보: IP 주소, 포트, 호스트 헤더</span><span class="sxs-lookup"><span data-stu-id="5d20c-139">Binding Information: IP Address, Port, Host header</span></span>  
  
 <span data-ttu-id="5d20c-140">IIS에서는 각 사이트에 대해 여러 개의 바인딩을 지정할 수 있으므로, 각 스키마에 대해 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-140">IIS can specify multiple bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="5d20c-141">[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 이전에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 한 개의 스키마에 대해 여러 개의 주소를 지원하지 않았으며, 여러 개의 주소가 지정된 경우 활성화 중에 <xref:System.ArgumentException>을 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-141">Prior to [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] did not support multiple addresses for a schema and, if they were specified, threw a <xref:System.ArgumentException> during activation.</span></span>  
  
 <span data-ttu-id="5d20c-142">[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]를 사용하면 인터넷 서비스 공급자가 동일한 사이트의 동일한 스키마에 대해 기본 주소가 다른 여러 응용 프로그램을 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-142">The [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] enables Internet service providers to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="5d20c-143">예를 들어 사이트에 다음 기본 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-143">For example, a site could contain the following base addresses:</span></span>  
  
-   <span data-ttu-id="5d20c-144">http://payroll.myorg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="5d20c-144">http://payroll.myorg.com/Service.svc</span></span>  
  
-   <span data-ttu-id="5d20c-145">http://shipping.myorg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="5d20c-145">http://shipping.myorg.com/Service.svc</span></span>  
  
 <span data-ttu-id="5d20c-146">[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]를 사용하여 구성 파일의 AppDomain 수준에서 접두사 필터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-146">With [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], you specify a prefix filter at the AppDomain level in the configuration file.</span></span> <span data-ttu-id="5d20c-147">이 작업을 수행는 [ \<baseAddressPrefixFilters >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) 접두사 목록을 포함 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-147">You do this with the [\<baseAddressPrefixFilters>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) element, which contains a list of prefixes.</span></span> <span data-ttu-id="5d20c-148">IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록을 기반으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-148">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list.</span></span> <span data-ttu-id="5d20c-149">기본적으로 접두사가 지정되지 않으면 모든 주소가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-149">By default, when a prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="5d20c-150">접두사를 지정하면 해당 스키마에서 일치하는 기본 주소만 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-150">Specifying the prefix results in only the matching base address for that scheme to be passed through.</span></span>  
  
 <span data-ttu-id="5d20c-151">다음은 접두사 필터를 사용하는 구성 코드의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-151">The following is an example of configuration code that uses the prefix filters.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="5d20c-152">앞의 예제에서 net.tcp://payroll.myorg.com:8000 및 http://shipping.myorg.com:8000은 해당 스키마에 대해 통과되는 유일한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-152">In the preceding example, net.tcp://payroll.myorg.com:8000 and http://shipping.myorg.com:8000 are the only base addresses, for their respective schemes, which are passed through.</span></span>  
  
 <span data-ttu-id="5d20c-153">`baseAddressPrefixFilter`는 와일드카드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-153">The `baseAddressPrefixFilter` does not support wildcards.</span></span>  
  
 <span data-ttu-id="5d20c-154">IIS에서 제공하는 기본 주소에 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-154">The base addresses supplied by IIS may have addresses bound to other schemes not present in `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="5d20c-155">이러한 주소는 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-155">These addresses are not filtered out.</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a><span data-ttu-id="5d20c-156">.NET Framework 4 이상의 여러 IIS 바인딩 지원</span><span class="sxs-lookup"><span data-stu-id="5d20c-156">Multiple IIS Binding Support in .NET Framework 4 and later</span></span>  
 <span data-ttu-id="5d20c-157">.NET 4부터는 단일 기본 주소를 선택해야 할 필요 없이 <xref:System.ServiceModel.ServiceHostingEnvironment>의 <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> 설정을 true로 설정하여 IIS에서 여러 바인딩을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-157">Starting in .NET 4, you can enable support for multiple bindings in IIS without having to pick a single base address, by setting <xref:System.ServiceModel.ServiceHostingEnvironment>’s <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> setting to true.</span></span> <span data-ttu-id="5d20c-158">이 지원은 HTTP 프로토콜 체계로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-158">This support is limited to HTTP protocol schemes.</span></span>  
  
 <span data-ttu-id="5d20c-159">다음에서 사용 하 여 multipleSiteBindingsEnabled 구성 코드의 한 예로 [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-159">The following is an example of configuration code that uses multipleSiteBindingsEnabled on [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="5d20c-160">이 설정을 사용하여 여러 사이트 바인딩을 사용하도록 설정하는 경우 HTTP 프로토콜과 그 외의 프로토콜에 대한 모든 baseAddressPrefixFilters 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-160">Any baseAddressPrefixFilters settings are ignored, for both HTTP and non-HTTP protocols, when multiple site bindings are enabled using this setting.</span></span>  
  
 <span data-ttu-id="5d20c-161">세부 정보 및 예제 참조 [여러 IIS 사이트 바인딩 지원](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) 및 <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-161">For details and examples, see [Supporting Multiple IIS Site Bindings](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) and <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.</span></span>  
  
## <a name="extending-addressing-in-wcf-services"></a><span data-ttu-id="5d20c-162">WCF 서비스에서 주소 확장</span><span class="sxs-lookup"><span data-stu-id="5d20c-162">Extending Addressing in WCF Services</span></span>  
 <span data-ttu-id="5d20c-163">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 기본 주소 지정 모델은 다음과 같은 용도로 끝점 주소 URI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-163">The default addressing model of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services uses the endpoint address URI for the following purposes:</span></span>  
  
-   <span data-ttu-id="5d20c-164">끝점이 메시지를 수신 대기하는 위치인 서비스 수신 대기 주소 지정</span><span class="sxs-lookup"><span data-stu-id="5d20c-164">To specify the service listening address, the location at which the endpoint listens for messages,</span></span>  
  
-   <span data-ttu-id="5d20c-165">끝점이 SOAP 헤더로 간주하는 주소인 SOAP 주소 필터 지정</span><span class="sxs-lookup"><span data-stu-id="5d20c-165">To specify the SOAP address filter, the address an endpoint expects as a SOAP header.</span></span>  
  
 <span data-ttu-id="5d20c-166">이러한 각 목적에 대해 값을 별도로 지정할 수 있으며, 이렇게 하면 유용한 시나리오를 다루는 여러 가지 주소 지정 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-166">The values for each of these purposes can be specified separately, allowing several extensions of addressing that cover useful scenarios:</span></span>  
  
-   <span data-ttu-id="5d20c-167">SOAP 매개자: 클라이언트가 보낸 메시지는 메시지가 최종 대상에 도달하기 전에 메시지를 처리하는 하나 이상의 추가 서비스를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-167">SOAP intermediaries: a message sent by a client traverses one or more additional services that process the message before it reaches its final destination.</span></span> <span data-ttu-id="5d20c-168">SOAP 매개자는 메시지에 캐싱, 라우팅, 부하 분산 또는 스키마 유효성 검사 등의 여러 가지 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-168">SOAP intermediaries can perform various tasks, such as caching, routing, load-balancing, or schema validation on the messages.</span></span> <span data-ttu-id="5d20c-169">이 시나리오는 최종 대상을 지정하는 논리적 주소(`via`)가 아니라 매개자를 대상으로 하는 메시지를 별도의 실제 주소(`wsa:To`)로 보내어 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-169">This scenario is accomplished by sending messages to a separate physical address (`via`) that targets the intermediary rather than just to a logical address (`wsa:To`) that targets the ultimate destination.</span></span>  
  
-   <span data-ttu-id="5d20c-170">끝점의 수신 대기 주소는 개인 URI이며 해당 `listenURI` 속성과 다른 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-170">The listening address of the endpoint is a private URI and is set to a different value than its `listenURI` property.</span></span>  
  
 <span data-ttu-id="5d20c-171">`via`에서 지정하는 전송 주소는 `to` 매개 변수에서 지정하는 다른 원격 주소(서비스가 있는 주소)로 가기 위해 메시지가 처음 전송되어야 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-171">The transport address that the `via` specifies is the location to which a message should initially be sent on its way to some other remote address specified by the `to` parameter at which the service is located.</span></span> <span data-ttu-id="5d20c-172">대부분의 인터넷 시나리오에서 `via` URI는 서비스의 최종 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 주소의 `to` 속성과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-172">In most Internet scenarios, the `via` URI is the same as the <xref:System.ServiceModel.EndpointAddress.Uri%2A> property of the final `to` address of the service.</span></span> <span data-ttu-id="5d20c-173">수동 라우팅을 수행해야 하는 경우에만 이 두 주소를 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-173">You only distinguish between these two addresses when you must do manual routing.</span></span>  
  
### <a name="addressing-headers"></a><span data-ttu-id="5d20c-174">주소 지정 헤더</span><span class="sxs-lookup"><span data-stu-id="5d20c-174">Addressing Headers</span></span>  
 <span data-ttu-id="5d20c-175">하나 이상의 SOAP 헤더와 해당 기본 URI로 끝점에 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-175">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="5d20c-176">이 유용한 하나의 시나리오 집합이 SOAP 매개 시나리오 집합입니다. 이 시나리오 집합에서는 끝점에 매개자를 대상으로 한 SOAP 헤더를 포함할 해당 끝점의 클라이언트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-176">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span>  
  
 <span data-ttu-id="5d20c-177">코드나 구성을 사용하여 사용자 지정 주소 헤더를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-177">You can define custom address headers in two ways—by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="5d20c-178">코드에서는 <xref:System.ServiceModel.Channels.AddressHeader> 클래스를 사용하여 사용자 지정 주소 헤더를 만든 다음 <xref:System.ServiceModel.EndpointAddress> 생성에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-178">In code, create custom address headers by using the <xref:System.ServiceModel.Channels.AddressHeader> class, and then used in the construction of an <xref:System.ServiceModel.EndpointAddress>.</span></span>  
  
-   <span data-ttu-id="5d20c-179">사용자 지정 구성에서 [ \<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 의 자식으로 지정 되는 [ \<끝점 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-179">In configuration, custom [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) are specified as children of the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
 <span data-ttu-id="5d20c-180">일반적으로 구성을 사용하면 배포 후에 헤더를 변경할 수 있으므로 구성을 사용하는 것이 코드를 사용하는 것보다 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-180">Configuration is generally preferable to code, as it allows you to change the headers after deployment.</span></span>  
  
### <a name="custom-listening-addresses"></a><span data-ttu-id="5d20c-181">사용자 지정 수신 대기 주소</span><span class="sxs-lookup"><span data-stu-id="5d20c-181">Custom Listening Addresses</span></span>  
 <span data-ttu-id="5d20c-182">수신 대기 주소를 끝점의 URI 이외의 다른 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-182">You can set the listening address to a different value than the endpoint’s URI.</span></span> <span data-ttu-id="5d20c-183">이 기능은 노출할 SOAP 주소가 공용 SOAP 매개자의 주소이지만 실제로 수신 대기하는 끝점이 개인 네트워크 주소인 매개 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-183">This is useful in intermediary scenarios where the SOAP address to be exposed is that of a public SOAP intermediary, whereas the address where the endpoint actually listens is a private network address.</span></span>  
  
 <span data-ttu-id="5d20c-184">코드나 구성을 사용하여 사용자 지정 수신 대기 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-184">You can specify a custom listening address by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="5d20c-185">코드에서는 <xref:System.ServiceModel.Description.ClientViaBehavior> 클래스를 끝점의 동작 컬렉션에 추가하여 사용자 지정 수신 대기 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-185">In code, specify a custom listening address by adding a <xref:System.ServiceModel.Description.ClientViaBehavior> class to the endpoint’s behavior collection.</span></span>  
  
-   <span data-ttu-id="5d20c-186">구성에서 지정 된 사용자 지정 수신 대기 주소는 `ListenUri` 서비스의 특성 [ \<끝점 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-186">In configuration, specify a custom listening address with the `ListenUri` attribute of the service [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
### <a name="custom-soap-address-filter"></a><span data-ttu-id="5d20c-187">사용자 지정 SOAP 주소 필터</span><span class="sxs-lookup"><span data-stu-id="5d20c-187">Custom SOAP Address Filter</span></span>  
 <span data-ttu-id="5d20c-188"><xref:System.ServiceModel.EndpointAddress.Uri%2A>는 <xref:System.ServiceModel.EndpointAddress.Headers%2A> 속성과 함께 사용되어 끝점의 SOAP 주소 필터(<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-188">The <xref:System.ServiceModel.EndpointAddress.Uri%2A> is used in conjunction with any <xref:System.ServiceModel.EndpointAddress.Headers%2A> property to define an endpoint’s SOAP address filter (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>).</span></span> <span data-ttu-id="5d20c-189">기본적으로 이 필터는 들어오는 메시지에 끝점의 URI와 일치하는 `To` 메시지 헤더가 있는지, 모든 필수 끝점 헤더가 메시지에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-189">By default, this filter verifies that an incoming message has a `To` message header that matches the endpoint’s URI and that all of the required endpoint headers are present in the message.</span></span>  
  
 <span data-ttu-id="5d20c-190">일부 시나리오에서 끝점은 기본 전송에 도착하는 모든 메시지를 받고 해당 `To` 헤더가 있는 메시지는 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-190">In some scenarios, an endpoint receives all messages that arrive on the underlying transport, and not just those with the appropriate `To` header.</span></span> <span data-ttu-id="5d20c-191">이 기능을 사용하도록 설정하려면 사용자가 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d20c-191">To enable this, the user can use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d20c-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d20c-192">See Also</span></span>  
 [<span data-ttu-id="5d20c-193">끝점 주소 지정</span><span class="sxs-lookup"><span data-stu-id="5d20c-193">Specifying an Endpoint Address</span></span>](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 [<span data-ttu-id="5d20c-194">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="5d20c-194">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
