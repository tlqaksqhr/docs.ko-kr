---
title: "방법: 검색 프록시 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d70e0a-f6c3-4cfb-a7ca-f66ebddadde0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90713d1779566448547265d6487c113abdc84e00
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-implement-a-discovery-proxy"></a><span data-ttu-id="9be1c-102">방법: 검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="9be1c-102">How to: Implement a Discovery Proxy</span></span>
<span data-ttu-id="9be1c-103">이 항목에서는 검색 프록시를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-103">This topic explains how to implement a discovery proxy.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9be1c-104">검색 기능을 사용 하 여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], 참조 [WCF Discovery 개요](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-104"> the discovery feature in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span> <span data-ttu-id="9be1c-105">검색 프록시는 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 추상 클래스를 확장하는 클래스를 만들어 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-105">A discovery proxy can be implemented by creating a class that extends the <xref:System.ServiceModel.Discovery.DiscoveryProxy> abstract class.</span></span> <span data-ttu-id="9be1c-106">이 샘플에서는 많은 다른 지원 클래스가 정의되고 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-106">There are a number of other support classes defined and used in this sample.</span></span> <span data-ttu-id="9be1c-107">`OnResolveAsyncResult`, `OnFindAsyncResult` 및 `AsyncResult`</span><span class="sxs-lookup"><span data-stu-id="9be1c-107">`OnResolveAsyncResult`, `OnFindAsyncResult`, and `AsyncResult`.</span></span> <span data-ttu-id="9be1c-108">이러한 클래스는 <xref:System.IAsyncResult> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-108">These classes implement the <xref:System.IAsyncResult> interface.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9be1c-109"><xref:System.IAsyncResult> 참조 [System.IAsyncResult 인터페이스](xref:System.IAsyncResult)합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-109"> <xref:System.IAsyncResult> see [System.IAsyncResult interface](xref:System.IAsyncResult).</span></span>
  
 <span data-ttu-id="9be1c-110">이 항목에서는 검색 프록시 구현을 크게 다음 세 부분으로 나누어서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-110">Implementing a discovery proxy is broken down into three main parts in this topic:</span></span>  
  
-   <span data-ttu-id="9be1c-111">데이터 저장소를 포함하고 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 추상 클래스를 확장하는 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="9be1c-111">Define a class that contains a data store and extends the abstract <xref:System.ServiceModel.Discovery.DiscoveryProxy> class.</span></span>  
  
-   <span data-ttu-id="9be1c-112">`AsyncResult` 도우미 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="9be1c-112">Implement the helper `AsyncResult` class.</span></span>  
  
-   <span data-ttu-id="9be1c-113">검색 프록시 호스팅</span><span class="sxs-lookup"><span data-stu-id="9be1c-113">Host the Discovery Proxy.</span></span>  
  
### <a name="to-create-a-new-console-application-project"></a><span data-ttu-id="9be1c-114">새 콘솔 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-114">To create a new console application project</span></span>  
  
1.  <span data-ttu-id="9be1c-115">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-115">Start [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="9be1c-116">콘솔 응용 프로그램 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-116">Create a new console application project.</span></span> <span data-ttu-id="9be1c-117">프로젝트 이름을 `DiscoveryProxy`로 지정하고 솔루션 이름을 `DiscoveryProxyExample`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-117">Name the project `DiscoveryProxy` and the name the solution `DiscoveryProxyExample`.</span></span>  
  
3.  <span data-ttu-id="9be1c-118">프로젝트에 대한 다음 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-118">Add the following references to the project</span></span>  
  
    1.  <span data-ttu-id="9be1c-119">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="9be1c-119">System.ServiceModel.dll</span></span>  
  
    2.  <span data-ttu-id="9be1c-120">System.Servicemodel.Discovery.dll</span><span class="sxs-lookup"><span data-stu-id="9be1c-120">System.Servicemodel.Discovery.dll</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="9be1c-121">이러한 어셈블리는 4.0 이상 버전이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-121">Ensure that you reference version 4.0 or greater of these assemblies.</span></span>  
  
### <a name="to-implement-the-proxydiscoveryservice-class"></a><span data-ttu-id="9be1c-122">ProxyDiscoveryService 클래스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-122">To implement the ProxyDiscoveryService class</span></span>  
  
1.  <span data-ttu-id="9be1c-123">프로젝트에 새 코드 파일을 추가하고 이름을 DiscoveryProxy.cs로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-123">Add a new code file to your project and name it DiscoveryProxy.cs.</span></span>  
  
2.  <span data-ttu-id="9be1c-124">DiscoveryProxy.cs에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-124">Add the following `using` statements to DiscoveryProxy.cs.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using System.Xml;  
    ```  
  
3.  <span data-ttu-id="9be1c-125">`DiscoveryProxyService`에서 <xref:System.ServiceModel.Discovery.DiscoveryProxy>를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-125">Derive the `DiscoveryProxyService` from <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="9be1c-126">다음 예제와 같이 이 클래스에 `ServiceBehavior` 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-126">Apply the `ServiceBehavior` attribute to the class as shown in the following example.</span></span>  
  
    ```  
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]  
    public class DiscoveryProxyService : DiscoveryProxy  
    {  
    }  
    ```  
  
4.  <span data-ttu-id="9be1c-127">`DiscoveryProxy` 클래스 내에서 등록된 서비스를 저장할 사전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-127">Inside the `DiscoveryProxy` class define a dictionary to hold the registered services.</span></span>  
  
    ```  
    // Repository to store EndpointDiscoveryMetadata.   
    Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;  
    ```  
  
5.  <span data-ttu-id="9be1c-128">사전을 초기화하는 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-128">Define a constructor that initializes the dictionary.</span></span>  
  
    ```  
    public DiscoveryProxyService()  
            {  
                this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();  
            }  
    ```  
  
### <a name="to-define-the-methods-used-to-update-the-discovery-proxy-cache"></a><span data-ttu-id="9be1c-129">검색 프록시 캐시를 업데이트하는 데 사용되는 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-129">To define the methods used to update the discovery proxy cache</span></span>  
  
1.  <span data-ttu-id="9be1c-130">`AddOnlineservice` 메서드를 구현하여 캐시에 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-130">Implement the `AddOnlineservice` method to add services to the cache.</span></span> <span data-ttu-id="9be1c-131">이 메서드는 프록시가 알림 메시지를 받을 때마다 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-131">This is called every time the proxy receives an announcement message.</span></span>  
  
    ```  
    void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)  
            {  
                lock (this.onlineServices)  
                {  
                    this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;                  
                }  
  
                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");  
            }  
    ```  
  
2.  <span data-ttu-id="9be1c-132">캐시에서 서비스를 제거하는 데 사용되는 `RemoveOnlineService` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-132">Implement the `RemoveOnlineService` method that is used to remove services from the cache.</span></span>  
  
    ```  
    void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)  
            {  
                if (endpointDiscoveryMetadata != null)  
                {  
                    lock (this.onlineServices)  
                    {  
                        this.onlineServices.Remove(endpointDiscoveryMetadata.Address);                      
                    }  
  
                    PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");  
                }      
            }  
    ```  
  
3.  <span data-ttu-id="9be1c-133">서비스와 사전의 서비스를 일치시킬 `MatchFromOnlineService` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-133">Implement the `MatchFromOnlineService` methods that attempt to match a service with a service in the dictionary.</span></span>  
  
    ```  
    void MatchFromOnlineService(FindRequestContext findRequestContext)  
            {  
                lock (this.onlineServices)  
                {  
                    foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)  
                    {  
                        if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))  
                        {  
                            findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);  
                        }  
                    }  
                }  
            }  
    ```  
  
    ```  
    EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)  
            {  
                EndpointDiscoveryMetadata matchingEndpoint = null;  
                lock (this.onlineServices)  
                {  
                    foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)  
                    {  
                        if (criteria.Address == endpointDiscoveryMetadata.Address)  
                        {  
                            matchingEndpoint = endpointDiscoveryMetadata;  
                        }  
                    }  
                }  
                return matchingEndpoint;  
            }  
    ```  
  
4.  <span data-ttu-id="9be1c-134">검색 프록시가 수행하는 작업을 콘솔에 텍스트로 출력하는 `PrintDiscoveryMetadata` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-134">Implement the `PrintDiscoveryMetadata` method that provides the user with console text output of what the discovery proxy is doing.</span></span>  
  
    ```  
    void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)  
            {  
                Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");  
                foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)  
                {  
                    Console.WriteLine("** " + contractName.ToString());  
                    break;  
                }  
                Console.WriteLine("**** Operation Completed");  
            }  
    ```  
  
5.  <span data-ttu-id="9be1c-135">DiscoveryProxyService에 다음 AsyncResult 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-135">Add the following AsyncResult classes to the DiscoveryProxyService.</span></span> <span data-ttu-id="9be1c-136">이러한 클래스는 다양한 비동기 작업 결과를 구별하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-136">These classes are used to differentiate between the different asynchronous operation results.</span></span>  
  
    ```  
    sealed class OnOnlineAnnouncementAsyncResult : AsyncResult  
            {  
                public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)  
                    : base(callback, state)  
                {  
                    this.Complete(true);  
                }  
  
                public static void End(IAsyncResult result)  
                {  
                    AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);  
                }  
            }  
  
            sealed class OnOfflineAnnouncementAsyncResult : AsyncResult  
            {  
                public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)  
                    : base(callback, state)  
                {  
                    this.Complete(true);  
                }  
  
                public static void End(IAsyncResult result)  
                {  
                    AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);  
                }  
            }  
  
            sealed class OnFindAsyncResult : AsyncResult  
            {  
                public OnFindAsyncResult(AsyncCallback callback, object state)  
                    : base(callback, state)  
                {  
                    this.Complete(true);  
                }  
  
                public static void End(IAsyncResult result)  
                {  
                    AsyncResult.End<OnFindAsyncResult>(result);  
                }  
            }  
  
            sealed class OnResolveAsyncResult : AsyncResult  
            {  
                EndpointDiscoveryMetadata matchingEndpoint;  
  
                public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)  
                    : base(callback, state)  
                {  
                    this.matchingEndpoint = matchingEndpoint;  
                    this.Complete(true);  
                }  
  
                public static EndpointDiscoveryMetadata End(IAsyncResult result)  
                {  
                    OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);  
                    return thisPtr.matchingEndpoint;  
                }  
            }  
    ```  
  
### <a name="to-define-the-methods-that-implement-the-discovery-proxy-functionality"></a><span data-ttu-id="9be1c-137">검색 프록시 기능을 구현하는 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-137">To define the methods that implement the discovery proxy functionality</span></span>  
  
1.  <span data-ttu-id="9be1c-138"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-138">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-139">이 메서드는 검색 프록시가 온라인 알림 메시지를 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-139">This method is called when the discovery proxy receives an online announcement message.</span></span>  
  
    ```  
    // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy  
            protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)  
            {          
                this.AddOnlineService(endpointDiscoveryMetadata);  
                return new OnOnlineAnnouncementAsyncResult(callback, state);  
            }  
    ```  
  
2.  <span data-ttu-id="9be1c-140"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-140">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-141">이 메서드는 검색 프록시가 알림 메시지 처리를 완료할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-141">This method is called when the discovery proxy finishes processing an announcement message.</span></span>  
  
    ```  
    protected override void OnEndOnlineAnnouncement(IAsyncResult result)  
            {  
                OnOnlineAnnouncementAsyncResult.End(result);  
            }  
    ```  
  
3.  <span data-ttu-id="9be1c-142"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-142">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-143">이 메서드는 검색 프록시가 오프라인 알림 메시지를 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-143">This method is called with the discovery proxy receives an offline announcement message.</span></span>  
  
    ```  
    // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy  
            protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)  
            {  
                this.RemoveOnlineService(endpointDiscoveryMetadata);  
                return new OnOfflineAnnouncementAsyncResult(callback, state);  
            }  
    ```  
  
4.  <span data-ttu-id="9be1c-144"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-144">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-145">이 메서드는 검색 프록시가 오프라인 알림 메시지 처리를 완료할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-145">This method is called when the discovery proxy finishes processing an offline announcement message.</span></span>  
  
    ```  
    protected override void OnEndOfflineAnnouncement(IAsyncResult result)  
            {  
                OnOfflineAnnouncementAsyncResult.End(result);  
            }  
    ```  
  
5.  <span data-ttu-id="9be1c-146"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-146">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-147">이 메서드는 검색 프록시가 찾기 요청을 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-147">This method is called when the discovery proxy receives a find request.</span></span>  
  
    ```  
    // OnBeginFind method is called when a Probe request message is received by the Proxy  
            protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)  
            {  
                this.MatchFromOnlineService(findRequestContext);  
                return new OnFindAsyncResult(callback, state);  
            }  
    protected override IAsyncResult OnBeginFind(FindRequest findRequest, AsyncCallback callback, object state)  
    {  
        Collection<EndpointDiscoveryMetadata> matchingEndpoints = MatchFromCache(findRequest.Criteria);  
        return new OnFindAsyncResult(  
                    matchingEndpoints,  
                    callback,  
                    state);  
    }  
    ```  
  
6.  <span data-ttu-id="9be1c-148"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-148">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-149">이 메서드는 검색 프록시가 찾기 요청 처리를 완료할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-149">This method is called when the discovery proxy finishes processing a find request.</span></span>  
  
    ```  
    protected override void OnEndFind(IAsyncResult result)  
            {  
                OnFindAsyncResult.End(result);  
            }  
    ```  
  
7.  <span data-ttu-id="9be1c-150"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-150">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-151">이 메서드는 검색 프록시가 확인 메시지를 받을 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-151">This method is called when the discovery proxy receives a resolve message.</span></span>  
  
    ```  
    // OnBeginFind method is called when a Resolve request message is received by the Proxy  
            protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)  
            {  
                return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);  
            }  
    protected override IAsyncResult OnBeginResolve(ResolveRequest resolveRequest, AsyncCallback callback, object state)  
    {  
        return new OnResolveAsyncResult(  
            this.proxy.MatchFromOnlineService(resolveRequest.Criteria),  
            callback,  
            state);  
    }  
    ```  
  
8.  <span data-ttu-id="9be1c-152"><xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-152">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9be1c-153">이 메서드는 검색 프록시가 확인 메시지 처리를 완료할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-153">This method is called when the discovery proxy finishes processing a resolve message.</span></span>  
  
    ```  
    protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)  
    {  
        return OnResolveAsyncResult.End(result);  
    }  
    ```  
  
 <span data-ttu-id="9be1c-154">OnBegin..</span><span class="sxs-lookup"><span data-stu-id="9be1c-154">The OnBegin..</span></span> <span data-ttu-id="9be1c-155">/ OnEnd..</span><span class="sxs-lookup"><span data-stu-id="9be1c-155">/ OnEnd..</span></span> <span data-ttu-id="9be1c-156">메서드는 후속 검색 작업에 대한 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-156">methods provide the logic for the subsequent discovery operations.</span></span> <span data-ttu-id="9be1c-157">예를 들어 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> 및 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> 메서드는 검색 프록시에 대한 찾기 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-157">For example the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> and <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> methods implement the find logic for discovery proxy.</span></span> <span data-ttu-id="9be1c-158">검색 프록시가 프로브 메시지를 받으면 클라이언트에 응답을 보내기 위해 이러한 메서드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-158">When the discovery proxy receives a probe message these methods are executed to send a response back to the client.</span></span> <span data-ttu-id="9be1c-159">찾기 논리는 원하는 대로 수정할 수 있습니다. 예를 들어 찾기 작업의 일부로 알고리즘 또는 응용 프로그램별 XML 메타데이터 구문 분석을 통해 사용자 지정 범위 일치를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-159">You may modify the find logic as you wish, for example you can incorporate custom scope matching by algorithms or application specific XML metadata parsing as part of your find operation.</span></span>  
  
### <a name="to-implement-the-asyncresult-class"></a><span data-ttu-id="9be1c-160">AsyncResult 클래스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-160">To implement the AsyncResult class</span></span>  
  
1.  <span data-ttu-id="9be1c-161">다양한 비동기 결과 클래스를 파생시키는 데 사용되는 추상 기본 클래스 AsyncResult를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-161">Define the abstract base class AsyncResult which is used to derive the various async result classes.</span></span>  
  
2.  <span data-ttu-id="9be1c-162">AsyncResult.cs라는 새 코드 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-162">Create a new code file called AsyncResult.cs.</span></span>  
  
3.  <span data-ttu-id="9be1c-163">AsyncResult.cs에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-163">Add the following `using` statements to AsyncResult.cs.</span></span>  
  
    ```  
    using System;  
    using System.Threading;  
    ```  
  
4.  <span data-ttu-id="9be1c-164">다음 AsyncResult 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-164">Add the following AsyncResult class.</span></span>  
  
    ```  
    abstract class AsyncResult : IAsyncResult  
        {  
            AsyncCallback callback;  
            bool completedSynchronously;  
            bool endCalled;  
            Exception exception;  
            bool isCompleted;  
            ManualResetEvent manualResetEvent;  
            object state;  
            object thisLock;  
  
            protected AsyncResult(AsyncCallback callback, object state)  
            {  
                this.callback = callback;  
                this.state = state;  
                this.thisLock = new object();  
            }  
  
            public object AsyncState  
            {  
                get  
                {  
                    return state;  
                }  
            }  
  
            public WaitHandle AsyncWaitHandle  
            {  
                get  
                {  
                    if (manualResetEvent != null)  
                    {  
                        return manualResetEvent;  
                    }  
                    lock (ThisLock)  
                    {  
                        if (manualResetEvent == null)  
                        {  
                            manualResetEvent = new ManualResetEvent(isCompleted);  
                        }  
                    }  
                    return manualResetEvent;  
                }  
            }  
  
            public bool CompletedSynchronously  
            {  
                get  
                {  
                    return completedSynchronously;  
                }  
            }  
  
            public bool IsCompleted  
            {  
                get  
                {  
                    return isCompleted;  
                }  
            }  
  
            object ThisLock  
            {  
                get  
                {  
                    return this.thisLock;  
                }  
            }  
  
            protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)  
                where TAsyncResult : AsyncResult  
            {  
                if (result == null)  
                {  
                    throw new ArgumentNullException("result");  
                }  
  
                TAsyncResult asyncResult = result as TAsyncResult;  
  
                if (asyncResult == null)  
                {  
                    throw new ArgumentException("Invalid async result.", "result");  
                }  
  
                if (asyncResult.endCalled)  
                {  
                    throw new InvalidOperationException("Async object already ended.");  
                }  
  
                asyncResult.endCalled = true;  
  
                if (!asyncResult.isCompleted)  
                {  
                    asyncResult.AsyncWaitHandle.WaitOne();  
                }  
  
                if (asyncResult.manualResetEvent != null)  
                {  
                    asyncResult.manualResetEvent.Close();  
                }  
  
                if (asyncResult.exception != null)  
                {  
                    throw asyncResult.exception;  
                }  
  
                return asyncResult;  
            }  
  
            protected void Complete(bool completedSynchronously)  
            {  
                if (isCompleted)  
                {  
                    throw new InvalidOperationException("This async result is already completed.");  
                }  
  
                this.completedSynchronously = completedSynchronously;  
  
                if (completedSynchronously)  
                {  
                    this.isCompleted = true;  
                }  
                else  
                {  
                    lock (ThisLock)  
                    {  
                        this.isCompleted = true;  
                        if (this.manualResetEvent != null)  
                        {  
                            this.manualResetEvent.Set();  
                        }  
                    }  
                }  
  
                if (callback != null)  
                {  
                    callback(this);  
                }  
            }  
  
            protected void Complete(bool completedSynchronously, Exception exception)  
            {  
                this.exception = exception;  
                Complete(completedSynchronously);  
            }  
        }  
    ```  
  
### <a name="to-host-the-discoveryproxy"></a><span data-ttu-id="9be1c-165">DiscoveryProxy를 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="9be1c-165">To host the DiscoveryProxy</span></span>  
  
1.  <span data-ttu-id="9be1c-166">DiscoveryProxyExample 프로젝트에서 Program.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-166">Open the Program.cs file in the DiscoveryProxyExample project.</span></span>  
  
2.  <span data-ttu-id="9be1c-167">다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-167">Add the following `using` statements.</span></span>  
  
    ```  
    using System;  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    ```  
  
3.  <span data-ttu-id="9be1c-168">`Main()` 메서드 안에서 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-168">Within the `Main()` method, add the following code.</span></span> <span data-ttu-id="9be1c-169">그러면 `DiscoveryProxy` 클래스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-169">This creates an instance of the `DiscoveryProxy` class.</span></span>  
  
    ```  
    Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");  
                Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");  
  
                // Host the DiscoveryProxy service  
                ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());  
    ```  
  
4.  <span data-ttu-id="9be1c-170">다음 코드를 추가하여 검색 끝점 및 알림 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-170">Next add the following code to add a discovery endpoint and an announcement endpoint.</span></span>  
  
    ```  
    try  
              {                  
                  // Add DiscoveryEndpoint to receive Probe and Resolve messages  
                  DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));  
                  discoveryEndpoint.IsSystemEndpoint = false;  
  
                  // Add AnnouncementEndpoint to receive Hello and Bye announcement messages  
                  AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));                  
  
                  proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);  
                  proxyServiceHost.AddServiceEndpoint(announcementEndpoint);  
  
                  proxyServiceHost.Open();  
  
                  Console.WriteLine("Proxy Service started.");  
                  Console.WriteLine();  
                  Console.WriteLine("Press <ENTER> to terminate the service.");  
                  Console.WriteLine();  
                  Console.ReadLine();  
  
                  proxyServiceHost.Close();  
              }  
              catch (CommunicationException e)  
              {  
                  Console.WriteLine(e.Message);  
              }  
              catch (TimeoutException e)  
              {  
                  Console.WriteLine(e.Message);  
              }     
  
              if (proxyServiceHost.State != CommunicationState.Closed)  
              {  
                  Console.WriteLine("Aborting the service...");  
                  proxyServiceHost.Abort();  
              }  
    ```  
  
 <span data-ttu-id="9be1c-171">검색 프록시의 구현을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-171">You have completed implementing the discovery proxy.</span></span> <span data-ttu-id="9be1c-172">계속 진행 하 [하는 방법: 검색 프록시에 등록 하는 검색 가능한 서비스 구현](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-172">Continue on to [How to: Implement a Discoverable Service that Registers with the Discovery Proxy](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9be1c-173">예제</span><span class="sxs-lookup"><span data-stu-id="9be1c-173">Example</span></span>  
 <span data-ttu-id="9be1c-174">다음은 이 항목에서 사용되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-174">This is the full listing of the code used in this topic.</span></span>  
  
```  
// DiscoveryProxy.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using System.Xml;  
  
