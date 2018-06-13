---
title: 서비스 트랜잭션 동작
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: e49404626f6de1bfe260f0abb692d68ad779a7ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508516"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="3df0c-102">서비스 트랜잭션 동작</span><span class="sxs-lookup"><span data-stu-id="3df0c-102">Service Transaction Behavior</span></span>
<span data-ttu-id="3df0c-103">이 샘플에서는 클라이언트에서 조정하는 트랜잭션과 ServiceBehaviorAttribute 및 OperationBehaviorAttribute의 설정을 사용하여 서비스 트랜잭션 동작을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-103">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="3df0c-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 하지만 데이터베이스 테이블을 계산기 작업에 대 한 실행 상태 저장 수행된 된 작업의 서버 로그를 유지 하기 위해 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="3df0c-105">서버 로그 테이블에 대한 지속적인 쓰기는 클라이언트에서 조정하는 트랜잭션의 결과에 영향을 받습니다. 즉, 클라이언트 트랜잭션이 완료되지 않은 경우 웹 서비스 트랜잭션은 데이터베이스의 업데이트가 커밋되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-105">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3df0c-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3df0c-107">다음 서비스 계약에서는 모든 작업을 수행하려면 트랜잭션이 요청과 함께 이동해야 한다고 정의하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-107">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",  
                    SessionMode = SessionMode.Required)]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Subtract(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Multiply(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Divide(double n);  
}  
```  
  
 <span data-ttu-id="3df0c-108">들어오는 트랜잭션 흐름을 사용하도록 설정하기 위해 서비스는 transactionFlow 특성이 `true`로 설정된 시스템 제공 wsHttpBinding으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-108">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="3df0c-109">이 바인딩은 상호 운용 가능한 WSAtomicTransactionOctober2004 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-109">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="transactionalBinding" transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="3df0c-110">서비스와 트랜잭션에 대한 연결을 모두 시작한 후에 클라이언트는 이 트랜잭션 범위 내의 몇몇 서비스 작업에 액세스한 다음 트랜잭션을 완료하고 연결을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-110">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>  
  
```  
// Create a client  
CalculatorClient client = new CalculatorClient();  
  
// Create a transaction scope with the default isolation level of Serializable  
using (TransactionScope tx = new TransactionScope())  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation.  
    double value = 100.00D;  
    Console.WriteLine("  Adding {0}, running total={1}",  
                                        value, client.Add(value));  
  
    // Call the Subtract service operation.  
    value = 45.00D;  
    Console.WriteLine("  Subtracting {0}, running total={1}",  
                                        value, client.Subtract(value));  
  
    // Call the Multiply service operation.  
    value = 9.00D;  
    Console.WriteLine("  Multiplying by {0}, running total={1}",  
                                        value, client.Multiply(value));  
  
    // Call the Divide service operation.  
    value = 15.00D;  
    Console.WriteLine("  Dividing by {0}, running total={1}",  
                                        value, client.Divide(value));  
  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
  
// Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
 <span data-ttu-id="3df0c-111">서비스에는 서비스 트랜잭션 동작에 영향을 주는 세 가지 특성이 있으며 영향을 주는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-111">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>  
  
-   <span data-ttu-id="3df0c-112">`ServiceBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="3df0c-112">On the `ServiceBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="3df0c-113">`TransactionTimeout` 속성은 트랜잭션을 완료해야 하는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-113">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="3df0c-114">이 샘플에서는 30초로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-114">In this sample it is set to 30 seconds.</span></span>  
  
    -   <span data-ttu-id="3df0c-115">`TransactionIsolationLevel` 속성은 서비스가 지원하는 격리 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-115">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="3df0c-116">이 속성은 클라이언트의 격리 수준을 일치시키는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-116">This is required to match the client's isolation level.</span></span>  
  
    -   <span data-ttu-id="3df0c-117">`ReleaseServiceInstanceOnTransactionComplete` 속성은 트랜잭션이 완료될 때 서비스 인스턴스를 재활용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-117">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="3df0c-118">이 속성을 `false`로 설정하면 서비스는 전체 작업 요청에 대해 동일한 서비스 인스턴스를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-118">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="3df0c-119">이 설정은 누계를 유지 관리하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-119">This is required to maintain the running total.</span></span> <span data-ttu-id="3df0c-120">이 속성을 `true`로 설정하면 각 작업이 완료된 후에 새 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-120">If set to `true`, a new instance is generated after each completed action.</span></span>  
  
    -   <span data-ttu-id="3df0c-121">`TransactionAutoCompleteOnSessionClose` 속성에서는 세션을 닫을 때 처리되지 않은 트랜잭션을 완료할 것인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-121">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="3df0c-122">로 설정 하 여 `false`, 개별 작업은로 설정 하거나는 `OperationBehaviorAttribute``TransactionAutoComplete` 속성을 `true` 을 명시적으로 요청에 대 한 호출에서 `SetTransactionComplete` 메서드 트랜잭션을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-122">By setting it to `false`, the individual operations are required to either set the `OperationBehaviorAttribute``TransactionAutoComplete` property to `true` or to explicitly require a call to the `SetTransactionComplete` method to complete transactions.</span></span> <span data-ttu-id="3df0c-123">이 샘플에서는 두 가지 접근 방식을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-123">This sample demonstrates both approaches.</span></span>  
  
-   <span data-ttu-id="3df0c-124">`ServiceContractAttribute`:</span><span class="sxs-lookup"><span data-stu-id="3df0c-124">On the `ServiceContractAttribute`:</span></span>  
  
    -   <span data-ttu-id="3df0c-125">`SessionMode` 속성은 서비스가 적절한 요청을 논리 세션에 상호 연결시킬지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-125">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="3df0c-126">이 서비스에는 OperationBehaviorAttribute TransactionAutoComplete 속성이 `false`로 설정된 작업(Multiply 및 Divide)이 포함되기 때문에 `SessionMode.Required`를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-126">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="3df0c-127">예를 들어 Multiply 작업은 트랜잭션을 완료하는 대신 `SetTransactionComplete` 메서드를 사용하여 완료할 Divide에 대한 이후의 호출에 의존합니다. 서비스는 이러한 작업이 동일한 세션 내에서 발생하는지 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-127">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>  
  
-   <span data-ttu-id="3df0c-128">`OperationBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="3df0c-128">On the `OperationBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="3df0c-129">`TransactionScopeRequired` 속성은 작업의 동작이 트랜잭션 범위 내에서 실행되어야 하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-129">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="3df0c-130">이 속성은 이 샘플의 모든 작업에 대해 `true`로 설정되며, 클라이언트는 해당 트랜잭션을 모든 작업으로 이동하므로 동작은 해당 클라이언트 트랜잭션의 범위 내에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-130">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>  
  
    -   <span data-ttu-id="3df0c-131">`TransactionAutoComplete` 속성은 처리되지 않은 예외가 발생하지 않는 경우 메서드가 실행되는 트랜잭션을 자동으로 완료할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-131">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="3df0c-132">이전에 설명한 대로 이 속성은 Add 및 Subtract 작업에 대해 `true`로 설정되지만 Multiply 및 Divide 작업에 대해서는 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-132">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="3df0c-133">Add 및 Subtract 작업은 자동으로 동작을 완료하고, Divide는 `SetTransactionComplete` 메서드에 대한 명시적 호출을 통해 동작을 완료하며, Multiply는 동작을 완료하는 대신 Divide와 같은 이후의 호출에 의존하고 요청하여 동작을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-133">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>  
  
 <span data-ttu-id="3df0c-134">특성을 사용하는 서비스 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-134">The attributed service implementation is as follows:</span></span>  
  
```  
[ServiceBehavior(  
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
    TransactionTimeout = "00:00:30",  
    ReleaseServiceInstanceOnTransactionComplete = false,  
    TransactionAutoCompleteOnSessionClose = false)]  
public class CalculatorService : ICalculator  
{  
    double runningTotal;  
  
    public CalculatorService()  
    {  
        Console.WriteLine("Creating new service instance...");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Add(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));  
        runningTotal = runningTotal + n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Subtract(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));  
        runningTotal = runningTotal - n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Multiply(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal * n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Divide(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal / n;  
        OperationContext.Current.SetTransactionComplete();  
        return runningTotal;  
    }  
  
    // Logging method ommitted for brevity  
}   
```  
  
 <span data-ttu-id="3df0c-135">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-135">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3df0c-136">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-136">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Starting transaction  
Performing calculations...  
  Adding 100, running total=100  
  Subtracting 45, running total=55  
  Multiplying by 9, running total=495  
  Dividing by 15, running total=33  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="3df0c-137">서비스 작업 요청의 로깅은 서비스의 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-137">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="3df0c-138">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-138">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Press <ENTER> to terminate service.  
Creating new service instance...  
  Writing row 1 to database: Adding 100 to 0  
  Writing row 2 to database: Subtracting 45 from 100  
  Writing row 3 to database: Multiplying 55 by 9  
  Writing row 4 to database: Dividing 495 by 15  
```  
  
 <span data-ttu-id="3df0c-139">서비스는 계산의 누계를 유지하는 것 외에도 인스턴스 만들기를 보고하고(이 샘플의 경우 인스턴스 하나) 작업 요청을 데이터베이스에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-139">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="3df0c-140">모든 요청이 클라이언트의 트랜잭션으로 이동하기 때문에 트랜잭션을 완료하지 못하면 모든 데이터베이스 작업이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-140">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="3df0c-141">이에 대해서는 다음과 같은 여러 가지 방법을 통해 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-141">This can be demonstrated in a number of ways:</span></span>  
  
-   <span data-ttu-id="3df0c-142">`tx.Complete`()에 대한 클라이언트의 호출을 주석으로 처리하고 다시 실행 - 그러면 클라이언트가 트랜잭션을 완료하지 않고 트랜잭션 범위를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-142">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>  
  
-   <span data-ttu-id="3df0c-143">Divide 서비스 작업에 대한 호출을 주석으로 처리 - 그러면 Multiply 작업에서 시작된 작업이 완료되지 못하고 결과적으로 클라이언트의 트랜잭션도 완료되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-143">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>  
  
-   <span data-ttu-id="3df0c-144">클라이언트의 트랜잭션 범위 내 임의의 위치에서 처리되지 않은 예외 throw - 마찬가지로 클라이언트가 트랜잭션을 완료하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-144">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>  
  
 <span data-ttu-id="3df0c-145">이 중 어느 방법을 사용해도 해당 범위 내에서 수행된 작업이 커밋되지 않으며 데이터베이스와 연결된 행 수가 증가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-145">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3df0c-146">빌드 프로세스의 일부로 데이터베이스 파일이 bin 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-146">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="3df0c-147">데이터베이스 파일의 이 복사본을 확인하여 Visual Studio 프로젝트에 포함된 파일이 아닌 로그와 관련된 행을 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-147">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3df0c-148">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3df0c-148">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3df0c-149">SQL Server 2005 Express Edition 또는 SQL Server 2005를 설치했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-149">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="3df0c-150">서비스의 App.config 파일에서 데이터베이스 `connectionString` 을 설정하거나 appSettings `usingSql` 값을 `false`로 설정하여 데이터베이스 상호 작용을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-150">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>  
  
2.  <span data-ttu-id="3df0c-151">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3df0c-152">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="3df0c-153">Microsoft MSDTC Distributed Transaction Coordinator () 네트워크 트랜잭션 흐름을 사용 하 고 WsatConfig.exe 도구를 사용 하 여 Windows Communication Foundation (WCF) 트랜잭션을 네트워크 사용을 구성 해야 컴퓨터에서 샘플을 실행 하는 경우 이 옵션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-153">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="3df0c-154">여러 컴퓨터에서 샘플을 실행할 수 있도록 MSDTC(Microsoft Distributed Transaction Coordinator)를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="3df0c-154">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>  
  
1.  <span data-ttu-id="3df0c-155">서비스 컴퓨터에서 들어오는 네트워크 트랜잭션을 허용하도록 MSDTC를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-155">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>  
  
    1.  <span data-ttu-id="3df0c-156">**시작** 메뉴 이동 **제어판**, 다음 **관리 도구**, 차례로 **구성 요소 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-156">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="3df0c-157">마우스 오른쪽 단추로 클릭 **내 컴퓨터** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-157">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="3df0c-158">에 **MSDTC** 탭을 클릭 **보안 구성**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-158">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="3df0c-159">확인 **네트워크 DTC 액세스** 및 **허용 인바운드**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-159">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5.  <span data-ttu-id="3df0c-160">클릭 **예** MS DTC 서비스를 다시 시작 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-160">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="3df0c-161">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-161">Click **OK** to close the dialog box.</span></span>  
  
2.  <span data-ttu-id="3df0c-162">서비스 컴퓨터와 클라이언트 컴퓨터에서 예외 응용 프로그램 목록에 Microsoft Distributed Transaction Coordinator(MSDTC)가 포함되도록 Windows 방화벽을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-162">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>  
  
    1.  <span data-ttu-id="3df0c-163">제어판에서 Windows 방화벽 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-163">Run the Windows Firewall application from Control Panel.</span></span>  
  
    2.  <span data-ttu-id="3df0c-164">**예외** 탭을 클릭 **프로그램 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-164">From the **Exceptions** tab, click **Add Program**.</span></span>  
  
    3.  <span data-ttu-id="3df0c-165">C:\WINDOWS\System32 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-165">Browse to the folder C:\WINDOWS\System32.</span></span>  
  
    4.  <span data-ttu-id="3df0c-166">Msdtc.exe를 선택 하 고 클릭 **열려**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-166">Select Msdtc.exe and click **Open**.</span></span>  
  
    5.  <span data-ttu-id="3df0c-167">클릭 **확인** 를 닫으려면는 **프로그램 추가** 대화 상자와 클릭 **확인** Windows 방화벽 애플릿을 닫습니다를 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-167">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>  
  
3.  <span data-ttu-id="3df0c-168">클라이언트 컴퓨터에서 나가는 네트워크 트랜잭션을 허용하도록 MSDTC를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-168">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1.  <span data-ttu-id="3df0c-169">**시작** 메뉴 이동 **제어판**, 다음 **관리 도구**, 차례로 **구성 요소 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="3df0c-170">마우스 오른쪽 단추로 클릭 **내 컴퓨터** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-170">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="3df0c-171">에 **MSDTC** 탭을 클릭 **보안 구성**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-171">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="3df0c-172">확인 **네트워크 DTC 액세스** 및 **아웃 바운드 허용**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-172">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5.  <span data-ttu-id="3df0c-173">클릭 **예** MS DTC 서비스를 다시 시작 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-173">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="3df0c-174">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-174">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3df0c-175">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-175">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3df0c-176">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3df0c-176">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3df0c-177">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="3df0c-177">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3df0c-178">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df0c-178">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`  
  
## <a name="see-also"></a><span data-ttu-id="3df0c-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3df0c-179">See Also</span></span>
