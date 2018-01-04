---
title: "Send 활동의 캐시 공유 수준 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59c6ae1ae31a5aa256844e6efca158e4702b6aba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a><span data-ttu-id="3239e-102">Send 활동의 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="3239e-102">Changing the Cache Sharing Levels for Send Activities</span></span>
<span data-ttu-id="3239e-103"><xref:System.ServiceModel.Activities.SendMessageChannelCache> 확장을 사용하면 <xref:System.ServiceModel.Activities.Send> 메시징 활동을 사용하여 서비스 끝점으로 메시지를 전송하는 워크플로에 대한 채널 캐시 설정, 채널 팩터리 캐시 설정 및 캐시 공유 수준을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension enables you to customize the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using <xref:System.ServiceModel.Activities.Send> messaging activities.</span></span> <span data-ttu-id="3239e-104">이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-104">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="3239e-105">채널 팩터리 캐시는 캐시된 <xref:System.ServiceModel.ChannelFactory%601> 개체를 포함하고,</span><span class="sxs-lookup"><span data-stu-id="3239e-105">The channel factory cache contains cached <xref:System.ServiceModel.ChannelFactory%601> objects.</span></span> <span data-ttu-id="3239e-106">채널 캐시는 캐시된 채널을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-106">The channel cache contains cached channels.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3239e-107">워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동을 사용하여 메시지 또는 매개 변수를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-107">Workflows can use <xref:System.ServiceModel.Activities.Send> messaging activities to send either messages or parameters.</span></span> <span data-ttu-id="3239e-108">워크플로 런타임에서는 <xref:System.ServiceModel.Channels.IRequestChannel> 활동을 <xref:System.ServiceModel.Activities.ReceiveReply> 활동과 함께 사용할 경우 <xref:System.ServiceModel.Activities.Send> 형식 채널을 만드는 캐시에 채널 팩터리를 추가하고, <xref:System.ServiceModel.Channels.IOutputChannel> 없이 <xref:System.ServiceModel.Activities.Send> 활동만 사용할 경우 <xref:System.ServiceModel.Activities.ReceiveReply> 형식 채널을 만드는 캐시에 채널 팩터리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-108">The workflow runtime adds channel factories to the cache that create channels of type <xref:System.ServiceModel.Channels.IRequestChannel> when you use a <xref:System.ServiceModel.Activities.ReceiveReply> activity with a <xref:System.ServiceModel.Activities.Send> activity, and an <xref:System.ServiceModel.Channels.IOutputChannel> when just using a <xref:System.ServiceModel.Activities.Send> activity (no <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>  
  
## <a name="the-cache-sharing-levels"></a><span data-ttu-id="3239e-109">캐시 공유 수준</span><span class="sxs-lookup"><span data-stu-id="3239e-109">The Cache Sharing Levels</span></span>  
 <span data-ttu-id="3239e-110">기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="3239e-110">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost> the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="3239e-111"><xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱).</span><span class="sxs-lookup"><span data-stu-id="3239e-111">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="3239e-112">안전하지 않은 캐싱을 사용하지 않는 경우 구성에 정의된 끝점을 사용하지 않는 <xref:System.ServiceModel.Activities.Send> 활동에 대해서만 캐시를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-112">The cache is only available for <xref:System.ServiceModel.Activities.Send> activities that do not use endpoints defined in configuration unless unsafe caching is enabled.</span></span>  
  
 <span data-ttu-id="3239e-113">워크플로의 <xref:System.ServiceModel.Activities.Send> 활동에 대해 사용할 수 있는 다양한 캐시 공유 수준과 권장 사용법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-113">The following are the different cache sharing levels available for <xref:System.ServiceModel.Activities.Send> activities in a workflow and their recommended use:</span></span>  
  
-   <span data-ttu-id="3239e-114">**호스트 수준**: 호스트 공유 수준에서에서 캐시는 워크플로 서비스 호스트에서 호스팅되는 워크플로 인스턴스에서만에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-114">**Host Level**: In the host sharing level, the cache is available only to the workflow instances hosted in the workflow service host.</span></span> <span data-ttu-id="3239e-115">또한 프로세스 수준 캐시에서 워크플로 서비스 호스트 간에 캐시를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-115">A cache can also be shared between workflow service hosts in a process-wide cache.</span></span>  
  
