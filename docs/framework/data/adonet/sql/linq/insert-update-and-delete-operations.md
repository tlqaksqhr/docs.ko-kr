---
title: "삽입, 업데이트 및 삭제 작업"
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: adbe7faa50b06c330b942b451d5a4a0bd832cde3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="0977a-102">삽입, 업데이트 및 삭제 작업</span><span class="sxs-lookup"><span data-stu-id="0977a-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="0977a-103">`Insert`에서는 개체 모델에서 개체를 추가, 변경 및 제거함으로써 `Update`, `Delete` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="0977a-104">기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 사용자 작업을 SQL로 변환하여 데이터베이스로 변경 내용을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0977a-105">에서는 개체에 대한 변경 내용을 조작하고 유지하는 데 최대한의 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-105"> offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="0977a-106">엔터티 개체를 쿼리를 통해 검색하거나 새로 생성하여 사용할 수 있으면 응용 프로그램에서 해당 개체를 일반적인 개체로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="0977a-107">즉, 해당 값을 변경, 사용자 컬렉션에 추가할 수 있습니다 및 컬렉션에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0977a-108">에서는 변경 내용을 추적하여 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때 변경 내용을 데이터베이스로 다시 전송할 수 있도록 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-108"> tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0977a-109">에서는 하위 삭제 작업을 지원하거나 인식하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-109"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="0977a-110">설정 하거나 해야 제약 조건이 있는 테이블의 행을 삭제 하려는 경우는 `ON DELETE CASCADE` 는 데이터베이스의 외래 키 제약 조건에 규칙 하거나 사용자 고유의 코드를 사용 하 여 부모 개체를 삭제 하지 못하게 하는 자식 개체를 먼저 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="0977a-111">그러지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="0977a-112">자세한 내용은 참조 [하는 방법: 행 데이터베이스에서 삭제](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="0977a-113">다음에 인용된 예제에서는 Northwind 샘플 데이터베이스의 `Customer`와 `Order` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="0977a-114">간결하게 나타내기 위해 클래스 정의는 표시하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="0977a-115"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 변경 내용을 데이터베이스로 다시 전송하는 SQL 명령을 자동으로 생성하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0977a-116">일반적으로 저장 프로시저와 같은 사용자 지정 논리를 사용하여 이러한 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="0977a-117">자세한 내용은 참조 [는에서 기본 동작 재정의 개발자의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="0977a-118">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 이 용도로 저장 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0977a-118">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0977a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0977a-119">See Also</span></span>  
 [<span data-ttu-id="0977a-120">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="0977a-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="0977a-121">사용자 지정 삽입, 업데이트 및 삭제 작업</span><span class="sxs-lookup"><span data-stu-id="0977a-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
