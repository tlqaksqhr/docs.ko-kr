---
title: "트랜잭션된 MSMQ 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
caps.latest.revision: "50"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd656bed608811a5a04a47849bf915f708a62a9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-msmq-binding"></a><span data-ttu-id="2db66-102">트랜잭션된 MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="2db66-102">Transacted MSMQ Binding</span></span>
<span data-ttu-id="2db66-103">이 샘플에서는 MSMQ(메시지 큐)를 사용하여 큐에 있는 트랜잭션된 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2db66-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2db66-105">대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-105">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="2db66-106">좀더 정확하게 말하면 클라이언트는 큐에 메시지를 보내고,</span><span class="sxs-lookup"><span data-stu-id="2db66-106">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="2db66-107">서비스는 큐에서 보낸 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-107">The service receives messages from the queue.</span></span> <span data-ttu-id="2db66-108">따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-108">The service and client, therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="2db66-109">트랜잭션을 사용하여 메시지를 보내고 받는 경우 실제로 두 개의 개별 트랜잭션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-109">When transactions are used to send and receive messages, there are actually two separate transactions.</span></span> <span data-ttu-id="2db66-110">클라이언트가 트랜잭션의 범위 내에서 메시지를 보낼 때 트랜잭션은 클라이언트 및 클라이언트 큐 관리자의 로컬에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-110">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="2db66-111">서비스가 트랜잭션의 범위 내에서 메시지를 받을 때 트랜잭션은 서비스 및 수신 큐 관리자의 로컬에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-111">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="2db66-112">클라이언트와 서비스는 동일한 트랜잭션에 참여하지 않습니다. 이들은 큐에서 보내기 및 받기와 같은 작업을 수행할 때 서로 다른 트랜잭션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-112">It is very important to remember that the client and the service are not participating in the same transaction; rather, they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="2db66-113">이 샘플에서 클라이언트는 트랜잭션의 범위 내에서 일련의 메시지를 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-113">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="2db66-114">그러면 서비스는 큐로 전송된 메시지를 서비스에 정의된 트랜잭션 범위 내에서 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-114">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span>  
  
 <span data-ttu-id="2db66-115">다음 샘플 코드와 같이 서비스 계약은 `IOrderProcessor`입니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-115">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span> <span data-ttu-id="2db66-116">이 인터페이스는 큐에서 사용하기에 적합한 단방향 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-116">The interface defines a one-way service that is suitable for use with queues.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```  
  
 <span data-ttu-id="2db66-117">서비스 동작은 `TransactionScopeRequired`가 `true`로 설정된 작업 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-117">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="2db66-118">따라서 큐에서 메시지를 검색할 때 사용되는 트랜잭션 범위가 메서드에서 액세스하는 리소스 관리자에서 동일하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-118">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="2db66-119">또한 메서드에서 예외를 throw하는 경우 메시지가 큐로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-119">It also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="2db66-120">이 작업 동작을 설정하지 않을 경우 큐에 있는 채널은 큐로부터 메시지를 읽는 트랜잭션을 만들고 디스패치 전에 자동으로 이를 커밋하므로, 작업이 실패하면 메시지를 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-120">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before dispatch such that if the operation fails, the message is lost.</span></span> <span data-ttu-id="2db66-121">가장 일반적인 시나리오는 다음 코드에서와 같이 큐로부터 메시지를 읽을 때 사용되는 트랜잭션에 서비스 작업이 참여하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-121">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue, as demonstrated in the following code.</span></span>  
  
```  
 // This service class that implements the service contract.  
 // This added code writes output to the console window.  
 public class OrderProcessorService : IOrderProcessor  
 {  
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
     public void SubmitPurchaseOrder(PurchaseOrder po)  
     {  
         Orders.Add(po);  
         Console.WriteLine("Processing {0} ", po);  
     }  
  …  
}  
```  
  
 <span data-ttu-id="2db66-122">서비스는 자체 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-122">The service is self hosted.</span></span> <span data-ttu-id="2db66-123">MSMQ 전송을 사용하는 경우에는 사용되는 큐를 미리 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-123">When using the MSMQ transport, the queue used must be created in advance.</span></span> <span data-ttu-id="2db66-124">수동으로 또는 코드를 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-124">This can be done manually or through code.</span></span> <span data-ttu-id="2db66-125">이 샘플에서 서비스에는 큐가 있는지 확인하고 큐가 없으면 이를 만드는 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-125">In this sample, the service contains code to check for the existence of the queue and create the queue if it does not exist.</span></span> <span data-ttu-id="2db66-126">큐 이름은 구성 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-126">The queue name is read from the configuration file.</span></span> <span data-ttu-id="2db66-127">기본 주소에서 사용 되는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에 대 한 프록시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-127">The base address is used by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy to the service.</span></span>  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get the MSMQ queue name from appSettings in configuration.  
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
  
        // Close the ServiceHost to shut down the service.  
        serviceHost.Close();  
    }  
}  
```  
  
 <span data-ttu-id="2db66-128">다음 샘플 구성에서 보여 주는 것처럼 MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-128">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="2db66-129"><xref:System.Messaging>을 사용하여 큐를 만들 때 큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-129">The queue name uses a dot (.) for the local computer and backslash separators in its path when creating the queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="2db66-130">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 끝점은 net.msmq 체계의 큐 주소를 사용하고 로컬 컴퓨터를 나타내기 위해 "localhost"를 사용하며 경로에 슬래시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-130">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] endpoint uses the queue address with net.msmq scheme, uses "localhost" to denote the local computer, and uses forward slashes in its path.</span></span>  
  
 <span data-ttu-id="2db66-131">클라이언트는 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-131">The client creates a transaction scope.</span></span> <span data-ttu-id="2db66-132">트랜잭션 범위 내에서 큐와 통신을 수행하여 모든 메시지가 큐로 전송되거나 어떤 메시지도 큐로 전송되지 않는 가장 작은 단위로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-132">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="2db66-133">트랜잭션은 트랜잭션 범위에서 <xref:System.Transactions.TransactionScope.Complete%2A>를 호출하여 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-133">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  
  
