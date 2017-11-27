---
title: "DataRow 삭제"
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
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9eb89d711cbf66f3b6816e597c14359be1f3639
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datarow-deletion"></a><span data-ttu-id="83aea-102">DataRow 삭제</span><span class="sxs-lookup"><span data-stu-id="83aea-102">DataRow Deletion</span></span>
<span data-ttu-id="83aea-103">두 가지가 삭제 하는 데 사용할 수는 <xref:System.Data.DataRow> 에서 개체는 <xref:System.Data.DataTable> 개체:는 **제거** 의 메서드는 <xref:System.Data.DataRowCollection> 개체 및 <xref:System.Data.DataRow.Delete%2A> 의 메서드는 **DataRow**개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="83aea-104">반면는 <xref:System.Data.DataRowCollection.Remove%2A> 메서드 삭제는 **DataRow** 에서 **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> 메서드는 삭제할 행을 표시만 합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="83aea-105">응용 프로그램 호출 때 실제 제거는 **AcceptChanges** 메서드.</span><span class="sxs-lookup"><span data-stu-id="83aea-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="83aea-106"><xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="83aea-107">삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="83aea-108"><xref:System.Data.DataRow.Delete%2A> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRowCollection.Remove%2A> 또는 <xref:System.Data.DataRowCollection>가 호출되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="83aea-109"><xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>는 컬렉션의 상태를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="83aea-110">사용 하는 경우는 <xref:System.Data.DataSet> 또는 **DataTable** 함께에서 **DataAdapter** 및 사용 하 여 관계형 데이터 원본에서 **삭제** 의 메서드는  **DataRow** 행을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="83aea-111">**삭제** 메서드는 해당 행을 표시 **Deleted** 에 **DataSet** 또는 **DataTable** 되지만 제거 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="83aea-112">대신,는 **DataAdapter** 로 표시 된 행을 발견 하면 **Deleted**, 실행의 **DeleteCommand** 데이터 소스에서 행을 삭제 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="83aea-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="83aea-113">행 수 다음 영구적으로 제거를 사용 하 여 **AcceptChanges** 메서드.</span><span class="sxs-lookup"><span data-stu-id="83aea-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="83aea-114">사용 하는 경우 **제거** 행을 삭제 하려면 해당 행은 테이블에서 완전히 제거 되지만 **DataAdapter** 데이터 소스에서 행을 삭제 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="83aea-115">**제거** 의 메서드는 **DataRowCollection** 사용는 **DataRow** 인수로 서 다음 예제와 같이 컬렉션에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="83aea-116">반대로 다음 예제에서는 호출 하는 방법을 **삭제** 에서 메서드는 **DataRow** 변경 하려면 해당 **RowState** 를 **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="83aea-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="83aea-117">행 삭제로 표시 되 고 호출 하는 경우는 **AcceptChanges** 의 메서드는 **DataTable** 개체에서 행이 제거 되는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="83aea-118">반대로, 호출 하는 경우 **RejectChanges**, **RowState** 행의 되돌아갑니다로 표시 되기 전에 **Deleted**합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83aea-119">경우는 **RowState** 의 **DataRow** 은 **Added**, 테이블에만 추가 되 것을 의미 하 고으로 표시 되어 있어 **Deleted**는 테이블에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83aea-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83aea-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83aea-120">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="83aea-121">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="83aea-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="83aea-122">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="83aea-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
