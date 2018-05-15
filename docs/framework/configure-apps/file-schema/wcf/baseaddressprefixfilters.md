---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 8fffcd02b1c08172b184225f13a1852414cf429a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbaseaddressprefixfiltersgt"></a><span data-ttu-id="813ba-102">&lt;baseAddressPrefixFilters&gt;</span><span class="sxs-lookup"><span data-stu-id="813ba-102">&lt;baseAddressPrefixFilters&gt;</span></span>
<span data-ttu-id="813ba-103">IIS에서 Windows Communication Foundation (WCF) 응용 프로그램을 호스트할 때 적합 한 인터넷 정보 서비스 (IIS) 바인딩을 선택 하기 위한 메커니즘을 제공 하는 필터를 지정 하는 요소 전달 구성의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-103">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="813ba-104">\<baseAddressPrefixFilters > 대신 정규화 된 컴퓨터 이름을 사용 하 여, "localhost"를 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-104">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="813ba-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="813ba-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="813ba-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="813ba-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813ba-107">구문</span><span class="sxs-lookup"><span data-stu-id="813ba-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="813ba-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="813ba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="813ba-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="813ba-110">특성</span><span class="sxs-lookup"><span data-stu-id="813ba-110">Attributes</span></span>  
 <span data-ttu-id="813ba-111">없음</span><span class="sxs-lookup"><span data-stu-id="813ba-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="813ba-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="813ba-112">Child Elements</span></span>  
  
|<span data-ttu-id="813ba-113">요소</span><span class="sxs-lookup"><span data-stu-id="813ba-113">Element</span></span>|<span data-ttu-id="813ba-114">설명</span><span class="sxs-lookup"><span data-stu-id="813ba-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="813ba-115">\<add></span><span class="sxs-lookup"><span data-stu-id="813ba-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="813ba-116">서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-116">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="813ba-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="813ba-117">Parent Elements</span></span>  
  
|<span data-ttu-id="813ba-118">요소</span><span class="sxs-lookup"><span data-stu-id="813ba-118">Element</span></span>|<span data-ttu-id="813ba-119">설명</span><span class="sxs-lookup"><span data-stu-id="813ba-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="813ba-120">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="813ba-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="813ba-121">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="813ba-122">설명</span><span class="sxs-lookup"><span data-stu-id="813ba-122">Remarks</span></span>  
 <span data-ttu-id="813ba-123">접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-123">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="813ba-124">이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 응용 프로그램을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-124">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="813ba-125">IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 응용 프로그램의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-125">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="813ba-126">사이트의 응용 프로그램은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-126">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="813ba-127">IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-127">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="813ba-128">바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-128">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="813ba-129">IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-129">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="813ba-130">사이트에서 호스트되는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스는 체계별로 단 하나의 기본 주소에 대한 바인딩만 허용하므로 접두사 필터 기능을 사용하면 호스트되는 서비스에 대해 필요한 기본 주소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-130">Because a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="813ba-131">IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-131">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="813ba-132">예를 들어, 사이트에서 다음 기본 주소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-132">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="813ba-133">다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-133">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="813ba-134">이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-134">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="813ba-135">기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-135">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="813ba-136">접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-136">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="813ba-137">필터는 와일드카드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-137">The filter does not support any wildcards.</span></span> <span data-ttu-id="813ba-138">또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-138">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="813ba-139">이러한 주소는 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="813ba-139">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813ba-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="813ba-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="813ba-141">호스팅</span><span class="sxs-lookup"><span data-stu-id="813ba-141">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
