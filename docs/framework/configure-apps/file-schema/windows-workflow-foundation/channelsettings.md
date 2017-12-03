---
title: '&lt;channelSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00a7c919f59afd09e2bcc0807b191ac937bbea97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltchannelsettingsgt"></a><span data-ttu-id="40870-102">&lt;channelSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="40870-102">&lt;channelSettings&gt;</span></span>
<span data-ttu-id="40870-103">채널 캐시의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-103">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="40870-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40870-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="40870-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="40870-105">\<behaviors></span></span>  
<span data-ttu-id="40870-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="40870-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="40870-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="40870-107">\<behavior></span></span>  
<span data-ttu-id="40870-108">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="40870-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="40870-109">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="40870-109">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40870-110">구문</span><span class="sxs-lookup"><span data-stu-id="40870-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40870-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="40870-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40870-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40870-113">특성</span><span class="sxs-lookup"><span data-stu-id="40870-113">Attributes</span></span>  
  
|<span data-ttu-id="40870-114">특성</span><span class="sxs-lookup"><span data-stu-id="40870-114">Attribute</span></span>|<span data-ttu-id="40870-115">설명</span><span class="sxs-lookup"><span data-stu-id="40870-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40870-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="40870-116">idleTimeout</span></span>|<span data-ttu-id="40870-117">개체가 삭제되기 전에 캐시에서 유휴 상태로 있을 수 있는 최대 시간 간격을 지정하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="40870-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="40870-118">leaseTimeout</span></span>|<span data-ttu-id="40870-119">캐시에서 개체가 제거 되는 시간 간격을 지정 하는 TimeSpan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="40870-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="40870-120">maxItemsInCache</span></span>|<span data-ttu-id="40870-121">캐시에 유지될 수 있는 최대 개체 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40870-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="40870-122">Child Elements</span></span>  
 <span data-ttu-id="40870-123">없음</span><span class="sxs-lookup"><span data-stu-id="40870-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40870-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="40870-124">Parent Elements</span></span>  
  
|<span data-ttu-id="40870-125">요소</span><span class="sxs-lookup"><span data-stu-id="40870-125">Element</span></span>|<span data-ttu-id="40870-126">설명</span><span class="sxs-lookup"><span data-stu-id="40870-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40870-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="40870-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="40870-128">캐시 공유 수준, 채널 팩터리 캐시 설정 및 송신 메시징 활동을 사용 하 여 서비스 끝점으로 메시지를 보내는 워크플로 위한 채널 캐시 설정을 사용자 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40870-129">설명</span><span class="sxs-lookup"><span data-stu-id="40870-129">Remarks</span></span>  
 <span data-ttu-id="40870-130">이 서비스 동작은 서비스 끝점에 메시지를 전송하는 워크플로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="40870-131">이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40870-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="40870-132">기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="40870-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="40870-133"><xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="40870-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="40870-134">구성에 정의된 끝점이 있는 워크플로의 경우 기본적으로 Send 활동에 캐싱을 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40870-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="40870-135">기본 캐시 공유 수준을 변경 하 고 캐시 채널 팩터리 및 채널 캐시에 대 한 설정을 참조 하는 방법 [보내기 활동에 대 한 캐시 공유 수준 변경](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-135"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40870-136">예제</span><span class="sxs-lookup"><span data-stu-id="40870-136">Example</span></span>  
 <span data-ttu-id="40870-137">호스팅된 워크플로 서비스의 경우 응용 프로그램 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40870-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="40870-138">이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="40870-139">다음 예제에서는 포함 된 구성 파일의 내용이 표시는 **MyChannelCacheBehavior** 서비스 동작을 사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="40870-140">이 서비스 동작을 통해 서비스에 추가 **behaviorConfiguarion** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="40870-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40870-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40870-141">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [<span data-ttu-id="40870-142">Send 활동 수준의 캐시 공유를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="40870-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
