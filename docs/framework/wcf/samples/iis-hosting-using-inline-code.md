---
title: "인라인 코드를 사용한 IIS 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
caps.latest.revision: "40"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8207b2ec7c783630f9c4b87b4fbf754dfa96645
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="b73e0-102">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="b73e0-102">IIS Hosting Using Inline Code</span></span>
<span data-ttu-id="b73e0-103">이 샘플에서는 IIS(인터넷 정보 서비스)에서 호스팅하는 서비스를 구현하는 방법을 보여 줍니다. 여기서 서비스 코드는 .svc 파일에 인라인으로 포함되어 있으며 필요할 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="b73e0-104">또한 서비스 코드를 응용 프로그램의 \App_Code 디렉터리에 있는 소스 코드 파일에서 직접 구현하거나 \bin에 배포된 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="b73e0-105">이 샘플에서는 이러한 기술은 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-105">This sample does not demonstrate these techniques.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b73e0-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b73e0-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b73e0-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b73e0-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b73e0-109">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b73e0-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b73e0-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`  
  
 <span data-ttu-id="b73e0-111">이 샘플에서는 요청-회신 통신 패턴을 정의하는 계약을 구현하는 일반적인 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="b73e0-112">이 서비스는 IIS에서 호스팅되며 서비스 코드는 모두 Service.svc 파일에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="b73e0-113">서비스는 호스트에서 활성화되며 서비스로 전송된 첫 번째 메시지에 의해 필요할 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="b73e0-114">미리 컴파일할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="b73e0-115">서비스는 다음 코드에 정의된 대로 `ICalculator` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="b73e0-116">이 서비스 구현에서는 해당 결과를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-116">The service implementation calculates and returns the appropriate result.</span></span>  
  
```  
<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>   
…  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="b73e0-117">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b73e0-118">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b73e0-119">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b73e0-119">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b73e0-120">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b73e0-121">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b73e0-122">솔루션을 빌드한 후 setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="b73e0-123">이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-123">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="b73e0-124">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="b73e0-125">이 서비스를 호출할 수 있는 클라이언트 응용 프로그램을 만드는 방법에 대 한 예제를 보려면 [하는 방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73e0-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73e0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b73e0-126">See Also</span></span>  
 [<span data-ttu-id="b73e0-127">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="b73e0-127">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
