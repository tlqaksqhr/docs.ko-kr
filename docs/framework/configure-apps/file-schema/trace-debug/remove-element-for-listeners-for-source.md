---
title: "&lt;제거&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b983c5eb80f958098b6991970559d077b97a0759
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="526b9-102">&lt;제거&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;</span><span class="sxs-lookup"><span data-stu-id="526b9-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="526b9-103">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="526b9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="526b9-104">\<configuration></span></span>  
<span data-ttu-id="526b9-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="526b9-105">\<system.diagnostics></span></span>  
<span data-ttu-id="526b9-106">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="526b9-106">\<sources></span></span>  
<span data-ttu-id="526b9-107">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="526b9-107">\<source></span></span>  
<span data-ttu-id="526b9-108">\<수신기 ></span><span class="sxs-lookup"><span data-stu-id="526b9-108">\<listeners></span></span>  
<span data-ttu-id="526b9-109">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="526b9-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526b9-110">구문</span><span class="sxs-lookup"><span data-stu-id="526b9-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="526b9-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="526b9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="526b9-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="526b9-113">특성</span><span class="sxs-lookup"><span data-stu-id="526b9-113">Attributes</span></span>  
  
|<span data-ttu-id="526b9-114">특성</span><span class="sxs-lookup"><span data-stu-id="526b9-114">Attribute</span></span>|<span data-ttu-id="526b9-115">설명</span><span class="sxs-lookup"><span data-stu-id="526b9-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="526b9-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="526b9-117">제거할 수신기의 이름에서 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="526b9-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="526b9-118">Child Elements</span></span>  
 <span data-ttu-id="526b9-119">없음</span><span class="sxs-lookup"><span data-stu-id="526b9-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="526b9-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="526b9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="526b9-121">요소</span><span class="sxs-lookup"><span data-stu-id="526b9-121">Element</span></span>|<span data-ttu-id="526b9-122">설명</span><span class="sxs-lookup"><span data-stu-id="526b9-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="526b9-123">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="526b9-124">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="526b9-125">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="526b9-126">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="526b9-127">수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="526b9-128">설명</span><span class="sxs-lookup"><span data-stu-id="526b9-128">Remarks</span></span>  
 <span data-ttu-id="526b9-129">`<remove>` 에서 지정 된 수신기를 제거 하는 요소는 `Listeners` 추적 소스에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="526b9-130">요소를 제거할 수 있습니다는 `Listeners` 호출 하 여 프로그래밍 방식으로 추적 소스에 대 한 컬렉션은 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 에서 메서드는 <xref:System.Diagnostics.TraceSource.Listeners%2A> 속성의는 <xref:System.Diagnostics.TraceSource> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="526b9-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="526b9-131">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="526b9-132">예</span><span class="sxs-lookup"><span data-stu-id="526b9-132">Example</span></span>  
 <span data-ttu-id="526b9-133">사용 하는 방법을 보여 주는 다음 예제는 `<remove>` 요소를 사용 하기 전에 `<add>` 수신기에 추가할 요소의 `console` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다.</span><span class="sxs-lookup"><span data-stu-id="526b9-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="526b9-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="526b9-134">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="526b9-135">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="526b9-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="526b9-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="526b9-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [<span data-ttu-id="526b9-137">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="526b9-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
