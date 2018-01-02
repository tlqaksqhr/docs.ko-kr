---
title: "&lt;performanceCounters&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="51947-102">&lt;performanceCounters&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="51947-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="51947-103">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="51947-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="51947-104">\<configuration></span></span>  
<span data-ttu-id="51947-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="51947-105">\<system.diagnostics></span></span>  
<span data-ttu-id="51947-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="51947-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51947-107">구문</span><span class="sxs-lookup"><span data-stu-id="51947-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51947-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="51947-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51947-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51947-110">특성</span><span class="sxs-lookup"><span data-stu-id="51947-110">Attributes</span></span>  
  
|<span data-ttu-id="51947-111">특성</span><span class="sxs-lookup"><span data-stu-id="51947-111">Attribute</span></span>|<span data-ttu-id="51947-112">설명</span><span class="sxs-lookup"><span data-stu-id="51947-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51947-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="51947-113">filemappingsize</span></span>|<span data-ttu-id="51947-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="51947-115">성능 카운터에서 공유 글로벌 메모리를 바이트 단위로 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="51947-116">기본값은 524288입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51947-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="51947-117">Child Elements</span></span>  
 <span data-ttu-id="51947-118">없음</span><span class="sxs-lookup"><span data-stu-id="51947-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51947-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="51947-119">Parent Elements</span></span>  
  
|<span data-ttu-id="51947-120">요소</span><span class="sxs-lookup"><span data-stu-id="51947-120">Element</span></span>|<span data-ttu-id="51947-121">설명</span><span class="sxs-lookup"><span data-stu-id="51947-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="51947-122">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="51947-123">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51947-124">설명</span><span class="sxs-lookup"><span data-stu-id="51947-124">Remarks</span></span>  
 <span data-ttu-id="51947-125">성능 카운터 메모리 매핑된 파일 또는 공유 메모리를 사용 하 여 성능 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="51947-126">공유 메모리 크기에 따라 결정 인스턴스 수를 한 번에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51947-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="51947-127">두 가지 방법으로 공유 메모리: 전역 공유 메모리와 별도 공유 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="51947-128">전역 공유 메모리는.NET Framework 버전 1.0 또는 1.1와 함께 설치 된 모든 성능 카운터 범주에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51947-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="51947-129">.NET Framework 버전 2.0과 함께 설치 되는 성능 카운터 범주는 자체 메모리가 있는 각 성능 카운터 범주와 별도 공유 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="51947-130">구성 파일을 사용 해야만 전역 공유 메모리의 크기를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51947-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="51947-131">크기의 기본값은 524, 288 바이트이 하 이기, 최대 크기는 33,554,432 바이트가 고 최소 크기는 32, 768 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="51947-132">전역 공유 메모리 모든 프로세스와 범주 전체에서 공유 하는 이후 첫 번째 생성자는 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51947-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="51947-133">응용 프로그램 구성 파일의 크기를 정의 하는 경우 응용 프로그램이 첫 번째 응용 프로그램 성능 카운터를 실행 시키는 경우 크기가 크기에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51947-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="51947-134">따라서 올바른 위치를 지정 하는 `filemappingsize` 값은 Machine.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="51947-135">개별 성능 카운터로 있으므로 결국 많은 수의 서로 다른 이름 사용 하는 성능 카운터 인스턴스가 생성 되는 경우 전역 공유 메모리를 소진 되는 전역 공유 메모리에 메모리를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51947-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="51947-136">별도 공유 메모리 크기에 대 한 레지스트리에서 DWORD FileMappingSize 값 키 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<범주 이름 >*\Performance 참조 먼저, 구성 파일에서 전역 공유 메모리에 지정 된 값을 옵니다.</span><span class="sxs-lookup"><span data-stu-id="51947-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>*\Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="51947-137">FileMappingSize 값이 존재 하지 않는 경우 별도 공유 메모리 크기 1 4로 설정 됩니다 (1/4) 구성 파일의 전역 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="51947-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51947-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51947-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
