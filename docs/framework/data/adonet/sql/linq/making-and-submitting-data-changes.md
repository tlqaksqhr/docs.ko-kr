---
title: 데이터 변경 및 변경 내용 전송
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: c9d319727a750fbd3e2a186c28e79b20200c6bd0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360795"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="f7fde-102">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="f7fde-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="f7fde-103">이 단원의 항목에서는 데이터베이스에 변경 내용을 만들고 전송하는 방법과 낙관적 동시성 충돌을 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7fde-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="f7fde-105">자세한 내용은 참조 [사용자 지정 Insert, Update 및 Delete 작업](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="f7fde-106">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 동일한 용도로 저장된 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-106">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7fde-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f7fde-107">In This Section</span></span>  
 [<span data-ttu-id="f7fde-108">방법: 데이터베이스에 행 삽입</span><span class="sxs-lookup"><span data-stu-id="f7fde-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="f7fde-109">개체 모델에 개체를 추가하여 데이터베이스에 행을 삽입하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="f7fde-110">방법: 데이터베이스에서 행 업데이트</span><span class="sxs-lookup"><span data-stu-id="f7fde-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="f7fde-111">개체 모델에 개체를 업데이트하여 데이터베이스에 행을 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="f7fde-112">방법: 데이터베이스에서 행 삭제</span><span class="sxs-lookup"><span data-stu-id="f7fde-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="f7fde-113">개체 모델에서 개체를 삭제하여 데이터베이스의 행을 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="f7fde-114">방법: 데이터베이스에 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="f7fde-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="f7fde-115">데이터베이스에 개체 모델 변경 내용을 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="f7fde-116">방법: 트랜잭션을 사용하여 데이터 대괄호 전송</span><span class="sxs-lookup"><span data-stu-id="f7fde-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="f7fde-117">트랜젝션에 작업을 포함시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="f7fde-118">방법: 동적으로 데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="f7fde-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="f7fde-119">동적으로 데이터베이스를 생성하고 이 방법에 대한 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="f7fde-120">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="f7fde-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="f7fde-121">낙관적 동시성 문제를 해결하는 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7fde-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