namespace Microsoft.Samples.Discovery  
{  
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]  
    public class DiscoveryProxyService : DiscoveryProxy  
    {  
        // Repository to store EndpointDiscoveryMetadata. A database or a flat file could also be used instead.  
        Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;  
  
        public DiscoveryProxyService()  
        {  
            this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();  
        }  
  
        // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy  
        protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)  
        {          
            this.AddOnlineService(endpointDiscoveryMetadata);  
            return new OnOnlineAnnouncementAsyncResult(callback, state);  
        }  
  
        protected override void OnEndOnlineAnnouncement(IAsyncResult result)  
        {  
            OnOnlineAnnouncementAsyncResult.End(result);  
        }  
  
        // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy  
        protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)  
        {  
            this.RemoveOnlineService(endpointDiscoveryMetadata);  
            return new OnOfflineAnnouncementAsyncResult(callback, state);  
        }  
  
        protected override void OnEndOfflineAnnouncement(IAsyncResult result)  
        {  
            OnOfflineAnnouncementAsyncResult.End(result);  
        }  
  
        // OnBeginFind method is called when a Probe request message is received by the Proxy  
        protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)  
        {  
            this.MatchFromOnlineService(findRequestContext);  
            return new OnFindAsyncResult(callback, state);  
        }  
  
        protected override void OnEndFind(IAsyncResult result)  
        {  
            OnFindAsyncResult.End(result);  
        }  
  
        // OnBeginFind method is called when a Resolve request message is received by the Proxy  
        protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)  
        {  
            return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);  
        }  
  
        protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)  
        {  
            return OnResolveAsyncResult.End(result);  
        }  
  
        // The following are helper methods required by the Proxy implementation  
        void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)  
        {  
            lock (this.onlineServices)  
            {  
                this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;                  
            }  
  
            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");  
        }  
  
        void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)  
        {  
            if (endpointDiscoveryMetadata != null)  
            {  
                lock (this.onlineServices)  
                {  
                    this.onlineServices.Remove(endpointDiscoveryMetadata.Address);                      
                }  
  
                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");  
            }      
        }  
  
        void MatchFromOnlineService(FindRequestContext findRequestContext)  
        {  
            lock (this.onlineServices)  
            {  
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)  
                {  
                    if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))  
                    {  
                        findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);  
                    }  
                }  
            }  
        }  
  
        EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)  
        {  
            EndpointDiscoveryMetadata matchingEndpoint = null;  
            lock (this.onlineServices)  
            {  
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)  
                {  
                    if (criteria.Address == endpointDiscoveryMetadata.Address)  
                    {  
                        matchingEndpoint = endpointDiscoveryMetadata;  
                    }  
                }  
            }  
            return matchingEndpoint;  
        }  
  
        void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)  
        {  
            Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");  
            foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)  
            {  
                Console.WriteLine("** " + contractName.ToString());  
                break;  
            }  
            Console.WriteLine("**** Operation Completed");  
        }  
  
        sealed class OnOnlineAnnouncementAsyncResult : AsyncResult  
        {  
            public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)  
                : base(callback, state)  
            {  
                this.Complete(true);  
            }  
  
            public static void End(IAsyncResult result)  
            {  
                AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);  
            }  
        }  
  
        sealed class OnOfflineAnnouncementAsyncResult : AsyncResult  
        {  
            public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)  
                : base(callback, state)  
            {  
                this.Complete(true);  
            }  
  
            public static void End(IAsyncResult result)  
            {  
                AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);  
            }  
        }  
  
        sealed class OnFindAsyncResult : AsyncResult  
        {  
            public OnFindAsyncResult(AsyncCallback callback, object state)  
                : base(callback, state)  
            {  
                this.Complete(true);  
            }  
  
            public static void End(IAsyncResult result)  
            {  
                AsyncResult.End<OnFindAsyncResult>(result);  
            }  
        }  
  
        sealed class OnResolveAsyncResult : AsyncResult  
        {  
            EndpointDiscoveryMetadata matchingEndpoint;  
  
            public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)  
                : base(callback, state)  
            {  
                this.matchingEndpoint = matchingEndpoint;  
                this.Complete(true);  
            }  
  
            public static EndpointDiscoveryMetadata End(IAsyncResult result)  
            {  
                OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);  
                return thisPtr.matchingEndpoint;  
            }  
        }  
    }  
}  
```  
  
```  
// AsyncResult.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Threading;  
  
