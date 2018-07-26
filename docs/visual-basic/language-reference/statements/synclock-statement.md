---
title: SyncLock 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 6f5a89ebe359ca2fdae1d5545192dc2dcecca6a2
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244159"
---
# <a name="synclock-statement"></a><span data-ttu-id="ea2db-102">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="ea2db-102">SyncLock Statement</span></span>
<span data-ttu-id="ea2db-103">블록을 실행 하기 전에 문 블록에 대 한 배타적 잠금을 획득 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea2db-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea2db-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="ea2db-105">요소</span><span class="sxs-lookup"><span data-stu-id="ea2db-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="ea2db-106">필수.</span><span class="sxs-lookup"><span data-stu-id="ea2db-106">Required.</span></span> <span data-ttu-id="ea2db-107">개체 참조로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="ea2db-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-108">Optional.</span></span> <span data-ttu-id="ea2db-109">잠금을 획득할 때 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="ea2db-110">종료는 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea2db-111">설명</span><span class="sxs-lookup"><span data-stu-id="ea2db-111">Remarks</span></span>  
 <span data-ttu-id="ea2db-112">`SyncLock` 문을 사용 하면 여러 스레드가 동시에 문 블록을 실행 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="ea2db-113">`SyncLock` 블록을 입력 하 고 다른 스레드에서 실행 될 때까지 각 스레드를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="ea2db-114">가장 일반적인 사용 `SyncLock` 둘 이상의 스레드에서 동시에 업데이트할 데이터를 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="ea2db-115">데이터를 조작 하는 문을 중단 없이 완료로 이동 해야 하는 경우 배치 안에 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="ea2db-116">배타적 잠금으로 보호 된 문 블록이 라고도 함은 *임계*합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ea2db-117">규칙</span><span class="sxs-lookup"><span data-stu-id="ea2db-117">Rules</span></span>  
  
-   <span data-ttu-id="ea2db-118">분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-118">Branching.</span></span> <span data-ttu-id="ea2db-119">으로 분기할 수 없습니다는 `SyncLock` 블록 외부에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="ea2db-120">잠금 개체 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-120">Lock Object Value.</span></span> <span data-ttu-id="ea2db-121">변수의 `lockobject` 일 수 없습니다 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="ea2db-122">사용 하기 전에 잠금 개체를 만들어야을 `SyncLock` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="ea2db-123">값을 변경할 수 없습니다 `lockobject` 실행 하는 동안는 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="ea2db-124">메커니즘은 잠금 개체 그대로 유지 하는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="ea2db-125">사용할 수 없습니다는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ea2db-126">동작</span><span class="sxs-lookup"><span data-stu-id="ea2db-126">Behavior</span></span>  
  
