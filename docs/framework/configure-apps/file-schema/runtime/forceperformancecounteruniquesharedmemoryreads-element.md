---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c90799ed2db061e8f42cde79804789eb8d2da0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a><span data-ttu-id="ab7d8-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="ab7d8-102">&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; Element</span></span>
<span data-ttu-id="ab7d8-103">PerfCounter.dll이 .NET Framework 버전 1.1 응용 프로그램에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="ab7d8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ab7d8-104">\<configuration></span></span>  
<span data-ttu-id="ab7d8-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="ab7d8-105">\<runtime></span></span>  
<span data-ttu-id="ab7d8-106">\<forcePerformanceCounterUniqueSharedMemoryReads ></span><span class="sxs-lookup"><span data-stu-id="ab7d8-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab7d8-107">구문</span><span class="sxs-lookup"><span data-stu-id="ab7d8-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab7d8-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ab7d8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab7d8-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab7d8-110">특성</span><span class="sxs-lookup"><span data-stu-id="ab7d8-110">Attributes</span></span>  
  
|<span data-ttu-id="ab7d8-111">특성</span><span class="sxs-lookup"><span data-stu-id="ab7d8-111">Attribute</span></span>|<span data-ttu-id="ab7d8-112">설명</span><span class="sxs-lookup"><span data-stu-id="ab7d8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ab7d8-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ab7d8-114">범주별 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할 것인지 결정 PerfCounter.dll CategoryOptions 레지스트리 설정을 사용 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ab7d8-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ab7d8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ab7d8-116">값</span><span class="sxs-lookup"><span data-stu-id="ab7d8-116">Value</span></span>|<span data-ttu-id="ab7d8-117">설명</span><span class="sxs-lookup"><span data-stu-id="ab7d8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ab7d8-118">PerfCounter.dll는 CategoryOptions 사용 하지 않는 레지스트리가 설정 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="ab7d8-119">PerfCounter.dll는 CategoryOptions 레지스트리 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab7d8-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ab7d8-120">Child Elements</span></span>  
 <span data-ttu-id="ab7d8-121">없음</span><span class="sxs-lookup"><span data-stu-id="ab7d8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab7d8-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ab7d8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ab7d8-123">요소</span><span class="sxs-lookup"><span data-stu-id="ab7d8-123">Element</span></span>|<span data-ttu-id="ab7d8-124">설명</span><span class="sxs-lookup"><span data-stu-id="ab7d8-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ab7d8-125">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ab7d8-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab7d8-127">설명</span><span class="sxs-lookup"><span data-stu-id="ab7d8-127">Remarks</span></span>  
 <span data-ttu-id="ab7d8-128">이전의.NET Framework의 버전에는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], PerfCounter.dll 로드 된 버전의 프로세스에서 로드 된 런타임에 상응 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="ab7d8-129">컴퓨터의.NET Framework 버전 1.1 갖는 경우 및 [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] 설치 된.NET Framework 1.1 응용 프로그램 로드 PerfCounter.dll의.NET Framework 1.1 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="ab7d8-130">부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], PerfCounter.dll의 설치 된 최신 버전을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="ab7d8-131">즉,.NET Framework 1.1 응용 프로그램 로드 됩니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 버전 PerfCounter.dll의 경우는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-131">This means that a .NET Framework 1.1 application will load the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] version of PerfCounter.dll if the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] is installed on the computer.</span></span>  
  
 <span data-ttu-id="ab7d8-132">부터는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 성능 카운터를 사용 하 고 PerfCounter.dll 범주별 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 확인 하려면 각 공급자에 대 한 CategoryOptions 레지스트리 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="ab7d8-133">공유 메모리 범주별; 인식 하지 않으므로.NET Framework 1.1 PerfCounter.dll 해당 레지스트리 항목을 읽지 않습니다. 항상 전역 공유 메모리에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="ab7d8-134">이전 버전과 호환성을 위해는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll.NET Framework 1.1 응용 프로그램에서 실행 될 때 CategoryOptions 레지스트리 항목을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-134">For backward compatibility, the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="ab7d8-135">단순히.NET Framework 1.1 PerfCounter.dll 마찬가지로 전역 공유 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="ab7d8-136">지시할 수 있습니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll 레지스트리 설정을 사용 하 여 확인 하는 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-136">However, you can instruct the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab7d8-137">사용 하도록 설정 된 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소 범주별 공유 메모리 사용 됨을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="ab7d8-138">사용 하는 설정과 `true` CategoryOptions 레지스트리 설정을 참조 하는 PerfCounter.dll만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="ab7d8-139">CategoryOptions에 대 한 기본 설정은 범주별 공유 메모리를 사용 하는 그러나 전역 공유 메모리를 사용 해야 함을 나타내기 위해 CategoryOptions 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="ab7d8-140">CategoryOptions 설정을 포함 하는 레지스트리 키가 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="ab7d8-141">기본적으로 CategoryOptions은 3으로 설정, PerfCounter.dll 게 지시 범주별 공유 메모리를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="ab7d8-142">CategoryOptions을 0으로 설정 하는 경우 PerfCounter.dll 전역 공유 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="ab7d8-143">만들 인스턴스의 이름을 다시 사용 되 고 인스턴스와 다를 경우에 인스턴스 데이터를 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="ab7d8-144">모든 버전의 범주에 쓸 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="ab7d8-145">CategoryOptions가 1로 설정 하는 경우 전역 공유 메모리 사용 되지만 범주 이름을 다시 사용 하는 범주와 길이가 같은 경우에 인스턴스 데이터를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="ab7d8-146">메모리 누수 및 성능 카운터 메모리의 채우기를 0과 1 설정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab7d8-147">예제</span><span class="sxs-lookup"><span data-stu-id="ab7d8-147">Example</span></span>  
 <span data-ttu-id="ab7d8-148">다음 예제에서는 지정 PerfCounter.dll 범주별 공유 메모리를 사용 해야 하는지 여부를 확인 하려면 CategoryOptions 레지스트리 항목을 참조 해야 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab7d8-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab7d8-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab7d8-149">See Also</span></span>  
 [<span data-ttu-id="ab7d8-150">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ab7d8-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="ab7d8-151">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ab7d8-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
