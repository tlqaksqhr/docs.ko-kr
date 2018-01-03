---
title: "DependentTransaction으로 동시성 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b85a97d8-8e02-4555-95df-34c8af095148
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffda721459ef81d148d55359362fe1aeaf9e699e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-concurrency-with-dependenttransaction"></a><span data-ttu-id="7ee9c-102">DependentTransaction으로 동시성 관리</span><span class="sxs-lookup"><span data-stu-id="7ee9c-102">Managing Concurrency with DependentTransaction</span></span>
<span data-ttu-id="7ee9c-103"><xref:System.Transactions.Transaction> 개체는 <xref:System.Transactions.Transaction.DependentClone%2A> 메서드를 사용하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-103">The <xref:System.Transactions.Transaction> object is created using the <xref:System.Transactions.Transaction.DependentClone%2A> method.</span></span> <span data-ttu-id="7ee9c-104">이 개체는 다른 코드 부분(예: 작업자 스레드)이 여전히 트랜잭션에서 작업을 수행하는 동안 트랜잭션이 커밋되지 않도록 하는 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-104">Its sole purpose is to guarantee that the transaction cannot commit while some other pieces of code (for example, a worker thread) are still performing work on the transaction.</span></span> <span data-ttu-id="7ee9c-105">복제된 트랜잭션에서 수행한 작업이 완료되어 커밋할 준비가 되면 <xref:System.Transactions.DependentTransaction.Complete%2A> 메서드를 사용하여 트랜잭션 작성자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-105">When the work done within the cloned transaction is complete and ready to be committed, it can notify the creator of the transaction using the <xref:System.Transactions.DependentTransaction.Complete%2A> method.</span></span> <span data-ttu-id="7ee9c-106">따라서 데이터의 일관성과 정확성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-106">Thus, you can preserve the consistency and correctness of data.</span></span>  
  
 <span data-ttu-id="7ee9c-107"><xref:System.Transactions.DependentTransaction> 클래스는 비동기 작업 간의 일관성을 관리하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-107">The <xref:System.Transactions.DependentTransaction> class can also be used to manage concurrency between asynchronous tasks.</span></span> <span data-ttu-id="7ee9c-108">이 시나리오에서는 종속 복제본이 해당 작업을 수행하는 동안 부모가 계속해서 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-108">In this scenario, the parent can continue to execute any code while the dependent clone works on its own tasks.</span></span> <span data-ttu-id="7ee9c-109">즉, 종속 복제본이 완료될 때까지 부모의 실행이 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-109">In other words, the parent's execution is not blocked until the dependent completes.</span></span>  
  
## <a name="creating-a-dependent-clone"></a><span data-ttu-id="7ee9c-110">종속 복제본 만들기</span><span class="sxs-lookup"><span data-stu-id="7ee9c-110">Creating a Dependent Clone</span></span>  
 <span data-ttu-id="7ee9c-111">종속 트랜잭션을 만들려면 <xref:System.Transactions.Transaction.DependentClone%2A> 메서드를 호출하고 <xref:System.Transactions.DependentCloneOption> 열거를 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-111">To create a dependent transaction, call the <xref:System.Transactions.Transaction.DependentClone%2A> method and pass the <xref:System.Transactions.DependentCloneOption> enumeration as a parameter.</span></span> <span data-ttu-id="7ee9c-112">이 매개 변수는 종속 복제본이 `Commit` 메서드를 호출하여 트랜잭션을 커밋할 준비가 되었음을 나타내기 전에 부모 트랜잭션에서 <xref:System.Transactions.DependentTransaction.Complete%2A>이 호출된 경우의 트랜잭션 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-112">This parameter defines the behavior of the transaction if `Commit` is called on the parent transaction before the dependent clone indicates that it is ready for the transaction to commit (by calling the <xref:System.Transactions.DependentTransaction.Complete%2A> method).</span></span> <span data-ttu-id="7ee9c-113">이 매개 변수에 유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-113">The following values are valid for this parameter:</span></span>  
  
