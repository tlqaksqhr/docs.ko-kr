---
title: "&lt;sharedListeners&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: aef29e6107a2f441d8c1a6826b16f0f0c0b56973
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="e4098-102">&lt;sharedListeners&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="e4098-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="e4098-103">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="e4098-104">기본적으로이 수신기에 설치 된 모든 수신 하지 않음 하 고 런타임 시 이러한 수신기를 검색할 수 없으면입니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="e4098-105">공유 수신기로 식별 된 수신기 이름으로 원본 또는 추적에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="e4098-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e4098-106">\<configuration></span></span>  
<span data-ttu-id="e4098-107">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e4098-107">\<system.diagnostics></span></span>  
<span data-ttu-id="e4098-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="e4098-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4098-109">구문</span><span class="sxs-lookup"><span data-stu-id="e4098-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4098-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e4098-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e4098-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4098-112">특성</span><span class="sxs-lookup"><span data-stu-id="e4098-112">Attributes</span></span>  
 <span data-ttu-id="e4098-113">없음</span><span class="sxs-lookup"><span data-stu-id="e4098-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4098-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e4098-114">Child Elements</span></span>  
  
|<span data-ttu-id="e4098-115">요소</span><span class="sxs-lookup"><span data-stu-id="e4098-115">Element</span></span>|<span data-ttu-id="e4098-116">설명</span><span class="sxs-lookup"><span data-stu-id="e4098-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4098-117">\<add></span><span class="sxs-lookup"><span data-stu-id="e4098-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="e4098-118">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4098-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e4098-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e4098-120">요소</span><span class="sxs-lookup"><span data-stu-id="e4098-120">Element</span></span>|<span data-ttu-id="e4098-121">설명</span><span class="sxs-lookup"><span data-stu-id="e4098-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="e4098-122">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e4098-123">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4098-124">설명</span><span class="sxs-lookup"><span data-stu-id="e4098-124">Remarks</span></span>  
 <span data-ttu-id="e4098-125">공유 수신기 컬렉션에 수신기를 추가 활성 수신기를 게 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="e4098-126">여전히 추가 해야 추적 또는 추적 소스에 추가 하 여는 `Listeners` 해당 추적 요소에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="e4098-127">.NET Framework의 수신기 클래스에서 파생 되는 <xref:System.Diagnostics.TraceListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="e4098-128">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4098-129">예</span><span class="sxs-lookup"><span data-stu-id="e4098-129">Example</span></span>  
 <span data-ttu-id="e4098-130">사용 하는 방법을 보여 주는 다음 예제는 `<sharedListeners>` 수신기에 추가할 요소의 `console` 에 `Listeners` 컬렉션 모두에 대 한는 <xref:System.Diagnostics.TraceSource> 및 <xref:System.Diagnostics.Trace> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="e4098-131">콘솔 추적 수신기에 대 한 호출을 통해 콘솔에 추적 정보를 쓰는 <xref:System.Diagnostics.TraceSource> 또는 <xref:System.Diagnostics.Trace>합니다.</span><span class="sxs-lookup"><span data-stu-id="e4098-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="e4098-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4098-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="e4098-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e4098-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="e4098-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="e4098-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
