---
title: Poison Message Handling in MSMQ 4.0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: d0ddab7832e308336d5bfb1c5f75fd13fe63fe72
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="poison-message-handling-in-msmq-40"></a><span data-ttu-id="4328c-102">Poison Message Handling in MSMQ 4.0</span><span class="sxs-lookup"><span data-stu-id="4328c-102">Poison Message Handling in MSMQ 4.0</span></span>
<span data-ttu-id="4328c-103">이 샘플에서는 서비스에서 포이즌 메시지 처리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-103">This sample demonstrates how to perform poison message handling in a service.</span></span> <span data-ttu-id="4328c-104">이 샘플에 따라는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="4328c-104">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="4328c-105">이 샘플에서는 `netMsmqBinding`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-105">This sample uses the `netMsmqBinding`.</span></span> <span data-ttu-id="4328c-106">이 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 서비스에서 대기된 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
 <span data-ttu-id="4328c-107">대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-107">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="4328c-108">좀더 정확하게 말하면 클라이언트는 큐에 메시지를 보내고,</span><span class="sxs-lookup"><span data-stu-id="4328c-108">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="4328c-109">서비스는 큐에서 보낸 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-109">The service receives messages from the queue.</span></span> <span data-ttu-id="4328c-110">따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-110">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="4328c-111">포이즌 메시지는 메시지를 읽는 서비스가 메시지를 처리할 수 없어 메시지를 읽는 트랜잭션을 종료할 때 큐에서 반복적으로 읽는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-111">A poison message is a message that is repeatedly read from a queue when the service reading the message cannot process the message and therefore terminates the transaction under which the message is read.</span></span> <span data-ttu-id="4328c-112">이런 경우 메시지가 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-112">In such cases, the message is retried again.</span></span> <span data-ttu-id="4328c-113">이론적으로는, 메시지에 문제가 있는 경우 이런 현상이 계속해서 발생할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="4328c-113">This can theoretically go on forever if there is a problem with the message.</span></span> <span data-ttu-id="4328c-114">실제로는 트랜잭션을 사용하여 큐에서 읽고 서비스 작업을 호출하는 경우에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-114">Note that this can only occur when you use transactions to read from the queue and invoke the service operation.</span></span>  
  
 <span data-ttu-id="4328c-115">MSMQ의 버전에 따라 NetMsmqBinding에서는 포이즌 메시지의 제한적 검색부터 완전한 검색까지 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-115">Based on the version of MSMQ, the NetMsmqBinding supports limited detection to full detection of poison messages.</span></span> <span data-ttu-id="4328c-116">포이즌 메시지로 검색된 메시지는 몇 가지 방법으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-116">After the message has been detected as poisoned, then it can be handled in several ways.</span></span> <span data-ttu-id="4328c-117">또한 MSMQ의 버전에 따라 NetMsmqBinding에서는 포이즌 메시지의 제한된 처리부터 전체 처리까지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-117">Again, based on the version of MSMQ, the NetMsmqBinding supports limited handling to full handling of poison messages.</span></span>  
  
 <span data-ttu-id="4328c-118">이 샘플에서는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 및 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 플랫폼에서 제공되는 제한된 포이즌 기능 및 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 제공되는 전체 포이즌 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-118">This sample illustrates the limited poison facilities provided on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] platform and the full poison facilities provided on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="4328c-119">두 샘플의 목표는 큐에서 포이즌 메시지를 다른 큐로 이동하여 포이즌 메시지 서비스에 의해 처리되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-119">In both samples, the objective is move the poison message out of the queue to another queue which then can be serviced by a poison message service.</span></span>  
  
