---
title: "DataTable 제약 조건"
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
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 500dad1699843bae04aea6d5c16a1ccf53bb102a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="datatable-constraints"></a><span data-ttu-id="57c9d-102">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="57c9d-102">DataTable Constraints</span></span>
<span data-ttu-id="57c9d-103">제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="57c9d-104">제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="57c9d-105">제약 조건이 적용 됩니다 때는 `System.Data.DataSet.EnforceConstraints` 의 속성은 <xref:System.Data.DataSet> 은 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="57c9d-106">`EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57c9d-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="57c9d-107">ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="57c9d-108">기본적으로 제약 조건을 둘 다 만들어집니다 자동으로 추가 하 여 두 개 이상의 테이블 간에 관계를 만들 때 한 <xref:System.Data.DataRelation> 에 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="57c9d-109">그러나 지정 하 여이 동작을 비활성화할 수는 **createConstraints** = **false** 관계를 만들 때.</span><span class="sxs-lookup"><span data-stu-id="57c9d-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="57c9d-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="57c9d-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="57c9d-111">A **ForeignKeyConstraint** 업데이트 및 삭제 관련된 테이블에 전파 하는 방법에 대 한 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="57c9d-112">예를 들어 한 테이블의 행에 있는 값이 업데이트 되거나 삭제와 같은 값을도 또는에서 사용 될 하나 이상의 관련 테이블을 **ForeignKeyConstraint** 관련된 테이블에서 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="57c9d-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> 및 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 의 속성은 **ForeignKeyConstraint** 사용자가을 삭제 하거나 관련된 테이블의 행을 업데이트 하는 경우 수행할 동작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="57c9d-114">다음 표에 다양 한 설정에 사용할 수는 **DeleteRule** 및 **UpdateRule** 의 속성은 **ForeignKeyConstraint**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="57c9d-115">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="57c9d-115">Rule setting</span></span>|<span data-ttu-id="57c9d-116">설명</span><span class="sxs-lookup"><span data-stu-id="57c9d-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="57c9d-117">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="57c9d-117">**Cascade**</span></span>|<span data-ttu-id="57c9d-118">관련 행을 삭제하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="57c9d-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="57c9d-119">**SetNull**</span></span>|<span data-ttu-id="57c9d-120">에 관련된 행의 값을 설정 **DBNull**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="57c9d-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="57c9d-121">**SetDefault**</span></span>|<span data-ttu-id="57c9d-122">관련 행의 값을 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="57c9d-123">**없음**</span><span class="sxs-lookup"><span data-stu-id="57c9d-123">**None**</span></span>|<span data-ttu-id="57c9d-124">관련 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-124">Take no action on related rows.</span></span> <span data-ttu-id="57c9d-125">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-125">This is the default.</span></span>|  
  
 <span data-ttu-id="57c9d-126">A **ForeignKeyConstraint** 제한할 수, 관련 된 열 뿐만 아니라 전파에 대 한 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="57c9d-127">속성에 대 한 설정에 따라는 **ForeignKeyConstraint** , 열의 경우는 **EnforceConstraints** 의 속성은 **데이터 집합** 은 **true**, 부모 행에서 특정 작업을 수행 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="57c9d-128">예를 들어 경우는 **DeleteRule** 속성의는 **ForeignKeyConstraint** 은 **None**, 모든 자식 행을 설정한 경우 부모 행을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="57c9d-129">단일 열 사이 또는 사용 하 여 열 배열 사이 외래 키 제약 조건을 만들 수는 **ForeignKeyConstraint** 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="57c9d-130">그 결과 전달 **ForeignKeyConstraint** 개체는 **추가** 메서드는 테이블의 **제약 조건** 속성, 즉는 **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="57c9d-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="57c9d-131">다양 한 오버 로드에 생성자 인수를 전달할 수도 있습니다는 **추가** 의 메서드는 **ConstraintCollection** 만들려는 **ForeignKeyConstraint**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="57c9d-132">만들 때 한 **ForeignKeyConstraint**를 전달할 수 있습니다는 **DeleteRule** 및 **UpdateRule** 인수 또는 있습니다으로 값을 생성자에서와 같이 속성으로 설정할 수는 다음 예에서는 (여기서는 **DeleteRule** 값으로 설정 되어 **None**).</span><span class="sxs-lookup"><span data-stu-id="57c9d-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="57c9d-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="57c9d-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="57c9d-134">사용 하 여 행의 변화에 허용 되는 **AcceptChanges** 메서드 또는 취소를 사용 하는 **RejectChanges** 의 메서드는 **데이터 집합**, **DataTable**, 또는 **DataRow**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="57c9d-135">경우는 **DataSet** 포함 **ForeignKeyConstraints**호출는 **AcceptChanges** 또는 **RejectChanges** 메서드는 적용 **AcceptRejectRule**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="57c9d-136">**AcceptRejectRule** 의 속성은 **ForeignKeyConstraint** 자식 요소에서 수행 될 작업을 결정 경우 행 **AcceptChanges** 또는  **RejectChanges** 부모 행에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="57c9d-137">다음 표에서 사용할 수 있는 설정에 대 한는 **AcceptRejectRule**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="57c9d-138">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="57c9d-138">Rule setting</span></span>|<span data-ttu-id="57c9d-139">설명</span><span class="sxs-lookup"><span data-stu-id="57c9d-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="57c9d-140">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="57c9d-140">**Cascade**</span></span>|<span data-ttu-id="57c9d-141">자식 행의 변경을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="57c9d-142">**없음**</span><span class="sxs-lookup"><span data-stu-id="57c9d-142">**None**</span></span>|<span data-ttu-id="57c9d-143">자식 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-143">Take no action on child rows.</span></span> <span data-ttu-id="57c9d-144">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="57c9d-145">예제</span><span class="sxs-lookup"><span data-stu-id="57c9d-145">Example</span></span>  
 <span data-ttu-id="57c9d-146">다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.ConstraintCollection> 개체의 <xref:System.Data.DataTable>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="57c9d-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="57c9d-147">UniqueConstraint</span></span>  
 <span data-ttu-id="57c9d-148">**UniqueConstraint** 단일 열 또는 열 배열에 지정할 수 있는 개체는 **DataTable**, 지정 된 열 또는 열에 모든 데이터는 각 행 마다 고유한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="57c9d-149">사용 하 여 열 또는 열 배열의 unique 제약 조건을 만들 수 있습니다는 **UniqueConstraint** 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="57c9d-150">그 결과 전달 **UniqueConstraint** 개체는 **추가** 메서드 테이블의 **제약 조건** 속성, 즉는 **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="57c9d-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="57c9d-151">다양 한 오버 로드에 생성자 인수를 전달할 수도 있습니다는 **추가** 의 메서드는 **ConstraintCollection** 만들려는 **UniqueConstraint**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="57c9d-152">만들 때 한 **UniqueConstraint** 열 또는 열에 대 한 선택적 지정할 수 있습니다 하나 이상의 열이 기본 키인지 여부.</span><span class="sxs-lookup"><span data-stu-id="57c9d-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="57c9d-153">열에 대해 unique 제약 조건을 설정 하 여 만들 수도 있습니다는 **Unique** 열의 속성 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="57c9d-154">설정 또는 **Unique** 의 단일 열을 속성 **false** 있을 수 있는 모든 unique 제약 조건을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="57c9d-155">하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="57c9d-156">열을 제거 하는 경우는 **PrimaryKey** 속성은 **DataTable**, **UniqueConstraint** 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="57c9d-157">다음 예제에서는 한 **UniqueConstraint** 의 두 개의 열에는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="57c9d-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="57c9d-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57c9d-158">See Also</span></span>  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [<span data-ttu-id="57c9d-159">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="57c9d-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="57c9d-160">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="57c9d-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="57c9d-161">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="57c9d-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
