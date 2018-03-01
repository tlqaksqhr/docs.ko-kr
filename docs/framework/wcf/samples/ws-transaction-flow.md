---
title: WS Transaction Flow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf441831a205b022899999b1bf34e1505b8fb6bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ws-transaction-flow"></a>WS Transaction Flow
이 샘플에서는 클라이언트에서 조정하는 트랜잭션의 사용법과 WS-Atomic Transaction 또는 OleTransactions 프로토콜을 사용하는 트랜잭션 흐름의 클라이언트 및 서버 옵션을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 작업의 사용을 보여 주기 위해 특성을 사용 하지만 `TransactionFlowAttribute` 와 **TransactionFlowOption** 어떤 수준 트랜잭션 흐름이 활성화 된 결정 하는 열거형입니다. 흐름이 지정된 트랜잭션의 범위 내에서는 요청한 작업에 대한 로그가 데이터베이스에 기록되고 클라이언트에서 조정하는 트랜잭션이 완료될 때까지 유지됩니다. 클라이언트 트랜잭션이 완료되지 않으면 웹 서비스 트랜잭션에서 데이터베이스에 적합한 업데이트가 커밋되지 않도록 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서비스 및 트랜잭션에 대한 연결을 시작하면 클라이언트에서 여러 가지 서비스 작업에 액세스합니다. 서비스에 대한 계약은 서로 다른 `TransactionFlowOption` 설정을 보여 주는 각 작업을 사용하여 다음과 같이 정의됩니다.  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);   
}  
```  
  
 여기서는 처리될 순서대로 작업을 정의합니다.  
  
-   `Add` 연산 요청에는 흐름이 지정된 트랜잭션이 포함되어야 합니다.  
  
-   `Subtract` 연산 요청에는 흐름이 지정된 트랜잭션이 포함될 수 있습니다.  
  
-   `Multiply` 연산 요청에는 명시적으로 NotAllowed를 설정하여 흐름이 지정된 트랜잭션을 포함하지 않아야 합니다.  
  
-   `Divide` 연산 요청에는`TransactionFlow` 특성을 생략하여 흐름이 지정된 트랜잭션을 포함하지 않아야 합니다.  
  
 트랜잭션 흐름을에 바인딩을 사용 하도록 설정 하려면는 [ \<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) 적절 한 작업 특성과 함께 사용 하도록 설정 속성을 사용 해야 합니다. 이 샘플의 서비스 구성에서는 메타데이터 교환 끝점뿐만 아니라 TCP 끝점과 HTTP 끝점을 노출합니다. TCP 끝점과 HTTP 끝점 한 다음 바인딩을 사용 하 여는 [ \<transactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) 속성을 사용 합니다.  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
>  시스템 제공 netTcpBinding을 사용하면 transactionProtocol을 지정할 수 있지만 시스템 제공 wsHttpBinding에서는 상호 운용성이 보다 뛰어난 WSAtomicTransactionOctober2004 프로토콜만 사용합니다. OleTransactions 프로토콜은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트에서만 사용할 수 있습니다.  
  
 `ICalculator` 인터페이스를 구현하는 클래스에 대한 모든 메서드의 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성은 `true`로 설정되어 있습니다. 이 설정은 메서드 내에서 수행되는 모든 작업이 트랜잭션의 범위 내에서 발생하도록 선언합니다. 이 경우 수행되는 작업에는 로그 데이터베이스에 기록하는 작업이 포함됩니다. 작업 요청에 흐름이 지정된 트랜잭션이 포함되면 들어오는 트랜잭션의 범위 내에서 작업이 발생하거나 새 트랜잭션 범위가 자동으로 생성됩니다.  
  
> [!NOTE]
>  <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성은 서비스 메서드 구현에 로컬인 동작을 정의하며 트랜잭션 흐름에 대한 클라이언트의 기능이나 요구 사항은 정의하지 않습니다.  
  
```  
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```  
  
 클라이언트에서 작업에 대한 서비스의 `TransactionFlowOption`설정은`ICalculator` 인터페이스에 대해 클라이언트에서 생성한 정의에 반영됩니다. 또한 서비스의 `transactionFlow` 속성 설정은 클라이언트의 응용 프로그램 구성에 반영됩니다. 클라이언트는 다음과 같이 적합한 `endpointConfigurationName`을 선택하여 전송 및 프로토콜을 선택할 수 있습니다.  
  
```  
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```  
  
> [!NOTE]
>  이 샘플의 실제 동작은 선택한 프로토콜이나 전송에 관계없이 동일합니다.  
  
 서비스에 대한 연결을 시작하면 클라이언트는 다음과 같이 서비스 작업에 대한 호출에 따라 `TransactionScope`를 만듭니다.  
  
```  
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```  
  
 다음과 같이 작업이 호출됩니다.  
  
-   `Add` 요청에서 필요한 트랜잭션의 흐름을 서비스로 지정하고 서비스의 작업은 클라이언트의 트랜잭션 범위 내에서 발생합니다.  
  
-   첫 번째 `Subtract` 요청에서도 허용된 트랜잭션의 흐름을 서비스로 지정하고 서비스의 작업도 클라이언트의 트랜잭션 범위 내에서 발생합니다.  
  
-   두 번째 `Subtract` 요청은 `TransactionScopeOption.Suppress` 옵션으로 선언된 새 트랜잭션 범위 내에서 수행됩니다. 따라서 클라이언트의 초기 외부 트랜잭션이 표시되지 않고 요청에서 트랜잭션의 흐름을 서비스로 지정하지 않습니다. 이 접근 방식을 사용하면 필요하지 않은 경우 클라이언트에서 트랜잭션 흐름이 실행되지 않도록 하고 트랜잭션 흐름이 서비스로 지정되지 않도록 보호할 수 있습니다. 서비스의 작업은 새 트랜잭션과 연결되지 않은 트랜잭션의 범위 내에서 발생합니다.  
  
-   `Multiply` 요청은 클라이언트에서의 정의 생성 하는 서비스에 트랜잭션을 이동 하지 않는 `ICalculator` 인터페이스에 포함 되어는 <xref:System.ServiceModel.TransactionFlowAttribute> 로 설정 <xref:System.ServiceModel.TransactionFlowOption> `NotAllowed`합니다.  
  
-   `Divide` 요청에서도 `ICalculator` 인터페이스에 대해 클라이언트에서 생성한 정의에 `TransactionFlowAttribute`가 포함되지 않으므로 트랜잭션의 흐름을 서비스로 지정하지 않습니다. 또한 서비스의 작업은 또 다른 새 트랜잭션과 연결되지 않은 트랜잭션의 범위 내에서 발생합니다.  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 서비스 작업 요청의 로깅은 서비스의 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 성공적으로 실행되면 클라이언트의 트랜잭션 범위가 완료되고 해당 범위 내에서 수행된 모든 작업이 커밋됩니다. 특히 표시된 레코드 다섯 개는 서비스의 데이터베이스에 유지됩니다. 이러한 레코드 중 처음 두 개는 클라이언트의 트랜잭션 범위 내에서 발생한 것입니다.  
  
 클라이언트의 `TransactionScope`내 임의 지점에서 예외가 발생하면 트랜잭션이 완료되지 않습니다. 따라서 레코드는 데이터베이스로 커밋되지 않고 해당 범위 내에서 기록됩니다. 이 효과는 호출을 주석으로 처리하여 외부 `TransactionScope`를 완료한 후 샘플 실행을 반복하여 확인할 수 있습니다. 이러한 실행에서는 클라이언트 트랜잭션의 흐름이 마지막 세 연산으로 지정되지 않기 때문에 해당 연산(두 번째 `Subtract`, `Multiply` 및 `Divide` 요청)만 기록됩니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  지침에 따라 솔루션의 C# 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2.  SQL Server Express Edition 또는 SQL Server를 설치했고 연결 문자열이 서비스의 응용 프로그램 구성 파일에서 올바르게 설정되었는지 확인합니다. 데이터베이스를 사용하지 않고 샘플을 실행하려면 서비스의 응용 프로그램 구성 파일에서 `usingSql` 값을 `false`로 설정합니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
    > [!NOTE]
    >  다중 컴퓨터 구성의 경우 아래의 지침을 사용하여 DTC(Distributed Transaction Coordinator)를 사용하도록 설정하고 Windows SDK에서 WsatConfig.exe 도구를 사용하여 WCF 트랜잭션 네트워크 지원을 사용하도록 설정합니다. 참조 [Ws-atomic Transaction 지원 구성](http://go.microsoft.com/fwlink/?LinkId=190370) WsatConfig.exe 설정에 대 한 내용은 합니다.  
  
 한 컴퓨터에서 샘플을 실행하는지 아니면 여러 컴퓨터에서 샘플을 실행하는지 여부에 관계없이 네트워크 트랜잭션 흐름을 활성화하도록 MSDTC(Microsoft Distributed Transaction Coordinator)를 구성하고 WsatConfig.exe 도구를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 트랜잭션 네트워크 지원을 사용하도록 설정해야 합니다.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>샘플을 실행할 수 있도록 MSDTC(Microsoft Distributed Transaction Coordinator)를 구성하려면  
  
1.  Windows Server 2003 또는 Windows XP를 실행하는 서비스 컴퓨터에서 다음 지침에 따라 들어오는 네트워크 트랜잭션을 허용하도록 MSDTC를 구성합니다.  
  
    1.  **시작** 메뉴 이동 **제어판**, 다음 **관리 도구**, 차례로 **구성 요소 서비스**합니다.  
  
    2.  확장 **구성 요소 서비스**합니다. 열기는 **컴퓨터** 폴더입니다.  
  
    3.  마우스 오른쪽 단추로 클릭 **내 컴퓨터** 선택 **속성**합니다.  
  
    4.  에 **MSDTC** 탭을 클릭 **보안 구성**합니다.  
  
    5.  확인 **네트워크 DTC 액세스** 및 **허용 인바운드**합니다.  
  
    6.  클릭 **확인**, 클릭 **예** MSDTC 서비스를 다시 시작 합니다.  
  
    7.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
2.  Windows Server 2008 또는 Windows Vista를 실행하는 서비스 컴퓨터에서 다음 지침에 따라 들어오는 네트워크 트랜잭션을 허용하도록 MSDTC를 구성합니다.  
  
    1.  **시작** 메뉴 이동 **제어판**, 다음 **관리 도구**, 차례로 **구성 요소 서비스**합니다.  
  
    2.  확장 **구성 요소 서비스**합니다. 열기는 **컴퓨터** 폴더입니다. 선택 **Distributed Transaction Coordinator**합니다.  
  
    3.  마우스 오른쪽 단추로 클릭 **DTC Coordinator** 선택 **속성**합니다.  
  
    4.  에 **보안** 탭 **네트워크 DTC 액세스** 및 **인바운드 허용**합니다.  
  
    5.  클릭 **확인**, 클릭 **예** MSDTC 서비스를 다시 시작 합니다.  
  
    6.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
3.  클라이언트 컴퓨터에서 나가는 네트워크 트랜잭션을 허용하도록 MSDTC를 구성합니다.  
  
    1.  **시작** 메뉴 이동 `Control Panel`, 다음 **관리 도구**, 차례로 **구성 요소 서비스**합니다.  
  
    2.  마우스 오른쪽 단추로 클릭 **내 컴퓨터** 선택 **속성**합니다.  
  
    3.  에 **MSDTC** 탭을 클릭 **보안 구성**합니다.  
  
    4.  확인 **네트워크 DTC 액세스** 및 **아웃 바운드 허용**합니다.  
  
    5.  클릭 **확인**, 클릭 **예** MSDTC 서비스를 다시 시작 합니다.  
  
    6.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
