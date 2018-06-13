---
title: CommittableTransaction을 사용하여 명시적 트랜잭션 구현
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
ms.openlocfilehash: 1edcdefeaafbee3cfbc0810a47e64f38f9f97ddc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365685"
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a><span data-ttu-id="f0c45-102">CommittableTransaction을 사용하여 명시적 트랜잭션 구현</span><span class="sxs-lookup"><span data-stu-id="f0c45-102">Implementing an Explicit Transaction using CommittableTransaction</span></span>
<span data-ttu-id="f0c45-103"><xref:System.Transactions.CommittableTransaction> 클래스를 암시적으로 사용하는 경우와 달리 <xref:System.Transactions.TransactionScope> 클래스는 응용 프로그램이 트랜잭션을 사용할 수 있는 명시적 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-103">The <xref:System.Transactions.CommittableTransaction> class provides an explicit way for applications to use a transaction, as opposed to using the <xref:System.Transactions.TransactionScope> class implicitly.</span></span> <span data-ttu-id="f0c45-104">이 클래스는 여러 함수 호출이나 여러 스레드 호출에 같은 트랜잭션을 사용하려는 응용 프로그램에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-104">It is useful for applications that want to use the same transaction across multiple function calls or multiple thread calls.</span></span> <span data-ttu-id="f0c45-105"><xref:System.Transactions.TransactionScope> 클래스와 달리 응용 프로그램 작성기에서 특별히 <xref:System.Transactions.CommittableTransaction.Commit%2A> 및 <xref:System.Transactions.Transaction.Rollback%2A> 메서드를 호출하여 트랜잭션을 커밋하거나 중단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-105">Unlike the <xref:System.Transactions.TransactionScope> class, the application writer needs to specifically call the <xref:System.Transactions.CommittableTransaction.Commit%2A> and <xref:System.Transactions.Transaction.Rollback%2A> methods in order to commit or abort the transaction.</span></span>  
  
## <a name="overview-of-the-committabletransaction-class"></a><span data-ttu-id="f0c45-106">CommittableTransaction 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="f0c45-106">Overview of the CommittableTransaction class</span></span>  
 <span data-ttu-id="f0c45-107"><xref:System.Transactions.CommittableTransaction> 클래스는 <xref:System.Transactions.Transaction> 클래스에서 파생되므로 후자의 모든 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-107">The <xref:System.Transactions.CommittableTransaction> class derives from the <xref:System.Transactions.Transaction> class, therefore providing all the functionality of the latter.</span></span> <span data-ttu-id="f0c45-108"><xref:System.Transactions.Transaction.Rollback%2A> 개체의 롤백에 사용할 수도 있는 <xref:System.Transactions.Transaction> 클래스의 <xref:System.Transactions.CommittableTransaction> 메서드는 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-108">Specifically useful is the <xref:System.Transactions.Transaction.Rollback%2A> method on the <xref:System.Transactions.Transaction> class that can also be used to rollback a <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="f0c45-109"><xref:System.Transactions.Transaction> 클래스는 <xref:System.Transactions.CommittableTransaction> 클래스와 유사하지만 `Commit` 메서드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-109">The  <xref:System.Transactions.Transaction> class is similar to the <xref:System.Transactions.CommittableTransaction> class but does not offer a `Commit` method.</span></span> <span data-ttu-id="f0c45-110">이 클래스를 사용하면 트랜잭션의 커밋 시기에 대한 제어를 유지하면서 트랜잭션 개체(또는 개체의 복제본)를 다른 스레드에 있을 수도 있는 다른 메서드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-110">This enables you to pass the transaction object (or clones of it) to other methods (potentially on other threads) while still controlling when the transaction is committed.</span></span> <span data-ttu-id="f0c45-111">호출된 코드가 트랜잭션에 참여하고 응답할 수 있지만 <xref:System.Transactions.CommittableTransaction> 개체의 작성자만 트랜잭션을 커밋할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-111">The called code is able to enlist and vote on the transaction, but only the creator of the <xref:System.Transactions.CommittableTransaction> object has the ability to commit the transaction.</span></span>  
  
 <span data-ttu-id="f0c45-112"><xref:System.Transactions.CommittableTransaction> 클래스를 사용할 때는 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-112">You should note the followings when working with the <xref:System.Transactions.CommittableTransaction> class,</span></span>  
  
