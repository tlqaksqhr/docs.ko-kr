---
title: DataTable 편집
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: b806e642a5cce6a55ff0dcecc9b018f3ee78bad8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758622"
---
# <a name="datatable-edits"></a><span data-ttu-id="58369-102">DataTable 편집</span><span class="sxs-lookup"><span data-stu-id="58369-102">DataTable Edits</span></span>
<span data-ttu-id="58369-103"><xref:System.Data.DataRow>에서 열 값을 변경하는 경우, 변경된 값은 현재 상태의 행에 바로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="58369-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="58369-104"><xref:System.Data.DataRowState> 으로 설정 됩니다 **Modified**, 변경 내용을 적용는 또는 사용 하 여 취소 하 고는 <xref:System.Data.DataRow.AcceptChanges%2A> 또는 <xref:System.Data.DataRow.RejectChanges%2A> 의 메서드는 **DataRow**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="58369-105">**DataRow** 편집 하는 동안 행의 상태를 일시 중단 하는 데 사용할 수 있는 세 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="58369-106">이러한 메서드에는 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 및 <xref:System.Data.DataRow.CancelEdit%2A>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58369-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="58369-107">열 값을 수정 하는 경우는 **DataRow** 를 직접는 **DataRow** 사용 하 여 열 값을 관리 하는 **현재**, **기본**, 및 **원래** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="58369-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="58369-108">이러한 행 버전 이외에 **BeginEdit**, **EndEdit**, 및 **CancelEdit** 메서드 네 번째 행 버전을 사용: **Proposed**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="58369-109">행 버전에 대 한 자세한 내용은 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="58369-110">**Proposed** 편집 작업으로 호출 하 여 시작 하는 동안 행 버전이 존재 **BeginEdit** 를 사용 하 여 끝나는 **EndEdit** 또는 **CancelEdit**  또는 호출 하 여 **AcceptChanges** 또는 **RejectChanges**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="58369-111">편집 작업을 하는 동안 있습니다 유효성 검사 논리를 적용할 수 개별 열을 평가 하 여는 **ProposedValue** 에 **ColumnChanged** 의 이벤트는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="58369-112">**ColumnChanged** 이벤트에는 **DataColumnChangeEventArgs** 변경 되 고 있는 열에 및에 대 한 참조를 유지 하는 **ProposedValue**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="58369-113">사용자는 제안된 값을 검사한 후 이 값을 수정하거나 편집을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58369-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="58369-114">편집이 종료 되는 행의 이동은 **Proposed** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="58369-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="58369-115">호출 하 여 편집을 확인 수 **EndEdit**, 하거나 호출 하 여 취소할 수 있습니다 **CancelEdit**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="58369-116">하지만 **EndEdit** 편집을 확인 하는 **데이터 집합** 실제로 변경 될 때까지 받아들이지 않는 **AcceptChanges** 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58369-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="58369-117">이때 또한 호출 하는 경우 **AcceptChanges** 사용 하 여 편집을 종료 하기 전에 **EndEdit** 또는 **CancelEdit**, 편집이 종료 및 **제안됨** 행 값이 둘 다에 대해 허용 되는 **현재** 및 **원래** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="58369-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="58369-118">동일한 방식으로 호출 **RejectChanges** 편집을 종료 하 고 삭제는 **현재** 및 **Proposed** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="58369-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="58369-119">호출 **EndEdit** 또는 **CancelEdit** 호출한 후 **AcceptChanges** 또는 **RejectChanges** 편집에 이미 있기 때문에 아무 효과가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58369-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="58369-120">다음 예제에서는 사용 하는 방법을 **BeginEdit** 와 **EndEdit** 및 **CancelEdit**합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="58369-121">이 예제는 또한 확인는 **ProposedValue** 에 **ColumnChanged** 이벤트 편집을 취소 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58369-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="58369-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58369-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="58369-123">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="58369-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="58369-124">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="58369-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="58369-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="58369-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
