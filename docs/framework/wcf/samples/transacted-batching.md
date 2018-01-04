---
title: "트랜잭션된 일괄 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87d8e3e09618b214dcafb7afd82970dde54fc4fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transacted-batching"></a>트랜잭션된 일괄 처리
이 샘플에서는 MSMQ(메시지 큐)를 사용하여 트랜잭션된 읽기를 일괄 처리하는 방법을 보여 줍니다. 트랜잭션된 일괄 처리는 대기 중인 통신에서 트랜잭션된 읽기의 성능을 최적화하는 기능입니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 대기 중인 통신에서 클라이언트는 큐를 사용하여 서비스와 통신합니다. 좀더 정확하게 말하면 클라이언트는 큐에 메시지를 보내고, 서비스는 큐에서 보낸 메시지를 받습니다. 따라서 서비스와 클라이언트가 동시에 실행되고 있지 않더라도 큐를 사용하여 통신할 수 있습니다.  
  
 이 샘플에서는 트랜잭션된 일괄 처리를 보여 줍니다. 트랜잭션된 일괄 처리는 큐에 있는 많은 메시지를 읽고 처리할 때 단일 트랜잭션을 사용할 수 있도록 하는 동작입니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  서비스가 처음 실행되는 경우 서비스에서는 큐가 있는지 확인하고 큐가 없으면 큐를 만듭니다. 서비스를 처음 실행하여 큐를 만들거나 MSMQ 큐 관리자를 통해 큐를 만들 수 있습니다. Windows 2008에서 큐를 만들려면 다음 단계를 수행하세요.  
  
    1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 서버 관리자를 엽니다.  
  
    2.  확장 된 **기능** 탭 합니다.  
  
    3.  마우스 오른쪽 단추로 클릭 **개인 메시지 큐**를 선택 하 고 **새로**, **개인 큐**합니다.  
  
    4.  확인 된 **트랜잭션** 상자입니다.  
  
    5.  입력 `ServiceModelSamplesTransacted` 새 큐의 이름으로 합니다.  
  
    > [!NOTE]
    >  이 샘플에서 클라이언트는 수백 개의 메시지를 배치의 일부로 보냅니다. 일반적으로 서비스 응용 프로그램에서 이러한 작업을 처리하는 데는 어느 정도의 시간이 걸립니다.  
  
3.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
4.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>작업 그룹에 속해 있거나 Active Directory 통합이 없는 컴퓨터에서 샘플을 실행하려면  
  
1.  기본적으로 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 전송 보안이 설정됩니다. MSMQ 전송 보안에 대 한 두 가지 관련 속성은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> 및 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` 기본적으로 인증 모드 설정 `Windows` 보호 수준으로 설정 되 고 `Sign`합니다. MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 하며 MSMQ의 Active Directory 통합 옵션이 설치되어 있어야 합니다. 이 기준에 맞지 않는 컴퓨터에서 이 샘플을 실행하면 오류가 발생합니다.  
  
2.  컴퓨터가 도메인에 속해 있지 않거나 Active Directory 통합이 설치되어 있지 않은 경우에는 다음 샘플 구성과 같이 인증 모드와 보호 수준을 `None`으로 설정하여 전송 보안을 해제합니다.  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
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
  
    </system.serviceModel>  
    ```  
  
3.  샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경해야 합니다.  
  
    > [!NOTE]
    >  `security``mode`를 `None`으로 설정하는 것은 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.  
  
4.  원격 컴퓨터에서 데이터베이스를 실행하려면 데이터베이스가 상주하는 컴퓨터를 가리키도록 연결 문자열을 변경합니다.  
  
