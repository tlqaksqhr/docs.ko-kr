---
title: "&lt;진단&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c7997b3ffc1a1c3a16372398f43e8f0d06aadee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiagnosticsgt"></a><span data-ttu-id="30a5a-102">&lt;진단&gt;</span><span class="sxs-lookup"><span data-stu-id="30a5a-102">&lt;diagnostics&gt;</span></span>
<span data-ttu-id="30a5a-103">`diagnostics` 요소는 관리자가 런타임 검사 및 제어에 사용할 수 있는 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-103">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="30a5a-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="30a5a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="30a5a-105">\<진단 ></span><span class="sxs-lookup"><span data-stu-id="30a5a-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a5a-106">구문</span><span class="sxs-lookup"><span data-stu-id="30a5a-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics etwProviderId="String"       performanceCounters="Off/ServiceOnly/All/Default"              wmiProviderEnabled="Boolean" >       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
          maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
             <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30a5a-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="30a5a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="30a5a-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30a5a-109">특성</span><span class="sxs-lookup"><span data-stu-id="30a5a-109">Attributes</span></span>  
  
|<span data-ttu-id="30a5a-110">특성</span><span class="sxs-lookup"><span data-stu-id="30a5a-110">Attribute</span></span>|<span data-ttu-id="30a5a-111">설명</span><span class="sxs-lookup"><span data-stu-id="30a5a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30a5a-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="30a5a-112">etwProviderId</span></span>|<span data-ttu-id="30a5a-113">ETW 세션에 이벤트를 기록하는 이벤트 추적 공급자에 대한 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="30a5a-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="30a5a-114">performanceCounters</span></span>|<span data-ttu-id="30a5a-115">어셈블리에 대해 성능 카운터를 사용할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="30a5a-116">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-116">Valid values are</span></span><br /><br /> <span data-ttu-id="30a5a-117">-Off: 성능 카운터가 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="30a5a-118">-ServiceOnly:이 서비스와 관련 된 성능 카운터만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="30a5a-119">-모든: 성능을 런타임에 카운터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="30a5a-120">-기본: 단일 성능 카운터 인스턴스 _WCF_Admin 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="30a5a-121">이 인스턴스는 인프라에서 사용되는 SQM 데이터 컬렉션을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="30a5a-122">이 인스턴스의 어떤 카운터 값도 업데이트되지 않으므로 0으로 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="30a5a-123">이것은 WCF에 대한 구성이 없을 경우 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="30a5a-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="30a5a-124">wmiProviderEnabled</span></span>|<span data-ttu-id="30a5a-125">어셈블리에 대해 WMI 공급자를 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="30a5a-126">사용자가 WCF(Windows Communication Foundation)의 검사 및 제어 기능에 대해 런타임 액세스 권한을 얻으려면 WMI 공급자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="30a5a-127">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30a5a-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="30a5a-128">Child Elements</span></span>  
  
|<span data-ttu-id="30a5a-129">요소</span><span class="sxs-lookup"><span data-stu-id="30a5a-129">Element</span></span>|<span data-ttu-id="30a5a-130">설명</span><span class="sxs-lookup"><span data-stu-id="30a5a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30a5a-131">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="30a5a-131">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="30a5a-132">서비스 응용 프로그램 실행 중에 종단 간 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="30a5a-133">\<메시지 로깅 ></span><span class="sxs-lookup"><span data-stu-id="30a5a-133">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="30a5a-134">WCF 메시지 로깅의 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30a5a-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="30a5a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="30a5a-136">요소</span><span class="sxs-lookup"><span data-stu-id="30a5a-136">Element</span></span>|<span data-ttu-id="30a5a-137">설명</span><span class="sxs-lookup"><span data-stu-id="30a5a-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30a5a-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="30a5a-138">serviceModel</span></span>|<span data-ttu-id="30a5a-139">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30a5a-140">설명</span><span class="sxs-lookup"><span data-stu-id="30a5a-140">Remarks</span></span>  
 <span data-ttu-id="30a5a-141">`diagnostics` 섹션에서는 어셈블리에 있는 모든 서비스의 진단 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="30a5a-142">어셈블리에 서비스가 하나만 있는 경우가 아니라면 서비스 수준에서 별도의 진단 설정을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="30a5a-143">해당 섹션의 요구 사항에 따라 특성이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="30a5a-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30a5a-144">예</span><span class="sxs-lookup"><span data-stu-id="30a5a-144">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"  
       performanceCounters="all">  
       <messageLogging logEntireMessage="true"  
          logMalformedMessages="true"  
          logMessagesAtServiceLevel="true"  
          logMessagesAtTransportLevel="true"  
          maxMessagesToLog="42"  
          maxSizeOfMessageToLog="42">  
         <filters>  
         <clear />  
    </filters>  
       </messageLogging>  
</diagnostics>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30a5a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30a5a-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
