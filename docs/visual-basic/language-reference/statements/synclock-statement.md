---
title: SyncLock 문
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: cf2aad9ec2ba67200d175fbcddfcb49afeac6efc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604980"
---
# <a name="synclock-statement"></a><span data-ttu-id="2a89a-102">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="2a89a-102">SyncLock Statement</span></span>
<span data-ttu-id="2a89a-103">블록을 실행 하기 전에 문 블록에 대 한 단독 잠금을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a89a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a89a-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="2a89a-105">요소</span><span class="sxs-lookup"><span data-stu-id="2a89a-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="2a89a-106">필수.</span><span class="sxs-lookup"><span data-stu-id="2a89a-106">Required.</span></span> <span data-ttu-id="2a89a-107">개체 참조를 가리키는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="2a89a-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-108">Optional.</span></span> <span data-ttu-id="2a89a-109">잠금을 획득 하는 경우 실행할 문 블록.</span><span class="sxs-lookup"><span data-stu-id="2a89a-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="2a89a-110">종료는 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a89a-111">설명</span><span class="sxs-lookup"><span data-stu-id="2a89a-111">Remarks</span></span>  
 <span data-ttu-id="2a89a-112">`SyncLock` 문을 여러 스레드가 동시에 문 블록을 실행 하지 않도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="2a89a-113">`SyncLock` 각 스레드가 다른 스레드에서 실행 될 때까지 블록을 입력 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="2a89a-114">가장 일반적인 용도 `SyncLock` 에서 둘 이상의 스레드에서 동시에 업데이트 되 고 데이터를 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="2a89a-115">데이터를 조작 하는 문이 중단 없이 완료도 이동 해야 하는 경우 내에 배치 된 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="2a89a-116">배타적 잠금에 의해 보호 되는 문 블록 라고도 *임계 영역*합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2a89a-117">규칙</span><span class="sxs-lookup"><span data-stu-id="2a89a-117">Rules</span></span>  
  
-   <span data-ttu-id="2a89a-118">분기입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-118">Branching.</span></span> <span data-ttu-id="2a89a-119">으로 분기할 수 없습니다는 `SyncLock` 블록 외부에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="2a89a-120">잠금 개체 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-120">Lock Object Value.</span></span> <span data-ttu-id="2a89a-121">값 `lockobject` 안 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="2a89a-122">사용 하기 전에 잠금 개체를 만들어야는 `SyncLock` 문.</span><span class="sxs-lookup"><span data-stu-id="2a89a-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="2a89a-123">값을 변경할 수 없습니다 `lockobject` 실행 하는 동안 한 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="2a89a-124">메커니즘은 잠금 개체 변경 되지 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="2a89a-125">사용할 수 없습니다는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자에는 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2a89a-126">동작</span><span class="sxs-lookup"><span data-stu-id="2a89a-126">Behavior</span></span>  
  
