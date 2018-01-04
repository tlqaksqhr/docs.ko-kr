---
title: "Net.TCP Port Sharing 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dea3a0f0d69662021c78b0f1d57ad0ba8c11fcb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="nettcp-port-sharing-sample"></a><span data-ttu-id="abe3b-102">Net.TCP Port Sharing 샘플</span><span class="sxs-lookup"><span data-stu-id="abe3b-102">Net.TCP Port Sharing Sample</span></span>
<span data-ttu-id="abe3b-103">TCP/IP 프로토콜은 포트라는 16비트 숫자를 사용하여 동일한 컴퓨터에서 실행되는 여러 네트워크 응용 프로그램에 대한 연결을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-103">The TCP/IP protocol uses a 16-bit number, called a port, to differentiate connections to multiple network applications running on the same machine.</span></span> <span data-ttu-id="abe3b-104">응용 프로그램이 포트에서 수신 대기 중이면 이 포트의 모든 TCP 트래픽이 해당 응용 프로그램으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-104">If an application is listening on a port, then all TCP traffic for that port goes to that application.</span></span> <span data-ttu-id="abe3b-105">다른 응용 프로그램이 동시에 이 포트에서 수신 대기할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-105">Other applications cannot listen on that port at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="abe3b-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="abe3b-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="abe3b-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="abe3b-108">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="abe3b-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="abe3b-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 <span data-ttu-id="abe3b-110">대부분의 프로토콜은 표준 또는 기본 포트 번호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-110">Many protocols have a standard or default port number that they use.</span></span> <span data-ttu-id="abe3b-111">예를 들어 HTTP 프로토콜은 보통 TCP 포트 80을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-111">For example, the HTTP protocol typically uses TCP port 80.</span></span> <span data-ttu-id="abe3b-112">IIS(인터넷 정보 서비스)에는 여러 HTTP 응용 프로그램 간에 포트를 공유하는 수신기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-112">Internet Information Services (IIS) has a listener to share a port between multiple HTTP applications.</span></span> <span data-ttu-id="abe3b-113">IIS는 직접 포트에서 수신 대기하고 메시지 스트림에 있는 정보에 따라 적절한 응용 프로그램으로 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-113">IIS listens on the port directly and forwards messages to the appropriate application based on information inside the message stream.</span></span> <span data-ttu-id="abe3b-114">이렇게 하면 여러 HTTP 응용 프로그램이 메시지 수신 포트를 확보하기 위해 경쟁하지 않고 같은 포트 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-114">This allows multiple HTTP applications to use the same port number without having to compete to reserve the port for receiving messages.</span></span>  
  
 <span data-ttu-id="abe3b-115">NetTcp 포트 공유는 한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]이와 비슷하게 여러 네트워크 응용 프로그램이 하나의 포트를 공유할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-115">NetTcp Port Sharing is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]feature that similarly allows multiple network applications to share a single port.</span></span> <span data-ttu-id="abe3b-116">NetTcp 포트 공유 서비스는 net.tcp 프로토콜을 사용하여 연결을 받은 다음 대상 주소를 기준으로 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-116">The NetTcp Port Sharing Service accepts connections using the net.tcp protocol and forwards messages based on their destination address.</span></span>  
  
 <span data-ttu-id="abe3b-117">NetTcp 포트 공유 서비스는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-117">The NetTcp Port Sharing Service is not enabled by default.</span></span> <span data-ttu-id="abe3b-118">이 샘플을 실행하기 전에 수동으로 이 서비스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-118">Before running this sample, you must manually enable the service.</span></span> <span data-ttu-id="abe3b-119">자세한 내용은 참조 [하는 방법: Net.TCP Port Sharing Service를 사용 하도록 설정](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-119">For more information, see [How to: Enable the Net.TCP Port Sharing Service](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span></span> <span data-ttu-id="abe3b-120">서비스를 사용하지 않으면 서버 응용 프로그램이 시작될 때 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-120">If the service is disabled, an exception is thrown when the server application is started.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 <span data-ttu-id="abe3b-121">포트 공유는 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 바인딩 또는 <xref:System.ServiceModel.NetTcpBinding> 바인딩 요소의 <xref:System.ServiceModel.Channels.TcpTransportBindingElement> 속성을 설정하여 서버에서 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-121">Port sharing is enabled on the server by setting the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property of the <xref:System.ServiceModel.NetTcpBinding> binding or the <xref:System.ServiceModel.Channels.TcpTransportBindingElement> binding element.</span></span> <span data-ttu-id="abe3b-122">클라이언트는 서버에서 포트 공유를 사용하도록 구성된 방식에 대해 몰라도 관계 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-122">The client does not have to know how port sharing has been configured to use it on the server.</span></span>  
  
## <a name="enabling-port-sharing"></a><span data-ttu-id="abe3b-123">포트 공유 사용</span><span class="sxs-lookup"><span data-stu-id="abe3b-123">Enabling Port Sharing</span></span>  
 <span data-ttu-id="abe3b-124">다음 코드에서는 서버에서 포트 공유를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-124">The following code demonstrates enabling port sharing on the server.</span></span> <span data-ttu-id="abe3b-125">여기서는 임의의 URI 경로가 있는 고정 포트에서 `ICalculator` 서비스의 인스턴스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-125">It starts an instance of the `ICalculator` service on a fixed port with a random URI path.</span></span> <span data-ttu-id="abe3b-126">두 서비스에서 같은 포트를 공유할 수 있더라도, NetTcp 포트 공유 서비스에서 올바른 응용 프로그램에 메시지를 라우트할 수 있도록 전체 끝점 주소가 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-126">Even though two services can share the same port, their overall endpoint addresses still must be unique so that the NetTcp Port Sharing Service can route messages to the correct application.</span></span>  
  
```  
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address =  
   String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```  
  
 <span data-ttu-id="abe3b-127">포트 공유가 사용되면 포트 번호 충돌 없이 서비스를 여러 번 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-127">With port sharing enabled, you can run the service multiple times without having a conflict over the port number.</span></span> <span data-ttu-id="abe3b-128">코드를 변경하여 포트 공유를 사용하지 않는 경우 서비스의 두 복사본을 시작하면 두 번째 복사본에서 <xref:System.ServiceModel.AddressAlreadyInUseException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-128">If you change the code to disable port sharing, starting up two copies of the service results in the second failing with an <xref:System.ServiceModel.AddressAlreadyInUseException>.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="abe3b-129">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="abe3b-129">Running the Sample</span></span>  
 <span data-ttu-id="abe3b-130">테스트 클라이언트를 사용하여 메시지가 포트를 공유하는 서비스로 올바르게 라우트되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-130">You can use the test client to check that messages are correctly routed to services sharing the port.</span></span>  
  
```  
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```  
  
 <span data-ttu-id="abe3b-131">서비스의 각 인스턴스에서는 고유한 번호와 주소를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-131">Each instance of the service prints out its unique number and address.</span></span> <span data-ttu-id="abe3b-132">예를 들어, service.exe를 실행했을 때 다음 텍스트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-132">For instance, you may see the following text when you run service.exe.</span></span>  
  
```  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="abe3b-133">client.exe를 실행할 때 여기에 표시된 서비스 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-133">Enter the service number you see here when you run client.exe.</span></span>  
  
```  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="abe3b-134">클라이언트가 사용하는 생성된 주소를 변경하면 다중 컴퓨터 구성에서도 이 샘플을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-134">This sample can be run in a cross-machine configuration by changing the generated address that the client uses.</span></span> <span data-ttu-id="abe3b-135">Client.cs에서 끝점 주소 형식 문자열을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-135">In the Client.cs, change the endpoint address format string to match the new address of your service.</span></span> <span data-ttu-id="abe3b-136">"localhost"에 대한 모든 참조를 서버 컴퓨터의 IP 주소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-136">Replace any references to "localhost" with the IP address of the server machine.</span></span> <span data-ttu-id="abe3b-137">이렇게 변경한 후 샘플을 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-137">You must recompile the sample after making this change.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="abe3b-138">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="abe3b-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="abe3b-139">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-139">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="abe3b-140">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-140">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="abe3b-141">소개 단원에서 설명한 것처럼 NetTcp 포트 공유 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-141">Enable the NetTcp Port Sharing Service as previously described in the introduction section.</span></span>  
  
4.  <span data-ttu-id="abe3b-142">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="abe3b-143">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abe3b-143">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="abe3b-144">이 샘플의 실행에 대한 자세한 내용은 앞의 샘플 실행 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="abe3b-144">Specific details for running this sample are included previously in the Running the Sample section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe3b-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abe3b-145">See Also</span></span>
