---
title: '방법: 데이터베이스 값을 보존하여 충돌 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: d0d59c520beaab2d6c8c1594ee81a3eaecf1d03e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361697"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="4d799-102">방법: 데이터베이스 값을 보존하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="4d799-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="4d799-103">변경 내용을 다시 전송하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이를 조정하려면 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 데이터베이스에서 찾은 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="4d799-104">그런 다음 개체 모델의 현재 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="4d799-105">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d799-106">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="4d799-107">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d799-108">예제</span><span class="sxs-lookup"><span data-stu-id="4d799-108">Example</span></span>  
 <span data-ttu-id="4d799-109">이 시나리오에서는 User1이 변경 내용을 제출하려는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="4d799-110">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="4d799-111">Manager</span><span class="sxs-lookup"><span data-stu-id="4d799-111">Manager</span></span>|<span data-ttu-id="4d799-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="4d799-112">Assistant</span></span>|<span data-ttu-id="4d799-113">Department</span><span class="sxs-lookup"><span data-stu-id="4d799-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="4d799-114">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="4d799-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="4d799-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="4d799-115">Alfreds</span></span>|<span data-ttu-id="4d799-116">Maria</span><span class="sxs-lookup"><span data-stu-id="4d799-116">Maria</span></span>|<span data-ttu-id="4d799-117">Sales</span><span class="sxs-lookup"><span data-stu-id="4d799-117">Sales</span></span>|  
|<span data-ttu-id="4d799-118">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="4d799-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="4d799-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="4d799-119">Alfred</span></span>||<span data-ttu-id="4d799-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="4d799-120">Marketing</span></span>|  
|<span data-ttu-id="4d799-121">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="4d799-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="4d799-122">Mary</span><span class="sxs-lookup"><span data-stu-id="4d799-122">Mary</span></span>|<span data-ttu-id="4d799-123">서비스</span><span class="sxs-lookup"><span data-stu-id="4d799-123">Service</span></span>|  
  
 <span data-ttu-id="4d799-124">User1이 최신 데이터베이스 값으로 개체 모델의 현재 값을 덮어써서 이 충돌을 해결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="4d799-125">User1이 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 충돌을 해결하는 경우 데이터베이스의 결과는 다음 표와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="4d799-126">Manager</span><span class="sxs-lookup"><span data-stu-id="4d799-126">Manager</span></span>|<span data-ttu-id="4d799-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="4d799-127">Assistant</span></span>|<span data-ttu-id="4d799-128">Department</span><span class="sxs-lookup"><span data-stu-id="4d799-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="4d799-129">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="4d799-129">New state after conflict resolution.</span></span>|<span data-ttu-id="4d799-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="4d799-130">Alfreds</span></span><br /><br /> <span data-ttu-id="4d799-131">(원래 값)</span><span class="sxs-lookup"><span data-stu-id="4d799-131">(original)</span></span>|<span data-ttu-id="4d799-132">Mary</span><span class="sxs-lookup"><span data-stu-id="4d799-132">Mary</span></span><br /><br /> <span data-ttu-id="4d799-133">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="4d799-133">(from User2)</span></span>|<span data-ttu-id="4d799-134">서비스</span><span class="sxs-lookup"><span data-stu-id="4d799-134">Service</span></span><br /><br /> <span data-ttu-id="4d799-135">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="4d799-135">(from User2)</span></span>|  
  
 <span data-ttu-id="4d799-136">다음 예제 코드에서는 개체 모델의 현재 값을 데이터베이스 값으로 덮어쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="4d799-137">각 멤버 충돌에 대한 검사 또는 사용자 지정 처리는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d799-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4d799-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d799-138">See Also</span></span>  
 [<span data-ttu-id="4d799-139">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="4d799-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
