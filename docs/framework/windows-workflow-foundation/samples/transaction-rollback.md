---
title: "트랜잭션 롤백"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85ae459a8e79beba9ecffb16476b37468aeb632e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-rollback"></a><span data-ttu-id="3d569-102">트랜잭션 롤백</span><span class="sxs-lookup"><span data-stu-id="3d569-102">Transaction Rollback</span></span>
<span data-ttu-id="3d569-103">이 샘플에서는 앰비언트 <xref:System.Activities.NativeActivity>에 액세스하여 앰비언트 트랜잭션을 가져와서 명시적으로 롤백하는 사용자 지정 <xref:System.Activities.RuntimeTransactionHandle>를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-103">This sample shows how to create a custom <xref:System.Activities.NativeActivity> that accesses the ambient <xref:System.Activities.RuntimeTransactionHandle> to get the ambient transaction and explicitly roll it back.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="3d569-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="3d569-104">Sample Details</span></span>  
 <span data-ttu-id="3d569-105">워크플로에서 트랜잭션은 가장 바깥쪽 <xref:System.Activities.Statements.TransactionScope> 또는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>가 완료될 때 자동으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-105">In workflow, a transaction is automatically completed when the outermost <xref:System.Activities.Statements.TransactionScope> or <xref:System.ServiceModel.Activities.TransactedReceiveScope> completes.</span></span>  <span data-ttu-id="3d569-106">트랜잭션은 처리되지 않은 예외가 범위 경계에 전파될 때 암시적으로 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-106">A transaction implicitly rolls back when an unhandled exception propagates across the scope boundary.</span></span> <span data-ttu-id="3d569-107">그러나 예외를 throw할 필요 없이 트랜잭션을 명시적으로 롤백하는 것이 적합한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-107">However, there may be times when it makes sense to explicitly roll back a transaction without having to throw an exception.</span></span> <span data-ttu-id="3d569-108">이 경우에는 이 샘플의 활동과 같은 사용자 지정 롤백 활동을 사용하여 앰비언트 트랜잭션을 명시적으로 중단하고 선택적으로 예외 이유를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-108">In this case, you can use the custom rollback activity like the one in this sample to explicitly abort the ambient transaction and provide an optional exception reason.</span></span>  
  
 <span data-ttu-id="3d569-109">`RollbackActivity`는 <xref:System.Activities.NativeActivity>입니다. 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>을 가져오려면 실행 속성에 대한 액세스 권한이 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-109">The `RollbackActivity` is a <xref:System.Activities.NativeActivity> as it requires access to the execution properties to get the ambient <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="3d569-110">`Execute` 메서드에서 <xref:System.Activities.RuntimeTransactionHandle>을 가져와서 `null`인지 여부를 확인합니다. Null은 활동이 앰비언트 런타임 트랜잭션 없이 사용되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-110">In the `Execute` method, it obtains the <xref:System.Activities.RuntimeTransactionHandle> and checks whether it is `null`, which indicates that the activity was used without an ambient run-time transaction.</span></span> <span data-ttu-id="3d569-111">그런 다음 트랜잭션을 가져와서 `null`이 있는지 여부를 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-111">It then obtains the transaction, again checking whether `null` is present.</span></span> <span data-ttu-id="3d569-112">런타임 트랜잭션을 초기화하지 않고 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-112">It is possible to have an ambient <xref:System.Activities.RuntimeTransactionHandle> without ever initializing a run-time transaction.</span></span> <span data-ttu-id="3d569-113">마지막으로, <xref:System.Transactions.Transaction.Rollback%2A>을 호출하고 활동이 트랜잭션을 롤백했음을 나타내는 제네릭 예외 또는 사용자 제공 예외를 지정하여 트랜잭션을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-113">Finally it aborts the transaction by calling <xref:System.Transactions.Transaction.Rollback%2A> and specifying either a user-provided exception or a generic exception that states that the activity rolled back the transaction.</span></span>  
  
 <span data-ttu-id="3d569-114">데모 워크플로는 <xref:System.Activities.Statements.TransactionScope> 실행 전이나 후에 본문에서 트랜잭션 상태를 출력하는 `RollbackActivity`로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-114">The demonstration workflow consists of a <xref:System.Activities.Statements.TransactionScope> whose body prints the transaction status before and after the `RollbackActivity` executes.</span></span> <span data-ttu-id="3d569-115">트랜잭션이 롤백되었어도 <xref:System.Activities.Statements.TransactionScope>는 완료될 때까지 실행되며, 본문이 완료될 때까지 워크플로를 중단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-115">Note that even though the transaction has been rolled back, the <xref:System.Activities.Statements.TransactionScope> executes to completion and does not abort the workflow until the body completes.</span></span> <span data-ttu-id="3d569-116"><xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> 속성의 기본값은 `true`이므로 워크플로가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-116">The workflow is aborted because the <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> property defaults to `true`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3d569-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3d569-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="3d569-118">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactionRollback.sln 솔루션을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-118">Load the TransactionRollback.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d569-119">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="3d569-120">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-120">Press CTRL+F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d569-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3d569-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3d569-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3d569-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3d569-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3d569-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d569-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a><span data-ttu-id="3d569-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d569-125">See Also</span></span>  
 [<span data-ttu-id="3d569-126">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="3d569-126">Transactions</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
