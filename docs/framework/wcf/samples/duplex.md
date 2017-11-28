---
title: "이중"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Duplex Service Contract
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
caps.latest.revision: "40"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b0c5b5dc6bff78f06df75f4b5a9c5c3a8647dbf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="duplex"></a><span data-ttu-id="ff647-102">이중</span><span class="sxs-lookup"><span data-stu-id="ff647-102">Duplex</span></span>
<span data-ttu-id="ff647-103">Duplex 샘플은 이중 계약을 정의 및 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-103">The Duplex sample demonstrates how to define and implement a duplex contract.</span></span> <span data-ttu-id="ff647-104">이중 통신은 클라이언트가 서비스와의 세션을 설정할 때 이루어지며, 서비스가 클라이언트로 메시지를 다시 보낼 수 있는 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-104">Duplex communication occurs when a client establishes a session with a service and gives the service a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="ff647-105">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="ff647-106">이중 계약은 클라이언트에서 서비스로의 기본 인터페이스와 서비스에서 클라이언트의 콜백 인터페이스의 쌍으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-106">A duplex contract is defined as a pair of interfaces—a primary interface from the client to the service and a callback interface from the service to the client.</span></span> <span data-ttu-id="ff647-107">이 샘플에서 `ICalculatorDuplex` 인터페이스를 사용하여 클라이언트는 수학 연산을 수행하고 세션 도중 결과를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating the result over a session.</span></span> <span data-ttu-id="ff647-108">서비스는 `ICalculatorDuplexCallback` 인터페이스에서 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-108">The service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="ff647-109">클라이언트와 서비스 간에 전송되는 메시지 집합을 서로 연결하기 위해 컨텍스트를 설정해야 하므로 이중 계약에는 세션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff647-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ff647-111">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="ff647-112">이중 계약은 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-112">The duplex contract is defined as follows:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,  
                 CallbackContract=typeof(ICalculatorDuplexCallback))]  
public interface ICalculatorDuplex  
{  
    [OperationContract(IsOneWay = true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
}  
  
public interface ICalculatorDuplexCallback  
{  
    [OperationContract(IsOneWay = true)]  
    void Result(double result);  
    [OperationContract(IsOneWay = true)]  
    void Equation(string eqn);  
}  
```  
  
 <span data-ttu-id="ff647-113">`CalculatorService` 클래스는 기본 `ICalculatorDuplex` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="ff647-114">서비스는 <xref:System.ServiceModel.InstanceContextMode.PerSession> 인스턴스 모드를 사용하여 각 세션의 결과를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="ff647-115">`Callback`이라는 private 속성은 클라이언트에 대한 콜백 채널에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-115">A private property named `Callback` is used to access the callback channel to the client.</span></span> <span data-ttu-id="ff647-116">서비스는 콜백 인터페이스를 통해 클라이언트에 메시지를 다시 전송하기 위해 콜백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-116">The service uses the callback for sending messages back to the client through the callback interface.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorDuplex  
{  
    double result = 0.0D;  
    string equation;  
  
    public CalculatorService()  
    {  
        equation = result.ToString();  
    }  
  
    public void Clear()  
    {  
        Callback.Equation(equation + " = " + result.ToString());  
        equation = result.ToString();  
    }  
  
    public void AddTo(double n)  
    {  
        result += n;  
        equation += " + " + n.ToString();  
        Callback.Result(result);  
    }  
    ...  
    ICalculatorDuplexCallback Callback  
    {  
        get  
        {  
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ff647-117">클라이언트는 서비스에서 메시지를 수신하기 위해 이중 계약의 콜백 인터페이스를 구현하는 클래스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="ff647-118">이 샘플에서는 `CallbackHandler` 인터페이스를 구현하기 위해 `ICalculatorDuplexCallback` 클래스가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-118">In the sample, a `CallbackHandler` class is defined to implement the `ICalculatorDuplexCallback` interface.</span></span>  
  
```  
public class CallbackHandler : ICalculatorDuplexCallback  
{  
   public void Result(double result)  
   {  
      Console.WriteLine("Result({0})", result);  
   }  
  
   public void Equation(string equation)  
   {  
      Console.WriteLine("Equation({0}", equation);  
   }  
}  
```  
  
 <span data-ttu-id="ff647-119">이중 계약에 대해 생성된 프록시의 경우 생성 시 <xref:System.ServiceModel.InstanceContext>를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-119">The proxy that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> to be provided upon construction.</span></span> <span data-ttu-id="ff647-120">이 <xref:System.ServiceModel.InstanceContext>는 콜백 인터페이스를 구현하는 개체의 사이트로 사용되고 서비스에서 다시 전송된 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-120">This <xref:System.ServiceModel.InstanceContext> is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="ff647-121"><xref:System.ServiceModel.InstanceContext>는 `CallbackHandler` 클래스의 인스턴스를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-121">An <xref:System.ServiceModel.InstanceContext> is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="ff647-122">이 개체는 콜백 인터페이스를 통해 서비스에서 클라이언트로 전송된 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-122">This object handles messages sent from the service to the client on the callback interface.</span></span>  
  
```  
// Construct InstanceContext to handle messages on callback interface.  
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());  
  
// Create a client.  
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);  
  
Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");  
Console.WriteLine();  
  
