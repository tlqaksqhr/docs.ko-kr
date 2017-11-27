---
title: "추적 및 디버그 설정 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 97c96fbb1abf969d902159709ca0e738f475fab9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="abb42-102">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="abb42-102">Trace and Debug Settings Schema</span></span>
<span data-ttu-id="abb42-103">추적 및 디버그 설정은 메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="abb42-104">다음 표는 각 추적 및 디버그 설정 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="abb42-105">요소</span><span class="sxs-lookup"><span data-stu-id="abb42-105">Element</span></span>|<span data-ttu-id="abb42-106">설명</span><span class="sxs-lookup"><span data-stu-id="abb42-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abb42-107">\<add></span><span class="sxs-lookup"><span data-stu-id="abb42-107">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="abb42-108">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-108">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="abb42-109">\<add></span><span class="sxs-lookup"><span data-stu-id="abb42-109">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="abb42-110">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-110">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="abb42-111">\<add></span><span class="sxs-lookup"><span data-stu-id="abb42-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|<span data-ttu-id="abb42-112">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-112">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="abb42-113">\<add></span><span class="sxs-lookup"><span data-stu-id="abb42-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="abb42-114">추적 스위치를 설정하는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-114">Specifies the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="abb42-115">\<assert></span><span class="sxs-lookup"><span data-stu-id="abb42-115">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="abb42-116"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-116">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="abb42-117">\<clear></span><span class="sxs-lookup"><span data-stu-id="abb42-117">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="abb42-118">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-118">Clears the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="abb42-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="abb42-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="abb42-120">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="abb42-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="abb42-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="abb42-122">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-122">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="abb42-123">\<filter></span><span class="sxs-lookup"><span data-stu-id="abb42-123">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="abb42-124">추적의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-124">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="abb42-125">\<filter></span><span class="sxs-lookup"><span data-stu-id="abb42-125">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="abb42-126">`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-126">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="abb42-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="abb42-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="abb42-128">추적 소스의 `Listeners` 컬렉션에 대한 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-128">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="abb42-129">\<listeners></span><span class="sxs-lookup"><span data-stu-id="abb42-129">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="abb42-130">추적의 `Listeners` 컬렉션에 대한 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-130">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="abb42-131">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="abb42-131">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="abb42-132">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-132">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="abb42-133">\<remove></span><span class="sxs-lookup"><span data-stu-id="abb42-133">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="abb42-134">추적의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-134">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="abb42-135">\<remove></span><span class="sxs-lookup"><span data-stu-id="abb42-135">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="abb42-136">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-136">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="abb42-137">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="abb42-137">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="abb42-138">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-138">Contains listeners that any source or trace element can reference.</span></span>|  
|[<span data-ttu-id="abb42-139">\<sources></span><span class="sxs-lookup"><span data-stu-id="abb42-139">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="abb42-140">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-140">Contains trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="abb42-141">\<source></span><span class="sxs-lookup"><span data-stu-id="abb42-141">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="abb42-142">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-142">Specifies a trace source that initiates tracing messages.</span></span>|  
|[<span data-ttu-id="abb42-143">\<switches></span><span class="sxs-lookup"><span data-stu-id="abb42-143">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="abb42-144">추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-144">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[<span data-ttu-id="abb42-145">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="abb42-145">\<system.diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|<span data-ttu-id="abb42-146">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-146">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="abb42-147">\<trace></span><span class="sxs-lookup"><span data-stu-id="abb42-147">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="abb42-148">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb42-148">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abb42-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abb42-149">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="abb42-150">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="abb42-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
