---
title: "LINQ to DataSet 예제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 61e2e107c3e62569a47b4bd84e451ff55adab208
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="dc204-102">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="dc204-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="dc204-103">이 섹션에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 표준 쿼리 연산자를 사용 하는 예제를 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples that use the standard query operators.</span></span> <span data-ttu-id="dc204-104"><xref:System.Data.DataSet> 이러한 예에서 사용 된를 사용 하 여 채워집니다는 `FillDataSet` 에 지정 된 메서드를 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="dc204-105">자세한 내용은 참조 [표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)합니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc204-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="dc204-106">In This Section</span></span>  
 [<span data-ttu-id="dc204-107">쿼리 식 예제</span><span class="sxs-lookup"><span data-stu-id="dc204-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="dc204-108">다음 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="dc204-109">프로젝션</span><span class="sxs-lookup"><span data-stu-id="dc204-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="dc204-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="dc204-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="dc204-111">분할</span><span class="sxs-lookup"><span data-stu-id="dc204-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="dc204-112">정렬</span><span class="sxs-lookup"><span data-stu-id="dc204-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="dc204-113">요소 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="dc204-114">집계 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="dc204-115">조인 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="dc204-116">메서드 기반 쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="dc204-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="dc204-117">다음 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="dc204-118">프로젝션</span><span class="sxs-lookup"><span data-stu-id="dc204-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="dc204-119">분할</span><span class="sxs-lookup"><span data-stu-id="dc204-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="dc204-120">정렬</span><span class="sxs-lookup"><span data-stu-id="dc204-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="dc204-121">집합 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="dc204-122">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="dc204-123">요소 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="dc204-124">집계 연산자</span><span class="sxs-lookup"><span data-stu-id="dc204-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="dc204-125">Join</span><span class="sxs-lookup"><span data-stu-id="dc204-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="dc204-126">DataSet별 연산자 예제</span><span class="sxs-lookup"><span data-stu-id="dc204-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="dc204-127"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드와 <xref:System.Data.DataRowComparer> 클래스를 사용하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="dc204-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc204-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc204-128">See Also</span></span>  
 [<span data-ttu-id="dc204-129">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dc204-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [<span data-ttu-id="dc204-130">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="dc204-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
