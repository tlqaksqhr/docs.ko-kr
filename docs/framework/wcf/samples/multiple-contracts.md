---
title: "다중 계약"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfd9446edc176e3d4cb014db578990971128707c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="multiple-contracts"></a><span data-ttu-id="3fa51-102">다중 계약</span><span class="sxs-lookup"><span data-stu-id="3fa51-102">Multiple Contracts</span></span>
<span data-ttu-id="3fa51-103">Multiple Contracts 샘플에서는 서비스에서 두 개 이상의 계약을 구현하는 방법과 구현된 각 계약과의 통신을 위해 끝점을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-103">The Multiple Contracts sample demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span> <span data-ttu-id="3fa51-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="3fa51-105">서비스는 `ICalculator` 계약과 `ICalculatorSession` 계약의 두 가지 계약을 정의하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-105">The service has been modified to define two contracts, the `ICalculator` contract and the `ICalculatorSession` contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa51-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3fa51-107">서비스 클래스에서는 `ICalculator` 및 `ICalculatorSession` 계약을 모두 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-107">The service class implements both the `ICalculator` and `ICalculatorSession` contracts.</span></span> <span data-ttu-id="3fa51-108">계약 중 하나에 세션이 필요하기 때문에, 서비스에서는 <xref:System.ServiceModel.InstanceContextMode.PerSession> 인스턴스 모드를 사용하여 세션 수명이 지속되는 동안 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-108">Because one of the contracts requires a session, the service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the state over the lifetime of the session.</span></span>  
  
 <span data-ttu-id="3fa51-109">각 계약을 노출하는 두 개의 끝점을 정의하도록 서비스 구성이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-109">The service configuration has been modified to define two endpoints to expose each contract.</span></span> <span data-ttu-id="3fa51-110">`ICalculator` 끝점은 `basicHttpBinding`을 사용하여 기본 주소에서 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-110">The `ICalculator` endpoint is exposed at the base address using a `basicHttpBinding`.</span></span> <span data-ttu-id="3fa51-111">`ICalculatorSession` 끝점은 다음 샘플 구성에 표시된 것과 같이 `wsHttpBinding` 특성이 `bindingConfiguration`으로 설정된 `BindingWithSession`을 사용하여 baseaddress/세션에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-111">The `ICalculatorSession` endpoint is exposed at the baseaddress/session using a `wsHttpBinding` with the `bindingConfiguration` attribute set to `BindingWithSession`, as shown in the following sample configuration.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="3fa51-112">생성된 클라이언트 코드에는 이제 원래 `ICalculator` 계약과 새 `ICalculatorSession` 계약 모두의 클라이언트 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-112">The generated client code now includes a client class for both the original `ICalculator` contract and the new `ICalculatorSession` contract.</span></span> <span data-ttu-id="3fa51-113">클라이언트 구성 및 코드는 적절한 서비스 끝점에서 각 계약과 통신하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-113">The client configuration and code have been modified to communicate with each contract at the appropriate service endpoint.</span></span>  
  
 <span data-ttu-id="3fa51-114">클라이언트는 콘솔 창 응용 프로그램(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-114">The client is a console windows application (.exe).</span></span> <span data-ttu-id="3fa51-115">서비스는 인터넷 정보 서비스(IIS)에 의해 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-115">The service is hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="3fa51-116">클라이언트 콘솔 창은 각 끝점에 전송되는 작업을 표시하며, 먼저 기본 끝점을 표시하고 그 뒤에 보안 끝점을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-116">The client console window displays the operations sent to each of the endpoints, first the basic endpoint, followed by the secure endpoint.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3fa51-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3fa51-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3fa51-118">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3fa51-119">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3fa51-120">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-120">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fa51-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3fa51-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa51-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3fa51-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa51-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3fa51-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa51-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
  
## <a name="see-also"></a><span data-ttu-id="3fa51-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fa51-125">See Also</span></span>