## <a name="msmq-v40-poison-handling-sample"></a><span data-ttu-id="4328c-120">MSMQ v4.0 Poison Handling 샘플</span><span class="sxs-lookup"><span data-stu-id="4328c-120">MSMQ v4.0 Poison Handling Sample</span></span>  
 <span data-ttu-id="4328c-121">[!INCLUDE[wv](../../../../includes/wv-md.md)]의 MSMQ에서는 포이즌 메시지를 저장하는 데 사용할 수 있는 포이즌 하위 큐 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-121">In [!INCLUDE[wv](../../../../includes/wv-md.md)], MSMQ provides a poison sub-queue facility that can be used to store poison messages.</span></span> <span data-ttu-id="4328c-122">이 샘플에서는 [!INCLUDE[wv](../../../../includes/wv-md.md)]를 사용하여 포이즌 메시지를 처리하는 가장 좋은 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-122">This sample demonstrates the best practice of dealing with poison messages using [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>  
  
 <span data-ttu-id="4328c-123">[!INCLUDE[wv](../../../../includes/wv-md.md)]의 포이즌 메시지 검색은 매우 정교합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-123">The poison message detection in [!INCLUDE[wv](../../../../includes/wv-md.md)] is quite sophisticated.</span></span> <span data-ttu-id="4328c-124">검색에 도움이 되는 속성은 세 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-124">There are 3 properties that help with detection.</span></span> <span data-ttu-id="4328c-125"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>는 큐에서 지정된 메시지를 다시 읽고 응용 프로그램으로 디스패치하여 처리할 수 있는 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-125">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is number of times a given message is re-read from the queue and dispatched to the application for processing.</span></span> <span data-ttu-id="4328c-126">메시지를 응용 프로그램으로 디스패치할 수 없어 큐에 다시 배치하거나 응용 프로그램이 서비스 작업에서 트랜잭션을 롤백하는 경우에 큐의 메시지를 다시 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-126">A message is re-read from the queue when it is put back into the queue because the message cannot be dispatched to the application or the application rolls back the transaction in the service operation.</span></span> <span data-ttu-id="4328c-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>는 메시지를 재시도 큐로 이동하는 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-127"><xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> is the number of times the message is moved to the retry queue.</span></span> <span data-ttu-id="4328c-128"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>에 도달하면 메시지가 재시도 큐로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-128">When <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reached, the message is moved to the retry queue.</span></span> <span data-ttu-id="4328c-129"><xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> 속성은 메시지가 재시도 큐에서 다시 기본 큐로 이동한 후의 시간 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-129">The property <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> is the time delay after which the message is moved from the retry queue back to the main queue.</span></span> <span data-ttu-id="4328c-130"><xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>는 0으로 다시 설정되고,</span><span class="sxs-lookup"><span data-stu-id="4328c-130">The <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> is reset to 0.</span></span> <span data-ttu-id="4328c-131">메시지가 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-131">The message is tried again.</span></span> <span data-ttu-id="4328c-132">메시지를 읽으려는 시도가 모두 실패하면 메시지가 포이즌으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-132">If all attempts to read the message have failed, then the message is marked as poisoned.</span></span>  
  
 <span data-ttu-id="4328c-133">메시지가 포이즌으로 표시되면 메시지는 <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> 열거의 설정에 따라 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-133">Once the message is marked as poisoned, the message is dealt with according to the settings in the <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> enumeration.</span></span> <span data-ttu-id="4328c-134">반복하려는 경우 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-134">To reiterate the possible values:</span></span>  
  
-   <span data-ttu-id="4328c-135">Fault(기본값): 수신기와 서비스 호스트에 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-135">Fault (default): To fault the listener and also the service host.</span></span>  
  
-   <span data-ttu-id="4328c-136">Drop: 메시지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-136">Drop: To drop the message.</span></span>  
  
-   <span data-ttu-id="4328c-137">Move: 메시지를 포이즌 메시지 하위 큐로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-137">Move: To move the message to the poison message sub-queue.</span></span> <span data-ttu-id="4328c-138">이 값은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-138">This value is available only on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>  
  
-   <span data-ttu-id="4328c-139">Reject: 메시지를 보낸 사람의 배달 못 한 편지 큐로 돌려보내는 방법으로 메시지를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-139">Reject: To reject the message, sending the message back to the sender's dead-letter queue.</span></span> <span data-ttu-id="4328c-140">이 값은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-140">This value is available only on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>  
  
 <span data-ttu-id="4328c-141">이 샘플에서는 포이즌 메시지에 `Move` 처리를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-141">The sample demonstrates using the `Move` disposition for the poison message.</span></span> <span data-ttu-id="4328c-142">`Move`를 사용하면 메시지가 포이즌 하위 큐로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-142">`Move` causes the message to move to the poison sub-queue.</span></span>  
  
 <span data-ttu-id="4328c-143">서비스 계약은 `IOrderProcessor`이며, 이는 큐에 사용하기에 적합한 단방향 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-143">The service contract is `IOrderProcessor`, which defines a one-way service that is suitable for use with queues.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```

 <span data-ttu-id="4328c-144">서비스 작업에는 주문을 처리하고 있다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-144">The service operation displays a message stating it is processing the order.</span></span> <span data-ttu-id="4328c-145">포이즌 메시지 기능을 보여 주기 위해 `SubmitPurchaseOrder` 서비스 작업에서는 서비스를 임의로 호출하여 트랜잭션을 롤백하는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-145">To demonstrate the poison message functionality, the `SubmitPurchaseOrder` service operation throws an exception to rollback the transaction on a random invocation of the service.</span></span> <span data-ttu-id="4328c-146">그러면 메시지는 큐로 돌아가서,</span><span class="sxs-lookup"><span data-stu-id="4328c-146">This causes the message to be put back in the queue.</span></span> <span data-ttu-id="4328c-147">포이즌 메시지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-147">Eventually the message is marked as poison.</span></span> <span data-ttu-id="4328c-148">구성은 포이즌 메시지를 포이즌 하위 큐로 이동하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-148">The configuration is set to move the poison message to the poison sub-queue.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
public class OrderProcessorService : IOrderProcessor  
{  
    static Random r = new Random(137);  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
  
        int randomNumber = r.Next(10);  
  
        if (randomNumber % 2 == 0)  
        {  
            Orders.Add(po);  
            Console.WriteLine("Processing {0} ", po);  
        }  
        else  
        {  
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);  
            Console.WriteLine();  
            throw new Exception("Cannot process purchase order: " + po.PONumber);  
        }  
    }  
  
    public static void OnServiceFaulted(object sender, EventArgs e)   
    {  
        Console.WriteLine("Service Faulted");  
    }  
  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Get MSMQ queue name from app settings in configuration.  
        string queueName = ConfigurationManager.AppSettings["queueName"];  
  
        // Create the transacted MSMQ queue if necessary.  
        if (!System.Messaging.MessageQueue.Exists(queueName))  
            System.Messaging.MessageQueue.Create(queueName, true);  
  
        // Get the base address that is used to listen for WS-MetaDataExchange requests.  
        // This is useful to generate a proxy for the client.  
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];  
  
        // Create a ServiceHost for the OrderProcessorService type.  
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));  
  
        // Hook on to the service host faulted events.  
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);  
  
        // Open the ServiceHostBase to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        if(serviceHost.State != CommunicationState.Faulted) {  
            serviceHost.Close();  
        }  
  
    }  
}  
```

 <span data-ttu-id="4328c-149">서비스 구성에는 다음 구성 파일에 표시된 `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` 및 `receiveErrorHandling`와 같은 포이즌 메시지 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-149">The service configuration includes the following poison message properties: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, and `receiveErrorHandling` as shown in the following configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />  
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>  
  </appSettings>  
  <system.serviceModel>  
    <services>  
      <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="PoisonBinding"   
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  
    <bindings>  
      <netMsmqBinding>  
        <binding name="PoisonBinding"   
                 receiveRetryCount="0"  
                 maxRetryCycles="1"  
                 retryCycleDelay="00:00:05"                        
                 receiveErrorHandling="Move">  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="processing-messages-from-the-poison-message-queue"></a><span data-ttu-id="4328c-150">포이즌 메시지 큐의 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="4328c-150">Processing messages from the poison message queue</span></span>  
 <span data-ttu-id="4328c-151">포이즌 메시지 서비스에서는 최종 포이즌 메시지 큐로부터 메시지를 읽어 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-151">The poison message service reads messages from the final poison message queue and processes them.</span></span>  
  
 <span data-ttu-id="4328c-152">포이즌 메시지 큐의 메시지는 메시지를 처리 중인 서비스로 주소가 지정되는 메시지입니다. 이 서비스는 포이즌 메시지 서비스 끝점과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-152">Messages in the poison message queue are messages that are addressed to the service that is processing the message, which could be different from the poison message service endpoint.</span></span> <span data-ttu-id="4328c-153">따라서 포이즌 메시지 서비스가 큐에서 메시지를 읽고, WCF 채널 계층은 끝점에서 불일치를 발견 및 메시지를 디스패치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-153">Therefore, when the poison message service reads messages from the queue, the WCF channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="4328c-154">이 경우 메시지의 주소는 주문 처리 서비스로 지정되지만 포이즌 메시지 서비스에서 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-154">In this case, the message is addressed to the order processing service but is being received by the poison message service.</span></span> <span data-ttu-id="4328c-155">메시지의 주소가 다른 끝점으로 지정되는 경우에도 메시지를 계속 받으려면 `ServiceBehavior`를 추가하여 메시지 주소가 지정된 서비스 끝점과 일치하는 주소를 필터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-155">To continue to receive the message even if the message is addressed to a different endpoint, we must add a `ServiceBehavior` to filter addresses where the match criterion is to match any service endpoint the message is addressed to.</span></span> <span data-ttu-id="4328c-156">포이즌 메시지 큐에서 읽은 메시지를 성공적으로 처리하려면 이러한 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-156">This is required to successfully process messages that you read from the poison message queue.</span></span>  
  
 <span data-ttu-id="4328c-157">포이즌 메시지 서비스 구현 자체는 서비스 구현과 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-157">The poison message service implementation itself is very similar to the service implementation.</span></span> <span data-ttu-id="4328c-158">이 구현에서는 계약을 구현하고 주문을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-158">It implements the contract and processes the orders.</span></span> <span data-ttu-id="4328c-159">코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-159">The code example is as follows.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
  
    public static void OnServiceFaulted(object sender, EventArgs e)   
    {  
        Console.WriteLine("Service Faulted...exiting app");  
        Environment.Exit(1);  
    }  
  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
  
        // Create a ServiceHost for the OrderProcessorService type.  
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));  
  
        // Hook on to the service host faulted events.  
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);  
  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The poison message service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHostBase to shutdown the service.  
        if(serviceHost.State != CommunicationState.Faulted)  
        {  
            serviceHost.Close();  
        }  
    }  
```

 <span data-ttu-id="4328c-160">주문 큐에서 메시지를 읽는 주문 처리 서비스와 달리 포이즌 메시지 서비스는 포이즌 하위 큐에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-160">Unlike the order processing service that reads messages from the order queue, the poison message service reads messages from the poison sub-queue.</span></span> <span data-ttu-id="4328c-161">포이즌 큐는 기본 큐의 하위 큐로서 "poison"이라는 이름이 지정되고 MSMQ에서 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-161">The poison queue is a sub-queue of the main queue, is named "poison" and is automatically generated by MSMQ.</span></span> <span data-ttu-id="4328c-162">이 큐에 액세스하려면 다음 샘플 구성처럼 기본 큐 이름, ";" 및 하위 큐 이름(여기서는 -"poison")을 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-162">To access it, provide the main queue name followed by a ";" and the sub-queue name, in this case -"poison", as shown in the following sample configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4328c-163">MSMQ v3.0 샘플에서 포이즌 큐 이름은 하위 큐가 아닌 메시지를 이동한 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-163">In the sample for MSMQ v3.0, the poison queue name is not a sub-queue, rather the queue that we moved the message to.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"  
                  binding="netMsmqBinding"  
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >  
        </endpoint>  
      </service>  
    </services>  
  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="4328c-164">샘플을 실행하면 클라이언트, 서비스 및 포이즌 메시지 서비스 동작이 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-164">When you run the sample, the client, service, and poison message service activities are displayed in console windows.</span></span> <span data-ttu-id="4328c-165">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-165">You can see the service receive messages from the client.</span></span> <span data-ttu-id="4328c-166">서비스를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-166">Press ENTER in each console window to shut down the services.</span></span>  
  
 <span data-ttu-id="4328c-167">서비스가 실행되어 주문 처리를 시작하고 임의로 처리를 종료하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-167">The service starts running, processing orders and at random starts to terminate processing.</span></span> <span data-ttu-id="4328c-168">주문을 처리했다는 메시지가 나타나면 클라이언트를 다시 실행하여 서비스에서 실제로 메시지를 종료한 것이 확인될 때까지 다른 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-168">If the message indicates it has processed the order, you can run the client again to send another message until you see the service has actually terminated a message.</span></span> <span data-ttu-id="4328c-169">구성된 포이즌 설정에 따라 최종 포이즌 큐로 이동하기 전에 메시지 처리가 한 번 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-169">Based on the configured poison settings, the message is tried once for processing before moving it to the final poison queue.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89  
