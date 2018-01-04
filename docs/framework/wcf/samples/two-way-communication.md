---
title: "상호 통신"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ea6ea34e83f9c813062620c5029ea4b812cd777
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="two-way-communication"></a><span data-ttu-id="805d8-102">상호 통신</span><span class="sxs-lookup"><span data-stu-id="805d8-102">Two-Way Communication</span></span>
<span data-ttu-id="805d8-103">이 샘플에서는 MSMQ를 통해 트랜잭션된 대기 중인 양방향 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-103">This sample demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span> <span data-ttu-id="805d8-104">이 샘플에서는 `netMsmqBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-104">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="805d8-105">이 경우 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 서비스에서 대기 중인 메시지 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-105">In this case, the service is a self-hosted console application that allows you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="805d8-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="805d8-107">이 샘플에 따라는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-107">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="805d8-108">대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-108">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="805d8-109">클라이언트는 큐로 메시지를 보내고 서비스는 큐에서 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-109">The client sends messages to a queue, and the service receives messages from the queue.</span></span> <span data-ttu-id="805d8-110">따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="805d8-111">이 샘플에서는 큐를 사용하는 양방향 통신을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-111">This sample demonstrates 2-way communication using queues.</span></span> <span data-ttu-id="805d8-112">클라이언트는 트랜잭션의 범위 내에서 큐로 구매 주문을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-112">The client sends purchase orders to the queue from within the scope of a transaction.</span></span> <span data-ttu-id="805d8-113">서비스는 주문을 받고 처리한 다음 트랜잭션의 범위 내에 있는 큐에서 주문 상태로 클라이언트를 콜백합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-113">The service receives the orders, processes the order and then calls back the client with the status of the order from the queue within the scope of a transaction.</span></span> <span data-ttu-id="805d8-114">양방향 통신을 쉽게 수행하기 위해 클라이언트와 서비스는 둘 다 큐를 사용하여 구매 주문과 주문 상태를 큐에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-114">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>  
  
 <span data-ttu-id="805d8-115">서비스 계약 `IOrderProcessor`는 큐를 사용하는 데 적합한 단방향 서비스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-115">The service contract `IOrderProcessor` defines one-way service operations that suit the use of queuing.</span></span> <span data-ttu-id="805d8-116">서비스 작업에는 주문 상태를 보내는 데 사용되는 회신 끝점이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-116">The service operation includes the reply endpoint to use to send the order statuses to.</span></span> <span data-ttu-id="805d8-117">회신 끝점은 주문 상태를 클라이언트로 다시 보내는 큐의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-117">The reply endpoint is the URI of the queue to send the order status back to the client.</span></span> <span data-ttu-id="805d8-118">주문 처리 응용 프로그램에서 이 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-118">The order processing application implements this contract.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}  
```  
  
 <span data-ttu-id="805d8-119">주문 상태를 보낼 회신 계약은 클라이언트에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-119">The reply contract to send order status is specified by the client.</span></span> <span data-ttu-id="805d8-120">클라이언트는 주문 상태 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-120">The client implements the order status contract.</span></span> <span data-ttu-id="805d8-121">서비스는 생성된 이 계약의 프록시를 사용하여 주문 상태를 클라이언트로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-121">The service uses the generated proxy of this contract to send order status back to the client.</span></span>  
  
```  
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```  
  
 <span data-ttu-id="805d8-122">서비스 작업은 전송된 구매 주문을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-122">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="805d8-123"><xref:System.ServiceModel.OperationBehaviorAttribute>를 서비스 작업에 적용하여 큐에서 메시지를 받는 데 사용되는 트랜잭션에 자동 인리스트먼트를 지정하고 서비스 작업 완료 시 트랜잭션이 자동으로 완료되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-123">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in a transaction that is used to receive the message from the queue and automatic completion of transactions on completion of the service operation.</span></span> <span data-ttu-id="805d8-124">`Orders` 클래스는 주문 처리 기능을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-124">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="805d8-125">이 경우에는 구매 주문을 사전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-125">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="805d8-126">서비스 작업이 참여하는 트랜잭션은 `Orders` 클래스의 작업에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-126">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>  
  
 <span data-ttu-id="805d8-127">서비스 작업은 전송된 구매 주문을 처리할 뿐만 아니라 주문 상태에 대해 클라이언트에 다시 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-127">The service operation, in addition to processing the submitted purchase order, replies back to the client on the status of the order.</span></span>  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```  
  
 <span data-ttu-id="805d8-128">MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-128">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="805d8-129">서비스의 끝점은 구성 파일의 System.ServiceModel 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-129">The endpoint for the service is defined in the System.ServiceModel section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="805d8-130">MSMQ 큐 이름 및 끝점 주소는 약간 다른 주소 지정 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-130">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="805d8-131">MSMQ 큐 이름은 로컬 컴퓨터에 점(.)을 사용하고, 그 경로에는 백슬래시 구분 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-131">The MSMQ queue name uses a dot (.) for the local machine and backslash separators in its path.</span></span> <span data-ttu-id="805d8-132">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 끝점 주소에서는 net.msmq: 체계를 지정하고 로컬 컴퓨터에 "localhost"를 사용하며 경로에 슬래시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-132">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] endpoint address specifies a net.msmq: scheme, uses "localhost" for the local machine, and uses forward slashes in its path.</span></span> <span data-ttu-id="805d8-133">원격 컴퓨터에서 호스트되는 큐에서 읽으려면 "." 및 "localhost"를 원격 컴퓨터 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-133">To read from a queue that is hosted on the remote machine, replace the "." and "localhost" to the remote machine name.</span></span>  
  
 <span data-ttu-id="805d8-134">서비스는 자체 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-134">The service is self hosted.</span></span> <span data-ttu-id="805d8-135">MSMQ 전송을 사용하는 경우에는 사용되는 큐를 미리 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-135">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="805d8-136">수동으로 또는 코드를 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-136">This can be done manually or through code.</span></span> <span data-ttu-id="805d8-137">이 샘플에서 서비스는 큐가 있는지 확인하고 필요한 경우 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-137">In this sample, the service checks for the existence of the queue and creates it, if necessary.</span></span> <span data-ttu-id="805d8-138">큐 이름은 구성 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-138">The queue name is read from the configuration file.</span></span> <span data-ttu-id="805d8-139">기본 주소에서 사용 되는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에 대 한 프록시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-139">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderProcessorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="805d8-140">클라이언트에서 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-140">The client creates a transaction.</span></span> <span data-ttu-id="805d8-141">큐와의 통신은 트랜잭션 범위 내에서 발생하므로 트랜잭션 범위를 모든 메시지가 성공하거나 실패하는 가장 작은 단위로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-141">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span>  
  