```  
// Create a client.  
OrderProcessorClient client = new OrderProcessorClient();  
  
// Create the purchase order.  
PurchaseOrder po = new PurchaseOrder();  
po.CustomerId = "somecustomer.com";  
po.PONumber = Guid.NewGuid().ToString();  
  
PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
lineItem1.ProductId = "Blue Widget";  
lineItem1.Quantity = 54;  
lineItem1.UnitCost = 29.99F;  
  
PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
lineItem2.ProductId = "Red Widget";  
lineItem2.Quantity = 890;  
lineItem2.UnitCost = 45.89F;  
  
po.orderLineItems = new PurchaseOrderLineItem[2];  
po.orderLineItems[0] = lineItem1;  
po.orderLineItems[1] = lineItem2;  
  
// Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Make a queued call to submit the purchase order.  
    client.SubmitPurchaseOrder(po);  
    // Complete the transaction.  
    scope.Complete();  
}  
  
// Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="2db66-134">트랜잭션이 작동 중임을 확인하려면 아래 샘플 코드에서와 같이 클라이언트를 수정하여 트랜잭션 범위를 주석 처리하고 솔루션을 다시 빌드한 다음 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-134">To verify that transactions are working, modify the client by commenting the transaction scope as shown in the following sample code, rebuild the solution, and run the client.</span></span>  
  
```  
//scope.Complete();  
```  
  
 <span data-ttu-id="2db66-135">트랜잭션이 완료되지 않았으므로 메시지가 큐에 보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-135">Because the transaction is not completed, the messages are not sent to the queue.</span></span>  
  
 <span data-ttu-id="2db66-136">샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-136">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="2db66-137">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-137">You can see the service receive messages from the client.</span></span> <span data-ttu-id="2db66-138">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-138">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="2db66-139">큐를 사용하므로 클라이언트와 서비스가 동시에 실행 중일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-139">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="2db66-140">클라이언트를 실행하고 종료한 다음 서비스를 다시 시작해도 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-140">You can run the client, shut it down, and then start up the service and it still receives the messages.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2db66-141">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2db66-141">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2db66-142">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-142">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2db66-143">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="2db66-143">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="2db66-144">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-144">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="2db66-145">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-145">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="2db66-146">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2db66-146">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="2db66-147">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-147">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="2db66-148">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-148">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="2db66-149">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-149">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="2db66-150">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-150">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="2db66-151">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-151">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="2db66-152">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="2db66-153">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-153">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="2db66-154">기본적으로 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 전송 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-154">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="2db66-155">MSMQ 전송 보안과 관련된 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>와 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>이라는 두 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-155">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.</span></span> <span data-ttu-id="2db66-156">기본적으로 인증 모드는 `Windows`로 설정되고 보호 수준은 `Sign`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-156">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="2db66-157">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 하며 MSMQ의 Active Directory 통합 옵션이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-157">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the Active Directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="2db66-158">이 기준에 맞지 않는 컴퓨터에서 이 샘플을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-158">If you run this sample on a computer that does not satisfy these criteria, you receive an error.</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="2db66-159">작업 그룹에 속해 있거나 Active Directory 통합이 없는 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2db66-159">To run the sample on a computer joined to a workgroup or without Active Directory integration</span></span>  
  
1.  <span data-ttu-id="2db66-160">컴퓨터가 도메인에 속해 있지 않거나 Active Directory 통합이 설치되어 있지 않은 경우에는 다음 샘플 구성 코드에서와 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-160">If your computer is not part of a domain or does not have Active Directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"  
                 behaviorConfiguration="OrderProcessorServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint. -->  
          <endpoint  
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <!-- The mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex. -->  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="OrderProcessorServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="2db66-161">샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-161">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2db66-162">`security``mode`를 `None`으로 설정하는 것은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-162">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2db66-163">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-163">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2db66-164">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2db66-164">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2db66-165">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2db66-165">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2db66-166">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db66-166">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`  
  
## <a name="see-also"></a><span data-ttu-id="2db66-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2db66-167">See Also</span></span>
