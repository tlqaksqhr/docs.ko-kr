---
title: 워크플로 트랜잭션
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 2bb5f6498b365f3b773eea9a5adce1ec1158a289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517256"
---
# <a name="workflow-transactions"></a><span data-ttu-id="f399a-102">워크플로 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="f399a-102">Workflow Transactions</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="f399a-103">에서는 <xref:System.Transactions> 활동을 사용하여 트랜잭션된 작업 단위의 범위를 지정함으로써 <xref:System.Activities.Statements.TransactionScope> 트랜잭션에 참여할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-103"> provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="f399a-104"><xref:System.Transactions.TransactionScope?displayProperty=nameWithType>는 명시적으로 완료되어야 하지만 <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> 활동은 트랜잭션이 성공적으로 완료되면 호출이 암시적으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="f399a-105"><xref:System.Activities.Statements.TransactionScope.Body%2A> 활동의 <xref:System.Activities.Statements.TransactionScope>에 포함되는 모든 활동은 트랜잭션에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="f399a-106">WF에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 사용하여 트랜잭션을 워크플로로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="f399a-107"><xref:System.Activities.Statements.TransactionScope> 활동과 마찬가지로 <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>에 포함된 모든 활동은 트랜잭션에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="f399a-108">WF에서는 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>에 종속되는 활동이 <xref:System.Activities.Statements.TransactionScope> 및 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 모두에서 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="f399a-109">시스템 제공 활동이 일부 요구 사항을 충족하지 않을 경우 <xref:System.Activities.RuntimeTransactionHandle>을 통해 사용자 지정 활동을 작성하여 고급 흐름 및 트랜잭션 제어 시나리오를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
 <span data-ttu-id="f399a-110">다음 예제에서에서 가져온는 [기본 TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) 샘플에 구성 된는 워크플로가 생성 되며는 <xref:System.Activities.Statements.Sequence> 포함 하 여 자식 활동을 포함 하는 활동은 <xref:System.Activities.Statements.TransactionScope> 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-110">In the following example, taken from the [Basic TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) sample, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="f399a-111"><xref:System.Activities.Statements.TransactionScope.Body%2A>의 <xref:System.Activities.Statements.TransactionScope> 활동은 <xref:System.Activities.Statements.TransactionScope> 활동에 의해 초기화된 트랜잭션에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
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
  
 <span data-ttu-id="f399a-112">자세한 내용은 참조는 기본 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) 샘플과 기반 시나리오 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-112">For more information, see the basic [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples, and the scenario based [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples.</span></span> <span data-ttu-id="f399a-113">자세한 내용은 사용에 대 한 참조 <xref:System.ServiceModel.Activities.TransactedReceiveScope>, 참조 [트랜잭션을 워크플로 서비스 내부 및 외부로 흐르는](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f399a-113">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f399a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f399a-114">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
