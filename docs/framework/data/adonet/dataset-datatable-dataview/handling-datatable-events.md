---
title: "DataTable 이벤트 처리"
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
ms.assetid: 62f404a5-13ea-4b93-a29f-55b74a16c9d3
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f7ab9d1043fdd1d4d78ec09390f227f297e471c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="handling-datatable-events"></a><span data-ttu-id="3b72e-102">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="3b72e-102">Handling DataTable Events</span></span>
<span data-ttu-id="3b72e-103"><xref:System.Data.DataTable> 개체는 응용 프로그램에서 처리할 수 있는 일련의 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-103">The <xref:System.Data.DataTable> object provides a series of events that can be processed by an application.</span></span> <span data-ttu-id="3b72e-104">다음 표에서는 `DataTable` 이벤트에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-104">The following table describes `DataTable` events.</span></span>  
  
|<span data-ttu-id="3b72e-105">Event</span><span class="sxs-lookup"><span data-stu-id="3b72e-105">Event</span></span>|<span data-ttu-id="3b72e-106">설명</span><span class="sxs-lookup"><span data-stu-id="3b72e-106">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.Initialized>|<span data-ttu-id="3b72e-107"><xref:System.Data.DataTable.EndInit%2A>의 `DataTable` 메서드가 호출된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-107">Occurs after the <xref:System.Data.DataTable.EndInit%2A> method of a `DataTable` is called.</span></span> <span data-ttu-id="3b72e-108">이 이벤트는 기본적으로 디자인 타임 시나리오를 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-108">This event is intended primarily to support design-time scenarios.</span></span>|  
|<xref:System.Data.DataTable.ColumnChanged>|<span data-ttu-id="3b72e-109"><xref:System.Data.DataColumn>에서 값이 성공적으로 변경된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-109">Occurs after a value has been successfully changed in a <xref:System.Data.DataColumn>.</span></span>|  
|<xref:System.Data.DataTable.ColumnChanging>|<span data-ttu-id="3b72e-110">`DataColumn`의 값이 제출될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-110">Occurs when a value has been submitted for a `DataColumn`.</span></span>|  
|<xref:System.Data.DataTable.RowChanged>|<span data-ttu-id="3b72e-111">`DataColumn` 값 또는 <xref:System.Data.DataRow.RowState%2A>에 있는 <xref:System.Data.DataRow>의 `DataTable`가 성공적으로 변경된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-111">Occurs after a `DataColumn` value or the <xref:System.Data.DataRow.RowState%2A> of a <xref:System.Data.DataRow> in the `DataTable` has been changed successfully.</span></span>|  
|<xref:System.Data.DataTable.RowChanging>|<span data-ttu-id="3b72e-112">`DataColumn` 값 또는 `RowState`에 있는 `DataRow`의 `DataTable`에 대한 변경된 값이 제출될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-112">Occurs when a change has been submitted for a `DataColumn` value or the `RowState` of a `DataRow` in the `DataTable`.</span></span>|  
|<xref:System.Data.DataTable.RowDeleted>|<span data-ttu-id="3b72e-113">`DataRow`의 `DataTable`가 `Deleted`로 표시된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-113">Occurs after a `DataRow` in the `DataTable` has been marked as `Deleted`.</span></span>|  
|<xref:System.Data.DataTable.RowDeleting>|<span data-ttu-id="3b72e-114">`DataRow`의 `DataTable`가 `Deleted`로 표시되기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-114">Occurs before a `DataRow` in the `DataTable` is marked as `Deleted`.</span></span>|  
|<xref:System.Data.DataTable.TableCleared>|<span data-ttu-id="3b72e-115"><xref:System.Data.DataTable.Clear%2A>의 `DataTable` 메서드 호출을 통해 모든 `DataRow`가 성공적으로 삭제된 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-115">Occurs after a call to the <xref:System.Data.DataTable.Clear%2A> method of the `DataTable` has successfully cleared every `DataRow`.</span></span>|  
|<xref:System.Data.DataTable.TableClearing>|<span data-ttu-id="3b72e-116">`Clear` 메서드가 호출된 후 `Clear` 작업이 시작되기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-116">Occurs after the `Clear` method is called but before the `Clear` operation begins.</span></span>|  
|<xref:System.Data.DataTable.TableNewRow>|<span data-ttu-id="3b72e-117">`DataRow`의 `NewRow` 메서드 호출을 통해 새 `DataTable`가 만들어진 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-117">Occurs after a new `DataRow` is created by a call to the `NewRow` method of the `DataTable`.</span></span>|  
|<xref:System.ComponentModel.MarshalByValueComponent.Disposed>|<span data-ttu-id="3b72e-118">`DataTable`이 `Disposed`가 될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-118">Occurs when the `DataTable` is `Disposed`.</span></span> <span data-ttu-id="3b72e-119"><xref:System.ComponentModel.MarshalByValueComponent>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-119">Inherited from <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3b72e-120">행을 추가하거나 삭제하는 대부분의 작업은 `ColumnChanged` 및 `ColumnChanging` 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-120">Most operations that add or delete rows do not raise the `ColumnChanged` and `ColumnChanging` events.</span></span> <span data-ttu-id="3b72e-121">그러나 `ReadXml` 메서드는 `ColumnChanged` 및 `ColumnChanging` 이벤트를 발생시킵니다. 단, 읽고 있는 XML 문서가 `XmlReadMode`이고 `DiffGram`가 `Auto` 또는 `DiffGram`로 설정되어 있는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-121">However, the `ReadXml` method does raise `ColumnChanged` and `ColumnChanging` events, unless the `XmlReadMode` is set to `DiffGram` or is set to `Auto` when the XML document being read is a `DiffGram`.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3b72e-122">`DataSet` 이벤트가 발생한 `RowChanged`에서 데이터를 수정하면 데이터가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-122">Data corruption can occur if data is modified in a `DataSet` from which the `RowChanged` event is raised.</span></span> <span data-ttu-id="3b72e-123">이와 같은 데이터 손상이 발생하면 예외가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-123">No exception will be raised if such data corruption occurs.</span></span>  
  