-   <span data-ttu-id="3239e-116">**인스턴스 수준**: 인스턴스 공유 수준, 캐시를 전체 수명 동안 특정 워크플로 인스턴스에 사용할 수 있지만 캐시는 다른 워크플로 인스턴스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-116">**Instance Level**: In the instance sharing level, the cache is available to a particular workflow instance throughout its lifetime but the cache is not available to other workflow instances.</span></span>  
  
-   <span data-ttu-id="3239e-117">**캐시 없음**: 캐시는 기본적으로 해제 되어 구성에 정의 된 끝점을 사용 하는 워크플로 설정한 경우.</span><span class="sxs-lookup"><span data-stu-id="3239e-117">**No Cache**: The cache is turned off by default if you have a workflow that uses endpoints defined in configuration.</span></span> <span data-ttu-id="3239e-118">또한 이 경우 캐시를 설정하면 안전하지 않으므로 캐시를 해제된 상태로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-118">It is also recommended to keep the cache turned off in this case because turning it on could be unsecure.</span></span> <span data-ttu-id="3239e-119">예를 들어 전송할 때마다 다른 ID(다른 자격 증명 또는 가장 사용)가 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-119">For example, if a different identity (different credentials or using impersonation) is required for each send.</span></span>  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a><span data-ttu-id="3239e-120">클라이언트 워크플로에 대한 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="3239e-120">Changing the Cache Sharing Level for a Client Workflow</span></span>  
 <span data-ttu-id="3239e-121">클라이언트 워크플로의 캐시 공유를 설정하려면 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 클래스의 인스턴스를 원하는 워크플로 인스턴스 집합에 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-121">To set the cache sharing in a client workflow, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to the desired set of workflow instances.</span></span> <span data-ttu-id="3239e-122">그러면 모든 워크플로 인스턴스에서 캐시를 공유하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-122">This results in sharing the cache across all the workflow instances.</span></span> <span data-ttu-id="3239e-123">다음 코드 예제에서는 이러한 단계를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-123">The following code examples show how to perform these steps.</span></span>  
  
 <span data-ttu-id="3239e-124">먼저 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 형식의 인스턴스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-124">First, declare an instance of type <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span></span>  
  
```  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 <span data-ttu-id="3239e-125">다음은 각 클라이언트 워크플로 인스턴스에 캐시 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-125">Next, add the cache extension to each client workflow instance.</span></span>  
  
```  
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object   
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a><span data-ttu-id="3239e-126">호스팅된 워크플로 서비스에 대한 캐시 공유 수준 변경</span><span class="sxs-lookup"><span data-stu-id="3239e-126">Changing the Cache Sharing Level for a Hosted Workflow Service</span></span>  
 <span data-ttu-id="3239e-127">호스팅된 워크플로 서비스의 캐시 공유를 설정하려면 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 클래스의 인스턴스를 모든 워크플로 서비스 호스트에 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-127">To set the cache sharing in a hosted workflow service, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to all the workflow service hosts.</span></span> <span data-ttu-id="3239e-128">그러면 모든 워크플로 서비스 호스트에서 캐시를 공유하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-128">This results in sharing the cache across all the workflow service hosts.</span></span> <span data-ttu-id="3239e-129">다음 코드 예제에서는 이러한 단계를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-129">The following code examples show to perform these steps.</span></span>  
  
 <span data-ttu-id="3239e-130">먼저 클래스 수준에서 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 형식 인스턴스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-130">First, declare an instance  of type <xref:System.ServiceModel.Activities.SendMessageChannelCache> at the class level.</span></span>  
  
