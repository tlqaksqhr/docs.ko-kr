---
title: 워크플로 트랜잭션
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66eecb9795c5a65b03559c28f2bfab0b3992bc8f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-transactions"></a>워크플로 트랜잭션
[!INCLUDE[wf1](../../../includes/wf1-md.md)]에서는 <xref:System.Transactions> 활동을 사용하여 트랜잭션된 작업 단위의 범위를 지정함으로써 <xref:System.Activities.Statements.TransactionScope> 트랜잭션에 참여할 수 있도록 지원합니다. <xref:System.Transactions.TransactionScope?displayProperty=nameWithType>는 명시적으로 완료되어야 하지만 <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> 활동은 트랜잭션이 성공적으로 완료되면 호출이 암시적으로 완료됩니다. <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동의 <xref:System.Activities.Statements.TransactionScope>에 포함되는 모든 활동은 트랜잭션에 참여합니다. WF에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 사용하여 트랜잭션을 워크플로로 전달할 수 있습니다. <xref:System.Activities.Statements.TransactionScope> 활동과 마찬가지로 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>에 포함된 모든 활동은 트랜잭션에 참여합니다. WF에서는 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>에 종속되는 활동이 <xref:System.Activities.Statements.TransactionScope> 및 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 모두에서 작동하는지 확인합니다. 시스템 제공 활동이 일부 요구 사항을 충족하지 않을 경우 <xref:System.Activities.RuntimeTransactionHandle>을 통해 사용자 지정 활동을 작성하여 고급 흐름 및 트랜잭션 제어 시나리오를 사용하도록 설정할 수 있습니다.  
  
 다음 예제에서에서 가져온는 [기본 TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) 샘플에 구성 된는 워크플로가 생성 되며는 <xref:System.Activities.Statements.Sequence> 포함 하 여 자식 활동을 포함 하는 활동은 <xref:System.Activities.Statements.TransactionScope> 활동입니다. <xref:System.Activities.Statements.TransactionScope.Body%2A>의 <xref:System.Activities.Statements.TransactionScope> 활동은 <xref:System.Activities.Statements.TransactionScope> 활동에 의해 초기화된 트랜잭션에서 실행됩니다.  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
 자세한 내용은 참조는 기본 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) 샘플과 기반 시나리오 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) 샘플입니다. 자세한 내용은 사용에 대 한 참조 <xref:System.ServiceModel.Activities.TransactedReceiveScope>, 참조 [트랜잭션을 워크플로 서비스 내부 및 외부로 흐르는](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
