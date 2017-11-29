---
title: "방법: 데이터베이스에서 행 삭제"
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
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2bf7a701831dd08803c7fff6455d6ec3898df363
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="fef20-102">방법: 데이터베이스에서 행 삭제</span><span class="sxs-lookup"><span data-stu-id="fef20-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="fef20-103">해당 제거 하 여 데이터베이스의 행을 삭제할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 가 테이블 관련 컬렉션에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="fef20-104">변경 내용을 적절 한 sql 변환 `DELETE` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-104"> translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="fef20-105">에서는 하위 삭제 작업을 지원하거나 인식하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-105"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="fef20-106">제약 조건이 있는 테이블의 행을 삭제하려면 다음 작업 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
-   <span data-ttu-id="fef20-107">데이터베이스의 외래 키 제약 조건에 `ON DELETE CASCADE` 규칙을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
-   <span data-ttu-id="fef20-108">사용자 고유의 코드를 사용하여 부모 개체를 삭제하는 데 방해가 되는 자식 개체를 먼저 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="fef20-109">그러지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="fef20-110">이 항목의 뒷부분에 있는 두 번째 코드 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fef20-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fef20-111">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="fef20-112">자세한 내용은 참조 [사용자 지정 Insert, Update 및 Delete 작업](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="fef20-113">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 동일한 용도로 저장 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-113">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="fef20-114">다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="fef20-115">자세한 내용은 참조 [하는 방법: 데이터베이스에 연결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="fef20-116">데이터베이스에서 행을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="fef20-116">To delete a row in the database</span></span>  
  
1.  <span data-ttu-id="fef20-117">삭제할 행에 대한 데이터베이스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-117">Query the database for the row to be deleted.</span></span>  
  
2.  <span data-ttu-id="fef20-118"><xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3.  <span data-ttu-id="fef20-119">데이터베이스에 변경 내용을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef20-120">예제</span><span class="sxs-lookup"><span data-stu-id="fef20-120">Example</span></span>  
 <span data-ttu-id="fef20-121">첫째 코드 예제에서는 데이터베이스에서 Order #11000에 속하는 주문 상세 정보를 쿼리하고 이러한 주문 상세 정보를 삭제하도록 표시한 다음 변경 내용을 데이터베이스에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="fef20-122">예제</span><span class="sxs-lookup"><span data-stu-id="fef20-122">Example</span></span>  
 <span data-ttu-id="fef20-123">두 번째 예제의 목표는 주문(#10250)을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="fef20-124">이 코드에서는 먼저 `OrderDetails` 테이블을 조사하여 제거할 주문에 자식 개체가 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="fef20-125">주문에 자식 개체가 있으면 먼저 해당 자식을 제거한 다음 주문을 제거하도록 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="fef20-126"><xref:System.Data.Linq.DataContext>에서는 데이터베이스로 전달되는 삭제 명령이 데이터베이스 제약 조건을 따르도록 실제 삭제 작업을 올바른 순서대로 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fef20-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fef20-127">See Also</span></span>  
 [<span data-ttu-id="fef20-128">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="fef20-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="fef20-129">방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef20-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="fef20-130">만들고 데이터 변경 내용을 전송</span><span class="sxs-lookup"><span data-stu-id="fef20-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