## <a name="additional-related-events"></a><span data-ttu-id="3b72e-124">추가 관련 이벤트</span><span class="sxs-lookup"><span data-stu-id="3b72e-124">Additional Related Events</span></span>  
 <span data-ttu-id="3b72e-125"><xref:System.Data.DataTable.Constraints%2A> 속성은 <xref:System.Data.ConstraintCollection> 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-125">The <xref:System.Data.DataTable.Constraints%2A> property holds a <xref:System.Data.ConstraintCollection> instance.</span></span> <span data-ttu-id="3b72e-126"><xref:System.Data.ConstraintCollection> 클래스는 <xref:System.Data.ConstraintCollection.CollectionChanged> 이벤트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-126">The <xref:System.Data.ConstraintCollection> class exposes a <xref:System.Data.ConstraintCollection.CollectionChanged> event.</span></span> <span data-ttu-id="3b72e-127">이 이벤트는 `ConstraintCollection`에서 제약 조건이 추가되거나 수정되거나 제거될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-127">This event fires when a constraint is added, modified, or removed from the `ConstraintCollection`.</span></span>  
  
 <span data-ttu-id="3b72e-128"><xref:System.Data.DataTable.Columns%2A> 속성은 <xref:System.Data.DataColumnCollection> 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-128">The <xref:System.Data.DataTable.Columns%2A> property holds a <xref:System.Data.DataColumnCollection> instance.</span></span> <span data-ttu-id="3b72e-129">`DataColumnCollection` 클래스는 <xref:System.Data.DataColumnCollection.CollectionChanged> 이벤트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-129">The `DataColumnCollection` class exposes a <xref:System.Data.DataColumnCollection.CollectionChanged> event.</span></span> <span data-ttu-id="3b72e-130">이 이벤트는 `DataColumn`에서 `DataColumnCollection`이 추가되거나 수정되거나 제거될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-130">This event fires when a `DataColumn` is added, modified, or removed from the `DataColumnCollection`.</span></span> <span data-ttu-id="3b72e-131">열의 이름, 형식, 식 또는 위치 등이 변경되어 열이 수정되면 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-131">Modifications that cause the event to fire include changes to the name, type, expression or ordinal position of a column.</span></span>  
  
 <span data-ttu-id="3b72e-132"><xref:System.Data.DataSet.Tables%2A>의 <xref:System.Data.DataSet> 속성은 <xref:System.Data.DataTableCollection> 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-132">The <xref:System.Data.DataSet.Tables%2A> property of a <xref:System.Data.DataSet> holds a <xref:System.Data.DataTableCollection> instance.</span></span> <span data-ttu-id="3b72e-133">`DataTableCollection` 클래스는 `CollectionChanged`와 `CollectionChanging` 이벤트를 모두 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-133">The `DataTableCollection` class exposes both a `CollectionChanged` and a `CollectionChanging` event.</span></span> <span data-ttu-id="3b72e-134">이 두 이벤트는 `DataTable`에서 `DataSet`이 추가되거나 제거될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-134">These events fire when a `DataTable` is added to or removed from the `DataSet`.</span></span>  
  
 <span data-ttu-id="3b72e-135">`DataRows`가 변경되는 경우에도 관련 <xref:System.Data.DataView>의 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-135">Changes to `DataRows` can also trigger events for an associated <xref:System.Data.DataView>.</span></span> <span data-ttu-id="3b72e-136">`DataView` 클래스는 <xref:System.Data.DataView.ListChanged> 값이 변경되거나 뷰의 구성 또는 정렬 순서가 변경될 때 발생하는 `DataColumn` 이벤트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-136">The `DataView` class exposes a <xref:System.Data.DataView.ListChanged> event that fires when a `DataColumn` value changes or when the composition or sort order of the view changes.</span></span> <span data-ttu-id="3b72e-137"><xref:System.Data.DataRowView> 클래스는 관련 <xref:System.Data.DataRowView.PropertyChanged> 값이 변경될 때 발생하는 `DataColumn` 이벤트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-137">The <xref:System.Data.DataRowView> class exposes a <xref:System.Data.DataRowView.PropertyChanged> event that fires when an associated `DataColumn` value changes.</span></span>  
  
