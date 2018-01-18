---
title: "낙관적 동시성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4cc1ac0446f13bcc6bc1c8262eae5716302c3e2d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="58883-102">낙관적 동시성</span><span class="sxs-lookup"><span data-stu-id="58883-102">Optimistic Concurrency</span></span>
<span data-ttu-id="58883-103">다중 사용자 환경에서는 낙관적 동시성 및 비관적 동시성의 두 가지 모델을 사용하여 데이터베이스의 데이터를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-103">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="58883-104"><xref:System.Data.DataSet> 개체는 데이터를 원격으로 사용하거나 데이터와 상호 작용하는 등의 장기 실행 작업에 대해 낙관적 동시성을 사용하기에 적합하도록 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-104">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="58883-105">비관적 동시성은 데이터 소스의 행을 잠가 다른 사용자가 데이터를 수정하더라도 현재 사용자에게 영향을 미치지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-105">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="58883-106">비관적 모델에서 잠금이 적용되는 작업을 수행하면, 해당 잠금 소유자가 잠금을 해제하기 전까지 다른 사용자는 잠금과 충돌하는 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-106">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="58883-107">이 모델은 동시성 충돌이 발생하는 경우 트랜잭션 롤백에 필요한 비용보다 잠금을 통해 데이터를 보호하는 비용이 적게 들도록 데이터 경합이 높은 환경에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-107">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="58883-108">따라서 비관적 동시성 모델에서는 행을 업데이트하는 사용자가 잠금을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-108">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="58883-109">이 사용자가 업데이트 작업을 마치고 잠금을 해제할 때까지 다른 사용자는 해당 행을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-109">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="58883-110">이러한 이유로 비관적 동시성은 레코드를 프로그래밍 방식으로 처리하는 경우와 같이 잠금 시간이 짧은 경우에 가장 잘 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-110">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="58883-111">비관적 동시성 모델은 사용자가 데이터와 상호 작용하여 비교적 오랜 시간 레코드를 잠그는 경우에는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-111">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58883-112">동일한 작업에서 여러 행을 업데이트해야 하는 경우에는 비관적 잠금을 사용하는 것보다는 트랜잭션을 만드는 것이 훨씬 확장성이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-112">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="58883-113">비관적 동시성과 달리, 낙관적 동시성의 사용자는 특정 행을 읽을 때 행을 잠그지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-113">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="58883-114">이 경우 사용자가 행을 업데이트할 때 행을 읽은 후 다른 사용자가 해당 행을 변경했는지 여부를 응용 프로그램에서 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-114">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="58883-115">낙관적 동시성은 주로 데이터 경합이 낮은 환경에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-115">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="58883-116">레코드를 잠그려면 서버 리소스가 추가로 소요되기 때문에, 낙관적 동시성을 사용하면 레코드를 잠글 필요가 없어 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-116">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="58883-117">또한 레코드 잠금을 유지하기 위해서는 데이터베이스 서버와의 연결이 유지되어야 하는데,</span><span class="sxs-lookup"><span data-stu-id="58883-117">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="58883-118">낙관적 동시성 모델에서는 그럴 필요가 없기 때문에 짧은 시간에 더 많은 클라이언트가 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-118">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="58883-119">낙관적 동시성 모델에서는 한 사용자가 데이터베이스에서 값을 읽은 후 해당 값의 수정을 시도하기 전에 다른 사용자가 해당 값을 변경하면 위반이 발생한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-119">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="58883-120">다음 예제의 첫 번째 설명에는 서버에서 동시성 위반을 해결하는 방법이 가장 잘 나타나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-120">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="58883-121">다음 표에서는 낙관적 동시성의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58883-121">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="58883-122">오후 1시에 User1이 다음 값을 갖는 행을 데이터베이스에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-122">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="58883-123">**CustID 성, 이름**</span><span class="sxs-lookup"><span data-stu-id="58883-123">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="58883-124">101 Smith Bob</span><span class="sxs-lookup"><span data-stu-id="58883-124">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="58883-125">열 이름</span><span class="sxs-lookup"><span data-stu-id="58883-125">Column name</span></span>|<span data-ttu-id="58883-126">원래 값</span><span class="sxs-lookup"><span data-stu-id="58883-126">Original value</span></span>|<span data-ttu-id="58883-127">현재 값</span><span class="sxs-lookup"><span data-stu-id="58883-127">Current value</span></span>|<span data-ttu-id="58883-128">데이터베이스 값</span><span class="sxs-lookup"><span data-stu-id="58883-128">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="58883-129">CustID</span><span class="sxs-lookup"><span data-stu-id="58883-129">CustID</span></span>|<span data-ttu-id="58883-130">101</span><span class="sxs-lookup"><span data-stu-id="58883-130">101</span></span>|<span data-ttu-id="58883-131">101</span><span class="sxs-lookup"><span data-stu-id="58883-131">101</span></span>|<span data-ttu-id="58883-132">101</span><span class="sxs-lookup"><span data-stu-id="58883-132">101</span></span>|  
|<span data-ttu-id="58883-133">LastName</span><span class="sxs-lookup"><span data-stu-id="58883-133">LastName</span></span>|<span data-ttu-id="58883-134">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-134">Smith</span></span>|<span data-ttu-id="58883-135">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-135">Smith</span></span>|<span data-ttu-id="58883-136">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-136">Smith</span></span>|  
|<span data-ttu-id="58883-137">FirstName</span><span class="sxs-lookup"><span data-stu-id="58883-137">FirstName</span></span>|<span data-ttu-id="58883-138">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-138">Bob</span></span>|<span data-ttu-id="58883-139">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-139">Bob</span></span>|<span data-ttu-id="58883-140">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-140">Bob</span></span>|  
  
 <span data-ttu-id="58883-141">오후 1시 1분에 User2가 같은 행을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-141">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="58883-142">오후 1시 03분에 User2 변경 **FirstName** "Robert"을 "Bob"에서 데이터베이스를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-142">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="58883-143">열 이름</span><span class="sxs-lookup"><span data-stu-id="58883-143">Column name</span></span>|<span data-ttu-id="58883-144">원래 값</span><span class="sxs-lookup"><span data-stu-id="58883-144">Original value</span></span>|<span data-ttu-id="58883-145">현재 값</span><span class="sxs-lookup"><span data-stu-id="58883-145">Current value</span></span>|<span data-ttu-id="58883-146">데이터베이스 값</span><span class="sxs-lookup"><span data-stu-id="58883-146">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="58883-147">CustID</span><span class="sxs-lookup"><span data-stu-id="58883-147">CustID</span></span>|<span data-ttu-id="58883-148">101</span><span class="sxs-lookup"><span data-stu-id="58883-148">101</span></span>|<span data-ttu-id="58883-149">101</span><span class="sxs-lookup"><span data-stu-id="58883-149">101</span></span>|<span data-ttu-id="58883-150">101</span><span class="sxs-lookup"><span data-stu-id="58883-150">101</span></span>|  
