---
title: "시퀀스의 요소 정렬"
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
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f296565beb284095dce2520cd545f8af61dc6b48
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="bee89-102">시퀀스의 요소 정렬</span><span class="sxs-lookup"><span data-stu-id="bee89-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="bee89-103"><xref:System.Linq.Enumerable.OrderBy%2A> 연산자를 사용하여 하나 이상의 키에 따른 시퀀스를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="bee89-104">에서는 `string`, `int` 등과 같이 간단한 기본 형식에 따라 순서를 지원하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-104"> is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="bee89-105">익명 형식과 같이 복잡한 다중값 클래스에 대한 순서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="bee89-106">또한 `byte` 데이터 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bee89-107">예</span><span class="sxs-lookup"><span data-stu-id="bee89-107">Example</span></span>  
 <span data-ttu-id="bee89-108">다음 예제에서는 고용 날짜 기준으로 `Employees`를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="bee89-109">예</span><span class="sxs-lookup"><span data-stu-id="bee89-109">Example</span></span>  
 <span data-ttu-id="bee89-110">다음 예제에서는 `where`를 사용하여 화물편으로 `Orders`에 보낸 `London`를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="bee89-111">예</span><span class="sxs-lookup"><span data-stu-id="bee89-111">Example</span></span>  
 <span data-ttu-id="bee89-112">다음 예제에서는 단가가 최상위에서 최하위 순으로 `Products`를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="bee89-113">예</span><span class="sxs-lookup"><span data-stu-id="bee89-113">Example</span></span>  
 <span data-ttu-id="bee89-114">다음 예제에서는 복합 `OrderBy`를 사용하여 `Customers`를 도시별로 정렬한 다음 연락처 이름으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="bee89-115">예</span><span class="sxs-lookup"><span data-stu-id="bee89-115">Example</span></span>  
 <span data-ttu-id="bee89-116">다음 예제에서는 발송된 나라별로 `EmployeeID 1`에서 주문을 정렬한 다음 운임료를 최상위에서 최하위 기준으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="bee89-117">예</span><span class="sxs-lookup"><span data-stu-id="bee89-117">Example</span></span>  
 <span data-ttu-id="bee89-118">다음 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> 및 <xref:System.Linq.Enumerable.GroupBy%2A> 연산자를 조합하여 범주별로 최고 단가인 `Products`를 찾은 다음 범주 ID로 그룹을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="bee89-119">Northwind 샘플 데이터베이스에 대한 이전 쿼리를 실행할 경우 결과는 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bee89-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="bee89-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bee89-120">See Also</span></span>  
 [<span data-ttu-id="bee89-121">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="bee89-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="bee89-122">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="bee89-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
