---
title: '&lt;appDomainResourceMonitoring&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e892d8ab9001d3670c801b43ba444aa24b2e41
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="f0388-102">&lt;appDomainResourceMonitoring&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="f0388-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="f0388-103">프로세스의 수명 동안 프로세스의 모든 응용 프로그램 도메인에서 통계를 수집하도록 런타임에 명령합니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="f0388-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f0388-104">\<configuration></span></span>  
<span data-ttu-id="f0388-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="f0388-105">\<runtime></span></span>  
<span data-ttu-id="f0388-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="f0388-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0388-107">구문</span><span class="sxs-lookup"><span data-stu-id="f0388-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0388-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f0388-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f0388-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0388-110">특성</span><span class="sxs-lookup"><span data-stu-id="f0388-110">Attributes</span></span>  
  
|<span data-ttu-id="f0388-111">특성</span><span class="sxs-lookup"><span data-stu-id="f0388-111">Attribute</span></span>|<span data-ttu-id="f0388-112">설명</span><span class="sxs-lookup"><span data-stu-id="f0388-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f0388-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f0388-114">런타임에 응용 프로그램 도메인 리소스 모니터링에 대 한 통계를 수집 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f0388-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="f0388-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f0388-116">값</span><span class="sxs-lookup"><span data-stu-id="f0388-116">Value</span></span>|<span data-ttu-id="f0388-117">설명</span><span class="sxs-lookup"><span data-stu-id="f0388-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f0388-118">응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="f0388-119">응용 프로그램 도메인 리소스 모니터링에 대 한 통계 수집 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0388-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f0388-120">Child Elements</span></span>  
 <span data-ttu-id="f0388-121">없음</span><span class="sxs-lookup"><span data-stu-id="f0388-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0388-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f0388-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f0388-123">요소</span><span class="sxs-lookup"><span data-stu-id="f0388-123">Element</span></span>|<span data-ttu-id="f0388-124">설명</span><span class="sxs-lookup"><span data-stu-id="f0388-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f0388-125">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f0388-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0388-127">설명</span><span class="sxs-lookup"><span data-stu-id="f0388-127">Remarks</span></span>  
 <span data-ttu-id="f0388-128">응용 프로그램 도메인 리소스 모니터링은 호스트 하는 관리 되는 응용 프로그램 도메인 클래스를 통해 사용할 수 있는 [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 이벤트 추적에 대 한 ETW (Windows).</span><span class="sxs-lookup"><span data-stu-id="f0388-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="f0388-129">모니터링이 사용 하는 경우 프로세스의 수명에 대 한 프로세스의 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="f0388-130">관리 코드에서 모니터링을 사용 하려면 사용 하 여는 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="f0388-131">이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상.</span><span class="sxs-lookup"><span data-stu-id="f0388-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0388-132">예제</span><span class="sxs-lookup"><span data-stu-id="f0388-132">Example</span></span>  
 <span data-ttu-id="f0388-133">다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0388-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0388-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0388-134">See Also</span></span>  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="f0388-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f0388-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f0388-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f0388-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
