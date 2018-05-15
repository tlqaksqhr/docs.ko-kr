---
title: '&lt;수신기&gt; 요소에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2f0d795d6a8789772ff3fd46648fbc0d683c66e5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltlistenersgt-element-for-lttracegt"></a><span data-ttu-id="bd0b7-102">&lt;수신기&gt; 요소에 대 한 &lt;추적&gt;</span><span class="sxs-lookup"><span data-stu-id="bd0b7-102">&lt;listeners&gt; Element for &lt;trace&gt;</span></span>
<span data-ttu-id="bd0b7-103">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="bd0b7-104">수신기는 추적 출력을 적절 한 대상에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="bd0b7-105">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-105">\<configuration> Element</span></span>  
<span data-ttu-id="bd0b7-106">\<system.diagnostics > 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="bd0b7-107">\<추적 > 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-107">\<trace> Element</span></span>  
<span data-ttu-id="bd0b7-108">\<수신기 > 요소에 대 한 \<추적 ></span><span class="sxs-lookup"><span data-stu-id="bd0b7-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0b7-109">구문</span><span class="sxs-lookup"><span data-stu-id="bd0b7-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd0b7-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd0b7-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd0b7-112">특성</span><span class="sxs-lookup"><span data-stu-id="bd0b7-112">Attributes</span></span>  
 <span data-ttu-id="bd0b7-113">없음</span><span class="sxs-lookup"><span data-stu-id="bd0b7-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd0b7-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-114">Child Elements</span></span>  
  
|<span data-ttu-id="bd0b7-115">요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-115">Element</span></span>|<span data-ttu-id="bd0b7-116">설명</span><span class="sxs-lookup"><span data-stu-id="bd0b7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0b7-117">\<add></span><span class="sxs-lookup"><span data-stu-id="bd0b7-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="bd0b7-118">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="bd0b7-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="bd0b7-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="bd0b7-120">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="bd0b7-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="bd0b7-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="bd0b7-122">수신기를 제거는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd0b7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bd0b7-124">요소</span><span class="sxs-lookup"><span data-stu-id="bd0b7-124">Element</span></span>|<span data-ttu-id="bd0b7-125">설명</span><span class="sxs-lookup"><span data-stu-id="bd0b7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bd0b7-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bd0b7-127">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="bd0b7-128">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd0b7-129">설명</span><span class="sxs-lookup"><span data-stu-id="bd0b7-129">Remarks</span></span>  
 <span data-ttu-id="bd0b7-130"><xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스 공유할지 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="bd0b7-131">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하 고 다른 클래스 동일한 수신기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="bd0b7-132">.NET Framework와 함께 제공 되는 수신기 클래스에서 파생 되는 <xref:System.Diagnostics.TraceListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bd0b7-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bd0b7-133">Configuration File</span></span>  
 <span data-ttu-id="bd0b7-134">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd0b7-135">예제</span><span class="sxs-lookup"><span data-stu-id="bd0b7-135">Example</span></span>  
 <span data-ttu-id="bd0b7-136">사용 하는 방법을 보여 주는 다음 예제는  **\<수신기 >** 수신기에 추가할 요소의 `MyListener` 및 `MyEventListener` 에 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="bd0b7-137">`MyListener` 라는 파일을 만들어 `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="bd0b7-138">`MyEventListener` 이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd0b7-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd0b7-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd0b7-139">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="bd0b7-140">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bd0b7-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