```  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 <span data-ttu-id="3239e-131">다음은 각 워크플로 서비스 호스트에 정적 캐시 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-131">Next, add the static cache extension to each workflow service host.</span></span>  
  
```  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 <span data-ttu-id="3239e-132">호스팅된 워크플로 서비스의 캐시 공유를 인스턴스 수준으로 설정하려면 `Func<SendMessageChannelCache>` 대리자를 워크플로 서비스 호스트에 확장으로 추가한 다음 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 클래스의 새 인스턴스를 인스턴스화하는 코드에 이 대리자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-132">To set the cache sharing in a hosted workflow service to the instance level, add a `Func<SendMessageChannelCache>` delegate as an extension to the workflow service host and assign this delegate to the code that instantiates a new instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class.</span></span> <span data-ttu-id="3239e-133">그러면 워크플로 서비스 호스트의 모든 워크플로 인스턴스에서 단일 캐시를 공유하는 대신 개별 워크플로 인스턴스마다 다른 캐시가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-133">This results in a different cache for each individual workflow instance, instead of a single cache shared by all workflow instances in the workflow service host.</span></span> <span data-ttu-id="3239e-134">다음 코드 예제에서는 람다 식을 사용하여 대리자가 가리키는 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 확장을 직접 정의함으로써 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-134">The following code example shows how to achieve this by using a lambda expression to directly define the <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension that the delegate points to.</span></span>  
  
```  
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings   
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings   
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a><span data-ttu-id="3239e-135">캐시 설정 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3239e-135">Customizing Cache Settings</span></span>  
 <span data-ttu-id="3239e-136">채널 팩터리 캐시 및 채널 캐시에 대한 캐시 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-136">You can customize the cache settings for the channel factory cache and the channel cache.</span></span> <span data-ttu-id="3239e-137">캐시 설정은 <xref:System.ServiceModel.Activities.ChannelCacheSettings> 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-137">The cache settings are defined in the <xref:System.ServiceModel.Activities.ChannelCacheSettings> class.</span></span> <span data-ttu-id="3239e-138"><xref:System.ServiceModel.Activities.SendMessageChannelCache> 클래스는 기본 생성자의 채널 캐시와 채널 팩터리 캐시에 대한 기본 캐시 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-138">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> class defines default cache settings for the channel factory cache and the channel cache in its default constructor.</span></span> <span data-ttu-id="3239e-139">다음 표에서는 각 캐시 유형에 대한 이러한 캐시 설정의 기본값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-139">The following table lists the default values of these cache settings for each type of cache.</span></span>  
  
|<span data-ttu-id="3239e-140">설정</span><span class="sxs-lookup"><span data-stu-id="3239e-140">Settings</span></span>|<span data-ttu-id="3239e-141">LeaseTimeout(분)</span><span class="sxs-lookup"><span data-stu-id="3239e-141">LeaseTimeout (min)</span></span>|<span data-ttu-id="3239e-142">IdleTimeout(분)</span><span class="sxs-lookup"><span data-stu-id="3239e-142">IdleTimeout (min)</span></span>|<span data-ttu-id="3239e-143">MaxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="3239e-143">MaxItemsInCache</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="3239e-144">팩터리 캐시 기본값</span><span class="sxs-lookup"><span data-stu-id="3239e-144">Factory Cache Default</span></span>|<span data-ttu-id="3239e-145">TimeSpan.MaxValue</span><span class="sxs-lookup"><span data-stu-id="3239e-145">TimeSpan.MaxValue</span></span>|<span data-ttu-id="3239e-146">2</span><span class="sxs-lookup"><span data-stu-id="3239e-146">2</span></span>|<span data-ttu-id="3239e-147">16</span><span class="sxs-lookup"><span data-stu-id="3239e-147">16</span></span>|  
|<span data-ttu-id="3239e-148">채널 캐시 기본값</span><span class="sxs-lookup"><span data-stu-id="3239e-148">Channel Cache Default</span></span>|<span data-ttu-id="3239e-149">5</span><span class="sxs-lookup"><span data-stu-id="3239e-149">5</span></span>|<span data-ttu-id="3239e-150">2</span><span class="sxs-lookup"><span data-stu-id="3239e-150">2</span></span>|<span data-ttu-id="3239e-151">16</span><span class="sxs-lookup"><span data-stu-id="3239e-151">16</span></span>|  
  
 <span data-ttu-id="3239e-152">팩터리 캐시 및 채널 캐시 설정을 사용자 지정하려면 매개 변수가 있는 생성자 <xref:System.ServiceModel.Activities.SendMessageChannelCache>을 사용하여 <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> 클래스를 인스턴스화하고 <xref:System.ServiceModel.Activities.ChannelCacheSettings>의 새 인스턴스를 사용자 지정 값과 함께 각 `factorySettings` 및 `channelSettings` 매개 변수에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-152">To customize the factory cache and channel cache settings, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> and pass a new instance of the <xref:System.ServiceModel.Activities.ChannelCacheSettings> with custom values to each of the `factorySettings` and `channelSettings` parameters.</span></span> <span data-ttu-id="3239e-153">다음에는 이 클래스의 새 인스턴스를 워크플로 서비스 호스트 또는 워크플로 인스턴스에 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-153">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="3239e-154">다음 코드 예제에서는 워크플로 인스턴스에 대해 이러한 단계를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-154">The following code example shows how to perform these steps for a workflow instance.</span></span>  
  
```  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,   
                        IdleTimeout = TimeSpan.FromMinutes(5),   
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,   
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="3239e-155">워크플로 서비스의 구성에 끝점이 정의되어 있을 때 캐싱을 사용하려면 <xref:System.ServiceModel.Activities.SendMessageChannelCache> 매개 변수를 <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>로 설정한 상태에서 매개 변수가 있는 생성자 `allowUnsafeCaching`을 사용하여 `true` 클래스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-155">To enable caching when your workflow service has endpoints defined in configuration, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> with the `allowUnsafeCaching` parameter set to `true`.</span></span> <span data-ttu-id="3239e-156">다음에는 이 클래스의 새 인스턴스를 워크플로 서비스 호스트 또는 워크플로 인스턴스에 확장으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-156">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="3239e-157">다음 코드 예제에서는 워크플로 인스턴스에 대해 캐싱을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-157">The following code example shows how to enable caching for a workflow instance.</span></span>  
  