-   <span data-ttu-id="2a89a-127">메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-127">Mechanism.</span></span> <span data-ttu-id="2a89a-128">스레드에 도달 하면는 `SyncLock` 문을 평가 `lockobject` 식을 식에 의해 반환 된 개체에 대 한 단독 잠금을 가져올 때까지 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="2a89a-129">다른 스레드가 도달 하면는 `SyncLock` 문, 가져오지 않습니다 잠금을 첫 번째 스레드가 실행 될 때까지 `End SyncLock` 문.</span><span class="sxs-lookup"><span data-stu-id="2a89a-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="2a89a-130">보호 된 데이터.</span><span class="sxs-lookup"><span data-stu-id="2a89a-130">Protected Data.</span></span> <span data-ttu-id="2a89a-131">경우 `lockobject` 는 `Shared` 변수는 배타적 잠금을 설정 하면 클래스의 모든 인스턴스에서 스레드를 실행할 수 없도록는 `SyncLock` 다른 스레드가 실행 되는 동안 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="2a89a-132">모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="2a89a-133">경우 `lockobject` 인스턴스 변수 (하지 `Shared`), 잠금을 방지 실행 되는 현재 인스턴스에서 실행 하는 스레드는 `SyncLock` 동일한 인스턴스에 있는 다른 스레드가 동시에 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="2a89a-134">개별 인스턴스에 의해 유지 관리 하는 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="2a89a-135">획득 및 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-135">Acquisition and Release.</span></span> <span data-ttu-id="2a89a-136">A `SyncLock` 블록 처럼 동작는 `Try...Finally` 구문은 `Try` 블록에서 배타적 잠금을 획득 `lockobject` 및 `Finally` 차단 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="2a89a-137">이 인해는 `SyncLock` 블록은 블록을 종료 하는 방법에 관계 없이 잠금 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="2a89a-138">예외가 처리 되지 않은 경우에 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="2a89a-139">프레임 워크 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-139">Framework Calls.</span></span> <span data-ttu-id="2a89a-140">`SyncLock` 획득 하 고 호출 하 여 단독 잠금을 해제 하는 블록의 `Enter` 및 `Exit` 의 메서드는 `Monitor` 클래스에 <xref:System.Threading> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="2a89a-141">프로그래밍 방법</span><span class="sxs-lookup"><span data-stu-id="2a89a-141">Programming Practices</span></span>  
 <span data-ttu-id="2a89a-142">`lockobject` 식은 단독으로 클래스에 속하는 개체는 항상 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="2a89a-143">선언 해야 합니다는 `Private` 현재 인스턴스에 속한 데이터를 보호 하기 위해 개체 변수 또는 `Private Shared` 모든 인스턴스에 공통 되는 데이터를 보호 하는 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="2a89a-144">사용 하지 않아야는 `Me` 키워드를 잠금을 제공 하는 예를 들어 개체 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="2a89a-145">에 대 한 잠금 개체와 해당 참조를 사용할 수를 클래스 외부의 코드에 클래스의 인스턴스에 대 한 참조를는 `SyncLock` 블록을, 다른 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="2a89a-146">이러한 방식으로 다른 클래스와 클래스 서로 차단할 수에서 관련 없는 실행 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="2a89a-147">잠그는 경우 문자열에 동일한 문자열을 사용 하는 프로세스의 다른 코드는 동일한 잠금을 공유 하므로 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="2a89a-148">또한 사용해 서는 안는 `Me.GetType` 에 대 한 잠금 개체를 제공 하려면 메서드 데이터를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="2a89a-149">때문에 이것이 `GetType` 항상 동일한 반환 `Type` 지정된 된 클래스 이름에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="2a89a-150">외부 코드에서 호출할 수 `GetType` 클래스에 가져오고, 사용 하는 동일한 잠금 개체인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="2a89a-151">이 두 클래스에서 서로 차단 결과로 해당 `SyncLock` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a89a-152">예제</span><span class="sxs-lookup"><span data-stu-id="2a89a-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="2a89a-153">설명</span><span class="sxs-lookup"><span data-stu-id="2a89a-153">Description</span></span>  
 <span data-ttu-id="2a89a-154">다음 예제에서는 메시지의 단순 목록을 유지 관리 하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="2a89a-155">배열에서 메시지를 보유 하 고 마지막 변수에 해당 배열의 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="2a89a-156">`addAnotherMessage` 프로시저 마지막 요소를 증가 시키고 새 메시지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="2a89a-157">이러한 두 작업에 의해 보호 되는 `SyncLock` 및 `End SyncLock` 문, 마지막 요소 증가 된 후에 다른 스레드가 마지막 요소를 다시 증가 수 전에 새 메시지를 저장 해야 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="2a89a-158">경우는 `simpleMessageList` 클래스 공유 모든 인스턴스에서 해당 변수는 메시지 목록은 한 `messagesList` 및 `messagesLast` 로 선언 됩니다 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="2a89a-159">이 경우 변수 `messagesLock` 이어야 `Shared`모든 인스턴스에 사용 되는 단일 잠금 개체가 있을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a89a-160">코드</span><span class="sxs-lookup"><span data-stu-id="2a89a-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="2a89a-161">설명</span><span class="sxs-lookup"><span data-stu-id="2a89a-161">Description</span></span>  
 <span data-ttu-id="2a89a-162">다음 예제에서는 스레드를 사용 하 고 `SyncLock`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="2a89a-163">으로 `SyncLock` 문이 있으면 문 블록은 임계 영역 및 `balance` 음수 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="2a89a-164">주석으로 처리는 `SyncLock` 및 `End SyncLock` 문을 맞추고 나머지의 영향을 확인할 수는 `SyncLock` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2a89a-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a89a-165">코드</span><span class="sxs-lookup"><span data-stu-id="2a89a-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="2a89a-166">설명</span><span class="sxs-lookup"><span data-stu-id="2a89a-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a89a-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a89a-167">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="2a89a-168">스레드 동기화</span><span class="sxs-lookup"><span data-stu-id="2a89a-168">Thread Synchronization</span></span>](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="2a89a-169">스레딩</span><span class="sxs-lookup"><span data-stu-id="2a89a-169">Threading</span></span>](../../programming-guide/concepts/threading/index.md)