-   <span data-ttu-id="7ee9c-114"><xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>는 부모 트랜잭션이 시간 초과될 때까지 또는 완료를 나타내는 모든 종속 트랜잭션에서 <xref:System.Transactions.DependentTransaction.Complete%2A>가 호출될 때까지 부모 트랜잭션의 커밋 프로세스를 차단하는 종속 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-114"><xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete> creates a dependent transaction that blocks the commit process of the parent transaction until the parent transaction times out, or until <xref:System.Transactions.DependentTransaction.Complete%2A> is called on all dependents indicating their completion.</span></span> <span data-ttu-id="7ee9c-115">이 기능은 종속 트랜잭션이 완료될 때까지 클라이언트에서 부모 트랜잭션을 커밋하지 않으려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-115">This is useful when the client does not want the parent transaction to commit until the dependent transactions have completed.</span></span> <span data-ttu-id="7ee9c-116">부모가 종속 트랜잭션보다 일찍 작업을 마치고 트랜잭션에서 <xref:System.Transactions.CommittableTransaction.Commit%2A>을 호출하면 모든 종속 트랜잭션이 <xref:System.Transactions.DependentTransaction.Complete%2A>를 호출할 때까지 커밋 프로세스가 트랜잭션에 대해 추가 작업을 수행하고 새 인리스트먼트를 만들 수 있는 상태로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-116">If the parent finishes its work earlier than the dependent transaction and calls <xref:System.Transactions.CommittableTransaction.Commit%2A> on the transaction, the commit process is blocked in a state where additional work can be done on the transaction and new enlistments can be created, until all of the dependents call <xref:System.Transactions.DependentTransaction.Complete%2A>.</span></span> <span data-ttu-id="7ee9c-117">모든 트랜잭션이 작업을 완료하고 <xref:System.Transactions.DependentTransaction.Complete%2A>를 호출하면 즉시 트랜잭션의 커밋 프로세스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-117">As soon as all of them have finished their work and call <xref:System.Transactions.DependentTransaction.Complete%2A>, the commit process for the transaction begins.</span></span>  
  
-   <span data-ttu-id="7ee9c-118">반면 <xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>는 <xref:System.Transactions.CommittableTransaction.Commit%2A>가 호출되기 전에 부모 트랜잭션에서 <xref:System.Transactions.DependentTransaction.Complete%2A>이 호출되는 경우 자동으로 중단되는 종속 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-118"><xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>, on the other hand, creates a dependent transaction that automatically aborts if <xref:System.Transactions.CommittableTransaction.Commit%2A> is called on the parent transaction before <xref:System.Transactions.DependentTransaction.Complete%2A> is called.</span></span> <span data-ttu-id="7ee9c-119">이 경우 종속 트랜잭션에서 수행된 모든 작업이 하나의 트랜잭션 수명 내에서 그대로 유지되며 아무도 작업의 일부만 커밋할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-119">In this case, all the work done in the dependent transaction is intact within one transaction lifetime, and no one has a chance to commit just a portion of it.</span></span>  
  
 <span data-ttu-id="7ee9c-120"><xref:System.Transactions.DependentTransaction.Complete%2A> 메서드는 응용 프로그램이 종속 트랜잭션에서 작업을 완료할 때 한 번만 호출되어야 합니다. 그렇지 않으면 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-120">The <xref:System.Transactions.DependentTransaction.Complete%2A> method must be called only once when your application finishes its work on the dependent transaction; otherwise, a <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="7ee9c-121">이 메서드를 호출한 후에는 트랜잭션에서 추가 작업을 시도하지 말아야 합니다. 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-121">After this call is invoked, you must not attempt any additional work on the transaction, or an exception is thrown.</span></span>  
  
 <span data-ttu-id="7ee9c-122">다음 코드 예제에서는 종속 트랜잭션을 복제하고 작업자 스레드로 전달함으로써 종속 트랜잭션을 만들어 두 개의 동시 작업을 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-122">The following code example shows how to create a dependent transaction to manage two concurrent tasks by cloning a dependent transaction and passing it to a worker thread.</span></span>  
  
