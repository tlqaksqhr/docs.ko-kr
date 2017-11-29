---
title: "&lt;선택을 취소&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d5e8518f2ca8a04d91f5bfdd9f6389c741d0278e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="8bd04-102">&lt;선택을 취소&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;</span><span class="sxs-lookup"><span data-stu-id="8bd04-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="8bd04-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8bd04-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8bd04-104">\<configuration></span></span>  
<span data-ttu-id="8bd04-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="8bd04-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8bd04-106">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="8bd04-106">\<sources></span></span>  
<span data-ttu-id="8bd04-107">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="8bd04-107">\<source></span></span>  
<span data-ttu-id="8bd04-108">\<수신기 ></span><span class="sxs-lookup"><span data-stu-id="8bd04-108">\<listeners></span></span>  
<span data-ttu-id="8bd04-109">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="8bd04-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd04-110">구문</span><span class="sxs-lookup"><span data-stu-id="8bd04-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bd04-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8bd04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8bd04-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bd04-113">특성</span><span class="sxs-lookup"><span data-stu-id="8bd04-113">Attributes</span></span>  
 <span data-ttu-id="8bd04-114">없음</span><span class="sxs-lookup"><span data-stu-id="8bd04-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8bd04-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8bd04-115">Child Elements</span></span>  
 <span data-ttu-id="8bd04-116">없음</span><span class="sxs-lookup"><span data-stu-id="8bd04-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bd04-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8bd04-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8bd04-118">요소</span><span class="sxs-lookup"><span data-stu-id="8bd04-118">Element</span></span>|<span data-ttu-id="8bd04-119">설명</span><span class="sxs-lookup"><span data-stu-id="8bd04-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8bd04-120">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8bd04-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="8bd04-122">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="8bd04-123">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="8bd04-124">수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bd04-125">설명</span><span class="sxs-lookup"><span data-stu-id="8bd04-125">Remarks</span></span>  
 <span data-ttu-id="8bd04-126">`<clear>` 에서 모든 수신기를 제거 하는 요소는 `Listeners` 추적 소스에 대 한 컬렉션 포함 하는 <xref:System.Diagnostics.DefaultTraceListener>합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="8bd04-127">사용할 수는 `<clear>` 요소를 사용 하기 전에 `<add>` 요소를 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="8bd04-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8bd04-128">Configuration File</span></span>  
 <span data-ttu-id="8bd04-129">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bd04-130">예제</span><span class="sxs-lookup"><span data-stu-id="8bd04-130">Example</span></span>  
 <span data-ttu-id="8bd04-131">사용 하는 방법을 보여 주는 다음 예제는 `<clear>` 요소를 사용 하기 전에 `<add>` 요소를 추가 하는 수신기 `console` 및 `textListener` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd04-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="8bd04-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bd04-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="8bd04-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8bd04-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="8bd04-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="8bd04-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
