---
title: "계층적 구성 모델"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf8e7b37b6430be1eed9bc037bfa06aeb825b866
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="c196e-102">계층적 구성 모델</span><span class="sxs-lookup"><span data-stu-id="c196e-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="c196e-103">이 샘플에서는 서비스의 구성 파일 계층 구조를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="c196e-104">또한 계층 구조의 상위 수준에서 바인딩, 서비스 동작 및 끝점 동작이 상속되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="c196e-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c196e-105">Sample details</span></span>  
 <span data-ttu-id="c196e-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]용으로 개발된 기능 중 하나는 향상된 계층적 구성 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-106">One of the features developed for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="c196e-107">계층적 구성 모델의 예로는 Machine.config -> Rootweb.config -> Web.config로 정의되는 구성 모델이 있습니다. [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]에서는 명시적으로 구성할 필요 없이 구성 계층 구조의 상위 수준에 정의된 바인딩 및 동작이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="c196e-108">이 샘플에서는 컴퓨터 또는 응용 프로그램 수준에 정의된 구성 요소를 사용하여 서비스 구성을 단순화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="c196e-109">이 샘플은 계층 구조의 세 수준에 정의된 9개의 서비스로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="c196e-110">`Service1`은 루트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-110">`Service1` is at the root.</span></span> <span data-ttu-id="c196e-111">`Service2` 및 `Service3`는 `Service1`에서 기본 요소를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="c196e-112">`Service4`, `Service5`, `Service6` 및 `Service7`은 계층 구조의 세 번째 수준에 정의되어 있으며 `Service3`에서 기본 요소를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="c196e-113">마지막으로 `Service10` 및 `Service11`은 계층 구조의 네 번째 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="c196e-114">모든 서비스는 `IDesc` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="c196e-115">다음은 이 인터페이스에 노출되는 메서드를 보여 주는 `IDesc` 인터페이스의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="c196e-116">`IDesc` 인터페이스는 Service1.cs에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 <span data-ttu-id="c196e-117">서비스에서 이러한 메서드를 구현하는 과정은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="c196e-118">`ListEndpoints`는 모든 서비스 끝점을 반복하고 서비스에 있는 모든 끝점의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="c196e-119">`ListServiceBehaviors`는 서비스에 추가된 모든 동작을 반복하고 서비스와 관련된 모든 서비스 동작의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="c196e-120">`ListEndpointBehaviors`는 끝점 동작의 목록을 반환한다는 점을 제외하고는 `ListServiceBehaviors`와 유사한 방식으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="c196e-121">이 구현을 통해 클라이언트는 서비스에서 노출하는 끝점 수와 서비스에 추가된 서비스 동작 및 끝점 동작을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="c196e-122">샘플의 일부로 구현된 클라이언트에서는 솔루션의 모든 서비스에 대한 서비스 참조를 추가하고 각 서비스에 대한 이러한 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="c196e-123">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c196e-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="c196e-124">클라이언트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c196e-124">To run the client</span></span>  
  
1.  <span data-ttu-id="c196e-125">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ConfigHierarchicalModel.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="c196e-126">클라이언트 프로젝트가 아직 시작 프로젝트로 설정되지 않은 경우 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="c196e-127">**솔루션 탐색기**를 솔루션을 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="c196e-128">**공용 속성**선택, **시작 프로젝트**, 클릭 하 고 **개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="c196e-129">**개의 시작 프로젝트** 드롭다운 목록에서 선택 **클라이언트**합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="c196e-130">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="c196e-131">Ctrl+Shift+B를 눌러 샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="c196e-132">Ctrl+F5를 눌러 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c196e-133">이러한 단계가 제대로 수행되지 않으면 다음 단계를 따라 사용 환경이 올바르게 설정되었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c196e-133">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="c196e-134">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="c196e-135">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="c196e-136">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c196e-137">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c196e-138">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c196e-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c196e-139">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c196e-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c196e-140">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c196e-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="c196e-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c196e-141">See Also</span></span>  
 [<span data-ttu-id="c196e-142">AppFabric 관리 샘플</span><span class="sxs-lookup"><span data-stu-id="c196e-142">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)
