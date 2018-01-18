---
title: "프로그래밍 가이드(LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fc7c58f7062871fc3f6ac084bdeafcb12dad1f86
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="104a8-102">프로그래밍 가이드(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="104a8-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="104a8-103">이 단원에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 프로그래밍에 대한 개념 정보와 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="104a8-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="104a8-104">In This Section</span></span>  
 [<span data-ttu-id="104a8-105">LINQ to DataSet의 쿼리</span><span class="sxs-lookup"><span data-stu-id="104a8-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="104a8-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 작성하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="104a8-107">데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="104a8-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="104a8-108"><xref:System.Data.DataSet> 개체를 쿼리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="104a8-109">DataRow 비교</span><span class="sxs-lookup"><span data-stu-id="104a8-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="104a8-110"><xref:System.Data.DataRowComparer> 개체를 사용하여 데이터 행을 비교하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="104a8-111">쿼리에서 DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="104a8-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="104a8-112">만들기에 대 한 정보를 제공는 <xref:System.Data.DataTable> 에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 사용 하 여 쿼리는 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="104a8-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="104a8-113">방법: CopyToDataTable 구현\<T > 제네릭 형식 T가 DataRow 아닙니다</span><span class="sxs-lookup"><span data-stu-id="104a8-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="104a8-114">제네릭 매개 변수 T가 `CopyToDataTable<T>` 형식이 아닌 사용자 지정 <xref:System.Data.DataRow> 메서드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="104a8-115">제네릭 Field 및 SetField 메서드</span><span class="sxs-lookup"><span data-stu-id="104a8-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="104a8-116">제네릭 <xref:System.Data.DataRowExtensions.Field%2A> 및 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="104a8-117">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="104a8-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="104a8-118"><xref:System.Data.DataView> 개체를 사용한 데이터 바인딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="104a8-119">LINQ to DataSet 쿼리 디버깅</span><span class="sxs-lookup"><span data-stu-id="104a8-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="104a8-120">디버깅 및 문제 해결에 대 한 정보를 제공 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="104a8-121">보안</span><span class="sxs-lookup"><span data-stu-id="104a8-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="104a8-122">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]의 보안 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="104a8-123">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="104a8-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="104a8-124">[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 연산자를 사용하는 쿼리 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="104a8-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="104a8-125">참조</span><span class="sxs-lookup"><span data-stu-id="104a8-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="104a8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="104a8-126">See Also</span></span>  
 [<span data-ttu-id="104a8-127">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="104a8-127">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [<span data-ttu-id="104a8-128">빌드에 없음: LINQ 일반 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="104a8-128">NOT IN BUILD: LINQ General Programming Guide</span></span>](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049)  
 [<span data-ttu-id="104a8-129">LINQ 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="104a8-129">LINQ Framework</span></span>](http://msdn.microsoft.com/en-us/897ea0fc-40db-4694-bbe5-7dd339d5bf94)
