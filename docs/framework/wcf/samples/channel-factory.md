---
title: "채널 팩터리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f5fb22c329bf7b27c32f05a2d8e41734723f53b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="channel-factory"></a><span data-ttu-id="eaf3c-102">채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="eaf3c-102">Channel Factory</span></span>
<span data-ttu-id="eaf3c-103">이 샘플에서는 클라이언트 응용 프로그램에서 생성된 클라이언트 대신 <xref:System.ServiceModel.ChannelFactory> 클래스가 있는 채널을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="eaf3c-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaf3c-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="eaf3c-106">이 샘플에서는 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 서비스 끝점에 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="eaf3c-107">포함 된 클라이언트 형식의 생성 하는 서비스 끝점으로 채널을 만드는 일반적으로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 생성 된 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="eaf3c-108">이 샘플에서와 같이 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 채널을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="eaf3c-109">다음 샘플 코드에서 만들어진 서비스는 서비스에 동일는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-109">The service created by the following sample code is identical to the service in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="eaf3c-110">다중 컴퓨터 시나리오에서 이 샘플을 실행하는 경우에는 앞의 코드에서 "localhost"를 서비스를 실행하는 컴퓨터의 정규화된 이름으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="eaf3c-111">이 샘플에서는 구성을 사용하여 끝점 주소를 설정하지 않기 때문에 코드에서 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>  
  
 <span data-ttu-id="eaf3c-112">채널이 만들어지면 생성된 클라이언트의 경우와 마찬가지로 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
 <span data-ttu-id="eaf3c-113">채널을 닫으려면 먼저 <xref:System.ServiceModel.IClientChannel> 인터페이스로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="eaf3c-114">이는 생성된 채널이 `ICalculator` 및 `Add` 등의 메서드가 있지만 `Subtract`는 없는 `Close` 인터페이스를 사용하여 클라이언트 응용 프로그램에 선언되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="eaf3c-115">`Close` 메서드는 <xref:System.ServiceModel.ICommunicationObject> 인터페이스에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>  
  
```  
// Close the channel.  
 ((IClientChannel)client).Close();  
```  
  
 <span data-ttu-id="eaf3c-116">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="eaf3c-117">클라이언트 응용 프로그램을 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-117">Press ENTER in the client window to shut down the client application.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eaf3c-118">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="eaf3c-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="eaf3c-119">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="eaf3c-120">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="eaf3c-121">이 샘플에서는 메타데이터 게시를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="eaf3c-122">먼저 이 샘플의 메타데이터 게시를 사용하여 클라이언트 형식을 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>  
  
3.  <span data-ttu-id="eaf3c-123">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="eaf3c-124">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="eaf3c-124">To run the sample cross machine</span></span>  
  
1.  <span data-ttu-id="eaf3c-125">다음 코드에서 "localhost"를 서비스를 실행하는 컴퓨터의 정규화된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>  
  
    ```  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="eaf3c-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eaf3c-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eaf3c-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eaf3c-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf3c-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## <a name="see-also"></a><span data-ttu-id="eaf3c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaf3c-130">See Also</span></span>
