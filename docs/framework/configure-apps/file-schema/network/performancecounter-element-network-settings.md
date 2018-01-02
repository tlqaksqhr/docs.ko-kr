---
title: "&lt;performanceCounter&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 669811b20fd9980b6876683ec7eff4c235a676ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="1531d-102">&lt;performanceCounter&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="1531d-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1531d-103">네트워킹 성능 카운터를 사용 하지 않도록 설정 하거나 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="1531d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1531d-104">\<configuration></span></span>  
<span data-ttu-id="1531d-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="1531d-105">\<system.net></span></span>  
<span data-ttu-id="1531d-106">\<설정 ></span><span class="sxs-lookup"><span data-stu-id="1531d-106">\<settings></span></span>  
<span data-ttu-id="1531d-107">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="1531d-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1531d-108">구문</span><span class="sxs-lookup"><span data-stu-id="1531d-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1531d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1531d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1531d-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1531d-111">특성</span><span class="sxs-lookup"><span data-stu-id="1531d-111">Attributes</span></span>  
  
|<span data-ttu-id="1531d-112">특성</span><span class="sxs-lookup"><span data-stu-id="1531d-112">Attribute</span></span>|<span data-ttu-id="1531d-113">설명</span><span class="sxs-lookup"><span data-stu-id="1531d-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1531d-114">네트워킹 성능 카운터를 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="1531d-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1531d-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1531d-116">Child Elements</span></span>  
 <span data-ttu-id="1531d-117">없음</span><span class="sxs-lookup"><span data-stu-id="1531d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1531d-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1531d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1531d-119">요소</span><span class="sxs-lookup"><span data-stu-id="1531d-119">Element</span></span>|<span data-ttu-id="1531d-120">설명</span><span class="sxs-lookup"><span data-stu-id="1531d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1531d-121">설정</span><span class="sxs-lookup"><span data-stu-id="1531d-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="1531d-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1531d-123">설명</span><span class="sxs-lookup"><span data-stu-id="1531d-123">Remarks</span></span>  
 <span data-ttu-id="1531d-124">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="1531d-125">네트워킹 성능 카운터를 사용하려면 구성 파일에서 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="1531d-126">구성 파일의 단일 설정을 통해 모든 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="1531d-127">개별 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="1531d-128">특정 네트워킹 성능 카운터에 대 한 자세한 내용은 참조 하십시오. [네트워킹 성능 카운터](http://msdn.microsoft.com/en-us/d1860235-f643-46ae-846c-ff0ed8b0e3cd)합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-128">For more information on the specific networking performance counters, see [Networking Performance Counters](http://msdn.microsoft.com/en-us/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span></span>  
  
 <span data-ttu-id="1531d-129">기본값은 해당 네트워킹 성능 카운터가 비활성화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="1531d-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 **활성화** 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1531d-131">예</span><span class="sxs-lookup"><span data-stu-id="1531d-131">Example</span></span>  
 <span data-ttu-id="1531d-132">구성 하는 방법을 보여 주는 다음 예제는 <xref:System.Net> 및 관련 네임 스페이스 네트워킹 성능 카운터를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1531d-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1531d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1531d-133">See Also</span></span>  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="1531d-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1531d-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="1531d-135">네트워킹 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="1531d-135">Networking Performance Counters</span></span>](http://msdn.microsoft.com/en-us/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