```  
  
 <span data-ttu-id="4328c-170">포이즌 메시지 서비스를 시작하여 포이즌 큐에서 포이즌 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-170">Start up the poison message service to read the poisoned message from the poison queue.</span></span> <span data-ttu-id="4328c-171">이 예제에서는 포이즌 메시지 서비스가 메시지를 읽고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-171">In this example, the poison message service reads the message and processes it.</span></span> <span data-ttu-id="4328c-172">종료되어 포이즌 메시지가 된 구매 주문을 포이즌 메시지 서비스에서 읽는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-172">You could see that the purchase order that was terminated and poisoned is read by the poison message service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4328c-173">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4328c-173">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4328c-174">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4328c-175">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="4328c-175">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="4328c-176">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-176">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="4328c-177">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-177">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="4328c-178">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4328c-178">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="4328c-179">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-179">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="4328c-180">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-180">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="4328c-181">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-181">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="4328c-182">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-182">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="4328c-183">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-183">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="4328c-184">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-184">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="4328c-185">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 localhost 대신 실제 호스트 이름을 반영 하도록의 지침에 따라 큐 이름을 변경 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-185">To run the sample in a single- or cross-computer configuration, change the queue names to reflect the actual hostname instead of localhost and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="4328c-186">기본적으로 `netMsmqBinding` 바인딩 전송을 사용하여 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-186">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="4328c-187">`MsmqAuthenticationMode` 및 `MsmqProtectionLevel` 속성은 모두 전송 보안의 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-187">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="4328c-188">기본적으로 인증 모드는 `Windows`로 설정되고 보호 수준은 `Sign`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-188">By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="4328c-189">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-189">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="4328c-190">도메인에 속하지 않은 컴퓨터에서 이 샘플을 실행할 경우 "사용자의 내부 메시지 큐 인증서가 없습니다."라는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-190">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>  
  
#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="4328c-191">작업 그룹에 가입된 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4328c-191">To run the sample on a computer joined to a workgroup</span></span>  
  
1.  <span data-ttu-id="4328c-192">컴퓨터가 도메인에 속하지 않는 경우 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-192">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <bindings>  
        <netMsmqBinding>  
            <binding name="TransactedBinding">  
                <security mode="None"/>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="4328c-193">끝점의 bindingConfiguration 특성을 설정하여 끝점이 바인딩에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-193">Ensure the endpoint is associated with the binding by setting the endpoint's bindingConfiguration attribute.</span></span>  
  
2.  <span data-ttu-id="4328c-194">샘플을 실행하기 전에 PoisonMessageServer, 서버 및 클라이언트에서 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-194">Ensure that you change the configuration on the PoisonMessageServer, server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4328c-195">`security mode`를 `None`으로 설정하는 것은 `MsmqAuthenticationMode`, `MsmqProtectionLevel` 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-195">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel`, and `Message` security to `None`.</span></span>  
  
