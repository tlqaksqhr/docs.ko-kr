---
title: '&lt;gcConcurrent&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee00c3a307523d2cae831274630ad6828cd9daf6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="02006-102">&lt;gcConcurrent&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="02006-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="02006-103">공용 언어 런타임이 별도 스레드에서 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="02006-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="02006-104">\<configuration></span></span>  
<span data-ttu-id="02006-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="02006-105">\<runtime></span></span>  
<span data-ttu-id="02006-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="02006-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02006-107">구문</span><span class="sxs-lookup"><span data-stu-id="02006-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02006-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="02006-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02006-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02006-110">특성</span><span class="sxs-lookup"><span data-stu-id="02006-110">Attributes</span></span>  
  
|<span data-ttu-id="02006-111">특성</span><span class="sxs-lookup"><span data-stu-id="02006-111">Attribute</span></span>|<span data-ttu-id="02006-112">설명</span><span class="sxs-lookup"><span data-stu-id="02006-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="02006-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="02006-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="02006-114">런타임이 동시에 가비지 수집을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="02006-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="02006-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="02006-116">값</span><span class="sxs-lookup"><span data-stu-id="02006-116">Value</span></span>|<span data-ttu-id="02006-117">설명</span><span class="sxs-lookup"><span data-stu-id="02006-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="02006-118">동시에 가비지 컬렉션을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="02006-119">동시에 가비지 컬렉션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="02006-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="02006-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02006-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="02006-121">Child Elements</span></span>  
 <span data-ttu-id="02006-122">없음</span><span class="sxs-lookup"><span data-stu-id="02006-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02006-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="02006-123">Parent Elements</span></span>  
  
|<span data-ttu-id="02006-124">요소</span><span class="sxs-lookup"><span data-stu-id="02006-124">Element</span></span>|<span data-ttu-id="02006-125">설명</span><span class="sxs-lookup"><span data-stu-id="02006-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02006-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="02006-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02006-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02006-128">설명</span><span class="sxs-lookup"><span data-stu-id="02006-128">Remarks</span></span>  
 <span data-ttu-id="02006-129">.NET Framework 4 이전에는 워크스테이션 가비지 컬렉션이 별도 스레드에서 백그라운드로 가비지 컬렉션을 수행한 동시 가비지 컬렉션을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="02006-130">.NET Framework 4에서는 동시 가비지 수집이 역시 별도 스레드에서 백그라운드로 가비지 수집을 수행하는 백그라운드 GC로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="02006-131">.NET Framework 4.5부터 백그라운드 수집을 서버 가비지 수집에서 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="02006-132">`<gcConcurrent>` 요소는 런타임이 사용 가능한 경우 동시 또는 백그라운드 가비지 수집을 수행하는지 여부 또는 포그라운드에서 가비지 수집을 수행하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="02006-133">.NET Framework 4부터 동시 가비지 컬렉션이 백그라운드 가비지 컬렉션으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="02006-134">용어 *동시* 및 *배경* .NET Framework 설명서에서 같은 의미로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02006-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="02006-135">백그라운드 가비지 수집을 사용하지 않으려면, 이 문서에 설명된 대로 `<gcConcurrent>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="02006-136">기본적으로 런타임은 대기 시간에 최적화된 동시 또는 백그라운드 가비지 수집을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="02006-137">사용자 상호 작용이 많이 필요한 응용 프로그램인 경우에는 가비지 수집을 수행할 때 응용 프로그램의 일시 중지를 최소화하도록 동시 가비지 수집 기능을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02006-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="02006-138">`enabled` 요소의 `<gcConcurrent>` 특성을 `false`에 설정할 경우 런타임은 효율성이 최적화된 비동시성 가비지 수집을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="02006-139">다음 구성 파일에서는 백그라운드 가비지 수집을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="02006-140">컴퓨터 구성 파일에 `<gcConcurrentSetting>` 설정이 있는 경우 모든 .NET Framework 응용 프로그램에 대한 기본값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="02006-141">컴퓨터 구성 파일 설정은 응용 프로그램 구성 파일 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="02006-142">자세한 동시에 대 한 정보 및 백그라운드 가비지 수집의 "동시 가비지 수집" 섹션을 참조는 [가비지 수집 기본 사항](../../../../../docs/standard/garbage-collection/fundamentals.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="02006-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02006-143">예제</span><span class="sxs-lookup"><span data-stu-id="02006-143">Example</span></span>  
 <span data-ttu-id="02006-144">다음 예제에서는 동시 가비지 컬렉션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02006-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02006-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02006-145">See Also</span></span>  
 [<span data-ttu-id="02006-146">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="02006-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="02006-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="02006-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="02006-148">가비지 수집 기본 사항</span><span class="sxs-lookup"><span data-stu-id="02006-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
