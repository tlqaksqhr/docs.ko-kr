---
title: "방법: 정보 쿼리"
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
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0722f83c19c1eff43606afceeda484d72691eb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="ec907-102">방법: 정보 쿼리</span><span class="sxs-lookup"><span data-stu-id="ec907-102">How to: Query for Information</span></span>
<span data-ttu-id="ec907-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 쿼리는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리와 동일한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="ec907-104">유일한 차이점은에서 참조 된 개체가 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리가 데이터베이스의 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="ec907-105">자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec907-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ec907-106">에서는 작성한 쿼리를 해당 SQL 쿼리로 변환하고 SQL Server에 전달하여 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-106"> translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="ec907-107">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 쿼리의 일부 기능을 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서 사용할 때 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="ec907-108">자세한 내용은 참조 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec907-109">예제</span><span class="sxs-lookup"><span data-stu-id="ec907-109">Example</span></span>  
 <span data-ttu-id="ec907-110">다음 쿼리에서는 London의 고객 목록을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="ec907-111">이 예제에서 `Customers`는 Northwind 샘플 데이터베이스의 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ec907-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ec907-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec907-112">See Also</span></span>  
 [<span data-ttu-id="ec907-113">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="ec907-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="ec907-114">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="ec907-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="ec907-115">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="ec907-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
