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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b9d55087eb46cc304fa2a42a3e64208d9a4fec5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="two-way-communication"></a>상호 통신
이 샘플에서는 MSMQ를 통해 트랜잭션된 대기 중인 양방향 통신을 수행하는 방법을 보여 줍니다. 이 샘플에서는 `netMsmqBinding` 바인딩을 사용합니다. 이 경우 서비스는 자체적으로 호스트되는 콘솔 응용 프로그램으로서 이를 사용하여 서비스에서 대기 중인 메시지 받는 것을 볼 수 있습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에 따라는 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)합니다.  
  
 대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다. 클라이언트는 큐로 메시지를 보내고 서비스는 큐에서 메시지를 받습니다. 따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.  
  
 이 샘플에서는 큐를 사용하는 양방향 통신을 보여 줍니다. 클라이언트는 트랜잭션의 범위 내에서 큐로 구매 주문을 보냅니다. 서비스는 주문을 받고 처리한 다음 트랜잭션의 범위 내에 있는 큐에서 주문 상태로 클라이언트를 콜백합니다. 양방향 통신을 쉽게 수행하기 위해 클라이언트와 서비스는 둘 다 큐를 사용하여 구매 주문과 주문 상태를 큐에 삽입합니다.  
  
 서비스 계약 `IOrderProcessor`는 큐를 사용하는 데 적합한 단방향 서비스 작업을 정의합니다. 서비스 작업에는 주문 상태를 보내는 데 사용되는 회신 끝점이 포함됩니다. 회신 끝점은 주문 상태를 클라이언트로 다시 보내는 큐의 URI입니다. 주문 처리 응용 프로그램에서 이 계약을 구현합니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}  
```  
  
 주문 상태를 보낼 회신 계약은 클라이언트에서 지정합니다. 클라이언트는 주문 상태 계약을 구현합니다. 서비스는 생성된 이 계약의 프록시를 사용하여 주문 상태를 클라이언트로 다시 보냅니다.  
  
```  
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```  
  
 서비스 작업은 전송된 구매 주문을 처리합니다. <xref:System.ServiceModel.OperationBehaviorAttribute>를 서비스 작업에 적용하여 큐에서 메시지를 받는 데 사용되는 트랜잭션에 자동 인리스트먼트를 지정하고 서비스 작업 완료 시 트랜잭션이 자동으로 완료되도록 지정합니다. `Orders` 클래스는 주문 처리 기능을 캡슐화합니다. 이 경우에는 구매 주문을 사전에 추가합니다. 서비스 작업이 참여하는 트랜잭션은 `Orders` 클래스의 작업에서 사용할 수 있습니다.  
  
 서비스 작업은 전송된 구매 주문을 처리할 뿐만 아니라 주문 상태에 대해 클라이언트에 다시 회신합니다.  
  
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
  
 MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다. 서비스의 끝점은 구성 파일의 System.ServiceModel 섹션에 정의됩니다.  
  
> [!NOTE]
>  MSMQ 큐 이름 및 끝점 주소는 약간 다른 주소 지정 규칙을 사용합니다. MSMQ 큐 이름은 로컬 컴퓨터에 점(.)을 사용하고, 그 경로에는 백슬래시 구분 기호를 사용합니다. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 끝점 주소에서는 net.msmq: 체계를 지정하고 로컬 컴퓨터에 "localhost"를 사용하며 경로에 슬래시를 사용합니다. 원격 컴퓨터에서 호스트되는 큐에서 읽으려면 "." 및 "localhost"를 원격 컴퓨터 이름으로 바꿉니다.  
  
 서비스는 자체 호스트됩니다. MSMQ 전송을 사용하는 경우에는 사용되는 큐를 미리 만들어야 합니다. 수동으로 또는 코드를 통해 이 작업을 수행할 수 있습니다. 이 샘플에서 서비스는 큐가 있는지 확인하고 필요한 경우 큐를 만듭니다. 큐 이름은 구성 파일에서 읽습니다. 기본 주소에서 사용 되는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에 대 한 프록시를 생성 합니다.  
  
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
  
 클라이언트에서 트랜잭션을 만듭니다. 큐와의 통신은 트랜잭션 범위 내에서 발생하므로 트랜잭션 범위를 모든 메시지가 성공하거나 실패하는 가장 작은 단위로 간주할 수 있습니다.  
  
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
  
 클라이언트 코드는 서비스로부터 주문 상태를 수신하기 위해 `IOrderStatus` 계약을 구현합니다. 이 경우 주문 상태가 출력됩니다.  
  
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
  
 주문 상태 큐는 `Main` 메서드에 생성됩니다. 다음 샘플 구성과 같이 클라이언트 구성에는 주문 상태 서비스를 호스트하는 주문 상태 서비스 구성이 포함됩니다.  
  
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
  
 샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다. 서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
 서비스에는 구매 주문 정보가 표시되어 주문 상태를 주문 상태 큐로 다시 보내고 있음을 나타냅니다.  
  
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
  
 클라이언트에는 서비스에서 보낸 주문 상태 정보가 표시됩니다.  
  
```  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
    > [!NOTE]
    >  Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.  
  
 기본적으로 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 전송 보안이 설정됩니다. MSMQ 전송 보안에 대 한 두 가지 관련 속성은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> 및 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` 기본적으로 인증 모드 설정 `Windows` 보호 수준으로 설정 되 고 `Sign`합니다. MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 하며 MSMQ의 Active Directory 통합 옵션이 설치되어 있어야 합니다. 이 기준에 맞지 않는 컴퓨터에서 이 샘플을 실행하면 오류가 발생합니다.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>작업 그룹에 속해 있거나 Active Directory 통합이 없는 컴퓨터에서 샘플을 실행하려면  
  
1.  컴퓨터가 도메인에 속해 있지 않거나 Active Directory 통합이 설치되어 있지 않은 경우에는 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.  
  
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
  
2.  클라이언트 구성에서 보안을 해제하면 다음과 같이 생성됩니다.  
  
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
  
3.  이 샘플의 서비스에서는 `OrderProcessorService`에 바인딩을 만듭니다. 바인딩이 인스턴스화된 후 코드 줄을 추가하여 보안 모드를 `None`으로 설정합니다.  
  
    ```  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4.  샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경해야 합니다.  
  
    > [!NOTE]
    >  `security mode`를 `None`으로 설정하면 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 또는 `Message` 보안을 `None`으로 설정하는 것과 같습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
  
## <a name="see-also"></a>참고 항목
