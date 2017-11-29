---
title: "시퀀스의 요소 그룹화"
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
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a398bb7b951fcf2dd2449b6468a19d39a134a4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="688a2-102">시퀀스의 요소 그룹화</span><span class="sxs-lookup"><span data-stu-id="688a2-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="688a2-103"><xref:System.Linq.Enumerable.GroupBy%2A> 연산자는 시퀀스의 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="688a2-104">다음 예제에서는 Northwind 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="688a2-105"><xref:System.Linq.Enumerable.GroupBy%2A> 쿼리의 Null 열 값은 종종 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="688a2-106">자세한 내용은의 "GroupBy InvalidOperationException" 섹션을 참조 하십시오. [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="688a2-107">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-107">Example</span></span>  
 <span data-ttu-id="688a2-108">다음 예제에서는 `Products`에 따라 `CategoryID`를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="688a2-109">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-109">Example</span></span>  
 <span data-ttu-id="688a2-110">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A>를 사용하여 각 `CategoryID`에 대한 최대 단가를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="688a2-111">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-111">Example</span></span>  
 <span data-ttu-id="688a2-112">다음 예제에서는 Average를 사용하여 각 `UnitPrice`에 대한 평균 `CategoryID`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="688a2-113">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-113">Example</span></span>  
 <span data-ttu-id="688a2-114">다음 예제에서는 <xref:System.Linq.Queryable.Sum%2A>을 사용하여 각 `UnitPrice`에 대한 총 `CategoryID`를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="688a2-115">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-115">Example</span></span>  
 <span data-ttu-id="688a2-116">다음 예제에서는 <xref:System.Linq.Queryable.Count%2A>를 사용하여 각 `Products`에서 할인된 `CategoryID`의 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="688a2-117">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-117">Example</span></span>  
 <span data-ttu-id="688a2-118">다음 예제에서는 아래의 `where` 절을 사용하여 최소 10개의 제품이 있는 범주를 모두 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="688a2-119">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-119">Example</span></span>  
 <span data-ttu-id="688a2-120">다음 예제에서는 `CategoryID` 및 `SupplierID`에 따라 제품을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="688a2-121">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-121">Example</span></span>  
 <span data-ttu-id="688a2-122">다음 예제에서는 두 가지 제품 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="688a2-123">첫 번째 시퀀스에는 단가가 10 이하인 제품이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="688a2-124">두 번째 시퀀스에는 단가가 10보다 큰 제품이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="688a2-125">예제</span><span class="sxs-lookup"><span data-stu-id="688a2-125">Example</span></span>  
 <span data-ttu-id="688a2-126"><xref:System.Linq.Queryable.GroupBy%2A> 연산자는 하나의 키 인수만을 받아들일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="688a2-127">둘 이상의 키로 그룹화해야 하는 경우 다음 예제처럼 익명 형식을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="688a2-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="688a2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="688a2-128">See Also</span></span>  
 [<span data-ttu-id="688a2-129">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="688a2-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="688a2-130">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="688a2-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
