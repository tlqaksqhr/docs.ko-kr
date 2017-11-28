---
title: "단일 단계 및 다단계 트랜잭션 커밋"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 83a65f6973c64b14e17b701ba4b5562eab8641f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="f3305-102">단일 단계 및 다단계 트랜잭션 커밋</span><span class="sxs-lookup"><span data-stu-id="f3305-102">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="f3305-103">트랜잭션에 사용되는 각 리소스는 RM(리소스 관리자)에 의해 관리되고, RM의 작업은 TM(트랜잭션 관리자)에 의해 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-103">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="f3305-104">[트랜잭션에서 참가자 인 리스트 먼 트 리소스](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) 리소스 (또는 여러 리소스) 트랜잭션에 참여할 수 있습니다 어떻게을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-104">The [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="f3305-105">이 항목에서는 참여하는 리소스에서 트랜잭션 커밋을 조정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-105">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="f3305-106">트랜잭션이 끝나면 응용 프로그램이 트랜잭션을 커밋 또는 롤백하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-106">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="f3305-107">트랜잭션 관리자는 다른 리소스 관리자가 트랜잭션을 롤백하도록 응답하는 동안 일부 리소스 관리자가 커밋하도록 응답하는 경우와 같은 위험을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-107">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="f3305-108">트랜잭션에 둘 이상의 리소스가 관련된 경우 2PC(2단계 커밋)를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-108">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="f3305-109">2단계 커밋 프로토콜(준비 단계 및 커밋 단계)은 트랜잭션이 끝날 때 모든 리소스에 대한 모든 변경 내용이 함께 커밋 또는 롤백되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-109">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="f3305-110">그런 다음 모든 참가자에게 최종 결과를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-110">All the participants are then informed of the final result.</span></span> <span data-ttu-id="f3305-111">2 단계 커밋 프로토콜을 대 한 자세한 내용은 설명서를 참조 하십시오 "*트랜잭션 처리: 개념 및 기술 (데이터 관리 시스템의 Morgan Kaufmann 시리즈) ISBN:1558601902*" Jim g으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-111">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="f3305-112">단일 단계 커밋 프로토콜에 참여하여 트랜잭션의 성능을 최적화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-112">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="f3305-113">자세한 내용은 참조 [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용 하 여 최적화](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-113">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="f3305-114">트랜잭션의 결과에 대한 알림만 받고 응답에 참여하지 않으려면 <xref:System.Transactions.Transaction.TransactionCompleted> 이벤트에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-114">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="f3305-115">2PC(2단계 커밋)</span><span class="sxs-lookup"><span data-stu-id="f3305-115">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="f3305-116">첫 번째 트랜잭션 단계에서는 트랜잭션 관리자가 각 리소스를 쿼리하여 트랜잭션을 커밋 또는 롤백할지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-116">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="f3305-117">두 번째 트랜잭션 단계에서는 트랜잭션 관리자가 각 리소스에 쿼리 결과를 알리고 필요한 정리 작업을 수행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-117">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="f3305-118">이러한 종류의 트랜잭션에 참여하려면 리소스 관리자가 <xref:System.Transactions.IEnlistmentNotification> 인터페이스를 구현해야 합니다. 이 인터페이스는 2PC 중에 TM에서 알림으로 호출되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-118">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="f3305-119">다음 코드 샘플에서는 이러한 구현 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-119">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="f3305-120">준비 단계(1단계)</span><span class="sxs-lookup"><span data-stu-id="f3305-120">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="f3305-121">응용 프로그램에서 <xref:System.Transactions.CommittableTransaction.Commit%2A> 요청을 받으면 트랜잭션 관리자는 트랜잭션에 대한 각 리소스의 응답을 얻기 위해 참여하는 각 리소스에서 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 메서드를 호출하여 참여하는 모든 참가자의 준비 단계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-121">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="f3305-122"><xref:System.Transactions.IEnlistmentNotification> 인터페이스를 구현하는 리소스 관리자는 먼저 다음의 단순한 예제와 같이 <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-122">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```  
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="f3305-123">지속적인 리소스 관리자는 이 호출을 받을 경우 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 속성을 검색하여 얻을 수 있는 트랜잭션의 복구 정보와 커밋 시 트랜잭션을 완료하는 데 필요한 모든 정보를 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-123">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="f3305-124">RM이 작업자 스레드에서 이 작업을 수행할 수 있으므로 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 메서드 내에서 이 작업을 수행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-124">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="f3305-125">RM은 준비 작업을 완료할 경우 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 또는 <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> 메서드를 호출하여 커밋 또는 롤백하도록 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-125">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="f3305-126"><xref:System.Transactions.PreparingEnlistment> 클래스는 <xref:System.Transactions.Enlistment.Done%2A> 클래스에서 <xref:System.Transactions.Enlistment> 메서드를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-126">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="f3305-127">준비 단계 중에 <xref:System.Transactions.PreparingEnlistment> 콜백에서 이 메서드를 호출하면 메서드가 TM에 읽기 전용 인리스트먼트(즉, 트랜잭션에서 보호된 데이터를 읽을 수는 있지만 업데이트할 수 없는 리소스 관리자)임을 알리고 2단계의 트랜잭션 결과와 관련해서 RM이 트랜잭션 관리자로부터 더 이상 알림을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-127">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="f3305-128">모든 리소스 관리자가 <xref:System.Transactions.PreparingEnlistment.Prepared%2A>를 응답한 후 응용 프로그램에 트랜잭션 커밋 성공을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-128">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="f3305-129">커밋 단계(2단계)</span><span class="sxs-lookup"><span data-stu-id="f3305-129">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="f3305-130">트랜잭션의 두 번째 단계에서 트랜잭션 관리자는 모든 리소스 관리자로부터 준비 성공을 받을 경우(1단계가 끝날 때 모든 리소스 관리자가 <xref:System.Transactions.PreparingEnlistment.Prepared%2A>를 호출한 경우) 각 리소스 관리자에 대해 <xref:System.Transactions.IEnlistmentNotification.Commit%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-130">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="f3305-131">그런 다음 리소스 관리자가 변경 내용을 지속적으로 설정하고 커밋을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-131">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="f3305-132">리소스 관리자가 1단계에서 준비 실패를 보고한 경우 트랜잭션 관리자는 각 리소스 관리자에 대해 <xref:System.Transactions.IEnlistmentNotification.Rollback%2A>을 호출하고 응용 프로그램에 커밋 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-132">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="f3305-133">따라서 리소스 관리자는 다음 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-133">Thus, your resource manager should implement the following methods.</span></span>  
  
```  
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment    
     enlistment.Done();    
}  
```  
  
 <span data-ttu-id="f3305-134">RM은 알림 유형을 기반으로 트랜잭션을 끝내는 데 필요한 작업을 수행하고 <xref:System.Transactions.Enlistment.Done%2A> 매개 변수에서 <xref:System.Transactions.Enlistment> 메서드를 호출하여 트랜잭션이 끝났음을 TM에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-134">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="f3305-135">작업자 스레드에서 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-135">This work can be done on a worker thread.</span></span> <span data-ttu-id="f3305-136">2단계 알림이 1단계에서 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 메서드를 호출한 스레드와 동일한 스레드에서 인라인으로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-136">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="f3305-137">따라서 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> 호출 후에는 잠금 해제를 비롯하여 2단계 알림을 받기 전에 끝내야 하는 어떤 작업도 수행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-137">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="f3305-138">InDoubt 구현</span><span class="sxs-lookup"><span data-stu-id="f3305-138">Implementing InDoubt</span></span>  
 <span data-ttu-id="f3305-139">마지막으로 일시적인 리소스 관리자에 대해 <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-139">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="f3305-140">이 메서드는 트랜잭션 관리자가 하나 이상의 참가자와 연결이 끊어져 해당 상태를 알 수 없는 경우에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-140">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="f3305-141">이 경우 트랜잭션 참가자의 상태가 일치하지 않는지 나중에 조사할 수 있도록 이 사실을 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-141">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```  
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="f3305-142">단일 단계 커밋 최적화</span><span class="sxs-lookup"><span data-stu-id="f3305-142">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="f3305-143">단일 단계 커밋 프로토콜은 모든 업데이트가 명시적 코디네이션 없이 수행되므로 런타임에 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-143">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="f3305-144">이 프로토콜에 대 한 자세한 내용은 참조 하십시오. [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용 하 여 최적화](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3305-144">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3305-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3305-145">See Also</span></span>  
 [<span data-ttu-id="f3305-146">단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용 하 여 최적화</span><span class="sxs-lookup"><span data-stu-id="f3305-146">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
 [<span data-ttu-id="f3305-147">트랜잭션 참여 구성원으로 리소스를 인 리스트 먼 트</span><span class="sxs-lookup"><span data-stu-id="f3305-147">Enlisting Resources as Participants in a Transaction</span></span>](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)