## <a name="requirements"></a>요구 사항  
 이 샘플을 실행하려면 MSMQ가 설치되어 있어야 하고 SQL이나 SQL Express가 필요합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 이 샘플에서는 트랜잭션된 일괄 처리 동작을 보여 줍니다. 트랜잭션된 일괄 처리는 MSMQ의 대기 중인 전송과 함께 제공되는 성능 최적화 기능입니다.  
  
 트랜잭션을 사용하여 메시지를 보내고 받는 경우 실제로는 서로 다른 두 개의 트랜잭션이 존재합니다. 클라이언트가 트랜잭션의 범위 내에서 메시지를 보낼 때 트랜잭션은 클라이언트 및 클라이언트 큐 관리자의 로컬에 있습니다. 서비스가 트랜잭션의 범위 내에서 메시지를 받을 때 트랜잭션은 서비스 및 수신 큐 관리자의 로컬에 있습니다. 클라이언트와 서비스가 동일한 트랜잭션에 참여하지 않고 큐에서 보내기 및 받기와 같은 작업을 수행할 때 서로 다른 트랜잭션을 사용한다는 점은 매우 중요합니다.  
  
 이 샘플에서는 단일 트랜잭션을 사용하여 여러 서비스 작업을 실행합니다. 이 트랜잭션은 성능 최적화 기능으로만 사용되면 응용 프로그램의 의미 체계에 영향을 주지 않습니다. 샘플 기반 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)합니다.  
  
## <a name="comments"></a>설명  
 이 샘플에서 클라이언트는 트랜잭션의 범위 내에서 일련의 메시지를 서비스로 보냅니다. 성능 최적화를 보여 주기 위해 많은 메시지를 보내며, 여기에서는 최대 2,500개의 메시지를 보냅니다.  
  
 그러면 서비스는 큐로 전송된 메시지를 서비스에 정의된 트랜잭션 범위 내에서 받습니다. 일괄 처리를 수행하지 않으면 각 서비스 작업 호출에 대해 2500개의 트랜잭션이 생성됩니다. 따라서 시스템 성능에 영향을 줍니다. MSMQ 큐와 `Orders` 데이터베이스라는 두 개의 리소스 관리자가 관련되어 있으므로 각 트랜잭션은 DTC 트랜잭션이 됩니다. 여기에서는 메시지 일괄 처리 및 서비스 작업 호출이 단일 트랜잭션 내에서 수행되도록 하여 훨씬 더 적은 수의 트랜잭션을 사용함으로써 성능을 최적화합니다.  
  
 다음과 같이 일괄 처리 기능을 사용합니다.  
  
-   구성에서 트랜잭션된 일괄 처리 동작 지정  
  
-   단일 트랜잭션을 사용하여 읽을 메시지 수로 일괄 처리 크기 지정  
  
