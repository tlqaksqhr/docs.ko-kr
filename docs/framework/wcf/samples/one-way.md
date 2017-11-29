---
title: "단방향"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 05dbd465345f3b0cd9506f581f1a779f834c50fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="one-way"></a><span data-ttu-id="89984-102">단방향</span><span class="sxs-lookup"><span data-stu-id="89984-102">One-Way</span></span>
<span data-ttu-id="89984-103">이 샘플에서는 단방향 서비스 작업이 있는 서비스 계약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89984-103">This sample demonstrates a service contact with one-way service operations.</span></span> <span data-ttu-id="89984-104">클라이언트는 양방향 서비스 작업에서처럼 서비스 작업이 완료될 때까지 대기하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-104">The client does not wait for service operations to complete as is the case with two-way service operations.</span></span> <span data-ttu-id="89984-105">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 사용 하 여는 `wsHttpBinding` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="89984-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and uses the `wsHttpBinding` binding.</span></span> <span data-ttu-id="89984-106">이 샘플의 서비스는 자체적으로 호스팅되는 콘솔 응용 프로그램으로서 이를 통해 요청을 수신하고 처리하는 서비스를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-106">The service in this sample is a self-hosted console application to enable you to observe the service that receives and processes requests.</span></span> <span data-ttu-id="89984-107">클라이언트 역시 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="89984-107">The client is also a console application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89984-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="89984-109">단방향 서비스 계약을 만들려면 다음 샘플 코드에서와 같이 서비스 계약을 정의하고, <xref:System.ServiceModel.OperationContractAttribute> 클래스를 각 작업에 적용하여, <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-109">To create a one-way service contract, define your service contract, apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, and set <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> to `true` as shown in the following sample code:</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="89984-110">클라이언트가 서비스 작업이 완료될 때까지 기다리지 않음을 보여 주기 위해 이 샘플의 서비스 코드는 다음 샘플 코드에서와 같이 5초 지연을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-110">To demonstrate that the client does not wait for the service operations to complete, the service code in this sample implements a five-second delay, as shown in the following sample code:</span></span>  
  
```  
/ This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="89984-111">클라이언트가 서비스를 호출할 때 서비스 작업 완료까지 기다리지 않고 호출이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-111">When the client calls the service, the call returns without waiting for the service operation to complete.</span></span>  
  
 <span data-ttu-id="89984-112">샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-112">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="89984-113">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-113">You can see the service receive messages from the client.</span></span> <span data-ttu-id="89984-114">서비스와 클라이언트를 모두 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="89984-114">Press ENTER in each console window to shut down both the service and the client.</span></span>  
  
 <span data-ttu-id="89984-115">클라이언트가 서비스보다 먼저 종료하므로 단방향 서비스 작업이 완료될 때까지 클라이언트가 기다리지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89984-115">The client finishes ahead of the service, demonstrating that a client does not wait for one-way service operations to complete.</span></span> <span data-ttu-id="89984-116">클라이언트 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-116">The client output is as follows:</span></span>  
  
```  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="89984-117">서비스 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-117">The following service output is shown:</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
>  <span data-ttu-id="89984-118">정의에 따라 HTTP는 요청/응답 프로토콜입니다. 요청이 수행되면 응답이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-118">HTTP is, by definition, a request/response protocol; when a request is made, a response is returned.</span></span> <span data-ttu-id="89984-119">이는 HTTP를 통해 노출되는 단방향 서비스 작업에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-119">This is true even for a one-way service operation that is exposed over HTTP.</span></span> <span data-ttu-id="89984-120">작업이 호출되면 서비스 작업이 실행되기 전에 서비스가 202라는 HTTP 상태 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-120">When the operation is called, the service returns an HTTP status code of 202 before the service operation has executed.</span></span> <span data-ttu-id="89984-121">이 상태 코드는 요청의 처리가 수락되었으나 아직 처리가 완료되지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-121">This status code means that the request has been accepted for processing, but the processing has not yet been completed.</span></span> <span data-ttu-id="89984-122">작업을 호출한 클라이언트는 서비스로부터 202 응답을 받을 때까지 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-122">The client that called the operation blocks until it receives the 202 response from the service.</span></span> <span data-ttu-id="89984-123">이로 인해 세션을 사용하도록 구성된 바인딩을 통해 여러 개의 단방향 메시지가 보내질 경우 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-123">This can cause some unexpected behavior when multiple one-way messages are sent using a binding that is configured to use sessions.</span></span> <span data-ttu-id="89984-124">이 샘플에 사용된 `wsHttpBinding` 바인딩은 기본적으로 세션을 사용하여 보안 컨텍스트를 설정하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-124">The `wsHttpBinding` binding used in this sample is configured to use sessions by default to establish a security context.</span></span> <span data-ttu-id="89984-125">기본적으로 세션의 메시지는 보내진 순서대로 도착하는 것이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89984-125">By default, messages in a session are guaranteed to arrive in the order in which they are sent.</span></span> <span data-ttu-id="89984-126">그 때문에 세션에서 두 번째 메시지가 보내지면 첫 번째 메시지가 처리될 때까지 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-126">Because of this, when the second message in a session is sent, it is not processed until the first message has been processed.</span></span> <span data-ttu-id="89984-127">그 결과 클라이언트는 어떤 메시지에 대해 이전의 메시지 처리가 완료될 때까지 202 응답을 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-127">The result of this is that the client does not receive the 202 response for a message until the processing of the previous message has been completed.</span></span> <span data-ttu-id="89984-128">따라서 클라이언트는 후속 작업 호출 각각을 차단하는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="89984-128">The client therefore appears to block on each subsequent operation call.</span></span> <span data-ttu-id="89984-129">이 동작을 방지하기 위해 이 샘플에서는 각기 다른 인스턴스에 동시에 메시지를 디스패치하여 처리하도록 런타임을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-129">To avoid this behavior, this sample configures the runtime to dispatch messages concurrently to distinct instances for processing.</span></span> <span data-ttu-id="89984-130">이 샘플은 각 메시지를 다른 인스턴스에서 처리하도록 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>를 `PerCall`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-130">The sample sets <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> to `PerCall` so that each message can be processed by a different instance.</span></span> <span data-ttu-id="89984-131">한 번에 한 스레드가 메시지를 디스패치하도록 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>를 `Multiple`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to `Multiple` to allow more than one thread to dispatch messages at a time.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="89984-132">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="89984-132">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="89984-133">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="89984-134">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="89984-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="89984-135">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89984-136">클라이언트를 실행하기 전에 서비스를 실행하고, 서비스를 종료하기 전에 클라이언트를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="89984-136">Run the service before you run the client and shut down the client before shutting down the service.</span></span> <span data-ttu-id="89984-137">그러면 서비스가 종료했기 때문에 클라이언트가 보안 세션을 완전히 닫을 수 없을 때 클라이언트 예외가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-137">This avoids a client exception when the client cannot close the security session cleanly because the service is gone.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89984-138">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="89984-139">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="89984-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="89984-140">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="89984-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="89984-141">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89984-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
  
## <a name="see-also"></a><span data-ttu-id="89984-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89984-142">See Also</span></span>
