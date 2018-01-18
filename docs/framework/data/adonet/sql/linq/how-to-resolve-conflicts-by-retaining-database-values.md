---
title: "방법: 데이터베이스 값을 보존하여 충돌 해결"
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
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0747a4318fdab76c5fbd920f7291346d4d8ff58d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="94f06-102">방법: 데이터베이스 값을 보존하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="94f06-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="94f06-103">변경 내용을 다시 전송하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이를 조정하려면 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 데이터베이스에서 찾은 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="94f06-104">그런 다음 개체 모델의 현재 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="94f06-105">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94f06-106">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="94f06-107">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94f06-108">예</span><span class="sxs-lookup"><span data-stu-id="94f06-108">Example</span></span>  
 <span data-ttu-id="94f06-109">이 시나리오에서는 User1이 변경 내용을 제출하려는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="94f06-110">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="94f06-111">Manager</span><span class="sxs-lookup"><span data-stu-id="94f06-111">Manager</span></span>|<span data-ttu-id="94f06-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="94f06-112">Assistant</span></span>|<span data-ttu-id="94f06-113">Department</span><span class="sxs-lookup"><span data-stu-id="94f06-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="94f06-114">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="94f06-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="94f06-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="94f06-115">Alfreds</span></span>|<span data-ttu-id="94f06-116">Maria</span><span class="sxs-lookup"><span data-stu-id="94f06-116">Maria</span></span>|<span data-ttu-id="94f06-117">Sales</span><span class="sxs-lookup"><span data-stu-id="94f06-117">Sales</span></span>|  
|<span data-ttu-id="94f06-118">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="94f06-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="94f06-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="94f06-119">Alfred</span></span>||<span data-ttu-id="94f06-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="94f06-120">Marketing</span></span>|  
|<span data-ttu-id="94f06-121">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="94f06-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="94f06-122">Mary</span><span class="sxs-lookup"><span data-stu-id="94f06-122">Mary</span></span>|<span data-ttu-id="94f06-123">서비스</span><span class="sxs-lookup"><span data-stu-id="94f06-123">Service</span></span>|  
  
 <span data-ttu-id="94f06-124">User1이 최신 데이터베이스 값으로 개체 모델의 현재 값을 덮어써서 이 충돌을 해결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="94f06-125">User1이 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 충돌을 해결하는 경우 데이터베이스의 결과는 다음 표와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="94f06-126">Manager</span><span class="sxs-lookup"><span data-stu-id="94f06-126">Manager</span></span>|<span data-ttu-id="94f06-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="94f06-127">Assistant</span></span>|<span data-ttu-id="94f06-128">Department</span><span class="sxs-lookup"><span data-stu-id="94f06-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="94f06-129">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="94f06-129">New state after conflict resolution.</span></span>|<span data-ttu-id="94f06-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="94f06-130">Alfreds</span></span><br /><br /> <span data-ttu-id="94f06-131">(원래 값)</span><span class="sxs-lookup"><span data-stu-id="94f06-131">(original)</span></span>|<span data-ttu-id="94f06-132">Mary</span><span class="sxs-lookup"><span data-stu-id="94f06-132">Mary</span></span><br /><br /> <span data-ttu-id="94f06-133">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="94f06-133">(from User2)</span></span>|<span data-ttu-id="94f06-134">서비스</span><span class="sxs-lookup"><span data-stu-id="94f06-134">Service</span></span><br /><br /> <span data-ttu-id="94f06-135">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="94f06-135">(from User2)</span></span>|  
  
 <span data-ttu-id="94f06-136">다음 예제 코드에서는 개체 모델의 현재 값을 데이터베이스 값으로 덮어쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="94f06-137">각 멤버 충돌에 대한 검사 또는 사용자 지정 처리는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94f06-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="94f06-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94f06-138">See Also</span></span>  
 [<span data-ttu-id="94f06-139">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="94f06-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
