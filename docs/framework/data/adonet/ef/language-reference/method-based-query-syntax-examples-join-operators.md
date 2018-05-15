---
title: '메서드 기반 쿼리 구문 예제: 조인 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: a77a58d28c667e5dabf0dda4c8d2f4782ea83572
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="b75bd-102">메서드 기반 쿼리 구문 예제: 조인 연산자</span><span class="sxs-lookup"><span data-stu-id="b75bd-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="b75bd-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다는 <xref:System.Linq.Enumerable.Join%2A> 및 <xref:System.Linq.Enumerable.GroupJoin%2A> 를 쿼리 하는 메서드는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="b75bd-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b75bd-105">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="b75bd-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="b75bd-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="b75bd-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="b75bd-107">예제</span><span class="sxs-lookup"><span data-stu-id="b75bd-107">Example</span></span>  
 <span data-ttu-id="b75bd-108">다음 예제에서는 SalesOrderHeader 및 SalesOrderDetail 테이블에 대해 <xref:System.Linq.Enumerable.GroupJoin%2A>을 수행하여 고객별 주문 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="b75bd-109">그룹 조인은 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째(왼쪽) 데이터 소스의 각 요소를 반환하는 왼쪽 우선 외부 조인과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="b75bd-110">예제</span><span class="sxs-lookup"><span data-stu-id="b75bd-110">Example</span></span>  
 <span data-ttu-id="b75bd-111">다음 예제에서는 Contact 및 SalesOrderHeader 테이블에 대해 <xref:System.Linq.Enumerable.GroupJoin%2A>을 수행하여 연락처별 주문 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="b75bd-112">연락처별로 주문 횟수와 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="b75bd-113">Join</span><span class="sxs-lookup"><span data-stu-id="b75bd-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="b75bd-114">예제</span><span class="sxs-lookup"><span data-stu-id="b75bd-114">Example</span></span>  
 <span data-ttu-id="b75bd-115">다음 예제에서는 Contact 및 SalesOrderHeader 테이블에 대해 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="b75bd-116">예제</span><span class="sxs-lookup"><span data-stu-id="b75bd-116">Example</span></span>  
 <span data-ttu-id="b75bd-117">다음 예제에서는 Contact 및 SalesOrderHeader 테이블에 대한 조인을 수행하고 연락처 ID별로 결과를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="b75bd-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b75bd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b75bd-118">See Also</span></span>  
 [<span data-ttu-id="b75bd-119">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="b75bd-119">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