3.  <span data-ttu-id="4328c-196">메타데이터 교환을 작동하기 위해 http 바인딩을 사용하여 URL을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-196">In order for Meta Data Exchange to work, we register a URL with http binding.</span></span> <span data-ttu-id="4328c-197">이렇게 하려면 권한이 높은 명령 창에서 서비스를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-197">This requires that the service run in an elevated command window.</span></span> <span data-ttu-id="4328c-198">그렇지 않으면 예외가 같은: 처리 되지 않은 예외: System.ServiceModel.AddressAccessDeniedException: HTTP URL을 등록 하지 못했습니다 http://+:8000/ServiceModelSamples/service/합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-198">Otherwise, you get an exception such as: Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/.</span></span> <span data-ttu-id="4328c-199">프로세스에이 네임 스페이스에 액세스 권한이 없습니다 (참조 http://go.microsoft.com/fwlink/?LinkId=70353 세부 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="4328c-199">Your process does not have access rights to this namespace (see http://go.microsoft.com/fwlink/?LinkId=70353 for details).</span></span> <span data-ttu-id="4328c-200">---> System.Net.HttpListenerException: 액세스가 거부되었습니다."와 같은 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-200">---> System.Net.HttpListenerException: Access is denied.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4328c-201">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-201">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4328c-202">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4328c-202">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4328c-203">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="4328c-203">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4328c-204">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4328c-204">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`  
  
## <a name="see-also"></a><span data-ttu-id="4328c-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4328c-205">See Also</span></span>
