---
title: "배달 못 한 편지 큐"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2cd61bf9c1e3d7165b76f55f1808b04c979d4d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="dead-letter-queues"></a><span data-ttu-id="3c118-102">배달 못 한 편지 큐</span><span class="sxs-lookup"><span data-stu-id="3c118-102">Dead Letter Queues</span></span>
<span data-ttu-id="3c118-103">이 샘플에서는 배달에 실패한 메시지를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-103">This sample demonstrates how to handle and process messages that have failed delivery.</span></span> <span data-ttu-id="3c118-104">에 따라 결정 된 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="3c118-104">It is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="3c118-105">이 샘플에서는 `netMsmqBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-105">This sample uses the `netMsmqBinding` binding.</span></span> <span data-ttu-id="3c118-106">이 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 서비스에서 대기된 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-106">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c118-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c118-108">이 샘플에서는 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서만 사용할 수 있는 각 응용 프로그램의 배달 못 한 편지 큐를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-108">This sample demonstrates each application dead letter queue that is only available on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="3c118-109">샘플을 수정하면 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 및 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 MSMQ 3.0에 기본 시스템 차원 큐를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-109">The sample can be modified to use the default system-wide queues for MSMQ 3.0 on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
 <span data-ttu-id="3c118-110">대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-110">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="3c118-111">좀더 정확하게 말하면 클라이언트는 큐에 메시지를 보내고,</span><span class="sxs-lookup"><span data-stu-id="3c118-111">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="3c118-112">서비스는 큐에서 보낸 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-112">The service receives messages from the queue.</span></span> <span data-ttu-id="3c118-113">따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-113">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="3c118-114">대기 중인 통신에는 약간의 유휴 기간이 포함될 수 있으므로 메시지의 TTL(Time-To-Live) 값을 연결하여 시간이 지난 경우 메시지가 응용 프로그램으로 배달되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-114">Because queued communication can involve a certain amount of dormancy, you may want to associate a time-to-live value on the message to ensure that the message does not get delivered to the application if it has gone past the time.</span></span> <span data-ttu-id="3c118-115">메시지 배달 실패 여부를 응용 프로그램에 알려야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-115">There are also cases, where an application must be informed whether a message failed delivery.</span></span> <span data-ttu-id="3c118-116">메시지의 TTL(Time-To-Live)이 만료되었거나 메시지 배달에 실패한 경우 메시지는 배달 못 한 편지 큐에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-116">In all of these cases, such as when the time-to-live on the message has expired or the message failed delivery, the message is put in a dead letter queue.</span></span> <span data-ttu-id="3c118-117">그러면 보내는 응용 프로그램에서 배달 못 한 편지 큐의 메시지를 읽고 아무 작업도 수행하지 않거나 배달 실패 원인을 해결하고 메시지를 다시 보내는 등의 수정 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-117">The sending application can then read the messages in the dead-letter queue and take corrective actions that range from no action to correcting the reasons for failed delivery and resending the message.</span></span>  
  
 <span data-ttu-id="3c118-118">`NetMsmqBinding` 바인딩에서 배달 못 한 편지 큐는 다음과 같은 속성으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-118">The dead-letter queue in the `NetMsmqBinding` binding is expressed in the following properties:</span></span>  
  
-   <span data-ttu-id="3c118-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 속성은 클라이언트에 필요한 배달 못 한 편지 큐의 종류를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-119"><xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> property to express the kind of dead-letter queue required by the client.</span></span> <span data-ttu-id="3c118-120">이 열거형에는 다음과 같은 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-120">This enumeration has the following values:</span></span>  
  
-   <span data-ttu-id="3c118-121">`None`: 클라이언트에 필요한 배달 못 한 편지 큐가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-121">`None`: No dead-letter queue is required by the client.</span></span>  
  
-   <span data-ttu-id="3c118-122">`System`: 배달 못 한 시스템 큐를 사용하여 배달 못 한 메시지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-122">`System`: The system dead-letter queue is used to store dead messages.</span></span> <span data-ttu-id="3c118-123">배달 못 한 편지 시스템 큐는 컴퓨터에서 실행되는 모든 응용 프로그램에서 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-123">The system dead-letter queue is shared by all applications running on the computer.</span></span>  
  
