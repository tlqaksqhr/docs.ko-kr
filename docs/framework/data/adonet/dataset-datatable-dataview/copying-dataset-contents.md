---
title: "데이터 집합 콘텐츠 복사"
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
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d8f9eac80d7a6679e7b3717446e79caf54a5fed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="a3e05-102">데이터 집합 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="a3e05-102">Copying DataSet Contents</span></span>
<span data-ttu-id="a3e05-103">복사본을 만들 수는 <xref:System.Data.DataSet> 하면 원래 데이터는 영향을 주지 않고 데이터로 작업 하거나 사용할 수 있도록에서 데이터의 하위 집합으로는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="a3e05-104">복사 하는 경우는 **DataSet**를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-104">When copying a **DataSet**, you can:</span></span>  
  
-   <span data-ttu-id="a3e05-105">정확한 복사본을 만듭니다는 **DataSet**, 스키마, 데이터, 행 상태 정보 및 행 버전을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
-   <span data-ttu-id="a3e05-106">만들기는 **DataSet** 기존 스키마를 포함 하 **데이터 집합**, 하지만 수정 된 행만 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="a3e05-107">수정 된 모든 행을 반환 하거나 특정을 지정할 수 있습니다 **DataRowState**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="a3e05-108">행 상태에 대 한 자세한 내용은 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
-   <span data-ttu-id="a3e05-109">스키마 나 관계형 구조만 복사는 **데이터 집합** 없이 모든 행을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="a3e05-110"><xref:System.Data.DataTable>를 사용하여 행을 기존 <xref:System.Data.DataTable.ImportRow%2A>로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="a3e05-111">정확한 복사본을 만들려면는 **데이터 집합** 사용 하 여, 스키마와 데이터 모두 포함 하는 <xref:System.Data.DataSet.Copy%2A> 의 메서드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="a3e05-112">다음 코드 예제에는의 정확한 복사본을 만드는 방법을 보여 줍니다는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="a3e05-113">복사본을 만들 수는 **데이터 집합** 이 포함 된 스키마만 데이터 표시 하는 **Added**, **Modified**, 또는 **Deleted** 행을 사용 하 여는 <xref:System.Data.DataSet.GetChanges%2A> 의 메서드는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="a3e05-114">사용할 수도 있습니다 **GetChanges** 전달 하 여 지정한 행 상태의 행만 반환 하는 **DataRowState** 호출 시 값 **GetChanges**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="a3e05-115">다음 코드 예제에서는 전달 하는 방법을 보여 줍니다.는 **DataRowState** 를 호출할 때 **GetChanges**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="a3e05-116">복사본을 만들 수는 **데이터 집합** 스키마만 포함 하는, 사용 하 여는 <xref:System.Data.DataSet.Clone%2A> 의 메서드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="a3e05-117">복제 된 기존 행을 추가할 수도 **데이터 집합** 를 사용 하는 **ImportRow** 의 메서드는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="a3e05-118">**ImportRow** 지정된 된 테이블에 데이터, 행 상태 및 행 버전 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="a3e05-119">열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="a3e05-120">다음 코드 예제에서는의 복제본을 만듭니다는 **DataSet** 다음 원래에서 행을 추가 **데이터 집합** 에 **고객** 테이블에 **데이터 집합**  고객에 대 한 복제본 위치는 **CountryRegion** 열에 값이 "Germany"입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e05-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3e05-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3e05-121">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="a3e05-122">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="a3e05-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="a3e05-123">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a3e05-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
