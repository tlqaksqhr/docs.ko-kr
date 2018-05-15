---
title: '&lt;추가&gt; 요소에 대 한 &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="66070-102">&lt;추가&gt; 요소에 대 한 &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="66070-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="66070-103">추가 `namedCache` 항목에는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="66070-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="66070-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="66070-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="66070-105">\<memoryCache></span></span>  
<span data-ttu-id="66070-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="66070-106">\<namedCaches></span></span>  
<span data-ttu-id="66070-107">\<add></span><span class="sxs-lookup"><span data-stu-id="66070-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66070-108">구문</span><span class="sxs-lookup"><span data-stu-id="66070-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="66070-109">형식</span><span class="sxs-lookup"><span data-stu-id="66070-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66070-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66070-110">Attributes and Elements</span></span>  
 <span data-ttu-id="66070-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66070-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66070-112">특성</span><span class="sxs-lookup"><span data-stu-id="66070-112">Attributes</span></span>  
  
|<span data-ttu-id="66070-113">특성</span><span class="sxs-lookup"><span data-stu-id="66070-113">Attribute</span></span>|<span data-ttu-id="66070-114">설명</span><span class="sxs-lookup"><span data-stu-id="66070-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="66070-115">최대 허용 크기를 메가바이트 단위로 지정 하는 정수 값 하의 인스턴스는 <xref:System.Runtime.Caching.MemoryCache> 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66070-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="66070-116">기본값은 0으로, 즉는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 추론 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66070-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="66070-117">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="66070-118">캐시에서 사용할 수 있는 실제로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="66070-119">기본값은 0으로, 즉는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 크기 자동 조정 추론 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66070-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="66070-120">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="66070-121">이 값은 "hh: mm:" 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="66070-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66070-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66070-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="66070-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66070-123">Parent Elements</span></span>  
  
|<span data-ttu-id="66070-124">요소</span><span class="sxs-lookup"><span data-stu-id="66070-124">Element</span></span>|<span data-ttu-id="66070-125">설명</span><span class="sxs-lookup"><span data-stu-id="66070-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66070-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="66070-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="66070-127">명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="66070-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66070-128">설명</span><span class="sxs-lookup"><span data-stu-id="66070-128">Remarks</span></span>  
 <span data-ttu-id="66070-129">`add` 에 항목을 추가 하는 요소는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="66070-130">사용할 수는 [지우기](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) 요소를 사용 하기 전에 `add` 요소를 분명히 다른 수의 명명 된 캐시는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="66070-131">이 요소는 Web.config 파일 및 machine.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66070-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66070-132">예제</span><span class="sxs-lookup"><span data-stu-id="66070-132">Example</span></span>  
 <span data-ttu-id="66070-133">다음 예제에서는 기본값에 대 한 설정을 정의 하는 방법을 보여 줍니다. `namedCache` 항목을는 `namedCaches` 메모리 내 캐시에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="66070-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66070-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66070-134">See Also</span></span>  
 [<span data-ttu-id="66070-135">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="66070-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
