---
title: "AcceptChanges 및 RejectChanges"
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
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ac64fee869ce58413e799f4217f009ef6ae91a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="1be79-102">AcceptChanges 및 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="1be79-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="1be79-103">데이터에 대 한 변경 내용의 정확성을 확인 한 후는 <xref:System.Data.DataTable>를 사용 하 여 변경 내용을 적용 수 있습니다는 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드는 <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataSet>, 하는 설정의 **현재** 행 값이 고 **원래** 값을 설정 합니다는 **RowState** 속성을 **Unchanged**합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="1be79-104">수락 하거나 변경 내용이 거부 된 모든 지웁니다 **RowError** 정보 및 설정의 **HasErrors** 속성을 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="1be79-105">또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="1be79-106">자세한 내용은 참조 [Dataadapter로 데이터 원본 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="1be79-107">외래 키 제약 조건에 있는 경우에 **DataTable**, 변경 내용을 적용 하거나 사용 하 여 취소 **AcceptChanges** 및 **RejectChanges** 는 의자식행으로전파 **DataRow** 에 따라는 **ForeignKeyConstraint.AcceptRejectRule**합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="1be79-108">자세한 내용은 참조 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="1be79-109">다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="1be79-110">해결 된 오류를 참고는 **RowError** 값이 빈 문자열로 다시 설정 일으키는 **HasErrors** 속성으로 설정 되어야 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="1be79-111">모든 행 오류와 함께 해결 되거나 거부 되 면 **AcceptChanges** 전체에 대 한 모든 변경 내용을 적용 하기 위해 호출 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="1be79-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="1be79-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1be79-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="1be79-113">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="1be79-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="1be79-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="1be79-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
