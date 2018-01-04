---
title: "범위 샘플을 사용한 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa762df1dbfe92102f8cd719613099b23986ed0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="discovery-with-scopes-sample"></a><span data-ttu-id="d5d2e-102">범위 샘플을 사용한 검색</span><span class="sxs-lookup"><span data-stu-id="d5d2e-102">Discovery with Scopes Sample</span></span>
<span data-ttu-id="d5d2e-103">이 샘플에서는 범위를 사용하여 검색 가능한 끝점을 분류하는 방법과 <xref:System.ServiceModel.Discovery.DiscoveryClient>를 사용하여 끝점에 대한 비동기 검색을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-103">This sample shows how to use scopes to categorize discoverable endpoints as well how to use <xref:System.ServiceModel.Discovery.DiscoveryClient> to perform an asynchronous search for endpoints.</span></span> <span data-ttu-id="d5d2e-104">이 샘플의 서비스에서는 끝점 검색 동작을 추가하고 이를 사용하여 끝점에 범위를 추가하고 끝점의 검색 기능을 제어하여 각 끝점에 대한 검색을 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-104">On the service, this sample shows how to customize discovery for each endpoint by adding an endpoint discovery behavior and using it to add a scope to the endpoint as well as controlling the endpoint’s discoverability.</span></span> <span data-ttu-id="d5d2e-105">이 샘플의 클라이언트에서는 <xref:System.ServiceModel.Discovery.DiscoveryClient>를 만들고 <xref:System.ServiceModel.Discovery.FindCriteria>에 범위를 추가하는 방식으로 검색 매개 변수를 세부적으로 조정하여 범위를 포함하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-105">On the client, the sample goes over how clients can create a <xref:System.ServiceModel.Discovery.DiscoveryClient> and fine tune search parameters to include scopes by adding scopes to the <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span> <span data-ttu-id="d5d2e-106">이 샘플에서는 클라이언트가 종료 조건을 추가하여 응답을 제한하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-106">This sample also shows how clients can restrict responses by adding a termination criterion.</span></span>  
  
## <a name="service-features"></a><span data-ttu-id="d5d2e-107">Service Features</span><span class="sxs-lookup"><span data-stu-id="d5d2e-107">Service Features</span></span>  
 <span data-ttu-id="d5d2e-108">이 프로젝트에서는 <xref:System.ServiceModel.ServiceHost>에 추가되는 두 개의 서비스 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-108">This project shows two service endpoints being added to a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d5d2e-109">각 끝점에는 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>가 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-109">Each endpoint has a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> associated with it.</span></span> <span data-ttu-id="d5d2e-110">이 동작은 두 끝점 모두에 대한 URI 범위를 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-110">This behavior is used to add URI scopes for both endpoints.</span></span> <span data-ttu-id="d5d2e-111">범위는 클라이언트가 검색을 세부적으로 조정할 수 있도록 이러한 각 끝점을 구별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-111">Scopes are used to distinguish each of these endpoints so that the clients can fine tune the search.</span></span> <span data-ttu-id="d5d2e-112">두 번째 끝점의 경우 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> 속성을 `false`로 설정하여 검색 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-112">For the second endpoint, the discoverability can be disabled by setting the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> property to `false`.</span></span> <span data-ttu-id="d5d2e-113">이렇게 하면 이 끝점과 연결된 검색 메타데이터가 검색 메시지의 일부로 보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-113">This ensures that the discovery metadata associated with this endpoint is not sent as part of any discovery messages.</span></span>  
  
## <a name="client-features"></a><span data-ttu-id="d5d2e-114">Client Features</span><span class="sxs-lookup"><span data-stu-id="d5d2e-114">Client Features</span></span>  
 <span data-ttu-id="d5d2e-115">`FindCalculatorServiceAddress()` 메서드는 <xref:System.ServiceModel.Discovery.DiscoveryClient>를 사용하고 두 가지 제한으로 <xref:System.ServiceModel.Discovery.FindCriteria>를 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-115">The `FindCalculatorServiceAddress()` method shows how to use a <xref:System.ServiceModel.Discovery.DiscoveryClient> and pass in a <xref:System.ServiceModel.Discovery.FindCriteria> with two restrictions.</span></span> <span data-ttu-id="d5d2e-116">범위가 조건에 추가되고 <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> 속성은 1로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-116">A scope is added to the criteria and the <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> property is set to 1.</span></span> <span data-ttu-id="d5d2e-117">범위는 동일한 범위를 게시하는 서비스만으로 결과를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-117">The scope limits the results to only the services that publish the same scope.</span></span> <span data-ttu-id="d5d2e-118"><xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>를 1로 설정하면 <xref:System.ServiceModel.Discovery.DiscoveryClient>에서 기다리는 응답이 최대 1개의 끝점으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-118">Setting <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> to 1 limits the responses the <xref:System.ServiceModel.Discovery.DiscoveryClient> waits for to, at most, 1 endpoint.</span></span> <span data-ttu-id="d5d2e-119"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 호출은 제한 시간에 도달하거나 하나의 끝점이 발견될 때까지 스레드를 차단하는 동기 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-119">The <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> call is a synchronous operation that blocks the thread until a timeout is reached or one endpoint is found.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d5d2e-120">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="d5d2e-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="d5d2e-121">이 샘플에서는 HTTP 끝점을 사용하며 이 샘플을 실행하려면 적절한 URL ACL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="d5d2e-122">참조 [HTTP 및 HTTPS 구성](http://go.microsoft.com/fwlink/?LinkId=70353) 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-122">See [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="d5d2e-123">높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="d5d2e-124">명령이 지정한 대로 작동하지 않는 경우 `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%` 인수 대신 도메인과 사용자 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`</span></span>  
  
2.  <span data-ttu-id="d5d2e-125">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-125">Build the solution.</span></span>  
  
3.  <span data-ttu-id="d5d2e-126">빌드 디렉터리에서 서비스 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-126">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="d5d2e-127">클라이언트 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-127">Run the client executable.</span></span> <span data-ttu-id="d5d2e-128">클라이언트에서 서비스를 찾을 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-128">Note that the client is able to locate the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5d2e-129">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d5d2e-130">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5d2e-131">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5d2e-132">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d2e-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## <a name="see-also"></a><span data-ttu-id="d5d2e-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5d2e-133">See Also</span></span>