-   <span data-ttu-id="3c118-124">`Custom`: <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> 속성을 사용하여 지정한 사용자 지정 배달 못 한 편지 큐를 사용하여 배달 못 한 메시지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-124">`Custom`: A custom dead-letter queue specified using the <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property is used to store dead messages.</span></span> <span data-ttu-id="3c118-125">이 기능은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-125">This feature is only available on [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="3c118-126">이 기능은 응용 프로그램이 동일한 컴퓨터에서 실행되는 다른 응용 프로그램과 배달 못 한 편지 큐를 공유하지 않고 고유한 배달 못 한 편지 큐를 사용해야 하는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-126">This is used when the application must use its own dead letter queue instead of sharing it with other applications running on the same computer.</span></span>  
  
-   <span data-ttu-id="3c118-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> 속성은 배달 못 한 편지 큐로 사용할 특정 큐를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-127"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> property to express the specific queue to use as a dead-letter queue.</span></span> <span data-ttu-id="3c118-128">이 속성은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-128">This is available only in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span>  
  
 <span data-ttu-id="3c118-129">이 샘플에서 클라이언트는 트랜잭션 범위 내에서 서비스로 일괄 처리 메시지를 보내고 이러한 메시지의 "TTL(Time-To-Live)" 값을 임의로 낮게 지정합니다(약 2초).</span><span class="sxs-lookup"><span data-stu-id="3c118-129">In this sample, the client sends a batch of messages to the service from within the scope of a transaction and specifies an arbitrarily low value for "time-to-live" for these messages (about 2 seconds).</span></span> <span data-ttu-id="3c118-130">또한 클라이언트는 사용자 지정 배달 못 한 편지 큐를 지정하여 만료된 메시지를 큐에 삽입하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-130">The client also specifies a custom dead-letter queue to use to enqueue the messages that have expired.</span></span>  
  
 <span data-ttu-id="3c118-131">클라이언트 응용 프로그램은 배달 못 한 편지 큐에서 메시지를 읽고 메시지 보내기를 다시 시도하거나 원본 메시지가 배달 못 한 편지 큐에 저장된 원인을 해결한 후 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-131">The client application can read the messages in the dead-letter queue and either retry sending the message or correct the error that caused the original message to be placed in the dead-letter queue and send the message.</span></span> <span data-ttu-id="3c118-132">이 샘플에서 클라이언트는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-132">In the sample, the client displays an error message.</span></span>  
  
 <span data-ttu-id="3c118-133">다음 샘플 코드와 같이 서비스 계약은 `IOrderProcessor`입니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-133">The service contract is `IOrderProcessor`, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```  
  
 <span data-ttu-id="3c118-134">이 샘플에서 서비스 코드의입니다는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-134">The service code in the sample is that of the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
 <span data-ttu-id="3c118-135">서비스와의 통신은 트랜잭션 범위 내에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-135">Communication with the service takes place within the scope of a transaction.</span></span> <span data-ttu-id="3c118-136">서비스는 큐에서 메시지를 읽고 작업을 수행한 후 작업 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-136">The service reads messages from the queue, performs the operation and then displays the results of the operation.</span></span> <span data-ttu-id="3c118-137">응용 프로그램도 배달 못 한 메시지에 대해 배달 못 한 편지 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-137">The application also creates a dead-letter queue for dead-letter messages.</span></span>  
  
```  
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        // Get MSMQ queue name from app settings in configuration  
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];  
  
        // Create the transacted MSMQ queue for storing dead message if necessary.  
        if (!MessageQueue.Exists(deadLetterQueueName))  
            MessageQueue.Create(deadLetterQueueName, true);  
  
        // Create a proxy with given client endpoint configuration  
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
        // Create the purchase order  
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
  
        //Create a transaction scope.  
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Make a queued call to submit the purchase order  
            client.SubmitPurchaseOrder(po);  
            // Complete the transaction.  
            scope.Complete();  
        }  
  
        client.Close();  
  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="3c118-138">클라이언트 구성에는 메시지가 서비스에 도달하는 데 걸리는 시간을 짧게 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-138">The client's configuration specifies a short duration for the message to reach the service.</span></span> <span data-ttu-id="3c118-139">지정된 시간 내에 메시지를 전송할 수 없으면 메시지가 만료되어 배달 못 한 편지 큐로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-139">If the message cannot be transmitted within the duration specified, the message expires and is moved to the dead-letter queue.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c118-140">클라이언트는 지정된 시간 내에 서비스 큐로 메시지를 배달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-140">It is possible for the client to deliver the message to the service queue within the specified time.</span></span> <span data-ttu-id="3c118-141">배달 못 한 편지 서비스가 실행되는지 확인하려면 서비스를 시작하기 전에 클라이언트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-141">To ensure you see the dead-letter service in action, you should run the client before starting the service.</span></span> <span data-ttu-id="3c118-142">메시지는 시간이 초과되면 배달 못 한 편지 서비스로 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-142">The message times out and is delivered to the dead-letter service.</span></span>  
  
 <span data-ttu-id="3c118-143">응용 프로그램에서 배달 못 한 편지 큐로 사용할 큐를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-143">The application must define which queue to use as its dead-letter queue.</span></span> <span data-ttu-id="3c118-144">큐를 지정하지 않으면 기본 시스템 차원의 배달 못 한 트랜잭션 큐가 배달 못 한 메시지를 큐에 삽입하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-144">If no queue is specified, the default system-wide transactional dead-letter queue is used to queue dead messages.</span></span> <span data-ttu-id="3c118-145">이 예제에서 클라이언트 응용 프로그램은 응용 프로그램 고유의 배달 못 한 편지 큐를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-145">In this example, the client application specifies its own application dead-letter queue.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->  
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>  
  </appSettings>  
  
  <system.serviceModel>  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"   
                binding="netMsmqBinding"   
                bindingConfiguration="PerAppDLQBinding"   
                contract="IOrderProcessor" />  
    </client>  
  
    <bindings>  
      <netMsmqBinding>  
        <binding name="PerAppDLQBinding"  
                 deadLetterQueue="Custom"  
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"   
                 timeToLive="00:00:02"/>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="3c118-146">배달 못 한 메시지 서비스는 배달 못 한 편지 큐에서 메시지를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-146">The dead-letter message service reads messages from the dead-letter queue.</span></span> <span data-ttu-id="3c118-147">배달 못 한 메시지 서비스는 `IOrderProcessor` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-147">The dead-letter message service implements the `IOrderProcessor` contract.</span></span> <span data-ttu-id="3c118-148">그러나 이 구현에서는 주문을 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-148">Its implementation however is not to process orders.</span></span> <span data-ttu-id="3c118-149">배달 못 한 메시지 서비스는 클라이언트 서비스이며 주문을 처리하는 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-149">The dead-letter message service is a client service and does not have the facility to process orders.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c118-150">배달 못 한 편지 큐는 클라이언트 큐이며 클라이언트 큐 관리자에 대해 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-150">The dead-letter queue is a client queue and is local to the client queue manager.</span></span>  
  
 <span data-ttu-id="3c118-151">배달 못 한 메시지 서비스 구현에서는 메시지 배달 실패의 원인을 확인하고 올바른 방법으로 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-151">The dead-letter message service implementation checks for the reason a message failed delivery and takes corrective measures.</span></span> <span data-ttu-id="3c118-152">메시지 실패 원인은 <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> 및 <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A> 열거형으로 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-152">The reason for a message failure is captured in two enumerations, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> and <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>.</span></span> <span data-ttu-id="3c118-153">다음 샘플 코드와 같이 <xref:System.ServiceModel.Channels.MsmqMessageProperty>에서 <xref:System.ServiceModel.OperationContext>를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-153">You can retrieve the <xref:System.ServiceModel.Channels.MsmqMessageProperty> from the <xref:System.ServiceModel.OperationContext> as shown in the following sample code:</span></span>  
  
```  
public void SubmitPurchaseOrder(PurchaseOrder po)  
{  
    Console.WriteLine("Submitting purchase order did not succed ", po);  
    MsmqMessageProperty mqProp =   
                  OperationContext.Current.IncomingMessageProperties[  
                  MsmqMessageProperty.Name] as MsmqMessageProperty;  
    Console.WriteLine("Message Delivery Status: {0} ",   
                                                mqProp.DeliveryStatus);  
    Console.WriteLine("Message Delivery Failure: {0}",   
                                               mqProp.DeliveryFailure);  
    Console.WriteLine();  
    ….  
}  
```  
  
 <span data-ttu-id="3c118-154">배달 못 한 편지 큐의 메시지는 메시지를 처리하고 있는 서비스로 주소가 지정되는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-154">Messages in the dead-letter queue are messages that are addressed to the service that is processing the message.</span></span> <span data-ttu-id="3c118-155">따라서 배달 못 한 메시지 서비스가 큐에서 메시지를 읽으면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 채널 계층은 끝점에서 일치하지 않는 항목을 찾고 메시지를 디스패치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-155">Therefore, when the dead-letter message service reads messages from the queue, the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] channel layer finds the mismatch in endpoints and does not dispatch the message.</span></span> <span data-ttu-id="3c118-156">이 경우 메시지의 주소는 주문 처리 서비스로 지정되지만 배달 못 한 메시지 서비스에서 해당 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-156">In this case, the message is addressed to the order processing service but is received by the dead-letter message service.</span></span> <span data-ttu-id="3c118-157">다른 끝점으로 주소가 지정된 메시지를 받으려면 모든 주소와 일치하는 주소 필터를 `ServiceBehavior`에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-157">To receive a message that is addressed to a different endpoint, an address filter to match any address is specified in the `ServiceBehavior`.</span></span> <span data-ttu-id="3c118-158">이 구성은 배달 못 한 편지 큐에서 읽은 메시지를 성공적으로 처리하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-158">This is required to successfully process messages that are read from the dead-letter queue.</span></span>  
  
 <span data-ttu-id="3c118-159">이 샘플에서 배달 못 한 메시지 서비스는 실패의 원인이 메시지 시간 초과인 경우 메시지를 다시 보냅니다. 다른 모든 원인에 대해서는 다음 샘플 코드와 같이 배달 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-159">In this sample, the dead-letter message service resends the message if the reason for failure is that the message timed out. For all other reasons, it displays the delivery failure, as shown in the following sample code:</span></span>  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]  
public class PurchaseOrderDLQService : IOrderProcessor  
{  
    OrderProcessorClient orderProcessorService;  
    public PurchaseOrderDLQService()  
    {  
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Console.WriteLine("Submitting purchase order did not succeed ", po);  
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;  
  
        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);  
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);  
        Console.WriteLine();  
  
        // resend the message if timed out  
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||  
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)  
        {  
            // re-send  
            Console.WriteLine("Purchase order Time To Live expired");  
            Console.WriteLine("Trying to resend the message");  
  
            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue  
            orderProcessorService.SubmitPurchaseOrder(po);  
            Console.WriteLine("Purchase order resent");  
        }  
    }  
  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the PurchaseOrderDLQService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))  
        {  
            // Open the ServiceHostBase to create listeners and start listening for messages.  
            serviceHost.Open();  
  
            // The service can now be accessed.  
            Console.WriteLine("The dead letter service is ready.");  
            Console.WriteLine("Press <ENTER> to terminate service.");  
            Console.WriteLine();  
            Console.ReadLine();  
        }  
    }  
}   
```  
  
 <span data-ttu-id="3c118-160">다음 샘플에서는 배달 못 한 메시지에 대한 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-160">The following sample shows the configuration for a dead-letter message:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">  
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="DefaultBinding"   
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"   
                 binding="netMsmqBinding"   
                 bindingConfiguration="SystemDLQBinding"   
                 contract="IOrderProcessor" />  
    </client>  
  
    <bindings>  
      <netMsmqBinding>  
        <binding name="DefaultBinding" />  
        <binding name="SystemDLQBinding"  
                 deadLetterQueue="System"/>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="3c118-161">샘플을 실행하면 세 개의 실행 파일이 실행되어 각 응용 프로그램에서 배달 못 한 편지 큐가 어떻게 작동하는지를 보여 줍니다. 이러한 실행 파일에는 클라이언트, 서비스 및 각 응용 프로그램의 배달 못 한 편지 큐에서 메시지를 읽고 서비스로 다시 보내는 배달 못 한 편지 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-161">In running the sample, there are 3 executables to run to see how the dead-letter queue works for each application; the client, service and a dead-letter service that reads from the dead-letter queue for each application and resends the message to the service.</span></span> <span data-ttu-id="3c118-162">모든 응용 프로그램은 출력이 콘솔 창에 표시되는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-162">All are console applications with output in console windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c118-163">큐를 사용하므로 클라이언트와 서비스가 동시에 실행 중일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-163">Because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="3c118-164">클라이언트를 실행하고 종료한 다음 서비스를 다시 시작해도 서비스에서 계속 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-164">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="3c118-165">큐를 만들려면 서비스를 시작했다가 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-165">You should start the service and shut it down so that the queue can be created.</span></span>  
  
 <span data-ttu-id="3c118-166">클라이언트를 실행하면 클라이언트에 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-166">When running the client, the client displays the message:</span></span>  
  
```  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="3c118-167">클라이언트에서 메시지를 보내려고 시도하지만 짧은 시간 제한으로 인해 메시지는 만료되고 각 응용 프로그램의 배달 못 한 편지 큐에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-167">The client attempted to send the message but with a short timeout, the message expired and is now queued in the dead-letter queue for each application.</span></span>  
  
 <span data-ttu-id="3c118-168">그러면 메시지를 읽고 오류 코드를 표시한 다음 서비스로 메시지를 다시 보내는 배달 못 한 편지 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-168">You then run the dead-letter service, which reads the message and displays the error code and resends the message back to the service.</span></span>  
  
```  
The dead letter service is ready.  
Press <ENTER> to terminate service.  
  
Submitting purchase order did not succeed  
Message Delivery Status: InDoubt  
Message Delivery Failure: ReachQueueTimeout  
  
Purchase order Time To Live expired  
Trying to resend the message  
Purchase order resent  
```  
  
 <span data-ttu-id="3c118-169">서비스가 시작된 후 다시 전송된 메시지를 읽고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-169">The service starts and then reads the resent message and processes it.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3c118-170">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3c118-170">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3c118-171">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-171">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3c118-172">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="3c118-172">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="3c118-173">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-173">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="3c118-174">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-174">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="3c118-175">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="3c118-175">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="3c118-176">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-176">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="3c118-177">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-177">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="3c118-178">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-178">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="3c118-179">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-179">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="3c118-180">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-180">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="3c118-181">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-181">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="3c118-182">에서 샘플을 실행 단일 컴퓨터 또는 다중 컴퓨터 구성 변경 큐 이름을 적절 하 게 하는 컴퓨터의 전체 이름으로 localhost를 바꿉니다 및의 지침에 따라 [WindowsCommunicationFoundation샘플실행](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3c118-182">To run the sample in a single- or cross-computer configuration change queue names appropriately, replacing localhost with full name of the computer and follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="3c118-183">작업 그룹에 가입된 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3c118-183">To run the sample on a computer joined to a workgroup</span></span>  
  
1.  <span data-ttu-id="3c118-184">컴퓨터가 도메인에 속하지 않는 경우 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-184">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <bindings>  
        <netMsmqBinding>  
            <binding name="TransactedBinding">  
                <security mode="None"/>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="3c118-185">끝점의 `bindingConfiguration` 특성을 설정하여 끝점이 바인딩과 연결되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-185">Ensure the endpoint is associated with the binding by setting the endpoint's `bindingConfiguration` attribute.</span></span>  
  
2.  <span data-ttu-id="3c118-186">샘플을 실행하기 전에 DeadLetterService, 서버 및 클라이언트에서 구성을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-186">Ensure that you change the configuration on the DeadLetterService, server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c118-187">`security mode`를 `None`으로 설정하는 것은 `MsmqAuthenticationMode`, `MsmqProtectionLevel` 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-187">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3c118-188">설명</span><span class="sxs-lookup"><span data-stu-id="3c118-188">Comments</span></span>  
 <span data-ttu-id="3c118-189">기본적으로 `netMsmqBinding` 바인딩 전송을 사용하여 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-189">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="3c118-190">`MsmqAuthenticationMode` 및 `MsmqProtectionLevel` 속성은 모두 전송 보안의 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-190">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="3c118-191">기본적으로 인증 모드는 `Windows`로 설정되고 보호 수준은 `Sign`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-191">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="3c118-192">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-192">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="3c118-193">도메인에 속하지 않은 컴퓨터에서 이 샘플을 실행할 경우 "사용자의 내부 메시지 큐 인증서가 없습니다."라는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-193">If you run this sample on a computer that is not part of a domain, you receive the following error: "User's internal message queuing certificate does not exist".</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c118-194">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-194">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3c118-195">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3c118-195">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c118-196">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3c118-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c118-197">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c118-197">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
  
## <a name="see-also"></a><span data-ttu-id="3c118-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c118-198">See Also</span></span>
