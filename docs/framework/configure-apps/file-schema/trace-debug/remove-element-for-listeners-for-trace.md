---
title: "&lt;제거&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ff1eb93a6d81f83b60e2621296e0c9d995699898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="8d0ce-102">&lt;제거&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;</span><span class="sxs-lookup"><span data-stu-id="8d0ce-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="8d0ce-103">수신기를 제거는 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="8d0ce-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8d0ce-104">\<configuration></span></span>  
<span data-ttu-id="8d0ce-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="8d0ce-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8d0ce-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="8d0ce-106">\<trace></span></span>  
<span data-ttu-id="8d0ce-107">\<수신기 ></span><span class="sxs-lookup"><span data-stu-id="8d0ce-107">\<listeners></span></span>  
<span data-ttu-id="8d0ce-108">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="8d0ce-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0ce-109">구문</span><span class="sxs-lookup"><span data-stu-id="8d0ce-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d0ce-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d0ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8d0ce-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d0ce-112">특성</span><span class="sxs-lookup"><span data-stu-id="8d0ce-112">Attributes</span></span>  
  
|<span data-ttu-id="8d0ce-113">특성</span><span class="sxs-lookup"><span data-stu-id="8d0ce-113">Attribute</span></span>|<span data-ttu-id="8d0ce-114">설명</span><span class="sxs-lookup"><span data-stu-id="8d0ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d0ce-115">**name**</span><span class="sxs-lookup"><span data-stu-id="8d0ce-115">**name**</span></span>|<span data-ttu-id="8d0ce-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8d0ce-117">제거할 수신기의 이름에서 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d0ce-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d0ce-118">Child Elements</span></span>  
 <span data-ttu-id="8d0ce-119">없음</span><span class="sxs-lookup"><span data-stu-id="8d0ce-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d0ce-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d0ce-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8d0ce-121">요소</span><span class="sxs-lookup"><span data-stu-id="8d0ce-121">Element</span></span>|<span data-ttu-id="8d0ce-122">설명</span><span class="sxs-lookup"><span data-stu-id="8d0ce-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8d0ce-123">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="8d0ce-124">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="8d0ce-125">수신기는 추적 출력을 적절 한 대상에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8d0ce-126">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="8d0ce-127">ASP.NET 추적 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d0ce-128">설명</span><span class="sxs-lookup"><span data-stu-id="8d0ce-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d0ce-129">제거는 <xref:System.Diagnostics.DefaultTraceListener> 에서 `Listeners` 의 동작을 변경 하는 컬렉션은 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="8d0ce-130">호출 프로그램 `Assert` 또는 `Fail` 메서드는 메시지 상자를 표시 하는 경우에 메시지 상자가 표시 되지 않습니다 되지만 일반적으로 결과 <xref:System.Diagnostics.DefaultTraceListener> 에 속하지 않는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d0ce-131">예제</span><span class="sxs-lookup"><span data-stu-id="8d0ce-131">Example</span></span>  
 <span data-ttu-id="8d0ce-132">다음 예제에서는 추적에서 기본 추적 수신기를 제거 하는 방법을 보여 줍니다. **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0ce-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d0ce-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d0ce-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="8d0ce-134">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8d0ce-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