```csharp  
public class WorkerThread  
{  
    public void DoWork(DependentTransaction dependentTransaction)  
    {  
        Thread thread = new Thread(ThreadMethod);  
        thread.Start(dependentTransaction);   
    }  
  
    public void ThreadMethod(object transaction)   
    {   
        DependentTransaction dependentTransaction = transaction as DependentTransaction;  
        Debug.Assert(dependentTransaction != null);   
        try  
        {  
            using(TransactionScope ts = new TransactionScope(dependentTransaction))  
            {  
                /* Perform transactional work here */   
                ts.Complete();  
            }  
        }  
        finally  
        {  
            dependentTransaction.Complete();   
             dependentTransaction.Dispose();   
        }  
    }  
  
//Client code   
using(TransactionScope scope = new TransactionScope())  
{  
    Transaction currentTransaction = Transaction.Current;  
    DependentTransaction dependentTransaction;      
    dependentTransaction = currentTransaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
    WorkerThread workerThread = new WorkerThread();  
    workerThread.DoWork(dependentTransaction);  
    /* Do some transactional work here, then: */  
    scope.Complete();  
}  
```  
  
 <span data-ttu-id="7ee9c-123">클라이언트 코드에서는 앰비언트 트랜잭션도 설정하는 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-123">The client code creates a transactional scope that also sets the ambient transaction.</span></span> <span data-ttu-id="7ee9c-124">앰비언트 트랜잭션을 작업자 스레드로 전달하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-124">You should not pass the ambient transaction to the worker thread.</span></span> <span data-ttu-id="7ee9c-125">대신 현재 트랜잭션에서 <xref:System.Transactions.Transaction.DependentClone%2A> 메서드를 호출하여 현재(앰비언트) 트랜잭션을 복제하고 종속 트랜잭션을 작업자 스레드로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-125">Instead, you should clone the current (ambient) transaction by calling the <xref:System.Transactions.Transaction.DependentClone%2A> method on the current transaction, and pass the dependent to the worker thread.</span></span>  
  
 <span data-ttu-id="7ee9c-126">`ThreadMethod` 메서드는 새 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-126">The `ThreadMethod` method executes on the new thread.</span></span> <span data-ttu-id="7ee9c-127">클라이언트는 새 스레드를 시작하고 종속 트랜잭션을 `ThreadMethod` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-127">The client starts a new thread, passing the dependent transaction as the `ThreadMethod` parameter.</span></span>  
  
 <span data-ttu-id="7ee9c-128"><xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>를 사용하여 종속 트랜잭션이 만들어지므로 두 번째 스레드에서 수행한 모든 트랜잭션 작업이 완료되고 종속 트랜잭션에서 <xref:System.Transactions.DependentTransaction.Complete%2A>가 호출될 때까지 트랜잭션을 커밋할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-128">Because the dependent transaction is created with <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>, you are guaranteed that the transaction cannot be committed until all of the transactional work done on the second thread is finished and <xref:System.Transactions.DependentTransaction.Complete%2A> is called on the dependent transaction.</span></span> <span data-ttu-id="7ee9c-129">즉, 클라이언트의 범위가 종료 되는 경우 (끝날 때 트랜잭션 개체를 삭제 하려고 하면는 **를 사용 하 여** 문) 새 스레드 호출 하기 전에 <xref:System.Transactions.DependentTransaction.Complete%2A> 될때까지차단된클라이언트코드에서종속트랜잭션에대<xref:System.Transactions.DependentTransaction.Complete%2A> 에서 종속 항목에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-129">This means that if the client's scope ends (when it tries to dispose of the transaction object at the end of the **using** statement) before the new thread calls <xref:System.Transactions.DependentTransaction.Complete%2A> on the dependent transaction, the client code blocks until <xref:System.Transactions.DependentTransaction.Complete%2A> is called on the dependent.</span></span> <span data-ttu-id="7ee9c-130">그런 다음 트랜잭션이 커밋 또는 중단을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-130">Then the transaction can finish committing or aborting.</span></span>  
  
## <a name="concurrency-issues"></a><span data-ttu-id="7ee9c-131">동시성 문제</span><span class="sxs-lookup"><span data-stu-id="7ee9c-131">Concurrency Issues</span></span>  
 <span data-ttu-id="7ee9c-132"><xref:System.Transactions.DependentTransaction> 클래스를 사용할 때 주의해야 하는 몇 가지 추가 동시성 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-132">There are a few additional concurrency issues that you need to be aware of when using the <xref:System.Transactions.DependentTransaction> class:</span></span>  
  
-   <span data-ttu-id="7ee9c-133">작업자 스레드에서 트랜잭션을 롤백하지만 부모가 커밋하려고 시도하는 경우 <xref:System.Transactions.TransactionAbortedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-133">If the worker thread rolls back the transaction but the parent tries to commit it, a <xref:System.Transactions.TransactionAbortedException> is thrown.</span></span>  
  
-   <span data-ttu-id="7ee9c-134">트랜잭션의 각 작업자 스레드에 대해 새 종속 복제본을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-134">You should create a new dependent clone for each worker thread in the transaction.</span></span> <span data-ttu-id="7ee9c-135">동일한 종속 복제본을 여러 스레드로 전달하지 마십시오. 스레드 중 하나만 복제본에서 <xref:System.Transactions.DependentTransaction.Complete%2A>를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-135">Do not pass the same dependent clone to multiple threads, because only one of them can call <xref:System.Transactions.DependentTransaction.Complete%2A> on it.</span></span>  
  
-   <span data-ttu-id="7ee9c-136">작업자 스레드가 새 작업자 스레드를 생성하는 경우 종속 복제본에서 종속 복제본을 만들어 새 스레드로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ee9c-136">If the worker thread spawns a new worker thread, make sure to create a dependent clone from the dependent clone and pass it to the new thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee9c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ee9c-137">See Also</span></span>  
 <xref:System.Transactions.DependentTransaction>
