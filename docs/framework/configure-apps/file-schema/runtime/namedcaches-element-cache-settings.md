---
title: "&lt;namedCaches&gt; 요소 (캐시 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bdafddcb05dd50f059c9f6804573beec085a4a2a
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="8ed50-102">&lt;namedCaches&gt; 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="8ed50-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="8ed50-103">명명 된 구성 설정의 컬렉션을 지정 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8ed50-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="8ed50-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 속성 구성 설정의 컬렉션을 하나 이상에서 참조 `namedCaches` 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="8ed50-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8ed50-105">\<configuration></span></span>  
<span data-ttu-id="8ed50-106">\<system.runtime.caching ></span><span class="sxs-lookup"><span data-stu-id="8ed50-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="8ed50-107">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="8ed50-107">\<memoryCache></span></span>  
<span data-ttu-id="8ed50-108">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="8ed50-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed50-109">구문</span><span class="sxs-lookup"><span data-stu-id="8ed50-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="8ed50-110">형식</span><span class="sxs-lookup"><span data-stu-id="8ed50-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ed50-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ed50-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8ed50-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ed50-113">특성</span><span class="sxs-lookup"><span data-stu-id="8ed50-113">Attributes</span></span>  
  
|<span data-ttu-id="8ed50-114">특성</span><span class="sxs-lookup"><span data-stu-id="8ed50-114">Attribute</span></span>|<span data-ttu-id="8ed50-115">설명</span><span class="sxs-lookup"><span data-stu-id="8ed50-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="8ed50-116">최대 허용 크기 (메가바이트)에서 지정 하는 정수 값 하의 인스턴스는 <xref:System.Runtime.Caching.MemoryCache> 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="8ed50-117">기본값은 0으로의 크기 자동 조정 추론 하는 것을 의미는 <xref:System.Runtime.Caching.MemoryCache> 클래스는 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="8ed50-118">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="8ed50-119">캐시에서 사용할 수 있는 실제로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="8ed50-120">기본값은 0으로의 크기 자동 조정 추론 하는 것을 의미는 <xref:System.Runtime.Caching.MemoryCache> 클래스는 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="8ed50-121">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="8ed50-122">이 값은 "hh: mm:" 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ed50-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ed50-123">Child Elements</span></span>  
  
|<span data-ttu-id="8ed50-124">요소</span><span class="sxs-lookup"><span data-stu-id="8ed50-124">Element</span></span>|<span data-ttu-id="8ed50-125">설명</span><span class="sxs-lookup"><span data-stu-id="8ed50-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ed50-126">\<add></span><span class="sxs-lookup"><span data-stu-id="8ed50-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="8ed50-127">메모리 캐시용으로 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="8ed50-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="8ed50-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="8ed50-129">메모리 캐시에 대해 `namedCaches` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="8ed50-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="8ed50-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="8ed50-131">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ed50-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ed50-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8ed50-133">요소</span><span class="sxs-lookup"><span data-stu-id="8ed50-133">Element</span></span>|<span data-ttu-id="8ed50-134">설명</span><span class="sxs-lookup"><span data-stu-id="8ed50-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ed50-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="8ed50-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="8ed50-136"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ed50-137">설명</span><span class="sxs-lookup"><span data-stu-id="8ed50-137">Remarks</span></span>  
 <span data-ttu-id="8ed50-138">Web.config 파일의 메모리 캐시 구성 섹션에 포함 될 수 있습니다 `add`, `remove`, 및 `clear` 에 대 한 특성은 `namedCaches` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="8ed50-139">각 `namedCaches` 항목으로 고유 하 게 식별 되는 `name` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="8ed50-140">응용 프로그램 구성 파일의 정보를 참조 하 여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="8ed50-141">기본적으로 기본 캐시 인스턴스에 구성 파일에는 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="8ed50-142">기본 캐시 인스턴스는에서 반환 되는 인스턴스는 <xref:System.Runtime.Caching.MemoryCache.Default%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="8ed50-143">Name 특성을 "기본값"으로 설정 하면 요소의 기본 메모리 캐시 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ed50-144">예제</span><span class="sxs-lookup"><span data-stu-id="8ed50-144">Example</span></span>  
 <span data-ttu-id="8ed50-145">다음 예제에서는 설정 하 여 기본 캐시 항목 이름에는 캐시의 이름을 설정 하는 `name` 특성을 "default"입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="8ed50-146">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="8ed50-147">이러한 특성을 0으로 설정 됨을 의미의 크기 자동 조정 추론은 <xref:System.Runtime.Caching.MemoryCache> 클래스 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="8ed50-148">캐시를 구현 하는 2 분 마다 절대 곡선과 백분율을 기준으로 메모리 제한에 대 한 현재 메모리 로드를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed50-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed50-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ed50-149">See Also</span></span>  
 [<span data-ttu-id="8ed50-150">\<memoryCache > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="8ed50-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
