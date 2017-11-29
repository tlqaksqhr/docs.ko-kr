---
title: "세션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e36666b72d14bbe257cd6ced8a35c360659a91dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="session"></a><span data-ttu-id="0252f-102">세션</span><span class="sxs-lookup"><span data-stu-id="0252f-102">Session</span></span>
<span data-ttu-id="0252f-103">Session 샘플에서는 세션이 필요한 계약을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="0252f-104">세션에서는 여러 작업을 수행하기 위한 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="0252f-105">그러면 서비스에서 상태를 특정 세션에 연결하여 이후의 작업에서 이전 작업의 상태를 사용할 수 있게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="0252f-106">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="0252f-107">`ICalculator` 계약은 실행 결과를 유지하면서 일련의 산술 작업을 수행할 수 있도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="0252f-108">이 기능은 `ICalculatorSession` 계약에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="0252f-109">서비스에서는 계산 수행을 위해 여러 서비스 작업이 호출되는 동안 클라이언트의 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="0252f-110">클라이언트에서는 `Result()`를 호출하여 현재 결과를 검색하고 `Clear()`를 호출하여 결과를 0으로 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="0252f-111">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0252f-112">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0252f-113">계약의 <xref:System.ServiceModel.SessionMode>를 `Required`로 설정하면 특정 바인딩을 통해 계약이 노출된 경우에 바인딩에서 세션이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="0252f-114">바인딩에서 세션을 지원하지 않으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="0252f-115">`ICalculatorSession` 인터페이스는 다음 샘플 코드에 표시된 것과 같이 실행 결과를 수정하는 하나 이상의 작업을 호출할 수 있도록 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="0252f-116">서비스에서는 <xref:System.ServiceModel.InstanceContextMode>의 <xref:System.ServiceModel.InstanceContextMode.PerSession>를 사용하여 특정 서비스 인스턴스 컨텍스트를 들어오는 각 세션에 바인드합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="0252f-117">그러면 서비스에서 각 세션의 결과를 로컬 멤버 변수에서 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 <span data-ttu-id="0252f-118">샘플을 실행하면 클라이언트에서 서버에 대한 몇 개의 요청을 수행하고 결과를 요청하며, 그러면 결과가 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="0252f-119">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0252f-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0252f-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0252f-121">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0252f-122">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="0252f-123">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0252f-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0252f-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0252f-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0252f-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="0252f-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0252f-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0252f-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## <a name="see-also"></a><span data-ttu-id="0252f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0252f-128">See Also</span></span>
