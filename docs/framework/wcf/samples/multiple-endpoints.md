---
title: 다중 끝점
ms.date: 03/30/2017
helpviewer_keywords:
- Multiple EndPoints
ms.assetid: 8f0c2e1f-9aee-41c2-8301-c72b7f664412
ms.openlocfilehash: 1658db83c809f875914036e9e10ac86cc6a821c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501972"
---
# <a name="multiple-endpoints"></a><span data-ttu-id="d6235-102">다중 끝점</span><span class="sxs-lookup"><span data-stu-id="d6235-102">Multiple Endpoints</span></span>
<span data-ttu-id="d6235-103">Multiple Endpoints 샘플은 서비스에서 여러 끝점을 구성하는 방법과 클라이언트에서 각 끝점과 통신하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-103">The Multiple Endpoints sample demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span> <span data-ttu-id="d6235-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="d6235-105">서비스 구성은 `ICalculator` 계약을 지원하지만 각각 다른 바인딩을 사용하여 다른 주소에 있는 두 개의 끝점을 정의하기 위해 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-105">The service configuration has been modified to define two endpoints that support the `ICalculator` contract, but each at a different address using a different binding.</span></span> <span data-ttu-id="d6235-106">클라이언트 구성과 코드는 두 서비스 끝점 모두와 통신하기 위해 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-106">The client configuration and code have been modified to communicate with both of the service endpoints.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6235-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d6235-108">서비스 Web.config 파일은 각각 동일한 `ICalculator` 계약을 지원하지만 다른 바인딩을 사용하여 다른 주소에 있는 두 개의 끝점을 정의하기 위해 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-108">The service Web.config file has been modified to define two endpoints, each supporting the same `ICalculator` contract, but at different addresses using different bindings.</span></span> <span data-ttu-id="d6235-109">첫 번째 끝점은 `basicHttpBinding` 바인딩을 사용하여 기본 주소에 정의되고 보안은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-109">The first endpoint is defined at the base address using a `basicHttpBinding` binding, which does not have security enabled.</span></span> <span data-ttu-id="d6235-110">두 번째 끝점은 `wsHttpBinding` 바인딩을 사용하여 {baseaddress}/secure에 정의되고 Windows 인증과 함께 WS-Security를 사용하여 기본적으로 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-110">The second endpoint is defined at {baseaddress}/secure using a `wsHttpBinding` binding, which is secure by default, using WS-Security with Windows authentication.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- This endpoint is exposed at the base address provided by host:  
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- secure endpoint exposed at {base address}/secure:  
       http://localhost/servicemodelsamples/service.svc/secure -->  
  <endpoint address="secure"  
            binding="wsHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="d6235-111">두 끝점은 또한 클라이언트에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-111">Both endpoints are also configured on the client.</span></span> <span data-ttu-id="d6235-112">이러한 끝점에 이름이 제공되므로 호출자는 원하는 끝점 이름을 클라이언트의 생성자에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-112">These endpoints are given names so that the caller can pass the desired endpoint name into the constructor of the client.</span></span>  
  
```xml  
<client>  
  <!-- Passing "basic" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="basic"  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="basicHttpBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- Passing "secure" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="secure"  
address="http://localhost/servicemodelsamples/service.svc/secure"   
            binding="wsHttpBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
```  
  
 <span data-ttu-id="d6235-113">다음 코드와 같이 클라이언트는 두 끝점을 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-113">The client uses both endpoints as shown in the following code.</span></span>  
  
```  
static void Main()  
{  
    // Create a client to the basic endpoint configuration.  
    CalculatorClient client = new CalculatorClient("basic");  
    Console.WriteLine("Communicate with basic endpoint.");  
    // call operations  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    // Create a client to the secure endpoint configuration.  
    client = new CalculatorClient("secure");  
    Console.WriteLine("Communicate with secure endpoint.");  
    // Call operations.  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="d6235-114">클라이언트를 실행하면 두 끝점과의 상호 작용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-114">When you run the client, interactions with both endpoints are displayed.</span></span>  
  
```  
Communicate with basic endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Communicate with secure endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d6235-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d6235-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d6235-116">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d6235-117">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d6235-118">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6235-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d6235-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d6235-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d6235-121">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="d6235-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d6235-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6235-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpoints`  
  
## <a name="see-also"></a><span data-ttu-id="d6235-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6235-123">See Also</span></span>
