---
title: "&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;sharedListeners&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: bc3f97619c8ec28a61a9a51b431581383558a7d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a><span data-ttu-id="8f64c-102">&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="8f64c-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="8f64c-103">`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="8f64c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8f64c-104">\<configuration></span></span>  
<span data-ttu-id="8f64c-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="8f64c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8f64c-106">\<sharedListeners > 요소</span><span class="sxs-lookup"><span data-stu-id="8f64c-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="8f64c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8f64c-107">\<add></span></span>  
<span data-ttu-id="8f64c-108">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="8f64c-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f64c-109">구문</span><span class="sxs-lookup"><span data-stu-id="8f64c-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f64c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8f64c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f64c-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f64c-112">특성</span><span class="sxs-lookup"><span data-stu-id="8f64c-112">Attributes</span></span>  
  
|<span data-ttu-id="8f64c-113">특성</span><span class="sxs-lookup"><span data-stu-id="8f64c-113">Attribute</span></span>|<span data-ttu-id="8f64c-114">설명</span><span class="sxs-lookup"><span data-stu-id="8f64c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f64c-115">**type**</span><span class="sxs-lookup"><span data-stu-id="8f64c-115">**type**</span></span>|<span data-ttu-id="8f64c-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8f64c-117">필터의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-117">Specifies the type of the filter.</span></span> <span data-ttu-id="8f64c-118">형식의 전체 이름을 사용할 수 있습니다 (의 형식에는 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성), 하거나 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다 (의 형식에는 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> 속성).</span><span class="sxs-lookup"><span data-stu-id="8f64c-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="8f64c-119">정규화 된 형식 이름을 만드는 방법에 대 한 정보를 참조 하십시오. [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="8f64c-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="8f64c-120">**initializeData**</span></span>|<span data-ttu-id="8f64c-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8f64c-122">지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f64c-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f64c-123">Child Elements</span></span>  
 <span data-ttu-id="8f64c-124">없음</span><span class="sxs-lookup"><span data-stu-id="8f64c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f64c-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f64c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8f64c-126">요소</span><span class="sxs-lookup"><span data-stu-id="8f64c-126">Element</span></span>|<span data-ttu-id="8f64c-127">설명</span><span class="sxs-lookup"><span data-stu-id="8f64c-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8f64c-128">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8f64c-129">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="8f64c-130">모든 원본이 나 추적 요소를 참조할 수 있는 수신기의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="8f64c-131">수신기를 추가 **sharedListeners** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f64c-132">설명</span><span class="sxs-lookup"><span data-stu-id="8f64c-132">Remarks</span></span>  
 <span data-ttu-id="8f64c-133">수신기에 정의 된 경우는 `<add>` 의 요소는 `<sharedListeners>` 요소를 해당 수신기에 대 한 필터에 정의 되어야 합니다는 `<filter>` 의 자식인 요소는 `<add>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="8f64c-134">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f64c-135">예</span><span class="sxs-lookup"><span data-stu-id="8f64c-135">Example</span></span>  
 <span data-ttu-id="8f64c-136">사용 하는 방법을 보여 주는 다음 예제는 `<filter>` 추적 수신기에 필터를 추가 하는 요소 `console` 에 `sharedListeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f64c-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f64c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f64c-137">See Also</span></span>  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="8f64c-138">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8f64c-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
