---
title: '&lt;소스&gt; 요소'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcegt-element"></a><span data-ttu-id="4da86-102">&lt;소스&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="4da86-102">&lt;source&gt; Element</span></span>
<span data-ttu-id="4da86-103">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="4da86-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4da86-104">\<configuration></span></span>  
<span data-ttu-id="4da86-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4da86-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4da86-106">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="4da86-106">\<sources></span></span>  
<span data-ttu-id="4da86-107">\<소스 ></span><span class="sxs-lookup"><span data-stu-id="4da86-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da86-108">구문</span><span class="sxs-lookup"><span data-stu-id="4da86-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da86-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4da86-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4da86-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da86-111">특성</span><span class="sxs-lookup"><span data-stu-id="4da86-111">Attributes</span></span>  
  
|<span data-ttu-id="4da86-112">특성</span><span class="sxs-lookup"><span data-stu-id="4da86-112">Attribute</span></span>|<span data-ttu-id="4da86-113">설명</span><span class="sxs-lookup"><span data-stu-id="4da86-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4da86-114">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4da86-115">추적 소스 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="4da86-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4da86-117">응용 프로그램에서 추적 스위치 인스턴스 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="4da86-118">스위치에서 식별 되지 않는 경우는 `<switches>` 요소 값에 스위치에 대 한 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="4da86-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4da86-120">추적 스위치의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="4da86-121">있는 경우 유효한 클래스 이름 이어야 합니다 형식과 빈 문자열일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="4da86-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4da86-123">로 식별 되는 추적 소스 관련 특성에 대 한 값을 지정 된 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 해당 추적 소스에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="4da86-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4da86-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4da86-124">Child Elements</span></span>  
  
|<span data-ttu-id="4da86-125">요소</span><span class="sxs-lookup"><span data-stu-id="4da86-125">Element</span></span>|<span data-ttu-id="4da86-126">설명</span><span class="sxs-lookup"><span data-stu-id="4da86-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4da86-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="4da86-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="4da86-128">수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4da86-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4da86-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4da86-130">요소</span><span class="sxs-lookup"><span data-stu-id="4da86-130">Element</span></span>|<span data-ttu-id="4da86-131">설명</span><span class="sxs-lookup"><span data-stu-id="4da86-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4da86-132">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4da86-133">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4da86-134">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4da86-135">설명</span><span class="sxs-lookup"><span data-stu-id="4da86-135">Remarks</span></span>  
 <span data-ttu-id="4da86-136">이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da86-137">예제</span><span class="sxs-lookup"><span data-stu-id="4da86-137">Example</span></span>  
 <span data-ttu-id="4da86-138">사용 하는 방법을 보여 주는 다음 예제는 `<source>` 추적 소스를 추가할 요소의 `mySource` 명명 된 소스 스위치에 대 한 수준을 설정 하 고 `sourceSwitch`합니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4da86-139">콘솔 추적 수신기는 추적 정보를 콘솔에 작성 하는 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4da86-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4da86-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4da86-140">See Also</span></span>  
 [<span data-ttu-id="4da86-141">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4da86-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="4da86-142">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="4da86-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