```  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="3239e-158">채널 팩터리 및 채널에 대해 캐시를 완전히 비활성화하려면 채널 팩터리 캐시를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-158">To disable the cache completely for the channel factories and the channels, disable the channel factory cache.</span></span> <span data-ttu-id="3239e-159">해당 채널 팩터리에서 채널을 소유하므로 캐시를 비활성화하면 채널 캐시도 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-159">Doing so also turns off the channel cache as the channels are owned by their corresponding channel factories.</span></span> <span data-ttu-id="3239e-160">채널 팩터리 캐시를 사용하지 않도록 설정하려면 `factorySettings` 값 0을 사용하여 <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> 인스턴스로 초기화되는 <xref:System.ServiceModel.Activities.ChannelCacheSettings> 생성자에 <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-160">To disable the channel factory cache, pass the `factorySettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="3239e-161">다음 코드 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-161">The following code example shows this.</span></span>  
  
```  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="3239e-162">채널 팩터리 캐시만 사용하고 채널 캐시는 사용하지 않도록 설정하려면 `channelSettings` 값 0을 사용하여 <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> 인스턴스로 초기화되는 <xref:System.ServiceModel.Activities.ChannelCacheSettings> 생성자에 <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> 매개 변수를 전달하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-162">You can choose to use only the channel factory cache and disable the channel cache by passing the `channelSettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="3239e-163">다음 코드 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-163">The following code example shows this.</span></span>  
  
```  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="3239e-164">호스팅된 워크플로 서비스의 경우 응용 프로그램 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-164">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="3239e-165">이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-165">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="3239e-166">다음 예제에서는 포함 된 구성 파일의 내용이 표시는 `MyChannelCacheBehavior` 서비스 동작을 사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-166">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="3239e-167">이 서비스 동작을 통해 서비스에 추가 `behaviorConfiguarion` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3239e-167">This service behavior is added to the service through the `behaviorConfiguarion` attribute.</span></span>  
  
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