## <a name="sequence-of-operations"></a><span data-ttu-id="3b72e-138">작업 순서</span><span class="sxs-lookup"><span data-stu-id="3b72e-138">Sequence of Operations</span></span>  
 <span data-ttu-id="3b72e-139">다음은 `DataRow`가 추가, 수정 또는 삭제되는 경우의 작업 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-139">Here is the sequence of operations that occur when a `DataRow` is added, modified, or deleted:</span></span>  
  
1.  <span data-ttu-id="3b72e-140">제안된 레코드를 만들고 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-140">Create the proposed record and apply any changes.</span></span>  
  
2.  <span data-ttu-id="3b72e-141">식이 아닌 열의 제약 조건을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-141">Check constraints for non-expression columns.</span></span>  
  
3.  <span data-ttu-id="3b72e-142">가능한 경우 `RowChanging` 또는 `RowDeleting` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-142">Raise the `RowChanging` or `RowDeleting` events as applicable.</span></span>  
  
4.  <span data-ttu-id="3b72e-143">제안된 레코드를 현재 레코드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-143">Set the proposed record to be the current record.</span></span>  
  
5.  <span data-ttu-id="3b72e-144">관련된 인덱스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-144">Update any associated indexes.</span></span>  
  
6.  <span data-ttu-id="3b72e-145">관련 `ListChanged` 개체에 대해 `DataView` 이벤트를 발생시키고, 관련 `PropertyChanged` 개체에 대해 `DataRowView` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-145">Raise `ListChanged` events for associated `DataView` objects and `PropertyChanged` events for associated `DataRowView` objects.</span></span>  
  
7.  <span data-ttu-id="3b72e-146">모든 식 열을 계산합니다. 단, 열의 제약 조건 검사는 지금 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-146">Evaluate all expression columns, but delay checking any constraints on these columns.</span></span>  
  
