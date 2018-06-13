---
title: '&lt;추적&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59d5083632630513d2afc1f8d78400310451e46f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746061"
---
# <a name="lttracegt-element"></a><span data-ttu-id="0490e-102">&lt;추적&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="0490e-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="0490e-103">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="0490e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0490e-104">\<configuration></span></span>  
<span data-ttu-id="0490e-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="0490e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0490e-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="0490e-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0490e-107">구문</span><span class="sxs-lookup"><span data-stu-id="0490e-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0490e-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0490e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0490e-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0490e-110">특성</span><span class="sxs-lookup"><span data-stu-id="0490e-110">Attributes</span></span>  
  
|<span data-ttu-id="0490e-111">특성</span><span class="sxs-lookup"><span data-stu-id="0490e-111">Attribute</span></span>|<span data-ttu-id="0490e-112">설명</span><span class="sxs-lookup"><span data-stu-id="0490e-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="0490e-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0490e-114">추적 수신기 모든 쓰기 작업 후 출력 버퍼를 자동으로 플러시 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="0490e-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0490e-116">들여쓰기를 공백 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="0490e-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0490e-118">전역 잠금을 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="0490e-119">autoflush 특성</span><span class="sxs-lookup"><span data-stu-id="0490e-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="0490e-120">값</span><span class="sxs-lookup"><span data-stu-id="0490e-120">Value</span></span>|<span data-ttu-id="0490e-121">설명</span><span class="sxs-lookup"><span data-stu-id="0490e-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0490e-122">출력 버퍼를 자동으로 플러시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="0490e-123">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0490e-124">자동으로 출력 버퍼를 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="0490e-125">useGlobalLock 특성</span><span class="sxs-lookup"><span data-stu-id="0490e-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="0490e-126">값</span><span class="sxs-lookup"><span data-stu-id="0490e-126">Value</span></span>|<span data-ttu-id="0490e-127">설명</span><span class="sxs-lookup"><span data-stu-id="0490e-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0490e-128">수신기가 스레드로부터 안전; 전역 잠금을 사용 하지 않습니다. 그렇지 않으면 전역 잠금을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="0490e-129">수신기가 스레드로부터 안전 하 게 보호 하는 여부에 관계 없이 전역 잠금을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="0490e-130">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0490e-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0490e-131">Child Elements</span></span>  
  
|<span data-ttu-id="0490e-132">요소</span><span class="sxs-lookup"><span data-stu-id="0490e-132">Element</span></span>|<span data-ttu-id="0490e-133">설명</span><span class="sxs-lookup"><span data-stu-id="0490e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0490e-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="0490e-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="0490e-135">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0490e-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0490e-136">Parent Elements</span></span>  
  
|<span data-ttu-id="0490e-137">요소</span><span class="sxs-lookup"><span data-stu-id="0490e-137">Element</span></span>|<span data-ttu-id="0490e-138">설명</span><span class="sxs-lookup"><span data-stu-id="0490e-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0490e-139">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0490e-140">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0490e-141">예제</span><span class="sxs-lookup"><span data-stu-id="0490e-141">Example</span></span>  
 <span data-ttu-id="0490e-142">사용 하는 방법을 보여 주는 다음 예제는 `<trace>` 수신기에 추가할 요소의 `MyListener` 에 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="0490e-143">`MyListener` 명명 된 파일을 만듭니다. `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="0490e-144">`useGlobalLock` 특성이로 설정 된 `false`, 추적 수신기가 스레드로부터 안전 하 게 보호 하는 경우 사용할 필요가 없는 전역 잠금에 이르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="0490e-145">`autoflush` 특성이로 설정 된 `true`, 여부에 관계 없이 파일에 쓸 추적 수신기에 이르게는 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="0490e-146">`indentsize` 특성이 하면 들여쓰기 0 공간 수신기 0 (영)으로 설정 된 경우는 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0490e-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0490e-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0490e-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="0490e-148">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0490e-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
