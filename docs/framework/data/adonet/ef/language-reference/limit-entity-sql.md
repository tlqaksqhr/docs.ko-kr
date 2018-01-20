---
title: LIMIT(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c0b2a421b1187fcf88278b66f3225133330a3033
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="limit-entity-sql"></a><span data-ttu-id="5c2ac-102">LIMIT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5c2ac-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="5c2ac-103">ORDER BY 절에서 LIIMIT 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="5c2ac-104">LIMIT 절은 ORDER BY 절과 별도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2ac-105">구문</span><span class="sxs-lookup"><span data-stu-id="5c2ac-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c2ac-106">인수</span><span class="sxs-lookup"><span data-stu-id="5c2ac-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="5c2ac-107">선택할 항목의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="5c2ac-108">LIMIT 식 하위 절이 ORDER BY 절에 있으면 쿼리는 정렬 지정에 따라 정렬되고 결과 행의 수는 LIMIT 식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="5c2ac-109">예를 들어, LIMIT 5는 결과 집합을 다섯 개의 인스턴스 또는 행으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="5c2ac-110">LIMIT는 ORDER BY 절이 반드시 있어야 한다는 점을 제외하고는 TOP와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="5c2ac-111">SKIP 및 LIMIT 절은 각각 ORDER BY 절과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c2ac-112">TOP 한정자와 SKIP 하위 절이 모두 같은 쿼리 식에 있는 경우 Entity SQL 쿼리는 유효하지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="5c2ac-113">TOP 식을 변경하여 쿼리를 LIMIT 식에 다시 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c2ac-114">예</span><span class="sxs-lookup"><span data-stu-id="5c2ac-114">Example</span></span>  
 <span data-ttu-id="5c2ac-115">다음 Entity SQL 쿼리는 LIMIT와 함께 ORDER BY 연산자를 사용하여 SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="5c2ac-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5c2ac-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5c2ac-118">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5c2ac-119">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5c2ac-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="5c2ac-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c2ac-120">See Also</span></span>  
 [<span data-ttu-id="5c2ac-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="5c2ac-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="5c2ac-122">방법: 쿼리를 통해 페이지 결과</span><span class="sxs-lookup"><span data-stu-id="5c2ac-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="5c2ac-123">페이징</span><span class="sxs-lookup"><span data-stu-id="5c2ac-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="5c2ac-124">TOP</span><span class="sxs-lookup"><span data-stu-id="5c2ac-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
