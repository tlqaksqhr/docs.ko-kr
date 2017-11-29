---
title: "방법: 데이터베이스에 행 삽입"
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
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a96a0ab800076db16022f5b02c84d7a53ca99147
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="67234-102">방법: 데이터베이스에 행 삽입</span><span class="sxs-lookup"><span data-stu-id="67234-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="67234-103">연결 된 개체를 추가 하 여 데이터베이스에 행을 삽입 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 컬렉션과 다음 변경 내용을 데이터베이스로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="67234-104">변경 내용을 적절 한 SQL 변환 `INSERT` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="67234-104"> translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67234-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67234-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="67234-106">자세한 내용은 참조 [사용자 지정 Insert, Update 및 Delete 작업](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="67234-107">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 동일한 용도로 저장 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67234-107">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="67234-108">다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="67234-109">자세한 내용은 참조 [하는 방법: 데이터베이스에 연결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="67234-110">데이터베이스에 행을 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="67234-110">To insert a row into the database</span></span>  
  
1.  <span data-ttu-id="67234-111">전송할 행 데이터가 있는 새 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67234-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2.  <span data-ttu-id="67234-112">새 개체를 데이터베이스의 대상 테이블에 연결된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3.  <span data-ttu-id="67234-113">데이터베이스에 변경 내용을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67234-114">예제</span><span class="sxs-lookup"><span data-stu-id="67234-114">Example</span></span>  
 <span data-ttu-id="67234-115">다음 코드 예제에서는 `Order` 형식의 새 개체를 만들어 적절한 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="67234-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="67234-116">그런 다음 새 개체를 `Order` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="67234-117">마지막으로 변경 내용을 `Orders` 테이블의 새 행으로 데이터베이스에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="67234-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67234-118">See Also</span></span>  
 [<span data-ttu-id="67234-119">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="67234-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="67234-120">DataContext 메서드 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="67234-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="67234-121">방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67234-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="67234-122">만들고 데이터 변경 내용을 전송</span><span class="sxs-lookup"><span data-stu-id="67234-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
