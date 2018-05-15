---
title: '메서드 기반 쿼리 구문 예제: 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: f4e9b6df45e13680a428d1524eaf1a1b9315185a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="a5713-102">메서드 기반 쿼리 구문 예제: 필터링</span><span class="sxs-lookup"><span data-stu-id="a5713-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="a5713-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다는 `Where` 및 `Where…Contains` 를 쿼리 하는 메서드는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 메서드 기반 쿼리 구문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="a5713-104">단, 여기서...`Contains`</span><span class="sxs-lookup"><span data-stu-id="a5713-104">Note, Where…`Contains`</span></span> <span data-ttu-id="a5713-105">일부로 사용할 수 없습니다는 [컴파일된 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="a5713-106">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a5713-107">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="a5713-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="a5713-108">Where</span><span class="sxs-lookup"><span data-stu-id="a5713-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="a5713-109">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-109">Example</span></span>  
 <span data-ttu-id="a5713-110">다음 예제에서는 모든 온라인 주문을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="a5713-111">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-111">Example</span></span>  
 <span data-ttu-id="a5713-112">다음 예제에서는 주문 수량이 2보다 크고 6보다 작은 주문을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="a5713-113">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-113">Example</span></span>  
 <span data-ttu-id="a5713-114">다음 예제에서는 빨간색 제품을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="a5713-115">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-115">Example</span></span>  
 <span data-ttu-id="a5713-116">다음 예제에서는 `Where` 메서드를 사용하여 2003년 12월 1일 이후의 주문을 찾은 다음 `order.SalesOrderDetail` 탐색 속성을 사용하여 각 주문의 세부 사항을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="a5713-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="a5713-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="a5713-118">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-118">Example</span></span>  
 <span data-ttu-id="a5713-119">다음 예제에서는 배열을 `Where…Contains` 절의 일부로 사용하여 `ProductModelID`가 배열의 값과 일치하는 모든 제품을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="a5713-120">`Where…Contains` 절에 있는 조건자의 일부로 <xref:System.Array>, <xref:System.Collections.Generic.List%601> 또는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 형식의 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="a5713-121">LINQ to Entities 쿼리 내에서 컬렉션을 선언하고 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="a5713-122">자세한 내용은 다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5713-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a5713-123">예제</span><span class="sxs-lookup"><span data-stu-id="a5713-123">Example</span></span>  
 <span data-ttu-id="a5713-124">다음 예제에서는 배열을 `Where…Contains` 절에서 선언하고 초기화하여 `ProductModelID` 또는 `Size`가 배열의 값과 일치하는 모든 제품을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a5713-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a5713-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5713-125">See Also</span></span>  
 [<span data-ttu-id="a5713-126">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="a5713-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