namespace Microsoft.Samples.Discovery  
{  
    abstract class AsyncResult : IAsyncResult  
    {  
        AsyncCallback callback;  
        bool completedSynchronously;  
        bool endCalled;  
        Exception exception;  
        bool isCompleted;  
        ManualResetEvent manualResetEvent;  
        object state;  
        object thisLock;  
  
        protected AsyncResult(AsyncCallback callback, object state)  
        {  
            this.callback = callback;  
            this.state = state;  
            this.thisLock = new object();  
        }  
  
        public object AsyncState  
        {  
            get  
            {  
                return state;  
            }  
        }  
  
        public WaitHandle AsyncWaitHandle  
        {  
            get  
            {  
                if (manualResetEvent != null)  
                {  
                    return manualResetEvent;  
                }  
                lock (ThisLock)  
                {  
                    if (manualResetEvent == null)  
                    {  
                        manualResetEvent = new ManualResetEvent(isCompleted);  
                    }  
                }  
                return manualResetEvent;  
            }  
        }  
  
        public bool CompletedSynchronously  
        {  
            get  
            {  
                return completedSynchronously;  
            }  
        }  
  
        public bool IsCompleted  
        {  
            get  
            {  
                return isCompleted;  
            }  
        }  
  
        object ThisLock  
        {  
            get  
            {  
                return this.thisLock;  
            }  
        }  
  
        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)  
            where TAsyncResult : AsyncResult  
        {  
            if (result == null)  
            {  
                throw new ArgumentNullException("result");  
            }  
  
            TAsyncResult asyncResult = result as TAsyncResult;  
  
            if (asyncResult == null)  
            {  
                throw new ArgumentException("Invalid async result.", "result");  
            }  
  
            if (asyncResult.endCalled)  
            {  
                throw new InvalidOperationException("Async object already ended.");  
            }  
  
            asyncResult.endCalled = true;  
  
            if (!asyncResult.isCompleted)  
            {  
                asyncResult.AsyncWaitHandle.WaitOne();  
            }  
  
            if (asyncResult.manualResetEvent != null)  
            {  
                asyncResult.manualResetEvent.Close();  
            }  
  
            if (asyncResult.exception != null)  
            {  
                throw asyncResult.exception;  
            }  
  
            return asyncResult;  
        }  
  
