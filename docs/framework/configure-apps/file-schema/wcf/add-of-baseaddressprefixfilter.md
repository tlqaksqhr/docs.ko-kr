---
title: '&lt;baseAddressPrefixFilter&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: e4408488036be210e3a8b9cf8b8f8f8c2e669a1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365191"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="fe586-102">&lt;baseAddressPrefixFilter&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="fe586-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="fe586-103">IIS에서 Windows Communication Foundation (WCF) 응용 프로그램을 호스트 하는 경우 적절 한 인터넷 정보 서비스 (IIS) 바인딩을 선택 하기 위한 메커니즘을 제공할 통과 필터를 지정 하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="fe586-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fe586-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fe586-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="fe586-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="fe586-106">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="fe586-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="fe586-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fe586-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe586-108">구문</span><span class="sxs-lookup"><span data-stu-id="fe586-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe586-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fe586-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fe586-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe586-111">특성</span><span class="sxs-lookup"><span data-stu-id="fe586-111">Attributes</span></span>  
  
|<span data-ttu-id="fe586-112">특성</span><span class="sxs-lookup"><span data-stu-id="fe586-112">Attribute</span></span>|<span data-ttu-id="fe586-113">설명</span><span class="sxs-lookup"><span data-stu-id="fe586-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe586-114">prefix</span><span class="sxs-lookup"><span data-stu-id="fe586-114">prefix</span></span>|<span data-ttu-id="fe586-115">기본 주소의 일부와 일치하는지 비교하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe586-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fe586-116">Child Elements</span></span>  
 <span data-ttu-id="fe586-117">없음</span><span class="sxs-lookup"><span data-stu-id="fe586-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe586-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fe586-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fe586-119">요소</span><span class="sxs-lookup"><span data-stu-id="fe586-119">Element</span></span>|<span data-ttu-id="fe586-120">설명</span><span class="sxs-lookup"><span data-stu-id="fe586-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe586-121">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="fe586-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="fe586-122">IIS에서 Windows Communication Foundation (WCF) 응용 프로그램을 호스트할 때 적합 한 IIS 바인딩을 선택 하기 위한 메커니즘을 제공할 통과 필터를 지정 하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe586-123">설명</span><span class="sxs-lookup"><span data-stu-id="fe586-123">Remarks</span></span>  
 <span data-ttu-id="fe586-124">접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="fe586-125">이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 응용 프로그램을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="fe586-126">IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 응용 프로그램의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="fe586-127">사이트의 응용 프로그램은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="fe586-128">IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="fe586-129">바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="fe586-130">IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="fe586-131">사이트에서 호스팅되는 WCF 서비스에서는 각 스키마에 대 한 바인딩을 단 하나의 기본 주소를 허용 하므로 접두사 필터 기능 호스팅된 서비스의 필요한 기본 주소를 선택 하도록 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="fe586-132">IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="fe586-133">예를 들어, 사이트에서 다음 기본 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="fe586-134">다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="fe586-135">이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="fe586-136">기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="fe586-137">접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe586-138">필터는 와일드카드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="fe586-139">또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="fe586-140">이러한 주소는 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe586-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe586-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe586-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="fe586-142">호스팅</span><span class="sxs-lookup"><span data-stu-id="fe586-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