-   <span data-ttu-id="f0c45-113"><xref:System.Transactions.CommittableTransaction> 트랜잭션을 만들면 앰비언트 트랜잭션이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-113">Creating a <xref:System.Transactions.CommittableTransaction> transaction does not set the ambient transaction.</span></span> <span data-ttu-id="f0c45-114">해당되는 경우 리소스 관리자가 올바른 트랜잭션 컨텍스트에서 작동하려면 앰비언트 트랜잭션을 구체적으로 설정하고 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-114">You need to specifically set and reset the ambient transaction, to ensure that resource managers operate under the right transaction context when appropriate.</span></span> <span data-ttu-id="f0c45-115">현재 앰비언트 트랜잭션을 설정하려면 전역 <xref:System.Transactions.Transaction.Current%2A> 개체의 정적 <xref:System.Transactions.Transaction> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-115">The way to set the current ambient transaction is by setting the static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object.</span></span>  
  
-   <span data-ttu-id="f0c45-116"><xref:System.Transactions.CommittableTransaction> 개체는 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-116">A <xref:System.Transactions.CommittableTransaction> object cannot be reused.</span></span> <span data-ttu-id="f0c45-117"><xref:System.Transactions.CommittableTransaction> 개체가 커밋 또는 롤백되고 나면 다시 트랜잭션에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-117">Once a <xref:System.Transactions.CommittableTransaction> object has been committed or rolled back, it cannot be used again in a transaction.</span></span> <span data-ttu-id="f0c45-118">즉, 현재 앰비언트 트랜잭션 컨텍스트로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-118">That is, it cannot be set as the current ambient transaction context.</span></span>  
  
## <a name="creating-a-committabletransaction"></a><span data-ttu-id="f0c45-119">CommittableTransaction 만들기</span><span class="sxs-lookup"><span data-stu-id="f0c45-119">Creating a CommittableTransaction</span></span>  
 <span data-ttu-id="f0c45-120">다음 샘플에서는 새 <xref:System.Transactions.CommittableTransaction>을 만들어 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-120">The following sample creates a new <xref:System.Transactions.CommittableTransaction> and commits it.</span></span>  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 <span data-ttu-id="f0c45-121"><xref:System.Transactions.CommittableTransaction> 인스턴스를 만드는 경우 앰비언트 트랜잭션 컨텍스트가 자동으로 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-121">Creating an instance of <xref:System.Transactions.CommittableTransaction> does not automatically set the ambient transaction context.</span></span> <span data-ttu-id="f0c45-122">따라서 리소스 관리자에 대한 작업은 트랜잭션의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-122">Therefore, any operation on a resource manager is not part of that transaction.</span></span> <span data-ttu-id="f0c45-123">전역 <xref:System.Transactions.Transaction.Current%2A> 개체의 <xref:System.Transactions.Transaction>  속성은 앰비언트 트랜잭션을 설정하거나 검색하는 데 사용되며 응용 프로그램에서 수동으로 설정하여 리소스 관리자가 트랜잭션에 참여할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-123">The static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object is used to set or retrieve the ambient transaction and the application must manually set it to ensure that resource managers can participate in the transaction.</span></span> <span data-ttu-id="f0c45-124">이전의 앰비언트 트랜잭션을 저장하고 <xref:System.Transactions.CommittableTransaction> 개체의 사용을 마칠 때 복원하는 것도 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-124">It is also a good practice to save the old ambient transaction and restore it when you finish using the <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="f0c45-125">트랜잭션을 커밋하려면 명시적으로 <xref:System.Transactions.CommittableTransaction.Commit%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-125">To commit the transaction, you need to explicitly call the <xref:System.Transactions.CommittableTransaction.Commit%2A> method.</span></span> <span data-ttu-id="f0c45-126">트랜잭션을 롤백하는 경우 <xref:System.Transactions.Transaction.Rollback%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-126">For rolling back a transaction, you should call the <xref:System.Transactions.Transaction.Rollback%2A> method.</span></span> <span data-ttu-id="f0c45-127"><xref:System.Transactions.CommittableTransaction>이 커밋 또는 롤백될 때까지 트랜잭션에 관련된 모든 리소스가 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-127">It is important to note that until a <xref:System.Transactions.CommittableTransaction> has been committed or rolled back, all the resources involved in that transaction are still locked.</span></span>  
  
 <span data-ttu-id="f0c45-128">함수 호출 및 스레드에서 <xref:System.Transactions.CommittableTransaction> 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-128">A <xref:System.Transactions.CommittableTransaction> object can be used across function calls and threads.</span></span> <span data-ttu-id="f0c45-129">그러나 예외를 처리하고 오류가 발생할 경우 구체적으로 <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> 메서드를 호출하는 작업은 응용 프로그램 개발자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-129">However, it is up to the application developer to handle exceptions and specifically call the <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> method in case of failures.</span></span>  
  