|<span data-ttu-id="58883-151">LastName</span><span class="sxs-lookup"><span data-stu-id="58883-151">LastName</span></span>|<span data-ttu-id="58883-152">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-152">Smith</span></span>|<span data-ttu-id="58883-153">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-153">Smith</span></span>|<span data-ttu-id="58883-154">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-154">Smith</span></span>|  
|<span data-ttu-id="58883-155">FirstName</span><span class="sxs-lookup"><span data-stu-id="58883-155">FirstName</span></span>|<span data-ttu-id="58883-156">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-156">Bob</span></span>|<span data-ttu-id="58883-157">Robert</span><span class="sxs-lookup"><span data-stu-id="58883-157">Robert</span></span>|<span data-ttu-id="58883-158">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-158">Bob</span></span>|  
  
 <span data-ttu-id="58883-159">이 시점에서 업데이트할 때의 데이터베이스 값과 User2가 가진 원래 값이 일치하므로 업데이트는 성공적으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="58883-159">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="58883-160">오후 1시 5분에 User1이 "Bob"의 이름을 "James"로 변경하고 해당 행을 업데이트하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-160">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="58883-161">열 이름</span><span class="sxs-lookup"><span data-stu-id="58883-161">Column name</span></span>|<span data-ttu-id="58883-162">원래 값</span><span class="sxs-lookup"><span data-stu-id="58883-162">Original value</span></span>|<span data-ttu-id="58883-163">현재 값</span><span class="sxs-lookup"><span data-stu-id="58883-163">Current value</span></span>|<span data-ttu-id="58883-164">데이터베이스 값</span><span class="sxs-lookup"><span data-stu-id="58883-164">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="58883-165">CustID</span><span class="sxs-lookup"><span data-stu-id="58883-165">CustID</span></span>|<span data-ttu-id="58883-166">101</span><span class="sxs-lookup"><span data-stu-id="58883-166">101</span></span>|<span data-ttu-id="58883-167">101</span><span class="sxs-lookup"><span data-stu-id="58883-167">101</span></span>|<span data-ttu-id="58883-168">101</span><span class="sxs-lookup"><span data-stu-id="58883-168">101</span></span>|  
