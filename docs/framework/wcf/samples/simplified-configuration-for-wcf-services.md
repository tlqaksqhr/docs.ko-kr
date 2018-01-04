---
title: "WCF 서비스를 위한 단순화된 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02611dc44b98c1b8b5ef5ae74559f9f370483792
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="5e5cb-102">WCF 서비스를 위한 단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="5e5cb-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="5e5cb-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 일반적인 서비스 및 클라이언트를 구현하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-103">This sample demonstrates how to implement and configure a typical service and client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="5e5cb-104">이 샘플은 다른 모든 기본 기술 샘플의 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="5e5cb-105">서비스와 통신하기 위한 끝점을 노출하는 이 서비스에서는 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]의 단순화된 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="5e5cb-106">[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 이전 버전에서 끝점은 일반적으로 구성 파일(Web.config)에서 다음 예제 구성 코드와 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="5e5cb-107">[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]에서는 `<service>`가 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="5e5cb-108">서비스에서 끝점을 정의하지 않을 경우 각 기본 주소의 끝점과 구현된 계약이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="5e5cb-109">기본 주소가 계약 이름에 추가되어 끝점이 결정되고 바인딩은 주소 스키마에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="5e5cb-110">다음 코드 예제에서는 단순화된 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="5e5cb-111">구성된 대로 동일한 컴퓨터의 클라이언트는 http://localhost/servicemodelsamples/service.svc에서 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-111">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="5e5cb-112">원격 컴퓨터의 클라이언트가 서비스에 액세스하려면 localhost 대신 정규화된 도메인 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="5e5cb-113">기본적으로 서비스에서는 메타데이터를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="5e5cb-114">따라서 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="5e5cb-115">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5e5cb-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="5e5cb-116">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="5e5cb-117">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="5e5cb-118">다음 단계에 따라 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="5e5cb-119">마우스 오른쪽 단추로 클릭는 **서비스** 프로젝트를 마우스 선택 **시작 프로젝트로 설정**, 키를 누릅니다 **Ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="5e5cb-120">서비스가 실행 중이라는 콘솔 출력이 나타날 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="5e5cb-121">마우스 오른쪽 단추로 클릭는 **클라이언트** 프로젝트를 마우스 선택 **시작 프로젝트로 설정**, 키를 누릅니다 **Ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e5cb-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5e5cb-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5e5cb-124">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e5cb-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cb-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="5e5cb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e5cb-126">See Also</span></span>  
 [<span data-ttu-id="5e5cb-127">AppFabric 관리 샘플</span><span class="sxs-lookup"><span data-stu-id="5e5cb-127">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)  
 [<span data-ttu-id="5e5cb-128">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="5e5cb-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
