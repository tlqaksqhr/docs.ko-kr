---
title: "DataRow 및 DataRowView"
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
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e342ce805880da848da1e17700c055aba2c74f19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="599ae-102">DataRow 및 DataRowView</span><span class="sxs-lookup"><span data-stu-id="599ae-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="599ae-103"><xref:System.Data.DataView>는 <xref:System.Data.DataRowView> 개체의 열거할 수 있는 컬렉션을 노출시킵니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="599ae-104">**DataRowView** 개체 이름 또는 원본 테이블에 있는 열의 서 수 참조로 인덱싱된 개체 배열로 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="599ae-105">에 액세스할 수 있습니다는 <xref:System.Data.DataRow> 가 노출 하는 **DataRowView** 를 사용 하 여는 <xref:System.Data.DataRowView.Row%2A> 속성은 **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="599ae-106">사용 하 여 값을 볼 때는 **DataRowView**, <xref:System.Data.DataView.RowStateFilter%2A> 의 속성은 **DataView** 은 기본 행 버전 결정 **DataRow** 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="599ae-107">사용 하 여 다른 행 버전에 액세스 하는 방법에 대 한 내용은 **DataRow**, 참조 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="599ae-108">다음 코드 예제에서는 테이블의 현재 값과 원래 값을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="599ae-108">The following code example displays all the current and original values in a table.</span></span>  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="599ae-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="599ae-109">See Also</span></span>  
 <xref:System.Data.DataRowVersion>  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="599ae-110">DataView</span><span class="sxs-lookup"><span data-stu-id="599ae-110">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="599ae-111">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="599ae-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