        protected void Complete(bool completedSynchronously)  
        {  
            if (isCompleted)  
            {  
                throw new InvalidOperationException("This async result is already completed.");  
            }  
  
            this.completedSynchronously = completedSynchronously;  
  
            if (completedSynchronously)  
            {  
                this.isCompleted = true;  
            }  
            else  
            {  
                lock (ThisLock)  
                {  
                    this.isCompleted = true;  
                    if (this.manualResetEvent != null)  
                    {  
                        this.manualResetEvent.Set();  
                    }  
                }  
            }  
  
            if (callback != null)  
            {  
                callback(this);  
            }  
        }  
  
        protected void Complete(bool completedSynchronously, Exception exception)  
        {  
            this.exception = exception;  
            Complete(completedSynchronously);  
        }  
    }  
}  
```  
  
```  
// program.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.Samples.Discovery  
{  
    class Program  
    {  
        public static void Main()  
        {  
            Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");  
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");  
  
            // Host the DiscoveryProxy service  
            ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());  
  
            try  
            {                  
                // Add DiscoveryEndpoint to receive Probe and Resolve messages  
                DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));  
                discoveryEndpoint.IsSystemEndpoint = false;  
  
                // Add AnnouncementEndpoint to receive Hello and Bye announcement messages  
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));                  
  
                proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);  
                proxyServiceHost.AddServiceEndpoint(announcementEndpoint);  
  
                proxyServiceHost.Open();  
  
                Console.WriteLine("Proxy Service started.");  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to terminate the service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                proxyServiceHost.Close();  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
            }  
            catch (TimeoutException e)  
            {  
                Console.WriteLine(e.Message);  
            }     
  
            if (proxyServiceHost.State != CommunicationState.Closed)  
            {  
                Console.WriteLine("Aborting the service...");  
                proxyServiceHost.Abort();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9be1c-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9be1c-175">See Also</span></span>  
 [<span data-ttu-id="9be1c-176">WCF Discovery 개요</span><span class="sxs-lookup"><span data-stu-id="9be1c-176">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="9be1c-177">방법: 검색 프록시에 등록 하는 검색 가능한 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-177">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="9be1c-178">방법: 검색 프록시를 사용 하 여 서비스를 검색 하는 클라이언트 응용 프로그램을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be1c-178">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 [<span data-ttu-id="9be1c-179">방법: 검색 프록시 테스트</span><span class="sxs-lookup"><span data-stu-id="9be1c-179">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)
