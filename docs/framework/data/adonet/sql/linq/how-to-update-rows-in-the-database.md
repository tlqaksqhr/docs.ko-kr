---
title: '방법: 데이터베이스에서 행 업데이트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: b1e993aeb510d34e76d91cfd5222ef190d554846
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363756"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="cf4cd-102">방법: 데이터베이스에서 행 업데이트</span><span class="sxs-lookup"><span data-stu-id="cf4cd-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="cf4cd-103">연결 된 개체의 멤버 값을 수정 하 여 데이터베이스의 행을 업데이트할 수 있습니다는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 컬렉션과 다음 변경 내용을 데이터베이스로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="cf4cd-104"> 변경 내용을 적절 한 SQL 변환 `UPDATE` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-104"> translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf4cd-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="cf4cd-106">자세한 내용은 참조 [사용자 지정 Insert, Update 및 Delete 작업](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="cf4cd-107">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 동일한 용도로 저장된 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="cf4cd-108">다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="cf4cd-109">자세한 내용은 참조 [하는 방법: 데이터베이스에 연결](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="cf4cd-110">데이터베이스의 행을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="cf4cd-110">To update a row in the database</span></span>  
  
1.  <span data-ttu-id="cf4cd-111">업데이트할 행에 대한 데이터베이스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-111">Query the database for the row to be updated.</span></span>  
  
2.  <span data-ttu-id="cf4cd-112">결과 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체의 멤버 값에 대해 필요한 사항을 변경을 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3.  <span data-ttu-id="cf4cd-113">데이터베이스에 변경 내용을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf4cd-114">예제</span><span class="sxs-lookup"><span data-stu-id="cf4cd-114">Example</span></span>  
 <span data-ttu-id="cf4cd-115">다음 예제에서는 주문 #11000에 대한 데이터베이스를 쿼리한 다음 결과 `ShipName` 개체의 `ShipVia`과 `Order`에 대한 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="cf4cd-116">마지막으로 이러한 멤버 값의 변경 내용을 `ShipName`과 `ShipVia` 열의 변경 내용으로 데이터베이스에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cf4cd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf4cd-117">See Also</span></span>  
 [<span data-ttu-id="cf4cd-118">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="cf4cd-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="cf4cd-119">방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4cd-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="cf4cd-120">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="cf4cd-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
