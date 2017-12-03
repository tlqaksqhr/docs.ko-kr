---
title: "&lt;baseAddressPrefixFilter&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd0a0d7fc5a83c78a56df796714e70e2e2a61767
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="42351-102">&lt;baseAddressPrefixFilter&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="42351-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="42351-103">IIS(인터넷 정보 서비스)에서 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램을 호스트할 때 적합한 IIS 바인딩을 선택하기 위한 메커니즘을 제공할 통과 필터를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42351-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application in IIS.</span></span>  
  
 <span data-ttu-id="42351-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="42351-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="42351-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="42351-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="42351-106">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="42351-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="42351-107">\<add></span><span class="sxs-lookup"><span data-stu-id="42351-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42351-108">구문</span><span class="sxs-lookup"><span data-stu-id="42351-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42351-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42351-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42351-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42351-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42351-111">특성</span><span class="sxs-lookup"><span data-stu-id="42351-111">Attributes</span></span>  
  
|<span data-ttu-id="42351-112">특성</span><span class="sxs-lookup"><span data-stu-id="42351-112">Attribute</span></span>|<span data-ttu-id="42351-113">설명</span><span class="sxs-lookup"><span data-stu-id="42351-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42351-114">prefix</span><span class="sxs-lookup"><span data-stu-id="42351-114">prefix</span></span>|<span data-ttu-id="42351-115">기본 주소의 일부와 일치하는지 비교하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="42351-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42351-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42351-116">Child Elements</span></span>  
 <span data-ttu-id="42351-117">없음</span><span class="sxs-lookup"><span data-stu-id="42351-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42351-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42351-118">Parent Elements</span></span>  
  
|<span data-ttu-id="42351-119">요소</span><span class="sxs-lookup"><span data-stu-id="42351-119">Element</span></span>|<span data-ttu-id="42351-120">설명</span><span class="sxs-lookup"><span data-stu-id="42351-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42351-121">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="42351-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="42351-122">IIS에서 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램을 호스트할 때 적합한 IIS 바인딩을 선택하기 위한 메커니즘을 제공할 통과 필터를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="42351-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42351-123">설명</span><span class="sxs-lookup"><span data-stu-id="42351-123">Remarks</span></span>  
 <span data-ttu-id="42351-124">접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42351-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="42351-125">이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 응용 프로그램을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="42351-126">IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 응용 프로그램의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="42351-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="42351-127">사이트의 응용 프로그램은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="42351-128">IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42351-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="42351-129">바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="42351-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="42351-130">IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42351-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="42351-131">사이트에서 호스트되는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스는 체계별로 단 하나의 기본 주소에 대한 바인딩만 허용하므로 접두사 필터 기능을 사용하면 호스트되는 서비스에 대해 필요한 기본 주소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-131">Because a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="42351-132">IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="42351-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="42351-133">예를 들어, 사이트에서 다음 기본 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="42351-134">다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="42351-135">이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="42351-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="42351-136">기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="42351-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="42351-137">접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="42351-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42351-138">필터는 와일드카드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="42351-139">또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="42351-140">이러한 주소는 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42351-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42351-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42351-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="42351-142">호스팅</span><span class="sxs-lookup"><span data-stu-id="42351-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