// Call the AddTo service operation.  
double value = 100.00D;  
client.AddTo(value);  
  
// Call the SubtractFrom service operation.  
value = 50.00D;  
client.SubtractFrom(value);  
  
// Call the MultiplyBy service operation.  
value = 17.65D;  
client.MultiplyBy(value);  
  
// Call the DivideBy service operation.  
value = 2.00D;  
client.DivideBy(value);  
  
// Complete equation.  
client.Clear();  
  
Console.ReadLine();  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 <span data-ttu-id="ff647-123">세션 통신 및 이중 통신 모두를 지원하는 바인딩을 제공하도록 구성이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-123">The configuration has been modified to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="ff647-124">`wsDualHttpBinding`은 세션 통신을 지원하며 각 방향에 대해 하나씩, 이중 HTTP 연결을 제공하여 이중 통신을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-124">The `wsDualHttpBinding` supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span> <span data-ttu-id="ff647-125">서비스에서 유일한 구성 차이는 사용되는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-125">On the service, the only difference in configuration is the binding that is used.</span></span> <span data-ttu-id="ff647-126">클라이언트에서는 다음 샘플 구성과 같이 서버가 클라이언트에 연결하는 데 사용할 수 있는 주소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-126">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
  <endpoint name=""  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="wsDualHttpBinding"   
            bindingConfiguration="DuplexBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
</client>  
  
<bindings>  
  <!-- Configure a binding that support duplex communication. -->  
  <wsDualHttpBinding>  
    <binding name="DuplexBinding"   
             clientBaseAddress="http://localhost:8000/myClient/">  
    </binding>  
  </wsDualHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="ff647-127">샘플을 실행하면 서비스에서 전송된 콜백 인터페이스에서 클라이언트에 반환된 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-127">When you run the sample, you see the messages that are returned to the client on the callback interface that is sent from the service.</span></span> <span data-ttu-id="ff647-128">각 중간 결과가 표시된 다음 모든 작업이 완료되면 전체 수식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-128">Each intermediate result is displayed, followed by the entire equation upon the completion of all operations.</span></span> <span data-ttu-id="ff647-129">클라이언트를 종료하려면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-129">Press ENTER to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ff647-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ff647-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ff647-131">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ff647-132">지침에 따라 솔루션의 C#, c + + 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-132">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ff647-133">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff647-134">다중 컴퓨터 구성에서 클라이언트를 실행 하는 경우 대체 해야 모두에서 "localhost"는 `address` 특성에는 [끝점](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소 및 `clientBaseAddress` 특성에는 [ \< 바인딩 >](../../../../docs/framework/misc/binding.md) 의 요소는 [ \<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) 요소 다음에 표시 된 대로 적절 한 컴퓨터의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-134">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [endpoint](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element and the `clientBaseAddress` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown in the following:</span></span>  
  
    ```xml  
    <client>  
    <endpoint name = ""  
    address="http://service_machine_name/servicemodelsamples/service.svc"  
    ... />  
    </client>  
    ...  
    <wsDualHttpBinding>  
    <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">  
    </binding>  
    </wsDualHttpBinding>  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff647-135">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ff647-136">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ff647-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ff647-137">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ff647-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ff647-138">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff647-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`  
  
## <a name="see-also"></a><span data-ttu-id="ff647-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff647-139">See Also</span></span>