|<span data-ttu-id="58883-169">LastName</span><span class="sxs-lookup"><span data-stu-id="58883-169">LastName</span></span>|<span data-ttu-id="58883-170">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-170">Smith</span></span>|<span data-ttu-id="58883-171">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-171">Smith</span></span>|<span data-ttu-id="58883-172">Smith</span><span class="sxs-lookup"><span data-stu-id="58883-172">Smith</span></span>|  
|<span data-ttu-id="58883-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="58883-173">FirstName</span></span>|<span data-ttu-id="58883-174">Bob</span><span class="sxs-lookup"><span data-stu-id="58883-174">Bob</span></span>|<span data-ttu-id="58883-175">James</span><span class="sxs-lookup"><span data-stu-id="58883-175">James</span></span>|<span data-ttu-id="58883-176">Robert</span><span class="sxs-lookup"><span data-stu-id="58883-176">Robert</span></span>|  
  
 <span data-ttu-id="58883-177">이 시점에서 데이터베이스 값("Robert")과 User1이 예상한 원래 값("Bob")이 일치하지 않기 때문에 낙관적 동시성 위반이 발생하게 되며,</span><span class="sxs-lookup"><span data-stu-id="58883-177">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="58883-178">동시성 위반을 통해 업데이트가 실패했음을 간단하게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-178">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="58883-179">User2가 제공한 변경 내용을 User1이 제공한 내용으로 덮어쓸지, 아니면 User1의 변경 내용을 취소할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-179">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="58883-180">낙관적 동시성 위반 테스트</span><span class="sxs-lookup"><span data-stu-id="58883-180">Testing for Optimistic Concurrency Violations</span></span>  
 <span data-ttu-id="58883-181">여러 가지 기법을 사용하여 낙관적 동시성 위반을 테스트할 수 있는데,</span><span class="sxs-lookup"><span data-stu-id="58883-181">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="58883-182">그 중 하나가 테이블에 타임스탬프 열을 포함시키는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="58883-182">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="58883-183">일반적으로 데이터베이스에서는 레코드가 마지막으로 업데이트된 날짜와 시간을 식별하기 위해 타임스탬프 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-183">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="58883-184">이 기법을 사용하면 타임스탬프 열이 테이블 정의에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-184">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="58883-185">타임스탬프는 레코드가 업데이트될 때마다 현재 날짜와 시간을 적용하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-185">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="58883-186">낙관적 동시성 위반을 테스트하는 경우, 타임스탬프 열은 테이블의 내용에 대한 모든 쿼리와 함께 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-186">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="58883-187">업데이트를 시도하면 데이터베이스의 타임스탬프 값과 수정된 행에 포함된 원래 타임스탬프 값이 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-187">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="58883-188">두 값이 일치하면 업데이트가 수행되고 업데이트를 적용하기 위해 타임스탬프 열이 현재 시간에 맞게 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-188">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="58883-189">반대로, 두 값이 일치하지 않으면 낙관적 동시성 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-189">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="58883-190">원래 열의 모든 값이 데이터베이스에 있는 해당 값과 계속 일치하는지를 확인하여 낙관적 동시성 위반을 테스트하는 기법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-190">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="58883-191">예를 들어, 다음과 같은 쿼리를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="58883-191">For example, consider the following query:</span></span>  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="58883-192">행을 업데이트할 때 낙관적 동시성 위반을 테스트 하려면 **Table1**, 다음 UPDATE 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-192">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="58883-193">원래 값과 데이터베이스의 값이 일치하면 업데이트가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-193">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="58883-194">특정 값을 수정한 경우 WHERE 절과 일치하는 항목을 찾을 수 없으므로 업데이트를 수행하더라도 해당 행은 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-194">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="58883-195">항상 쿼리에 고유한 기본 키 값을 반환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-195">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="58883-196">그렇지 않으면 이전 UPDATE 문이 의도했던 것과는 달리 둘 이상의 행을 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-196">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="58883-197">데이터 소스의 열에 null이 허용되는 경우에는 일치하는 null 참조를 로컬 테이블 및 데이터 소스에서도 확인하도록 WHERE 절을 확장해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-197">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="58883-198">예를 들어, 다음 UPDATE 문은 로컬 행의 null 참조가 데이터 소스의 null 참조와 일치하는지 또는 로컬 행의 값이 데이터 소스의 값과 계속 일치하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-198">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="58883-199">낙관적 동시성 모델을 사용할 때는 덜 제한적인 조건을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-199">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="58883-200">예를 들어, WHERE 절에 기본 키 열만 사용하면 마지막 쿼리 이후에 다른 열이 업데이트되었는지 여부와 상관없이 데이터를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="58883-200">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="58883-201">또한 특정 열에 대해서만 WHERE 절을 사용할 수도 있는데, 이 경우 마지막으로 쿼리된 이후에 특정 필드가 업데이트되지 않았으면 데이터를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="58883-201">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="58883-202">DataAdapter.RowUpdated 이벤트</span><span class="sxs-lookup"><span data-stu-id="58883-202">The DataAdapter.RowUpdated Event</span></span>  
 <span data-ttu-id="58883-203">**RowUpdated** 의 이벤트는 <xref:System.Data.Common.DataAdapter> 개체를 낙관적 동시성 위반의 응용 프로그램에 대 한 알림을 제공할를 앞에서 설명한 기법과 함께 함께에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-203">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="58883-204">**RowUpdated** 를 업데이트 하려는 각 시도 후에 발생 한 **Modified** 에서 행는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-204">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="58883-205">이로써 예외 발생 시의 처리와 사용자 지정 오류 정보 및 다시 시도 논리 등의 추가를 포함하여 특별한 처리 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58883-205">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="58883-206"><xref:System.Data.Common.RowUpdatedEventArgs> 반환 개체는 **RecordsAffected** 테이블의 수정된 된 행에 대 한 특정 업데이트 명령으로 영향을 받는 행 수를 포함 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="58883-206">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="58883-207">낙관적 동시성을 테스트 하도록 업데이트 명령을 설정 하 여는 **RecordsAffected** 속성은, 결과적으로, 반환 값이 0 낙관적 동시성 위반이 발생 했을 때 업데이트 된 레코드가 없으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-207">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="58883-208">또한 이 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="58883-208">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="58883-209">**RowUpdated** 이벤트를 사용 하면이 항목을 처리 하 고 적절 한 설정 하 여 예외를 방지할 수 있습니다 **RowUpdatedEventArgs.Status** 같은 값  **UpdateStatus.SkipCurrentRow**합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-209">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="58883-210">에 대 한 자세한 내용은 **RowUpdated** 이벤트 참조 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-210">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="58883-211">설정할 수 있습니다 **DataAdapter.ContinueUpdateOnError** 를 **true**를 호출 하기 전에 **업데이트**는 에저장된오류정보에응답할**RowError** 경우 속성의 특정 행의 **업데이트** 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-211">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="58883-212">자세한 내용은 참조 [행 오류 정보](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-212">For more information, see [Row Error Information](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="58883-213">낙관적 동시성 예제</span><span class="sxs-lookup"><span data-stu-id="58883-213">Optimistic Concurrency Example</span></span>  
 <span data-ttu-id="58883-214">다음은 설정 하는 간단한 예제는 **UpdateCommand** 의 **DataAdapter** 낙관적 동시성을 테스트 하려면 다음 사용 하 여는 **RowUpdated** 를 테스트 하는 이벤트 낙관적 동시성 위반 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58883-214">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="58883-215">낙관적 동시성 위반이 발생 하는 경우 응용 프로그램 설정의 **RowError** 낙관적 동시성 위반을 반영 하도록 업데이트에 대 한 발급 하는 행의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58883-215">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="58883-216">UPDATE 명령의 WHERE 절에 전달 된 매개 변수 값에 매핑되는 참고는 **원래** 은 해당 열의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58883-216">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = dataSet.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName, connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="58883-217">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58883-217">See Also</span></span>  
 [<span data-ttu-id="58883-218">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="58883-218">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="58883-219">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="58883-219">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="58883-220">행 오류 정보</span><span class="sxs-lookup"><span data-stu-id="58883-220">Row Error Information</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 [<span data-ttu-id="58883-221">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="58883-221">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="58883-222">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="58883-222">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
