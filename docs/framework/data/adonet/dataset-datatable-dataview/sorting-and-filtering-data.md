---
title: "데이터 정렬 및 필터링"
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
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 01c09d94fd3224e8fd875b7f6eea06b2d2c35cca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="d7653-102">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="d7653-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="d7653-103"><xref:System.Data.DataView>를 사용하면 다음과 같은 여러 가지 방법으로 <xref:System.Data.DataTable>의 데이터를 정렬 및 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
-   <span data-ttu-id="d7653-104"><xref:System.Data.DataView.Sort%2A> 속성을 사용하여 하나 또는 여러 열의 정렬 순서를 지정하고, ASC(오름차순) 및 DESC(내림차순) 매개 변수를 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
-   <span data-ttu-id="d7653-105"><xref:System.Data.DataView.ApplyDefaultSort%2A> 속성을 사용하여 테이블의 기본 키 열을 기준으로 오름차순의 정렬 순서를 자동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="d7653-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>경우에 적용 됩니다는 **정렬** 속성은 null 참조 또는 빈 문자열인 경우 테이블에 기본 키가 정의 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
-   <span data-ttu-id="d7653-107"><xref:System.Data.DataView.RowFilter%2A> 속성을 사용하여 해당 열 값을 기준으로 행의 하위 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="d7653-108">사용할 수 있는 식에 대 한 자세한 내용은 **RowFilter** 속성에 대 한 참조 정보를 참조는 <xref:System.Data.DataColumn.Expression%2A> 속성은 <xref:System.Data.DataColumn> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="d7653-109">에 데이터를 전송할 데이터의 하위 집합에 대 한 동적 뷰를 제공 하는 특정 쿼리 결과를 사용 하 여 반환 하려는 경우는 <xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A> 의 메서드는 **DataView** 최상의 성능을 얻으려면 보다는 설정의 **RowFilter** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="d7653-110">설정의 **RowFilter** 속성 데이터, 응용 프로그램에 오버 헤드가 및 성능이 저하에 대 한 인덱스를 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="d7653-111">**RowFilter** 속성은 가장 적합 한 데이터 바인딩된 응용 프로그램에 바인딩된 컨트롤에서 필터링 된 결과 표시 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="d7653-112">**찾을** 및 **FindRows** 메서드를 다시 작성 해야 인덱스를 요구 하지 않고 현재 인덱스를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="d7653-113">에 대 한 자세한 내용은 **찾을** 및 **FindRows** 메서드 참조 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
-   <span data-ttu-id="d7653-114"><xref:System.Data.DataView.RowStateFilter%2A> 속성을 사용하면 표시할 행 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="d7653-115">**DataView** 암시적으로에 따라 노출 시킬 행 버전 관리는 **RowState** 기본 행의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="d7653-116">예를 들어 경우는 **RowStateFilter** 로 설정 된 **DataViewRowState.Deleted**, **DataView** 노출 된 **원래** 의 행 버전 모든 **Deleted** 있기 때문에 행 없음 **현재** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="d7653-117">사용 하 여 표시 된 행의 행 버전을 확인할 수 있습니다는 **RowVersion** 의 속성은 **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="d7653-118">다음 표에서에 대 한 옵션을 보여 줍니다. **DataViewRowState**합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="d7653-119">DataViewRowState 옵션</span><span class="sxs-lookup"><span data-stu-id="d7653-119">DataViewRowState options</span></span>|<span data-ttu-id="d7653-120">설명</span><span class="sxs-lookup"><span data-stu-id="d7653-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="d7653-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="d7653-121">**CurrentRows**</span></span>|<span data-ttu-id="d7653-122">**현재** 의 모든 행 버전 **Unchanged**, **Added**, 및 **Modified** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="d7653-123">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-123">This is the default.</span></span>|  
    |<span data-ttu-id="d7653-124">**추가**</span><span class="sxs-lookup"><span data-stu-id="d7653-124">**Added**</span></span>|<span data-ttu-id="d7653-125">**현재** 의 모든 행 버전 **Added** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="d7653-126">**삭제**</span><span class="sxs-lookup"><span data-stu-id="d7653-126">**Deleted**</span></span>|<span data-ttu-id="d7653-127">**원래** 의 모든 행 버전 **Deleted** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="d7653-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="d7653-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="d7653-129">**현재** 의 모든 행 버전 **Modified** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="d7653-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="d7653-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="d7653-131">**원래** 의 모든 행 버전 **Modified** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="d7653-132">**없음**</span><span class="sxs-lookup"><span data-stu-id="d7653-132">**None**</span></span>|<span data-ttu-id="d7653-133">행이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-133">No rows.</span></span>|  
    |<span data-ttu-id="d7653-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="d7653-134">**OriginalRows**</span></span>|<span data-ttu-id="d7653-135">**원래** 의 모든 행 버전 **Unchanged**, **Modified**, 및 **Deleted** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="d7653-136">**변경 되지 않은**</span><span class="sxs-lookup"><span data-stu-id="d7653-136">**Unchanged**</span></span>|<span data-ttu-id="d7653-137">**현재** 의 모든 행 버전 **Unchanged** 행.</span><span class="sxs-lookup"><span data-stu-id="d7653-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="d7653-138">행 상태 및 행 버전에 대 한 자세한 내용은 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="d7653-139">다음 코드 예제에서는 재고 수량이 재주문 수준보다 적거나 같은 모든 제품을 표시하는 뷰를 만듭니다. 이 때 먼저 공급자 ID로 정렬한 다음 제품 이름으로 정렬하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d7653-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7653-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7653-140">See Also</span></span>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="d7653-141">DataView</span><span class="sxs-lookup"><span data-stu-id="d7653-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="d7653-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d7653-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
