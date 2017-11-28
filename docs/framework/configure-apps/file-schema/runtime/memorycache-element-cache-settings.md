---
title: "&lt;memoryCache&gt; 요소 (캐시 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ded74486fd9a5687a9f5cdeee6061d4d58234e37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmemorycachegt-element-cache-settings"></a><span data-ttu-id="c94ad-102">&lt;memoryCache&gt; 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="c94ad-102">&lt;memoryCache&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="c94ad-103"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="c94ad-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheElement> 클래스는 캐시를 구성하는 데 사용할 수 있는 [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="c94ad-105"><xref:System.Runtime.Caching.MemoryCache> 클래스의 여러 인스턴스를 단일 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="c94ad-106">구성 파일의 각 `memoryCache` 요소에는 명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스의 설정을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="c94ad-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c94ad-107">\<configuration></span></span>  
<span data-ttu-id="c94ad-108">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="c94ad-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="c94ad-109">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="c94ad-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c94ad-110">구문</span><span class="sxs-lookup"><span data-stu-id="c94ad-110">Syntax</span></span>  
  
```xml  
<memoryCache   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
< memoryCache />  
```  
  
## <a name="type"></a><span data-ttu-id="c94ad-111">형식</span><span class="sxs-lookup"><span data-stu-id="c94ad-111">Type</span></span>  
 <span data-ttu-id="c94ad-112"><xref:System.Runtime.Caching.MemoryCache> 클래스.</span><span class="sxs-lookup"><span data-stu-id="c94ad-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c94ad-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c94ad-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c94ad-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c94ad-115">특성</span><span class="sxs-lookup"><span data-stu-id="c94ad-115">Attributes</span></span>  
  
|<span data-ttu-id="c94ad-116">특성</span><span class="sxs-lookup"><span data-stu-id="c94ad-116">Attribute</span></span>|<span data-ttu-id="c94ad-117">설명</span><span class="sxs-lookup"><span data-stu-id="c94ad-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="c94ad-118"><xref:System.Runtime.Caching.MemoryCache> 개체의 인스턴스가 증가될 수 있는 최대 메모리 크기(메가바이트 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="c94ad-119">기본값은 0입니다. 이 경우 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="c94ad-120">캐시 구성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="c94ad-121">캐시에서 사용할 수 있는 실제 메모리의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="c94ad-122">기본값은 0입니다. 이 경우 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="c94ad-123">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="c94ad-124">값은 "HH:MM:SS" 형식으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c94ad-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c94ad-125">Child Elements</span></span>  
  
|<span data-ttu-id="c94ad-126">요소</span><span class="sxs-lookup"><span data-stu-id="c94ad-126">Element</span></span>|<span data-ttu-id="c94ad-127">설명</span><span class="sxs-lookup"><span data-stu-id="c94ad-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c94ad-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c94ad-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="c94ad-129">`namedCache` 인스턴스에 대한 구성 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c94ad-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c94ad-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c94ad-131">요소</span><span class="sxs-lookup"><span data-stu-id="c94ad-131">Element</span></span>|<span data-ttu-id="c94ad-132">설명</span><span class="sxs-lookup"><span data-stu-id="c94ad-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c94ad-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="c94ad-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="c94ad-134">[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]에 빌드된 응용 프로그램에서 출력 캐싱을 구현할 수 있는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-134">Contains types that let you implement output caching in applications that are built into the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c94ad-135">설명</span><span class="sxs-lookup"><span data-stu-id="c94ad-135">Remarks</span></span>  
 <span data-ttu-id="c94ad-136"><xref:System.Runtime.Caching.MemoryCache> 클래스는 추상적인 <xref:System.Runtime.Caching.ObjectCache> 클래스의 구체적인 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="c94ad-137"><xref:System.Runtime.Caching.MemoryCache> 클래스의 인스턴스는 응용 프로그램 구성 파일의 구성 정보와 함께 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="c94ad-138">[memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) 구성 섹션은 `namedCaches` 구성 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="c94ad-139">메모리 기반 캐시 개체는 초기화된 후 우선 메모리 캐시 생성자에 전달된 매개 변수의 이름과 일치하는 `namedCaches` 항목을 찾으려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="c94ad-140">`namedCaches` 항목이 발견되면 구성 파일에서 폴링 및 메모리 관리 정보에 대한 검색이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="c94ad-141">그런 다음 초기화 프로세스는 생성자에 있는 구성 정보의 선택적인 이름/값 쌍 컬렉션을 사용하여 구성 항목의 재정의 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="c94ad-142">이름/값 쌍 컬렉션에서 다음 값 중 하나를 전달하는 경우 이러한 값은 구성 파일에서 가져온 정보를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="c94ad-143">예제</span><span class="sxs-lookup"><span data-stu-id="c94ad-143">Example</span></span>  
 <span data-ttu-id="c94ad-144">다음 예제에서는 <xref:System.Runtime.Caching.MemoryCache> 특성을 "기본값"으로 설정하여 `name` 개체의 이름을 기본 캐시 개체 이름으로 설정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="c94ad-145">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryLimitPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="c94ad-146">이러한 특성을 0으로 설정하면 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 자동 크기 조정 추론이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="c94ad-147">캐시 구현에서는 현재 메모리 로드가 절대 및 백분율 기반 메모리 제한과 2분마다 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94ad-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c94ad-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c94ad-148">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 [<span data-ttu-id="c94ad-149">\<system.runtime.caching > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="c94ad-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)  
 [<span data-ttu-id="c94ad-150">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="c94ad-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
