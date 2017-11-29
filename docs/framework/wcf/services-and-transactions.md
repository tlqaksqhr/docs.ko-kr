---
title: "서비스 및 트랜잭션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7a206ff3d82378e825cd612a6564366ef1e07977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="services-and-transactions"></a><span data-ttu-id="3978b-102">서비스 및 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="3978b-102">Services and Transactions</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="3978b-103"> 응용 프로그램은 클라이언트 내에서 트랜잭션을 초기화하고 서비스 작업 내에서 트랜잭션을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-103"> applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="3978b-104">클라이언트는 트랜잭션을 초기화하고 여러 서비스 작업을 호출하며 서비스 작업이 하나의 단위로 커밋되는지 또는 롤백되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="3978b-105">클라이언트 트랜잭션이 필요한 서비스 작업에 대해 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 지정하고 해당 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> 및 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성을 설정하여 서비스 계약에 트랜잭션 동작을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="3978b-106"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 매개 변수는 처리되지 않은 예외가 throw되지 않을 경우 메서드가 실행하는 트랜잭션을 자동으로 완료할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="3978b-107">이러한 특성 참조 [ServiceModel 트랜잭션 특성](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-107"> these attributes, see [ServiceModel Transaction Attributes](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="3978b-108">데이터베이스 업데이트 기록처럼 서비스 작업에서 수행되고 리소스 관리자가 관리하는 작업은 클라이언트의 트랜잭션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="3978b-109">다음 샘플에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute> 및 <xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 서비스 측 트랜잭션 동작을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 <span data-ttu-id="3978b-110">트랜잭션을 사용 하도록 설정할 수 있습니다 및 클라이언트를 구성 하 여 흐름의 트랜잭션과 Ws-atomictransaction 프로토콜을 사용 하는 바인딩 및 설정 서비스는 [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) 요소를 `true`표시 된 것 처럼 다음 샘플 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"   
          binding="netTcpBinding"   
          bindingConfiguration="netTcpBindingWSAT"   
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="3978b-111">클라이언트는 <xref:System.Transactions.TransactionScope>를 만들고 트랜잭션 범위 내에서 서비스 작업을 호출하여 트랜잭션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3978b-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3978b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3978b-112">See Also</span></span>  
 [<span data-ttu-id="3978b-113">System.ServiceModel의 트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="3978b-113">Transactional Support in System.ServiceModel</span></span>](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [<span data-ttu-id="3978b-114">트랜잭션 모델</span><span class="sxs-lookup"><span data-stu-id="3978b-114">Transaction Models</span></span>](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [<span data-ttu-id="3978b-115">WS 트랜잭션 흐름</span><span class="sxs-lookup"><span data-stu-id="3978b-115">WS Transaction Flow</span></span>](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
