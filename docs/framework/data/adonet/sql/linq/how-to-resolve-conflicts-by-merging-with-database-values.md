---
title: '방법: 데이터베이스 값을 병합하여 충돌 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: a263afb7daceccecf7153c6e9bcfc68e10638c30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360991"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="0ba67-102">방법: 데이터베이스 값을 병합하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="0ba67-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="0ba67-103">변경 내용을 다시 제출하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이점을 조정하려면 <xref:System.Data.Linq.RefreshMode.KeepChanges>를 사용하여 데이터베이스 값과 현재 클라이언트 멤버 값을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="0ba67-104">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ba67-105">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="0ba67-106">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ba67-107">예제</span><span class="sxs-lookup"><span data-stu-id="0ba67-107">Example</span></span>  
 <span data-ttu-id="0ba67-108">이 시나리오에서는 User1이 변경 내용을 제출하려는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="0ba67-109">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="0ba67-110">Manager</span><span class="sxs-lookup"><span data-stu-id="0ba67-110">Manager</span></span>|<span data-ttu-id="0ba67-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="0ba67-111">Assistant</span></span>|<span data-ttu-id="0ba67-112">Department</span><span class="sxs-lookup"><span data-stu-id="0ba67-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="0ba67-113">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="0ba67-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="0ba67-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="0ba67-114">Alfreds</span></span>|<span data-ttu-id="0ba67-115">Maria</span><span class="sxs-lookup"><span data-stu-id="0ba67-115">Maria</span></span>|<span data-ttu-id="0ba67-116">Sales</span><span class="sxs-lookup"><span data-stu-id="0ba67-116">Sales</span></span>|  
|<span data-ttu-id="0ba67-117">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="0ba67-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="0ba67-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="0ba67-118">Alfred</span></span>||<span data-ttu-id="0ba67-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="0ba67-119">Marketing</span></span>|  
|<span data-ttu-id="0ba67-120">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="0ba67-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="0ba67-121">Mary</span><span class="sxs-lookup"><span data-stu-id="0ba67-121">Mary</span></span>|<span data-ttu-id="0ba67-122">서비스</span><span class="sxs-lookup"><span data-stu-id="0ba67-122">Service</span></span>|  
  
 <span data-ttu-id="0ba67-123">User1이 데이터베이스 값을 현재 클라이언트 멤버 값과 병합하여 이 충돌을 해결하기로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="0ba67-124">그 결과, 현재 변경 집합 역시 해당 값을 변경할 때에만 데이터베이스 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="0ba67-125">User1이 <xref:System.Data.Linq.RefreshMode.KeepChanges>를 사용하여 문제를 해결하는 경우 데이터베이스의 결과는 다음 표와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="0ba67-126">Manager</span><span class="sxs-lookup"><span data-stu-id="0ba67-126">Manager</span></span>|<span data-ttu-id="0ba67-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="0ba67-127">Assistant</span></span>|<span data-ttu-id="0ba67-128">Department</span><span class="sxs-lookup"><span data-stu-id="0ba67-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="0ba67-129">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="0ba67-129">New state after conflict resolution.</span></span>|<span data-ttu-id="0ba67-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="0ba67-130">Alfred</span></span><br /><br /> <span data-ttu-id="0ba67-131">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="0ba67-131">(from User1)</span></span>|<span data-ttu-id="0ba67-132">Mary</span><span class="sxs-lookup"><span data-stu-id="0ba67-132">Mary</span></span><br /><br /> <span data-ttu-id="0ba67-133">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="0ba67-133">(from User2)</span></span>|<span data-ttu-id="0ba67-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="0ba67-134">Marketing</span></span><br /><br /> <span data-ttu-id="0ba67-135">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="0ba67-135">(from User1)</span></span>|  
  
 <span data-ttu-id="0ba67-136">다음 예제에서는 클라이언트 역시 해당 값을 변경하지 않는 경우 데이터베이스 값과 현재 클라이언트 멤버 값을 병합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="0ba67-137">검사 또는 개별 멤버 충돌에 대한 사용자 지정 처리 기능이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba67-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0ba67-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ba67-138">See Also</span></span>  
 [<span data-ttu-id="0ba67-139">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="0ba67-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="0ba67-140">방법: 데이터베이스 값을 보존하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="0ba67-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="0ba67-141">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="0ba67-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