## <a name="asynchronous-commit"></a><span data-ttu-id="f0c45-130">비동기 커밋</span><span class="sxs-lookup"><span data-stu-id="f0c45-130">Asynchronous Commit</span></span>  
 <span data-ttu-id="f0c45-131"><xref:System.Transactions.CommittableTransaction> 클래스는 트랜잭션의 비동기 커밋을 위한 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-131">The <xref:System.Transactions.CommittableTransaction> class also provides a mechanism for committing a transaction asynchronously.</span></span> <span data-ttu-id="f0c45-132">트랜잭션 커밋은 여러 번의 데이터베이스 액세스와 가능한 네트워크 대기 시간을 수반하므로 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-132">A transaction commit can take substantial time, as it might involve multiple database access and possible network latency.</span></span> <span data-ttu-id="f0c45-133">처리량이 많은 응용 프로그램에서 교착 상태를 방지하려는 경우 비동기 커밋을 사용하여 가능한 한 빨리 트랜잭션 작업을 완료하고 커밋 작업을 백그라운드 작업으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-133">When you want to avoid deadlocks in high throughput applications, you can use asynchronous commit to finish the transactional work as soon as possible, and run the commit operation as a background task.</span></span> <span data-ttu-id="f0c45-134"><xref:System.Transactions.CommittableTransaction.BeginCommit%2A> 클래스의 <xref:System.Transactions.CommittableTransaction.EndCommit%2A> 및 <xref:System.Transactions.CommittableTransaction> 메서드를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-134">The <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> and <xref:System.Transactions.CommittableTransaction.EndCommit%2A> methods of the <xref:System.Transactions.CommittableTransaction> class allow you to do so.</span></span>  
  
 <span data-ttu-id="f0c45-135"><xref:System.Transactions.CommittableTransaction.BeginCommit%2A>을 호출하여 보류 중인 커밋을 스레드 풀의 스레드로 디스패치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-135">You can call <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> to dispatch the commit holdup to a thread from the thread pool.</span></span> <span data-ttu-id="f0c45-136"><xref:System.Transactions.CommittableTransaction.EndCommit%2A>을 호출하여 트랜잭션이 실제로 커밋되었는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-136">You can also call <xref:System.Transactions.CommittableTransaction.EndCommit%2A> to determine if the transaction has actually been committed.</span></span> <span data-ttu-id="f0c45-137">어떤 이유로든 트랜잭션을 커밋하지 못하면 <xref:System.Transactions.CommittableTransaction.EndCommit%2A>에서 트랜잭션 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-137">If the transaction failed to commit for whatever reason, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> raises a transaction exception.</span></span> <span data-ttu-id="f0c45-138"><xref:System.Transactions.CommittableTransaction.EndCommit%2A>을 호출할 때까지 트랜잭션이 아직 커밋되지 않은 경우 트랜잭션이 커밋 또는 중단될 때까지 호출자가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-138">If the transaction is not yet committed by the time <xref:System.Transactions.CommittableTransaction.EndCommit%2A> is called, the caller is blocked until the transaction is committed or aborted.</span></span>  
  
 <span data-ttu-id="f0c45-139">비동기 커밋을 수행하는 가장 쉬운 방법은 커밋이 완료될 때 호출할 콜백 메서드를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-139">The easiest way to do an asynchronous commit is by providing a callback method, to be called when committing is finished.</span></span> <span data-ttu-id="f0c45-140">그러나 호출에 사용된 원래 <xref:System.Transactions.CommittableTransaction.EndCommit%2A> 개체에서 <xref:System.Transactions.CommittableTransaction> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-140">However, you must call the <xref:System.Transactions.CommittableTransaction.EndCommit%2A> method on the original <xref:System.Transactions.CommittableTransaction> object used to invoke the call.</span></span> <span data-ttu-id="f0c45-141">해당 개체를 가져오려면 하려면 다운 캐스트는 *IAsyncResult* 콜백 메서드의 매개 변수 때문는 <xref:System.Transactions.CommittableTransaction> 클래스 구현 <xref:System.IAsyncResult> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-141">To obtain that object, you can downcast the *IAsyncResult* parameter of the callback method, since the <xref:System.Transactions.CommittableTransaction> class implements <xref:System.IAsyncResult> class.</span></span>  
  
 <span data-ttu-id="f0c45-142">다음 예제에서는 비동기 커밋을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0c45-142">The following example shows how an asynchronous commit can be done.</span></span>  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction   
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;     
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0c45-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0c45-143">See Also</span></span>  
 [<span data-ttu-id="f0c45-144">트랜잭션 범위를 사용하여 암시적 트랜잭션 구현</span><span class="sxs-lookup"><span data-stu-id="f0c45-144">Implementing an Implicit Transaction using Transaction Scope</span></span>](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
 [<span data-ttu-id="f0c45-145">트랜잭션 처리</span><span class="sxs-lookup"><span data-stu-id="f0c45-145">Transaction Processing</span></span>](../../../../docs/framework/data/transactions/index.md)
