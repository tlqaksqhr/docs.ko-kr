---
title: DataTable에 데이터 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: c58f64dba0bceb4a35c67e16193a6627837436e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767130"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="b7f5d-102">DataTable에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="b7f5d-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="b7f5d-103"><xref:System.Data.DataTable>을 만들고 열 및 제약 조건을 사용하여 해당 테이블의 구조를 정의한 후에는 새 데이터 행을 테이블에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="b7f5d-104">새 행을 추가하려면 새 변수의 형식을 <xref:System.Data.DataRow>로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="b7f5d-105">새 **DataRow** 개체를 호출 하는 경우 반환 된 <xref:System.Data.DataTable.NewRow%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="b7f5d-106">**DataTable** 만듭니다는 **DataRow** 기반 개체는 테이블의 구조에 정의 된 대로 <xref:System.Data.DataColumnCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="b7f5d-107">다음 예제에서는를 호출 하 여 새 행을 만드는 방법을 **NewRow** 메서드.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="b7f5d-108">그러면 다음 예제와 같이 인덱스나 열 이름을 사용하여 새로 추가된 행을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="b7f5d-109">새 행에 데이터를 삽입 한 후는 **추가** 메서드를 사용 하는 행을 추가 하는 <xref:System.Data.DataRowCollection>다음 코드에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="b7f5d-110">호출할 수도 있습니다는 **추가** 로 형식화 된 값의 배열에 전달 하 여 새 행을 추가 하는 방법을 <xref:System.Object>다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="b7f5d-111">형식의 값 배열을 전달 **개체**을 **추가** 메서드 테이블에 새 행을 만들고 개체 배열에 있는 값에 해당 열 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="b7f5d-112">배열 값은 테이블에 나타나는 순서에 따라 해당 열과 순서대로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="b7f5d-113">다음 예제에서는 10 개의 행 새로 만든 추가 **고객** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b7f5d-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7f5d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7f5d-114">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="b7f5d-115">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="b7f5d-115">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="b7f5d-116">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b7f5d-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
