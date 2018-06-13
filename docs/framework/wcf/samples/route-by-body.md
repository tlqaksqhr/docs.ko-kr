---
title: 본문에 의한 경로
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: e9a0c947a1dd7ac2a6c7af74baaa072aae67358c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33504236"
---
# <a name="route-by-body"></a><span data-ttu-id="b7763-102">본문에 의한 경로</span><span class="sxs-lookup"><span data-stu-id="b7763-102">Route by Body</span></span>
<span data-ttu-id="b7763-103">이 샘플에서는 SOAP 작업이 있는 메시지 개체를 수락하는 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="b7763-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="b7763-105">서비스는 `Calculate` 요청 매개 변수를 받아 <xref:System.ServiceModel.Channels.Message> 응답을 반환하는 단일 <xref:System.ServiceModel.Channels.Message> 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="b7763-106">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7763-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b7763-108">이 샘플에서는 본문 콘텐츠에 기반한 메시지 디스패치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="b7763-109">기본 제공 Windows Communication Foundation (WCF) 서비스 모델 메시지 디스패치 메커니즘은 메시지 동작을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="b7763-110">반면 모든 작업을 Action=""으로 정의하는 기존 웹 서비스도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="b7763-111">동작 정보를 기준으로 계속 요청 메시지를 디스패치하는 WSDL을 기반으로 하여 서비스를 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="b7763-112">이 샘플에서는 WSDL을 기반으로 하는 서비스 계약을 보여 줍니다. WSDL은 샘플에 포함된 Service.wsdl에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="b7763-113">서비스 계약에 사용 된 것과 비슷한 계산기는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="b7763-114">하지만 `[OperationContract]`는 모든 작업에 대해 `Action=""`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="b7763-115">계약이 지정되면 서비스에서는 작업 사이에서 메시지를 디스패치할 수 있도록 사용자 지정 디스패치 동작 `DispatchByBodyBehavior`를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="b7763-116">이 디스패치 동작은 초기화는 `DispatchByBodyElementOperationSelector` 각 래퍼 요소의 QName에서 키가 지정 된 작업 이름 테이블이 포함 된 사용자 지정 작업 선택기입니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="b7763-117">`DispatchByBodyElementOperationSelector`는 본문의 첫 번째 자식에 대한 시작 태그를 살펴보고 이전에 설명한 테이블을 사용하여 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="b7763-118">클라이언트에서 사용 하 여 서비스에서 내보낸 WSDL에서 자동으로 생성 된 프록시 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="b7763-119">모든 작업의 동작이 비어 있어도 자동 생성된 프록시의 동작 매개 변수를 제외하고는 클라이언트 코드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="b7763-120">클라이언트 코드는 몇 가지 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-120">The client code performs several calculations.</span></span> <span data-ttu-id="b7763-121">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b7763-122">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b7763-123">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b7763-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b7763-124">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b7763-125">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b7763-126">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7763-127">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b7763-128">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b7763-128">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b7763-129">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="b7763-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b7763-130">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7763-130">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
## <a name="see-also"></a><span data-ttu-id="b7763-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7763-131">See Also</span></span>