-   <span data-ttu-id="ea2db-127">메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-127">Mechanism.</span></span> <span data-ttu-id="ea2db-128">스레드에 도달 하면 합니다 `SyncLock` 평가 문을 `lockobject` 식 식에서 반환 되는 개체에 대 한 배타적 잠금을 가져올 때까지 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="ea2db-129">다른 스레드가 도달 하면 합니다 `SyncLock` 문에서 가져오지 않습니다 잠금을 첫 번째 스레드가 실행 될 때까지 `End SyncLock` 문.</span><span class="sxs-lookup"><span data-stu-id="ea2db-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="ea2db-130">보호 된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-130">Protected Data.</span></span> <span data-ttu-id="ea2db-131">경우 `lockobject` 은 `Shared` 변수는 배타적 잠금을 설정 하면 스레드 클래스의 모든 인스턴스에서 실행 합니다 `SyncLock` 다른 스레드가 실행 되는 동안 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="ea2db-132">이 모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="ea2db-133">경우 `lockobject` 인스턴스 변수는 (되지 `Shared`), 잠금을 방지 실행의 현재 인스턴스에서 실행 하는 스레드는 `SyncLock` 동일한 인스턴스에 있는 다른 스레드와 동시에 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="ea2db-134">이 개별 인스턴스에 의해 유지 관리 하는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="ea2db-135">획득 및 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-135">Acquisition and Release.</span></span> <span data-ttu-id="ea2db-136">`SyncLock` 블록 처럼를 `Try...Finally` 는 생성 된 `Try` 블록에서 배타적 잠금을 획득 `lockobject` 및 `Finally` 차단 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="ea2db-137">이 인해는 `SyncLock` 블록은 블록을 종료 하는 방법에 관계 없이 잠금 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="ea2db-138">예외가 처리 되지 않은 경우에 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="ea2db-139">프레임 워크를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-139">Framework Calls.</span></span> <span data-ttu-id="ea2db-140">`SyncLock` 블록 획득 하 고 호출 하 여 배타적 잠금이 해제 합니다 `Enter` 및 `Exit` 의 메서드를 `Monitor` 클래스는 <xref:System.Threading> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="ea2db-141">프로그래밍 방법</span><span class="sxs-lookup"><span data-stu-id="ea2db-141">Programming Practices</span></span>  
 <span data-ttu-id="ea2db-142">`lockobject` 식은 클래스에 단독으로 속해 있는 개체에 항상 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="ea2db-143">선언 해야 합니다는 `Private` 현재 인스턴스에 속한 데이터를 보호 하기 위해 개체 변수 또는 `Private Shared` 모든 인스턴스에 공통 된 데이터를 보호 하기 위해 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="ea2db-144">사용 하지 않아야 합니다 `Me` 잠금을 제공 하는 키워드는 예를 들어 개체 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="ea2db-145">에 대 한 잠금 개체로 해당 참조를 사용할 수 클래스 외부 코드에 클래스의 인스턴스에 대 한 참조 하는 경우는 `SyncLock` 입장을 완전히 다른 블록 다양 한 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="ea2db-146">이러한 방식으로 다른 클래스와 클래스 차단할 수 서로 관련 없는 실행 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="ea2db-147">잠그는 경우 문자열에 동일한 문자열을 사용 하는 프로세스의 다른 코드가 같은 잠금을 공유 하므로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="ea2db-148">사용 하지도 말아야 합니다 `Me.GetType` 공유 데이터에 대 한 잠금 개체를 제공 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="ea2db-149">왜냐하면 `GetType` 항상 동일한 반환 `Type` 지정된 된 클래스 이름에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="ea2db-150">외부 코드를 호출할 수 `GetType` 클래스에서 사용 하는 동일한 잠금 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="ea2db-151">두 개의 클래스에서 서로 차단 합니다. 따라서 해당 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ea2db-152">예제</span><span class="sxs-lookup"><span data-stu-id="ea2db-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="ea2db-153">설명</span><span class="sxs-lookup"><span data-stu-id="ea2db-153">Description</span></span>  
 <span data-ttu-id="ea2db-154">다음 예제에서는 메시지의 단순 목록을 유지 관리 하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="ea2db-155">메시지 배열에 포함 하 고 마지막 변수에 해당 배열의 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="ea2db-156">`addAnotherMessage` 프로시저 마지막 요소를 증가 시키고 새 메시지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="ea2db-157">이러한 두 작업으로 보호 되는 `SyncLock` 및 `End SyncLock` 문을 마지막 요소가 증가 된 후에 다른 스레드가 마지막 요소를 다시 증가 수 전에 새 메시지를 저장 해야 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="ea2db-158">경우는 `simpleMessageList` 클래스가 단일 모든 인스턴스에서 해당 변수는 메시지 목록을 공유 `messagesList` 하 고 `messagesLast` 로 선언 됩니다 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="ea2db-159">이 예에서 변수 `messagesLock` 역시 `Shared`모든 인스턴스에 사용 되는 단일 잠금 개체가 있을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ea2db-160">코드</span><span class="sxs-lookup"><span data-stu-id="ea2db-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="ea2db-161">설명</span><span class="sxs-lookup"><span data-stu-id="ea2db-161">Description</span></span>  
 <span data-ttu-id="ea2db-162">다음 예제에서는 스레드 및 `SyncLock`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="ea2db-163">으로 `SyncLock` 문이 있으면 문 블록은 임계 영역이 및 `balance` 음수 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="ea2db-164">주석으로 처리 합니다 `SyncLock` 및 `End SyncLock` 문을 생략의 효과 확인 하려면를 `SyncLock` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="ea2db-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ea2db-165">코드</span><span class="sxs-lookup"><span data-stu-id="ea2db-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="ea2db-166">설명</span><span class="sxs-lookup"><span data-stu-id="ea2db-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2db-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea2db-167">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="ea2db-168">스레드 동기화</span><span class="sxs-lookup"><span data-stu-id="ea2db-168">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="ea2db-169">스레딩</span><span class="sxs-lookup"><span data-stu-id="ea2db-169">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
