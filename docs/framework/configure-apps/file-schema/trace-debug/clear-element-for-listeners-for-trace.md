---
title: '&lt;선택을 취소&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1705ed7cc847d60ecf8b42f4615d77f2cc569e21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="538be-102">&lt;선택을 취소&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;</span><span class="sxs-lookup"><span data-stu-id="538be-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="538be-103">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="538be-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="538be-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="538be-104">\<configuration></span></span>  
<span data-ttu-id="538be-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="538be-105">\<system.diagnostics></span></span>  
<span data-ttu-id="538be-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="538be-106">\<trace></span></span>  
<span data-ttu-id="538be-107">\<수신기 ></span><span class="sxs-lookup"><span data-stu-id="538be-107">\<listeners></span></span>  
<span data-ttu-id="538be-108">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="538be-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538be-109">구문</span><span class="sxs-lookup"><span data-stu-id="538be-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="538be-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="538be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="538be-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="538be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="538be-112">특성</span><span class="sxs-lookup"><span data-stu-id="538be-112">Attributes</span></span>  
 <span data-ttu-id="538be-113">없음</span><span class="sxs-lookup"><span data-stu-id="538be-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="538be-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="538be-114">Child Elements</span></span>  
 <span data-ttu-id="538be-115">없음</span><span class="sxs-lookup"><span data-stu-id="538be-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="538be-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="538be-116">Parent Elements</span></span>  
  
|<span data-ttu-id="538be-117">요소</span><span class="sxs-lookup"><span data-stu-id="538be-117">Element</span></span>|<span data-ttu-id="538be-118">설명</span><span class="sxs-lookup"><span data-stu-id="538be-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="538be-119">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="538be-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="538be-120">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="538be-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="538be-121">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538be-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="538be-122">수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="538be-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="538be-123">수신기는 추적 출력을 적절 한 대상에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="538be-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="538be-124">설명</span><span class="sxs-lookup"><span data-stu-id="538be-124">Remarks</span></span>  
 <span data-ttu-id="538be-125">`<clear>` 에서 모든 수신기를 제거 하는 요소는 `Listeners` 추적에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="538be-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="538be-126">사용할 수는 `<clear>` 요소를 사용 하기 전에 `<add>` 요소를 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538be-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="538be-127">지울 수 있습니다는 `Listeners` 호출 하 여 프로그래밍 방식으로 컬렉션은 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 에서 메서드는 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 속성 (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="538be-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="538be-128">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538be-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="538be-129">`<clear>` 요소 제거는 <xref:System.Diagnostics.DefaultTraceListener> 에서 `Listeners` 동작을 변경 하는 컬렉션은 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="538be-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="538be-130">호출 프로그램 `Assert` 또는 `Fail` 메서드는 메시지 상자가 표시에 일반적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="538be-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="538be-131">그러나는 메시지 상자는 표시 되지 않습니다는 <xref:System.Diagnostics.DefaultTraceListener> 에 속하지 않는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="538be-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="538be-132">예제</span><span class="sxs-lookup"><span data-stu-id="538be-132">Example</span></span>  
 <span data-ttu-id="538be-133">사용 하는 방법을 보여 주는 다음 예제는 `<clear>` 요소를 사용 하기 전에 `<add>` 수신기에 추가할 요소의 `console` 에 `Listeners` 추적에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="538be-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="538be-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="538be-134">See Also</span></span>  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="538be-135">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="538be-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="538be-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="538be-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [<span data-ttu-id="538be-137">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="538be-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
