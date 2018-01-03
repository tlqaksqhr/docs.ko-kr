---
title: "데이터 보기 수정"
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
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 921707b07f1e8c8a9208df7de74512325f3027d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-dataviews"></a><span data-ttu-id="feea8-102">데이터 보기 수정</span><span class="sxs-lookup"><span data-stu-id="feea8-102">Modifying DataViews</span></span>
<span data-ttu-id="feea8-103"><xref:System.Data.DataView>를 사용하여 원본 테이블의 데이터 행을 추가, 삭제 또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="feea8-104">사용 하는 기능은 **DataView** 의 세 가지 부울 속성 중 하나를 설정 하 여 제어 되는 원본 테이블에 데이터를 수정 하는 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="feea8-105">이러한 속성에는 <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> 및 <xref:System.Data.DataView.AllowDelete%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="feea8-106">으로 설정 되어 **true** 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="feea8-107">경우 **AllowNew** 은 **true**를 사용할 수 있습니다는 <xref:System.Data.DataView.AddNew%2A> 의 메서드는 **DataView** 새로 만들려면 <xref:System.Data.DataRowView>합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="feea8-108">새 행 내부에 추가 <xref:System.Data.DataTable> 될 때까지 <xref:System.Data.DataRowView.EndEdit%2A> 의 메서드는 **DataRowView** 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="feea8-109">경우는 <xref:System.Data.DataRowView.CancelEdit%2A> 의 메서드는 **DataRowView** 가 호출 된 새 행이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="feea8-110">또한에 참고 하나만 편집할 수 **DataRowView** 한 번에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="feea8-111">호출 하는 경우는 **AddNew** 또는 **BeginEdit** 의 메서드는 **DataRowView** 보류 중인 행이 있는 동안 **EndEdit** 에 암시적으로 호출 되는 보류 중인 행입니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="feea8-112">때 **EndEdit** 은 호출 내부에 변경 내용이 적용 됩니다 **DataTable** 수 나중에 커밋하거나 거부할 사용 하는 **AcceptChanges** 또는  **RejectChanges** 의 메서드는 **DataTable**, **DataSet**, 또는 **DataRow** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="feea8-113">경우 **AllowNew** 은 **false**를 호출 하면 예외가 throw 됩니다는 **AddNew** 의 메서드는 **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="feea8-114">경우 **AllowEdit** 은 **true**의 콘텐츠를 수정할 수는 **DataRow** 통해는 **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="feea8-115">변경 내용을 사용 하 여 원본 행을 확인할 수 있습니다 **DataRowView.EndEdit** 를 사용 하 여 변경 사항을 거부 또는 **DataRowView.CancelEdit**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="feea8-116">행은 한 번에 하나씩만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="feea8-117">호출 하는 경우는 **AddNew** 또는 **BeginEdit** 의 메서드는 **DataRowView** 보류 중인 행이 있는 동안 **EndEdit** 에 암시적으로 호출 보류 중인 행입니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="feea8-118">때 **EndEdit** 를 호출할 제안 된 변경 내용에 배치 됩니다는 **현재** 은 기본 행 버전 **DataRow** 수 나중에 커밋하거나 거부할는 를사용하여 **AcceptChanges** 또는 **RejectChanges** 의 메서드는 **DataTable**, **DataSet**, 또는 **DataRow** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="feea8-119">경우 **AllowEdit** 은 **false**에서 값을 수정 하려고 하면 예외가 throw 되는 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="feea8-120">기존 **DataRowView** 편집 되는 내부 이벤트 **DataTable** 제안 된 변경 내용으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="feea8-121">호출 하는 경우 유의 **EndEdit** 또는 **CancelEdit** 은 기본 **DataRow**, 보류 중인 변경 내용을 적용 되거나 취소 여부에 관계 없이 될  **EndEdit** 또는 **CancelEdit** 라고 하는 **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="feea8-122">경우 **AllowDelete** 은 **true**, 행을 삭제할 수는 **DataView** 를 사용 하 여는 **삭제** 의 메서드는 **DataView**  또는 **DataRowView** 개체 및 행 내부에서 삭제 됩니다 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="feea8-123">나중에 커밋 또는 사용 하 여 삭제를 거부할 수 **AcceptChanges** 또는 **RejectChanges** 각각.</span><span class="sxs-lookup"><span data-stu-id="feea8-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="feea8-124">경우 **AllowDelete** 은 **false**, 호출 하는 경우 예외가 throw 되는 **삭제** 의 메서드는 **DataView** 또는  **DataRowView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="feea8-125">다음 코드 예제에서는 사용 하 여 비활성화는 **DataView** 를 delete 행과 새 행을 사용 하 여 원본 테이블을 추가 하는 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="feea8-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="feea8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="feea8-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="feea8-127">DataView</span><span class="sxs-lookup"><span data-stu-id="feea8-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="feea8-128">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="feea8-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
