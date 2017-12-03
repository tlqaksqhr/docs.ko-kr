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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 680a86d453dd8ca7c78d0ca6ba60cbaa691e44f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="services-and-transactions"></a>서비스 및 트랜잭션
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램은 클라이언트 내에서 트랜잭션을 초기화하고 서비스 작업 내에서 트랜잭션을 조정할 수 있습니다. 클라이언트는 트랜잭션을 초기화하고 여러 서비스 작업을 호출하며 서비스 작업이 하나의 단위로 커밋되는지 또는 롤백되는지 확인합니다.  
  
 클라이언트 트랜잭션이 필요한 서비스 작업에 대해 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 지정하고 해당 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> 및 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성을 설정하여 서비스 계약에 트랜잭션 동작을 사용하도록 설정할 수 있습니다. <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 매개 변수는 처리되지 않은 예외가 throw되지 않을 경우 메서드가 실행하는 트랜잭션을 자동으로 완료할지 여부를 지정합니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]이러한 특성 참조 [ServiceModel 트랜잭션 특성](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)합니다.  
  
 데이터베이스 업데이트 기록처럼 서비스 작업에서 수행되고 리소스 관리자가 관리하는 작업은 클라이언트의 트랜잭션에 포함됩니다.  
  
 다음 샘플에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute> 및 <xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 서비스 측 트랜잭션 동작을 제어하는 방법을 보여 줍니다.  
  
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
  
 트랜잭션을 사용 하도록 설정할 수 있습니다 및 클라이언트를 구성 하 여 흐름의 트랜잭션과 Ws-atomictransaction 프로토콜을 사용 하는 바인딩 및 설정 서비스는 [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) 요소를 `true`표시 된 것 처럼 다음 샘플 구성 합니다.  
  
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
  
 클라이언트는 <xref:System.Transactions.TransactionScope>를 만들고 트랜잭션 범위 내에서 서비스 작업을 호출하여 트랜잭션을 시작할 수 있습니다.  
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [System.ServiceModel의 트랜잭션 지원](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [트랜잭션 모델](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [WS 트랜잭션 흐름](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
