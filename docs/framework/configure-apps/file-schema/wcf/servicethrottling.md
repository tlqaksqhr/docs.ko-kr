---
title: '&lt;serviceThrottling&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a059684967af26c72aca48a3fa6bb10c2f26b0c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="8f8a8-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="8f8a8-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="8f8a8-103">WCF(Windows Communication Foundation) 서비스의 스로틀 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="8f8a8-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f8a8-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-105">\<behaviors></span></span>  
<span data-ttu-id="8f8a8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8f8a8-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-107">\<behavior></span></span>  
<span data-ttu-id="8f8a8-108">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8a8-109">구문</span><span class="sxs-lookup"><span data-stu-id="8f8a8-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f8a8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8f8a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f8a8-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f8a8-112">특성</span><span class="sxs-lookup"><span data-stu-id="8f8a8-112">Attributes</span></span>  
  
|<span data-ttu-id="8f8a8-113">특성</span><span class="sxs-lookup"><span data-stu-id="8f8a8-113">Attribute</span></span>|<span data-ttu-id="8f8a8-114">설명</span><span class="sxs-lookup"><span data-stu-id="8f8a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f8a8-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="8f8a8-115">maxConcurrentCalls</span></span>|<span data-ttu-id="8f8a8-116"><xref:System.ServiceModel.ServiceHost>에서 현재 처리되는 메시지 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="8f8a8-117">제한을 초과하는 호출은 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="8f8a8-118">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="8f8a8-119">기본값은 16 * 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-119">The default is 16 * processor count.</span></span>|  
|<span data-ttu-id="8f8a8-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="8f8a8-120">maxConcurrentInstances</span></span>|<span data-ttu-id="8f8a8-121"><xref:System.ServiceModel.InstanceContext>에서 한 번에 실행하는 <xref:System.ServiceModel.ServiceHost> 개체 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="8f8a8-122">추가 인스턴스 생성 요청은 큐에 대기했다가 인스턴스 수가 한도 아래로 내려가면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="8f8a8-123">기본값은 maxConcurrentSessions와 MaxConcurrentCalls의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="8f8a8-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="8f8a8-124">maxConcurrentSessions</span></span>|<span data-ttu-id="8f8a8-125"><xref:System.ServiceModel.ServiceHost> 개체에서 수락할 수 있는 세션 수를 제한하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="8f8a8-126">서비스는 제한을 초과하는 연결을 수락하지만 제한 아래의 채널만 활성화되며 해당 채널에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="8f8a8-127">이 값을 0으로 설정하는 것은 Int32.MaxValue로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="8f8a8-128">기본값은 100 * 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-128">The default is 100 * processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f8a8-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f8a8-129">Child Elements</span></span>  
 <span data-ttu-id="8f8a8-130">없음</span><span class="sxs-lookup"><span data-stu-id="8f8a8-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f8a8-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f8a8-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8f8a8-132">요소</span><span class="sxs-lookup"><span data-stu-id="8f8a8-132">Element</span></span>|<span data-ttu-id="8f8a8-133">설명</span><span class="sxs-lookup"><span data-stu-id="8f8a8-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f8a8-134">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8f8a8-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8f8a8-135">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f8a8-136">설명</span><span class="sxs-lookup"><span data-stu-id="8f8a8-136">Remarks</span></span>  
 <span data-ttu-id="8f8a8-137">스로틀은 리소스가 과도하게 사용되는 것을 방지하기 위해 동시 호출, 인스턴스 또는 세션 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="8f8a8-138">특성 값에 도달할 때마다 추적이 기록되며</span><span class="sxs-lookup"><span data-stu-id="8f8a8-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="8f8a8-139">첫 번째 추적이 경고로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f8a8-140">예</span><span class="sxs-lookup"><span data-stu-id="8f8a8-140">Example</span></span>  
 <span data-ttu-id="8f8a8-141">다음 구성 예제에서는 서비스가 최대 동시 호출 수를 2로 제한하고 최대 동시 인스턴스 수를 10으로 제한하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="8f8a8-142">이 예제를 실행 하는의 자세한 예제를 보려면 [제한](../../../../../docs/framework/wcf/samples/throttling.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8a8-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f8a8-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f8a8-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="8f8a8-144">ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어</span><span class="sxs-lookup"><span data-stu-id="8f8a8-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
