---
title: "&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: eb624052c3638cb49abe143ebd4173a5ee85a054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="e748b-102">&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;</span><span class="sxs-lookup"><span data-stu-id="e748b-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="e748b-103">수신기를 추가 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="e748b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e748b-104">\<configuration></span></span>  
<span data-ttu-id="e748b-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e748b-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e748b-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="e748b-106">\<trace></span></span>  
<span data-ttu-id="e748b-107">\<수신기 ></span><span class="sxs-lookup"><span data-stu-id="e748b-107">\<listeners></span></span>  
<span data-ttu-id="e748b-108">\<add></span><span class="sxs-lookup"><span data-stu-id="e748b-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e748b-109">구문</span><span class="sxs-lookup"><span data-stu-id="e748b-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e748b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e748b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e748b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e748b-112">특성</span><span class="sxs-lookup"><span data-stu-id="e748b-112">Attributes</span></span>  
  
|<span data-ttu-id="e748b-113">특성</span><span class="sxs-lookup"><span data-stu-id="e748b-113">Attribute</span></span>|<span data-ttu-id="e748b-114">설명</span><span class="sxs-lookup"><span data-stu-id="e748b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e748b-115">**type**</span><span class="sxs-lookup"><span data-stu-id="e748b-115">**type**</span></span>|<span data-ttu-id="e748b-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e748b-117">수신기의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-117">Specifies the type of the listener.</span></span> <span data-ttu-id="e748b-118">에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="e748b-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="e748b-119">**initializeData**</span></span>|<span data-ttu-id="e748b-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e748b-121">지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="e748b-122">**name**</span><span class="sxs-lookup"><span data-stu-id="e748b-122">**name**</span></span>|<span data-ttu-id="e748b-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e748b-124">수신기의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e748b-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e748b-125">Child Elements</span></span>  
  
|<span data-ttu-id="e748b-126">요소</span><span class="sxs-lookup"><span data-stu-id="e748b-126">Element</span></span>|<span data-ttu-id="e748b-127">설명</span><span class="sxs-lookup"><span data-stu-id="e748b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e748b-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="e748b-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="e748b-129">필터에 수신기를 추가 `Listeners` 추적에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e748b-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e748b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e748b-131">요소</span><span class="sxs-lookup"><span data-stu-id="e748b-131">Element</span></span>|<span data-ttu-id="e748b-132">설명</span><span class="sxs-lookup"><span data-stu-id="e748b-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e748b-133">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="e748b-134">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="e748b-135">수신기는 추적 출력을 적절 한 대상에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e748b-136">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="e748b-137">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e748b-138">설명</span><span class="sxs-lookup"><span data-stu-id="e748b-138">Remarks</span></span>  
 <span data-ttu-id="e748b-139"><xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스 공유할지 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="e748b-140">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하 고 다른 클래스 동일한 수신기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="e748b-141">수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener>합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="e748b-142">지정 하지 않는 경우는 `name` 추적 수신기의 특성의 <xref:System.Diagnostics.TraceListener.Name%2A> 의 추적 수신기 기본값을 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="e748b-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="e748b-143">응용 프로그램에 수신기가 하나만 있는 경우에 이름을 지정 하지 않고 추가 하 고 이름에 대 한 빈 문자열을 지정 하 여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="e748b-144">그러나 응용 프로그램에 수신기를 하나 이상 있으면 식별 하 고 내에서 개별 추적 수신기를 관리할 수 있는 각 추적 수신기에 대 한 고유한 이름을 지정 해야는 <xref:System.Diagnostics.Debug.Listeners%2A> 및 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e748b-145">해당 유형의 하나만 추적 수신기에서 결과 이름을 지정 하 고에 추가 되 고 이름을 동일한 같은 종류의 추적 수신기를 여러 개 추가 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="e748b-146">그러나 여러 명의 동일한 수신기를 프로그래밍 방식으로 추가할 수는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="e748b-147">에 대 한 값은 **initializeData** 특성 만들 수신기의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="e748b-148">지정 하는 모든 추적 수신기 필요 **initializeData**합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e748b-149">사용 하는 경우는 `initializeData` 특성을 "'initializeData' 특성이 선언 되지 않았습니다." 경고는 컴파일러 발생할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="e748b-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="e748b-150">구성 설정의 추상 기본 클래스에 대해 유효성을 검사 하기 때문에이 경고가 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않으므로 `initializeData` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="e748b-151">일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="e748b-152">다음 표에서.NET Framework에 포함 된 추적 수신기가 표시 하 고 값을 설명 자신의 **initializeData** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="e748b-153">추적 수신기 클래스</span><span class="sxs-lookup"><span data-stu-id="e748b-153">Trace listener class</span></span>|<span data-ttu-id="e748b-154">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="e748b-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-155">`useErrorStream` 에 대 한 값은 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="e748b-156">설정의 `initializeData` 특성을 "`true`" 쓸 추적 및 디버그 출력을 <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`"에 쓸 수 <xref:System.Console.Out%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-157">파일의 이름에서 <xref:System.Diagnostics.DelimitedListTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-158">기존 이벤트 로그 원본의 이름의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-159">파일의 이름 하 여 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-160">파일의 이름 하 여 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e748b-161">파일의 이름 하 여 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e748b-162">예</span><span class="sxs-lookup"><span data-stu-id="e748b-162">Example</span></span>  
 <span data-ttu-id="e748b-163">다음 예제에서는 사용 하는 방법을 보여 줍니다.  **\<추가 >** 요소를 추가 하는 수신기 `MyListener` 및 `MyEventListener` 에 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="e748b-164">`MyListener`라는 파일을 만들어 `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="e748b-165">`MyEventListener`이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e748b-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e748b-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e748b-166">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [<span data-ttu-id="e748b-167">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e748b-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="e748b-168">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="e748b-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
