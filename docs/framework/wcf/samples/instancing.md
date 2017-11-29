---
title: "인스턴스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
caps.latest.revision: "40"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b38d70a4f4c3938d6cc6116c94a009ec0f34dc0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="instancing"></a><span data-ttu-id="82e70-102">인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="82e70-102">Instancing</span></span>
<span data-ttu-id="82e70-103">Instancing 샘플에서는 클라이언트 요청에 응답하여 서비스 클래스의 인스턴스가 만들어지는 방법을 제어하는 인스턴스 만들기 동작 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-103">The Instancing sample demonstrates the instancing behavior setting, which controls how instances of a service class are created in response to client requests.</span></span> <span data-ttu-id="82e70-104">샘플 기반는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 구현 하는 `ICalculator` 서비스 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="82e70-105">이 샘플은 `ICalculatorInstance`에서 상속되는 새 계약 `ICalculator`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-105">This sample defines a new contract, `ICalculatorInstance`, which inherits from `ICalculator`.</span></span> <span data-ttu-id="82e70-106">`ICalculatorInstance`에 의해 지정된 계약은 서비스 인스턴스의 상태를 검사하기 위한 세 개의 추가 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-106">The contract specified by `ICalculatorInstance` provides three additional operations for inspecting the state of the service instance.</span></span> <span data-ttu-id="82e70-107">인스턴스 만들기 설정을 변경하여 클라이언트를 실행하면 동작의 변화를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-107">By altering the instancing setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="82e70-108">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82e70-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="82e70-110">사용할 수 있는 인스턴스 만들기 모드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-110">The following instancing modes are available:</span></span>  
  
-   <span data-ttu-id="82e70-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: 새 서비스 인스턴스가 각 클라이언트 요청에 대해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: A new service instance is created for each client request.</span></span>  
  
-   <span data-ttu-id="82e70-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: 새 인스턴스가 각각의 새 클라이언트 세션에 대해 만들어지고 해당 세션의 수명이 유지 관리됩니다. 이를 수행하려면 세션을 지원하는 바인딩이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: A new instance is created for each new client session, and maintained for the lifetime of that session (requires a binding that supports session).</span></span>  
  
-   <span data-ttu-id="82e70-113"><xref:System.ServiceModel.InstanceContextMode.Single>: 서비스 클래스의 단일 인스턴스가 응용 프로그램의 수명에 대한 모든 클라이언트 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-113"><xref:System.ServiceModel.InstanceContextMode.Single>: A single instance of the service class handles all client requests for the lifetime of the application.</span></span>  
  
 <span data-ttu-id="82e70-114">다음 코드 샘플과 같이 서비스 클래스는 `[ServiceBehavior(InstanceContextMode=<setting>)]` 특성을 사용하여 인스턴스 만들기 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-114">The service class specifies instancing behavior with the `[ServiceBehavior(InstanceContextMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="82e70-115">주석 처리되는 줄을 변경하여 각 인스턴스 모드의 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-115">By changing which lines are commented out, you can observe the behavior of each of the instance modes.</span></span> <span data-ttu-id="82e70-116">인스턴스 만들기 모드를 변경한 후 서비스를 다시 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-116">Remember to rebuild the service after changing the instancing mode.</span></span> <span data-ttu-id="82e70-117">클라이언트에서 인스턴스 만들기와 관련하여 지정해야 할 설정은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-117">There are no instancing-related settings to specify on the client.</span></span>  
  
```  
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed   
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="82e70-118">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="82e70-119">실행 중인 서비스가 해당하는 인스턴스 모드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-119">The instance mode the service is running under is displayed.</span></span> <span data-ttu-id="82e70-120">인스턴스 만들기 모드의 동작을 반영하기 위해 각 작업 후에 인스턴스 ID와 작업 카운트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-120">After each operation, the instance ID and operation count are displayed to reflect the behavior of the instancing mode.</span></span> <span data-ttu-id="82e70-121">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-121">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82e70-122">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="82e70-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="82e70-123">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="82e70-124">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="82e70-125">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82e70-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82e70-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="82e70-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82e70-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="82e70-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82e70-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82e70-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
  
## <a name="see-also"></a><span data-ttu-id="82e70-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82e70-130">See Also</span></span>
