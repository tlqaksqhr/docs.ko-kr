---
title: "명령형 TransactionScope에서 워크플로 실행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40a9e00659cad1dd2ab22b85f3ed15d958fd107b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a><span data-ttu-id="3fa2f-102">명령형 TransactionScope에서 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="3fa2f-102">Execute a Workflow in an Imperative TransactionScope</span></span>
<span data-ttu-id="3fa2f-103">이 샘플에서는 명령형 C# 코드에서 <xref:System.Activities.WorkflowInvoker>의 <xref:System.Transactions.Transaction>를 사용하여 워크플로를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-103">This sample shows how to execute a workflow using <xref:System.Activities.WorkflowInvoker> under a <xref:System.Transactions.Transaction> from imperative C# code.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="3fa2f-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="3fa2f-104">Sample Details</span></span>  
 <span data-ttu-id="3fa2f-105">명령형 C# 코드에서 <xref:System.Transactions.TransactionScope>는 동일한 트랜잭션 내에서 실행되는 작업 집합을 캡슐화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-105">In imperative C# code, the <xref:System.Transactions.TransactionScope> is used to encapsulate a set of work that executes under the same transaction.</span></span> <span data-ttu-id="3fa2f-106"><xref:System.Transactions.TransactionScope>는 앰비언트 트랜잭션을 만들고 <xref:System.Transactions.Transaction.Current%2A> 속성을 초기화하는 방식으로 작동합니다. 이렇게 초기화한 속성에는 해당 스레드에서 실행되는 임의의 다른 작업을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-106">The <xref:System.Transactions.TransactionScope> works by creating an ambient transaction and initializing the <xref:System.Transactions.Transaction.Current%2A> property, which can then be accessed by any work being executed on that thread.</span></span>  
  
 <span data-ttu-id="3fa2f-107">워크플로에서 이와 같은 동작을 구현하려면 런타임에 각 활동을 실행하기 전에 <xref:System.Transactions.Transaction.Current%2A>를 초기화하는 작업을 추가로 수행해야 합니다. 워크플로의 경우 각 활동 사이에 스레드 선호도가 유지되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-107">To get equivalent behavior in workflow, the runtime has to do the extra work of initializing <xref:System.Transactions.Transaction.Current%2A> before executing each activity because a workflow does not maintain thread affinity between activities.</span></span> <span data-ttu-id="3fa2f-108">이와 같은 런타임 지원이 있으면 <xref:System.Activities.WorkflowInvoker> 내의 <xref:System.Transactions.TransactionScope>로 워크플로를 실행할 때 모든 활동을 <xref:System.Transactions.TransactionScope>에서 만든 앰비언트 트랜잭션의 컨텍스트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-108">With this runtime support, the resulting behavior is that when executing a workflow with <xref:System.Activities.WorkflowInvoker> inside a <xref:System.Transactions.TransactionScope>, all activities are guaranteed to run under the context of the ambient transaction created by the <xref:System.Transactions.TransactionScope>.</span></span>  
  
 <span data-ttu-id="3fa2f-109">워크플로는 각 워크플로 인스턴스에 대해 앰비언트 트랜잭션을 하나만 가질 수 있습니다. 중첩된 트랜잭션은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-109">A workflow can have only a single ambient transaction for each workflow instance; nested transactions are not available.</span></span> <span data-ttu-id="3fa2f-110">워크플로에 <xref:System.Activities.Statements.TransactionScope> 활동이 포함되어 있더라도 새로운 내부 트랜잭션이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-110">Even if the workflow contains a <xref:System.Activities.Statements.TransactionScope> activity, this does not create a new inner transaction.</span></span> <span data-ttu-id="3fa2f-111">대신, 이와 같은 경우에는 워크플로 외부에 만들어진 앰비언트 트랜잭션이 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-111">Instead, this reuses the ambient transaction that was created outside the workflow.</span></span>  
  
 <span data-ttu-id="3fa2f-112">이 샘플에서는 새 <xref:System.Transactions.TransactionScope>를 시작하고, 트랜잭션 ID를 출력하고, <xref:System.Activities.WorkflowInvoker>를 사용하여 워크플로를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-112">The sample begins a new <xref:System.Transactions.TransactionScope>, prints the transaction ID and begins a workflow using <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="3fa2f-113">이 워크플로는 트랜잭션 ID를 다시 출력하여 동일한 트랜잭션 내에서 진행되고 있음을 확인시켜 준 다음 <xref:System.Activities.Statements.TransactionScope>를 실행한 후 과정을 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-113">The workflow prints the transaction ID again, showing that it is the same transaction, then runs a <xref:System.Activities.Statements.TransactionScope>, then completes.</span></span> <span data-ttu-id="3fa2f-114"><xref:System.Activities.WorkflowInvoker.Invoke%2A>에 대한 <xref:System.Activities.WorkflowInvoker> 호출은 동기적이므로 워크플로가 완료될 때까지 원래 스레드가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-114">The <xref:System.Activities.WorkflowInvoker.Invoke%2A> call on <xref:System.Activities.WorkflowInvoker> is synchronous so the original thread blocks until the workflow completes.</span></span> <span data-ttu-id="3fa2f-115">워크플로가 완료되고 나면 트랜잭션이 완료되고 리소스가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-115">Once the workflow is complete, the transaction is completed and resources disposed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3fa2f-116">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3fa2f-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="3fa2f-117">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ImperativeTransactionSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ImperativeTransactionSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="3fa2f-118">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3fa2f-119">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-119">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fa2f-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3fa2f-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3fa2f-122">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3fa2f-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa2f-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`