8.  <span data-ttu-id="3b72e-147">식 열 계산 결과에 영향을 받은 관련 `ListChanged` 개체에 대해 `DataView` 이벤트를 발생시키고, 관련 `PropertyChanged` 개체에 대해 `DataRowView` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-147">Raise `ListChanged` events for associated `DataView` objects and `PropertyChanged` events for associated `DataRowView` objects affected by the expression column evaluations.</span></span>  
  
9. <span data-ttu-id="3b72e-148">가능한 경우 `RowChanged` 또는 `RowDeleted` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-148">Raise `RowChanged` or `RowDeleted` events as applicable.</span></span>  
  
10. <span data-ttu-id="3b72e-149">식 열의 제약 조건을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-149">Check constraints on expression columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b72e-150">식 열이 변경되는 경우에는 `DataTable` 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-150">Changes to expression columns never raise `DataTable` events.</span></span> <span data-ttu-id="3b72e-151">식 열이 변경되면 `DataView` 및 `DataRowView` 이벤트만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-151">Changes to expression columns only raise `DataView` and `DataRowView` events.</span></span> <span data-ttu-id="3b72e-152">식 열은 다른 여러 열에 종속될 수 있으므로 단일 `DataRow` 작업 중 여러 번 계산될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-152">Expression columns can have dependencies on multiple other columns, and can be evaluated multiple times during a single `DataRow` operation.</span></span> <span data-ttu-id="3b72e-153">식을 계산할 때마다 이벤트가 발생합니다. 또한 식 열이 변경되는 경우 동일한 식 열에 대한 여러 이벤트를 포함하여 단일 `DataRow` 작업에서 여러 `ListChanged` 및 `PropertyChanged` 이벤트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-153">Each expression evaluation raises events, and a single `DataRow` operation can raise multiple `ListChanged` and `PropertyChanged` events when expression columns are affected, possibly including multiple events for the same expression column.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3b72e-154"><xref:System.NullReferenceException> 이벤트 처리기 내에서 `RowChanged`을 throw하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3b72e-154">Do not throw a <xref:System.NullReferenceException> within the `RowChanged` event handler.</span></span> <span data-ttu-id="3b72e-155"><xref:System.NullReferenceException>이 `RowChanged`의 `DataTable` 이벤트 내에서 throw되면 `DataTable`이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-155">If a <xref:System.NullReferenceException> is thrown within the `RowChanged` event of a `DataTable`, then the `DataTable` will be corrupted.</span></span>  
  
### <a name="example"></a><span data-ttu-id="3b72e-156">예제</span><span class="sxs-lookup"><span data-stu-id="3b72e-156">Example</span></span>  
 <span data-ttu-id="3b72e-157">다음 예제에서는 `RowChanged`, `RowChanging`, `RowDeleted`, `RowDeleting`, `ColumnChanged`, `ColumnChanging`, `TableNewRow`, `TableCleared` 및 `TableClearing` 이벤트에 대한 이벤트 처리기를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-157">The following example demonstrates how to create event handlers for the `RowChanged`, `RowChanging`, `RowDeleted`, `RowDeleting`, `ColumnChanged`, `ColumnChanging`, `TableNewRow`, `TableCleared`, and `TableClearing` events.</span></span> <span data-ttu-id="3b72e-158">각 이벤트 처리기는 이벤트가 발생하면 콘솔 창에 해당 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3b72e-158">Each event handler displays output in the console window when it is fired.</span></span>  
  
 [!code-csharp[DataWorks DataTable.Events#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.Events/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.Events#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.Events/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3b72e-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b72e-159">See Also</span></span>  
 [<span data-ttu-id="3b72e-160">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="3b72e-160">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="3b72e-161">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="3b72e-161">Handling DataAdapter Events</span></span>](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 [<span data-ttu-id="3b72e-162">데이터 집합 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="3b72e-162">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 [<span data-ttu-id="3b72e-163">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3b72e-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
