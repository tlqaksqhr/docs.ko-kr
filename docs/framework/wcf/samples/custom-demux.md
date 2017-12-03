---
title: "사용자 지정 Demux"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: "41"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d4a460adfb8076f5d2c0fe273511e6de80be4ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-demux"></a>사용자 지정 Demux
이 샘플에서는 MSMQ 메시지 헤더는 서로 다른 서비스 작업에 매핑할 수 있는 방법을 보여 줍니다. 있도록 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 사용 하는 서비스 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 에서처럼 하나의 서비스 작업을 사용 하 여 제한 되지 않습니다는 [메시지 큐에 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) 및 [메시지 큐에 Windows Communication Foundation](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) 샘플입니다.  
  
 이 샘플의 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 대기 중인 메시지를 받는 서비스를 확인할 수 있습니다.  
  
 서비스 계약은 `IOrderProcessor`이며, 큐에서 사용하는 데 적합한 단방향 서비스를 정의합니다.  
  
```  
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```  
  
 MSMQ 메시지에는 Action 헤더가 없습니다. 다양한 MSMQ 메시지를 작업 계약에 자동으로 매핑할 수 없습니다. 따라서 작업 계약이 하나만 있을 수 있습니다. 이러한 제한을 해결하기 위해 서비스에서는 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 인터페이스의 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 메서드를 구현합니다. <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 메서드를 사용하여 서비스는 지정된 메시지 헤더를 특정 서비스 작업에 매핑할 수 있습니다. 이 샘플에서는 메시지의 레이블 헤더를 서비스 작업에 매핑합니다. 작업 계약의 `Name` 매개 변수는 지정된 메시지 레이블에 대해 디스패치되어야 하는 서비스 작업을 결정합니다. 예를 들어 메시지의 레이블 헤더에 "SubmitPurchaseOrder"가 포함되어 있으면 "SubmitPurchaseOrder" 서비스 작업이 호출됩니다.  
  
```  
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```  
  
 서비스는 다음 샘플 코드와 같이 <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> 인터페이스의 <xref:System.ServiceModel.Description.IContractBehavior> 메서드를 구현해야 합니다. 이렇게 하면 사용자 지정 `OperationSelector`가 서비스 프레임워크 디스패치 런타임에 적용됩니다.  
  
```  
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```  
  
 메시지는 OperationSelector에 도달하기 전에 디스패처의 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>를 통과해야 합니다. 기본적으로 서비스에 의해 구현된 계약에서 해당 동작을 찾을 수 없으면 메시지가 거부됩니다. 이러한 문제를 방지하기 위해 다음과 같이 <xref:System.ServiceModel.Description.IEndpointBehavior>를 적용하여 모든 메시지가 `MatchAllFilterBehavior`를 통과할 수 있도록 하는 `ContractFilter`라는 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>를 구현합니다.  
  
```  
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```  
  
 서비스에서 메시지를 받으면 레이블 헤더에서 제공하는 정보를 사용하여 적합한 서비스 작업이 디스패치됩니다. 다음 샘플 코드와 같이 메시지 본문은 `PurchaseOrder` 개체로 deserialize됩니다.  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```  
  
 서비스는 자체 호스트됩니다. MSMQ를 사용할 때 사용되는 큐는 미리 만들어야 합니다. 수동으로 또는 코드를 통해 이 작업을 수행할 수 있습니다. 이 샘플의 서비스에는 큐가 있는지 확인하고 없을 경우 큐를 만드는 코드가 포함되어 있습니다. 큐 이름은 구성 파일에서 읽습니다.  
  
```  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```  
  
 MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.  
  
> [!NOTE]
>  큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점 주소는 msmq.formatname 체계를 지정하며 로컬 컴퓨터로 localhost를 사용합니다. 이 체계를 따르는 주소는 MSMQ 형식 이름 주소 지정 지침에 따라 형식이 올바르게 지정된 큐 주소입니다.  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  이 샘플을 설치 해야 [메시지 큐](http://go.microsoft.com/fwlink/?LinkId=95143)합니다.  
  
 서비스를 시작하고 클라이언트를 실행합니다.  
  
 다음과 같은 출력이 클라이언트에 표시됩니다.  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 서비스에는 다음과 같은 출력이 표시되어야 합니다.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고 큐가 없으면 큐를 만듭니다. 서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다. Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.  
  
    1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.  
  
    2.  확장 된 **기능** 탭 합니다.  
  
    3.  마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.  
  
    4.  확인 된 **트랜잭션** 상자입니다.  
  
    5.  입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.  
  
3.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
4.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
### <a name="to-run-the-sample-across-computers"></a>다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  언어별 폴더의 \service\bin\ 폴더에서 서비스 컴퓨터로 서비스 프로그램 파일을 복사합니다.  
  
2.  언어별 폴더의 \client\bin\ 폴더에서 클라이언트 프로그램 파일을 클라이언트 컴퓨터로 복사합니다.  
  
3.  Client.exe.config 파일에서 orderQueueName을 변경하여 "." 대신 서비스 컴퓨터 이름을 지정합니다.  
  
4.  서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.  
  
5.  클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a>참고 항목  
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [메시지 큐](http://go.microsoft.com/fwlink/?LinkId=95143)
