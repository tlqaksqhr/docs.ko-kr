---
title: DataTable에서 데이터 보기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: 5d39d2a856a40b5ea20832a544ede360313309d3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761248"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="de910-102">DataTable에서 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="de910-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="de910-103">내용에 액세스할 수 있습니다는 <xref:System.Data.DataTable> 를 사용 하 여는 **행** 및 **열** 의 컬렉션은 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="de910-104">사용할 수도 있습니다는 <xref:System.Data.DataTable.Select%2A> 에 있는 데이터의 하위 집합을 반환 하는 메서드는 **DataTable** 검색 조건을 포함 하 여 기준에 따라 정렬 순서 및 행 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="de910-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="de910-105">또한 사용할 수는 <xref:System.Data.DataRowCollection.Find%2A> 의 메서드는 **DataRowCollection** 기본 키 값을 사용 하 여 특정 행을 검색할 때.</span><span class="sxs-lookup"><span data-stu-id="de910-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="de910-106">**선택** 의 메서드는 **DataTable** 개체 집합을 반환 <xref:System.Data.DataRow> 지정된 된 조건과 일치 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="de910-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="de910-107">**선택** 는 필터 식, 정렬 식의 선택적 옵션 인수가 사용 및 **DataViewRowState**합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="de910-108">필터 식에 따라 반환 하는 행을 식별 **DataColumn** 와 같은 값 `LastName = 'Smith'`합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="de910-109">정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="de910-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="de910-110">식을 작성 하는 방법에 대 한 규칙에 대 한 참조는 <xref:System.Data.DataColumn.Expression%2A> 의 속성은 **DataColumn** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="de910-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="de910-111">다양 한 호출을 수행 하는 경우는 **선택** 의 메서드는 **DataTable**를 먼저 만들어 성능을 향상 시킬 수 있습니다는 <xref:System.Data.DataView> 에 대 한는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="de910-112">만들기는 **DataView** 테이블의 행을 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="de910-113">**선택** 메서드 다음 인덱스를 개이고에서 쿼리 결과 생성 하는 데 시간이 상당히 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="de910-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="de910-114">만드는 방법에 대해서는 **DataView** 에 대 한는 **DataTable**, 참조 [데이터 보기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="de910-115">**선택** 메서드 보거나 조작 하려는 행의 버전에 따라 결정 된 <xref:System.Data.DataViewRowState>합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="de910-116">다음 표에 가능한 **DataViewRowState** 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="de910-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="de910-117">DataViewRowState 값</span><span class="sxs-lookup"><span data-stu-id="de910-117">DataViewRowState value</span></span>|<span data-ttu-id="de910-118">설명</span><span class="sxs-lookup"><span data-stu-id="de910-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="de910-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="de910-119">**CurrentRows**</span></span>|<span data-ttu-id="de910-120">변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행</span><span class="sxs-lookup"><span data-stu-id="de910-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="de910-121">**삭제**</span><span class="sxs-lookup"><span data-stu-id="de910-121">**Deleted**</span></span>|<span data-ttu-id="de910-122">삭제된 행</span><span class="sxs-lookup"><span data-stu-id="de910-122">A deleted row.</span></span>|  
|<span data-ttu-id="de910-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="de910-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="de910-124">원래 데이터가 수정된 현재 버전</span><span class="sxs-lookup"><span data-stu-id="de910-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="de910-125">(참조 **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="de910-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="de910-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="de910-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="de910-127">수정된 모든 행의 원래 버전.</span><span class="sxs-lookup"><span data-stu-id="de910-127">The original version of all modified rows.</span></span> <span data-ttu-id="de910-128">현재 버전은 사용할 수 있는 사용 하 여 **ModifiedCurrent**합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="de910-129">**추가**</span><span class="sxs-lookup"><span data-stu-id="de910-129">**Added**</span></span>|<span data-ttu-id="de910-130">새 행</span><span class="sxs-lookup"><span data-stu-id="de910-130">A new row.</span></span>|  
|<span data-ttu-id="de910-131">**없음**</span><span class="sxs-lookup"><span data-stu-id="de910-131">**None**</span></span>|<span data-ttu-id="de910-132">없음</span><span class="sxs-lookup"><span data-stu-id="de910-132">None.</span></span>|  
|<span data-ttu-id="de910-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="de910-133">**OriginalRows**</span></span>|<span data-ttu-id="de910-134">변경되지 않거나 삭제된 행을 포함하는 원래 행</span><span class="sxs-lookup"><span data-stu-id="de910-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="de910-135">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="de910-135">**Unchanged**</span></span>|<span data-ttu-id="de910-136">변경되지 않은 행</span><span class="sxs-lookup"><span data-stu-id="de910-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="de910-137">다음 예제에서는 **데이터 집합** 만 사용 하는 행 인 있도록 개체가 필터링 **DataViewRowState** 로 설정 된 **CurrentRows**합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 <span data-ttu-id="de910-138">**선택** 메서드를 사용 하 여 다른 행을 반환할 수 있습니다 **RowState** 값 이나 필드 값입니다.</span><span class="sxs-lookup"><span data-stu-id="de910-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="de910-139">다음 예제에서는 반환 된 **DataRow** 행을 삭제 하 고 반환 하는 값을 모두 참조 하는 배열 **DataRow** 배열의 모든 행을 참조 하는 기준으로 정렬 된 **에서는**, 여기서는 **CustID** 열이 5 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="de910-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="de910-140">에 대 한 정보를 보는 방법에 대 한 내용은 **Deleted** 행에서 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de910-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## <a name="see-also"></a><span data-ttu-id="de910-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de910-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="de910-142">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="de910-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="de910-143">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="de910-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="de910-144">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="de910-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
