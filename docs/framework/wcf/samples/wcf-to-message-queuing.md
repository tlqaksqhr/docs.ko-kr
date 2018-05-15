---
title: Windows Communication Foundation에서 메시지 큐로
ms.date: 03/30/2017
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
ms.openlocfilehash: 0864098a55cbd7b43100bf9e0a1836e749eb2bc9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="windows-communication-foundation-to-message-queuing"></a><span data-ttu-id="1c67a-102">Windows Communication Foundation에서 메시지 큐로</span><span class="sxs-lookup"><span data-stu-id="1c67a-102">Windows Communication Foundation to Message Queuing</span></span>
<span data-ttu-id="1c67a-103">이 샘플 Windows Communication Foundation (WCF) 응용 프로그램 메시지 큐 (MSMQ) 응용 프로그램에 메시지를 보낼 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-103">This sample demonstrates how a Windows Communication Foundation (WCF) application can send a message to a Message Queuing (MSMQ) application.</span></span> <span data-ttu-id="1c67a-104">이 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 서비스에서 대기된 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-104">The service is a self-hosted console application to enable you to observe the service receiving queued messages.</span></span> <span data-ttu-id="1c67a-105">서비스 및 클라이언트가 동시에 실행될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-105">The service and client do not have to be running at the same time.</span></span>  
  
 <span data-ttu-id="1c67a-106">서비스는 큐로부터 메시지를 받아 주문을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-106">The service receives messages from the queue and processes orders.</span></span> <span data-ttu-id="1c67a-107">다음 샘플 코드에서 보여 주는 것처럼 서비스는 트랜잭션 큐를 만들고 메시지 수신 메시지 처리기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-107">The service creates a transactional queue and sets up a message received message handler, as shown in the following sample code.</span></span>  

```csharp
static void Main(string[] args)  
{  
    if (!MessageQueue.Exists(  
              ConfigurationManager.AppSettings["queueName"]))  
       MessageQueue.Create(  
           ConfigurationManager.AppSettings["queueName"], true);  
        //Connect to the queue  
        MessageQueue Queue = new   
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);  
    Queue.ReceiveCompleted +=   
                 new ReceiveCompletedEventHandler(ProcessOrder);  
    Queue.BeginReceive();  
    Console.WriteLine("Order Service is running");  
    Console.ReadLine();  
}  
```

 <span data-ttu-id="1c67a-108">큐에 메시지가 수신되면 메시지 처리기 `ProcessOrder`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-108">When a message is received in the queue, the message handler `ProcessOrder` is invoked.</span></span>  

```csharp
public static void ProcessOrder(Object source,  
    ReceiveCompletedEventArgs asyncResult)  
{  
    try  
    {  
        // Connect to the queue.  
        MessageQueue Queue = (MessageQueue)source;  
        // End the asynchronous receive operation.  
        System.Messaging.Message msg =   
                     Queue.EndReceive(asyncResult.AsyncResult);  
        msg.Formatter = new System.Messaging.XmlMessageFormatter(  
                                new Type[] { typeof(PurchaseOrder) });  
        PurchaseOrder po = (PurchaseOrder) msg.Body;  
        Random statusIndexer = new Random();  
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
        Console.WriteLine("Processing {0} ", po);  
        Queue.BeginReceive();  
    }  
    catch (System.Exception ex)  
    {  
        Console.WriteLine(ex.Message);  
    }  
  
}  
```

 <span data-ttu-id="1c67a-109">서비스는 MSMQ 메시지 본문으로부터 `ProcessOrder`를 추출하고 주문을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-109">The service extracts the `ProcessOrder` from the MSMQ message body, and processes the order.</span></span>  
  
 <span data-ttu-id="1c67a-110">다음 샘플 구성에서 보여 주는 것처럼 MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-110">The MSMQ queue name is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
```xml  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="1c67a-111">큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-111">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span>  
  
 <span data-ttu-id="1c67a-112">다음 샘플 코드에서 보여 주는 것처럼 클라이언트가 구매 주문을 만들고 트랜잭션 범위 내에서 구매 주문을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-112">The client creates a purchase order and submits the purchase order within the scope of a transaction, as shown in the following sample code.</span></span>  

```csharp
// Create the purchase order  
PurchaseOrder po = new PurchaseOrder();  
// Fill in the details  
...  
  
OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");  
  
MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    client.SubmitPurchaseOrder(ordermsg);  
    scope.Complete();  
}  
Console.WriteLine("Order has been submitted:{0}", po);  
  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```

 <span data-ttu-id="1c67a-113">클라이언트는 큐에 MSMQ 메시지를 보내기 위해 사용자 지정 클라이언트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-113">The client uses a custom client in-order to send the MSMQ message to the queue.</span></span> <span data-ttu-id="1c67a-114">수신 하 고 메시지를 처리 하는 응용 프로그램 MSMQ 응용 프로그램 및 WCF 응용 프로그램이 아닌 이기 때문에 두 개의 응용 프로그램 간의 암시적인 서비스 계약은 없습니다는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-114">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="1c67a-115">따라서 이 시나리오에서는 Svcutil.exe 도구를 사용하여 프록시를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-115">So, we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>  
  
 <span data-ttu-id="1c67a-116">사용자 지정 클라이언트는 기본적으로 사용 하는 모든 WCF 응용 프로그램에 대해 동일는 `MsmqIntegration` 바인딩 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-116">The custom client is essentially the same for all WCF applications that use the `MsmqIntegration` binding to send messages.</span></span> <span data-ttu-id="1c67a-117">다른 클라이언트와 달리, 여기에는 서비스 작업 범위가 포함되지 않으며</span><span class="sxs-lookup"><span data-stu-id="1c67a-117">Unlike other clients, it does not include a range of service operations.</span></span> <span data-ttu-id="1c67a-118">메시지 제출 작업으로만 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-118">It is a submit message operation only.</span></span>  

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor  
{  
    public OrderProcessorClient(){}  
  
    public OrderProcessorClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SubmitPurchaseOrder(msg);  
    }  
}  
```

 <span data-ttu-id="1c67a-119">샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-119">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="1c67a-120">서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-120">You can see the service receive messages from the client.</span></span> <span data-ttu-id="1c67a-121">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-121">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="1c67a-122">큐를 사용하므로 클라이언트와 서비스가 동시에 실행 중일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-122">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="1c67a-123">예를 들어 클라이언트를 실행하고 종료한 다음 서비스를 다시 시작해도 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-123">For example, you could run the client, shut it down, and then start up the service and it would still receive its messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c67a-124">이 샘플을 사용하려면 메시지 큐를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-124">This sample requires the installation of Message Queuing.</span></span> <span data-ttu-id="1c67a-125">설치 지침 참조 [메시지 큐](http://go.microsoft.com/fwlink/?LinkId=94968)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-125">See the installation instructions in [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968).</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="1c67a-126">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1c67a-126">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1c67a-127">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-127">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1c67a-128">서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고</span><span class="sxs-lookup"><span data-stu-id="1c67a-128">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="1c67a-129">큐가 없으면 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-129">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="1c67a-130">서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-130">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="1c67a-131">Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="1c67a-131">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="1c67a-132">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-132">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="1c67a-133">확장 된 **기능** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-133">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="1c67a-134">마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-134">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="1c67a-135">확인 된 **트랜잭션** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-135">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="1c67a-136">입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-136">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="1c67a-137">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="1c67a-138">지침에 따라 단일 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-138">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1c67a-139">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1c67a-139">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="1c67a-140">언어별 폴더의 \service\bin\ 폴더에서 서비스 컴퓨터로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-140">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="1c67a-141">언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-141">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="1c67a-142">Client.exe.config 파일에서 클라이언트 끝점 주소를 변경하여 "." 대신 서비스 컴퓨터 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-142">In the Client.exe.config file, change the client endpoint address to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="1c67a-143">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-143">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="1c67a-144">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-144">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1c67a-145">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1c67a-146">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1c67a-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1c67a-147">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="1c67a-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1c67a-148">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c67a-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## <a name="see-also"></a><span data-ttu-id="1c67a-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c67a-149">See Also</span></span>  
 [<span data-ttu-id="1c67a-150">방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="1c67a-150">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="1c67a-151">메시지 큐</span><span class="sxs-lookup"><span data-stu-id="1c67a-151">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=94968)