-   실행할 최대 동시 일괄 처리 수 지정  
  
 이 예제에서는 트랜잭션을 커밋하기 전에 100개의 서비스 작업이 단일 트랜잭션으로 호출되도록 하여 트랜잭션 수를 줄임으로써 성능 향상을 보여 줍니다.  
  
 서비스 동작은 `TransactionScopeRequired`가 `true`로 설정된 작업 동작을 정의합니다. 따라서 큐에서 메시지를 검색할 때 사용되는 트랜잭션 범위가 메서드에서 액세스하는 리소스 관리자에서 동일하게 사용됩니다. 이 예제에서는 기본 데이터베이스를 사용하여 메시지에 포함된 구매 주문 정보를 저장합니다. 트랜잭션 범위도 메서드에서 예외가 throw될 경우 큐로 메시지가 반환되도록 설정됩니다. 이 작업 동작을 설정하지 않으면 대기 중인 채널에서 트랜잭션을 만들어 큐의 메시지를 읽고 디스패치하기 전에 자동으로 커밋하므로 작업이 실패할 경우 메시지가 손실됩니다. 가장 일반적인 시나리오는 다음 코드에 표시된 대로 큐에서 메시지를 읽는 데 사용되는 트랜잭션에 서비스 작업이 참여하는 것입니다.  
  
 `ReleaseServiceInstanceOnTransactionComplete`를 `false`로 설정합니다. 이 설정은 일괄 처리에 중요한 요구 사항입니다. `ReleaseServiceInstanceOnTransactionComplete`의 `ServiceBehaviorAttribute` 속성은 트랜잭션이 완료된 다음 서비스 인스턴스로 수행할 작업을 나타냅니다. 기본적으로 서비스 인스턴스는 트랜잭션이 완료될 때 해제됩니다. 일괄 처리에서 중요한 측면은 큐에 있는 많은 메시지를 읽고 디스패치하는 데 단일 트랜잭션을 사용한다는 점입니다. 따라서 서비스 인스턴스를 해제하면 일괄 처리 사용을 부정하여 영구적인 트랜잭션 완료로 끝납니다. 이 속성을 `true`로 설정하고 트랜잭션된 일괄 처리 동작을 끝점에 추가하면 일괄 처리 유효성 검사 동작에서 예외가 throw됩니다.  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```  
  
 `Orders` 클래스는 주문 처리를 캡슐화합니다. 이 예제에서는 구매 주문 정보로 데이터베이스를 업데이트합니다.  
  
```  
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```  
  
 일괄 처리 동작 및 구성은 서비스 응용 프로그램 구성에 지정됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  일괄 처리 크기는 시스템에 정보를 제공합니다. 예를 들어 일괄 처리 크기를 20으로 지정하면 단일 트랜잭션을 사용하여 20개의 메시지를 읽고 디스패치한 다음에 트랜잭션이 커밋됩니다. 그러나 일괄 처리 크기에 도달하기 전에 트랜잭션에서 일괄 처리를 커밋하는 경우도 있습니다.  
>   
>  트랜잭션이 생성되면 틱을 시작하는 시간 제한이 모든 트랜잭션에 연결됩니다. 이 시간 제한이 만료되면 트랜잭션이 중단됩니다. 일괄 처리 크기에 도달하기 전에 이 시간 제한이 만료될 수 있습니다. 중단으로 인해 일괄 처리 작업이 다시 실행되는 것을 방지하려면 `TransactedBatchingBehavior`에서 트랜잭션에 남은 시간을 확인해야 합니다. 트랜잭션 시간 제한의 80%가 사용되면 트랜잭션이 커밋됩니다.  
>   
>  큐에 메시지가 더 이상 없으면 일괄 처리 크기가 처리될 때까지 기다리지 않고 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>에서 트랜잭션을 커밋합니다.  
>   
>  일괄 처리 크기는 응용 프로그램에 따라 선택할 수 있습니다. 일괄 처리 크기가 너무 작으면 원하는 성능을 얻지 못할 수 있습니다. 그러나 일괄 처리 크기가 너무 크면 성능이 저하될 수 있습니다. 예를 들어 트랜잭션을 더 길게 늘리고 데이터베이스에 잠금을 유지하거나 트랜잭션이 교착 상태가 되어 일괄 처리가 롤백되고 작업을 다시 수행하도록 할 수 있습니다.  
  
 클라이언트는 트랜잭션 범위를 만듭니다. 트랜잭션 범위 내에서 큐와 통신을 수행하여 모든 메시지가 큐로 전송되거나 어떤 메시지도 큐로 전송되지 않는 가장 작은 단위로 처리되도록 합니다. 트랜잭션은 트랜잭션 범위에서 <xref:System.Transactions.TransactionScope.Complete%2A>를 호출하여 커밋합니다.  
  
```  
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
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
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```  
  
 샘플을 실행하면 클라이언트 및 서비스 동작이 서비스 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다. 서비스에서 클라이언트가 보내는 메시지를 받는 것을 볼 수 있습니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다. 큐를 사용하므로 클라이언트와 서비스가 동시에 실행 중일 필요는 없습니다. 클라이언트를 실행하고 종료한 다음 서비스를 다시 시작해도 서비스에서 계속 메시지를 받을 수 있습니다. 일괄 처리에서 메시지를 읽고 처리할 때 롤링 출력이 표시됩니다.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a>참고 항목