```  
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```  
  
 <span data-ttu-id="805d8-142">클라이언트 코드는 서비스로부터 주문 상태를 수신하기 위해 `IOrderStatus` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-142">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="805d8-143">이 경우 주문 상태가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-143">In this case, it prints out the order status.</span></span>  
  
```  
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,   
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,   
                                                           status);  
    }  
}  
```  
  
 <span data-ttu-id="805d8-144">주문 상태 큐는 `Main` 메서드에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-144">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="805d8-145">다음 샘플 구성과 같이 클라이언트 구성에는 주문 상태 서비스를 호스트하는 주문 상태 서비스 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-145">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service   
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
              binding="netMsmqBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="805d8-146">샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-146">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="805d8-147">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-147">You can see the service receive messages from the client.</span></span> <span data-ttu-id="805d8-148">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="805d8-149">서비스에는 구매 주문 정보가 표시되어 주문 상태를 주문 상태 큐로 다시 보내고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-149">The service displays the purchase order information and indicates it is sending back the order status to the order status queue.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 <span data-ttu-id="805d8-150">클라이언트에는 서비스에서 보낸 주문 상태 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-150">The client displays the order status information sent by the service.</span></span>  
  
```  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="805d8-151">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="805d8-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="805d8-152">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="805d8-153">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-153">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="805d8-154">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="805d8-155">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-155">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint names in the client configuration to match the client code.</span></span>  
  
 <span data-ttu-id="805d8-156">기본적으로 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 전송 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-156">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="805d8-157">MSMQ 전송 보안에 대 한 두 가지 관련 속성은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> 및 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` 기본적으로 인증 모드 설정 `Windows` 보호 수준으로 설정 되 고 `Sign`합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-157">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="805d8-158">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 하며 MSMQ의 Active Directory 통합 옵션이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-158">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="805d8-159">이 기준에 맞지 않는 컴퓨터에서 이 샘플을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-159">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="805d8-160">작업 그룹에 속해 있거나 Active Directory 통합이 없는 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="805d8-160">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="805d8-161">컴퓨터가 도메인에 속해 있지 않거나 Active Directory 통합이 설치되어 있지 않은 경우에는 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-161">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"   
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2.  <span data-ttu-id="805d8-162">클라이언트 구성에서 보안을 해제하면 다음과 같이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-162">Turning off security for a client configuration generates the following:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service   
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
                    binding="netMsmqBinding"   
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="805d8-163">이 샘플의 서비스에서는 `OrderProcessorService`에 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-163">The service for this sample creates a binding in the `OrderProcessorService`.</span></span> <span data-ttu-id="805d8-164">바인딩이 인스턴스화된 후 코드 줄을 추가하여 보안 모드를 `None`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-164">Add a line of code after the binding is instantiated to set the security mode to `None`.</span></span>  
  
    ```  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4.  <span data-ttu-id="805d8-165">샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-165">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="805d8-166">`security mode`를 `None`으로 설정하면 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 또는 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-166">Setting `security mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> or `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="805d8-167">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="805d8-168">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="805d8-168">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="805d8-169">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="805d8-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="805d8-170">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="805d8-170">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
  
## <a name="see-also"></a><span data-ttu-id="805d8-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="805d8-171">See Also</span></span>
