---
title: "DataAdapter로 데이터 원본 업데이트"
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
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 44bd1672c6423277fa90eee98ce954e7c1c5334e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="updating-data-sources-with-dataadapters"></a><span data-ttu-id="31346-102">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="31346-102">Updating Data Sources with DataAdapters</span></span>
<span data-ttu-id="31346-103">`Update`의 <xref:System.Data.Common.DataAdapter> 메서드를 호출하면 <xref:System.Data.DataSet>의 변경 내용이 데이터 소스에 다시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-103">The `Update` method of the <xref:System.Data.Common.DataAdapter> is called to resolve changes from a <xref:System.Data.DataSet> back to the data source.</span></span> <span data-ttu-id="31346-104">`Update` 메서드는 `Fill` 메서드와 마찬가지로 `DataSet`의 인스턴스, 선택적 <xref:System.Data.DataTable> 개체 또는 `DataTable` 이름을 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-104">The `Update` method, like the `Fill` method, takes as arguments an instance of a `DataSet`, and an optional <xref:System.Data.DataTable> object or `DataTable` name.</span></span> <span data-ttu-id="31346-105">`DataSet` 인스턴스는 변경 내용을 포함하는 `DataSet`이며 `DataTable`은 변경 내용을 검색할 테이블을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-105">The `DataSet` instance is the `DataSet` that contains the changes that have been made, and the `DataTable` identifies the table from which to retrieve the changes.</span></span> <span data-ttu-id="31346-106">`DataTable`을 지정하지 않으면 `DataTable`의 첫 번째 `DataSet`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-106">If no `DataTable` is specified, the first `DataTable` in the `DataSet` is used.</span></span>  
  
 <span data-ttu-id="31346-107">`Update` 메서드를 호출하면 `DataAdapter`가 변경 내용을 분석하여 INSERT, UPDATE, DELETE 등의 적절한 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-107">When you call the `Update` method, the `DataAdapter` analyzes the changes that have been made and executes the appropriate command (INSERT, UPDATE, or DELETE).</span></span> <span data-ttu-id="31346-108">`DataAdapter`에 대한 변경 사항이 발견되면 <xref:System.Data.DataRow>는 <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 또는 <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>를 사용하여 변경 내용을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-108">When the `DataAdapter` encounters a change to a <xref:System.Data.DataRow>, it uses the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, or <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> to process the change.</span></span> <span data-ttu-id="31346-109">이로써 가능한 경우 디자인 타임에 저장 프로시저를 사용하여 명령 구문을 지정함으로써 ADO.NET 응용 프로그램의 성능을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-109">This allows you to maximize the performance of your ADO.NET application by specifying command syntax at design time and, where possible, through the use of stored procedures.</span></span> <span data-ttu-id="31346-110">`Update`를 호출하기 전에 명령을 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-110">You must explicitly set the commands before calling `Update`.</span></span> <span data-ttu-id="31346-111">`Update`를 호출했는데 삭제된 행에 대한 `DeleteCommand`가 없는 경우와 같이 특정 업데이트에 사용할 적절한 명령이 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-111">If `Update` is called and the appropriate command does not exist for a particular update (for example, no `DeleteCommand` for deleted rows), an exception is thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31346-112">SQL Server 저장 프로시저를 통해 `DataAdapter`로 데이터를 편집하거나 삭제하는 경우에는 저장 프로시저 정의에 SET NOCOUNT ON을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-112">If you are using SQL Server stored procedures to edit or delete data using a `DataAdapter`, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="31346-113">SET NOCOUNT ON을 사용하는 경우 반환되는 행 개수가 0이 되어 `DataAdapter`가 이를 동시성 충돌로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-113">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="31346-114">그 결과 <xref:System.Data.DBConcurrencyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-114">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
 <span data-ttu-id="31346-115">명령 매개 변수를 사용하여 `DataSet`의 수정된 각 행에 대해 SQL 문이나 저장 프로시저의 입력 및 출력 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-115">Command parameters can be used to specify input and output values for an SQL statement or stored procedure for each modified row in a `DataSet`.</span></span> <span data-ttu-id="31346-116">자세한 내용은 참조 [DataAdapter 매개 변수](../../../../docs/framework/data/adonet/dataadapter-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-116">For more information, see [DataAdapter Parameters](../../../../docs/framework/data/adonet/dataadapter-parameters.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31346-117"><xref:System.Data.DataTable>에서의 행 삭제 및 제거의 차이점을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-117">It is important to understand the difference between deleting a row in a <xref:System.Data.DataTable> and removing the row.</span></span> <span data-ttu-id="31346-118">`Remove` 또는 `RemoveAt` 메서드를 호출하면 행이 즉시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-118">When you call the `Remove` or `RemoveAt` method, the row is removed immediately.</span></span> <span data-ttu-id="31346-119">그런 다음 `DataTable`에 `DataSet` 또는 `DataAdapter`을 전달하고 `Update`를 호출하면 백 엔드 데이터 소스에 있는 해당 행은 아무런 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-119">Any corresponding rows in the back end data source will not be affected if you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`.</span></span> <span data-ttu-id="31346-120">`Delete` 메서드를 사용하면 행이 `DataTable`에 그대로 남아 있고 삭제 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-120">When you use the `Delete` method, the row remains in the `DataTable` and is marked for deletion.</span></span> <span data-ttu-id="31346-121">그런 다음 `DataTable`에 `DataSet` 또는 `DataAdapter`을 전달하고 `Update`를 호출하면 백 엔드 데이터 소스의 해당 행이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-121">If you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`, the corresponding row in the back end data source is deleted.</span></span>  
  
 <span data-ttu-id="31346-122">`DataTable`이 단일 데이터베이스 테이블에 매핑되거나 단일 데이터베이스 테이블에서 생성된 경우에는 <xref:System.Data.Common.DbCommandBuilder> 개체를 사용하여 `DeleteCommand`의 `InsertCommand`, `UpdateCommand` 및 `DataAdapter` 개체를 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-122">If your `DataTable` maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` objects for the `DataAdapter`.</span></span> <span data-ttu-id="31346-123">자세한 내용은 참조 [commandbuilder 생성 명령을](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-123">For more information, see [Generating Commands with CommandBuilders](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).</span></span>  
  
## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a><span data-ttu-id="31346-124">UpdatedRowSource를 사용하여 DataSet에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="31346-124">Using UpdatedRowSource to Map Values to a DataSet</span></span>  
 <span data-ttu-id="31346-125">`DataTable` 개체의 `DataAdapter` 속성을 사용하면 <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A>의 Update 메서드를 호출한 이후 데이터 소스에서 반환된 값이 <xref:System.Data.Common.DbCommand>에 다시 매핑되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-125">You can control how the values returned from the data source are mapped back to the `DataTable` following a call to the Update method of a `DataAdapter`, by using the <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> property of a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="31346-126">`UpdatedRowSource` 속성을 <xref:System.Data.UpdateRowSource> 열거형 값 중 하나로 설정하면 `DataAdapter` 명령에서 반환하는 출력 매개 변수를 무시할지 아니면 `DataSet`의 변경된 행에 적용할지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-126">By setting the `UpdatedRowSource` property to one of the <xref:System.Data.UpdateRowSource> enumeration values, you can control whether output parameters returned by the `DataAdapter` commands are ignored or applied to the changed row in the `DataSet`.</span></span> <span data-ttu-id="31346-127">반환되는 첫 번째 행이 있는 경우 이를 `DataTable`의 변경된 행에 적용할지 여부도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-127">You can also specify whether the first returned row (if it exists) is applied to the changed row in the `DataTable`.</span></span>  
  
 <span data-ttu-id="31346-128">다음 표에서는 `UpdateRowSource` 열거형의 여러 값과 각 값이 `DataAdapter`에 사용하는 명령의 동작에 미치는 영향에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-128">The following table describes the different values of the `UpdateRowSource` enumeration and how they affect the behavior of a command used with a `DataAdapter`.</span></span>  
  
|<span data-ttu-id="31346-129">UpdatedRowSource 열거형</span><span class="sxs-lookup"><span data-stu-id="31346-129">UpdatedRowSource Enumeration</span></span>|<span data-ttu-id="31346-130">설명</span><span class="sxs-lookup"><span data-stu-id="31346-130">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:System.Data.UpdateRowSource.Both>|<span data-ttu-id="31346-131">출력 매개 변수 및 반환된 결과 집합의 첫 번째 행 모두 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-131">Both the output parameters and the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|  
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|<span data-ttu-id="31346-132">반환된 결과 집합의 첫 번째 행 데이터만 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-132">Only the data in the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|  
|<xref:System.Data.UpdateRowSource.None>|<span data-ttu-id="31346-133">출력 매개 변수 또는 반환된 결과 집합의 행이 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-133">Any output parameters or rows of a returned result set are ignored.</span></span>|  
|<xref:System.Data.UpdateRowSource.OutputParameters>|<span data-ttu-id="31346-134">출력 매개 변수만 `DataSet`의 변경된 행에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-134">Only output parameters may be mapped to the changed row in the `DataSet`.</span></span>|  
  
 <span data-ttu-id="31346-135">`Update` 메서드는 변경 내용을 데이터 소스에 다시 적용하지만 사용자가 `DataSet`을 마지막으로 채운 이후에 다른 클라이언트에서 데이터 소스의 데이터를 수정했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-135">The `Update` method resolves your changes back to the data source; however other clients may have modified data at the data source since the last time you filled the `DataSet`.</span></span> <span data-ttu-id="31346-136">현재 데이터로 `DataSet`을 새로 고치려면 `DataAdapter` 및 `Fill` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-136">To refresh your `DataSet` with current data, use the `DataAdapter` and `Fill` method.</span></span> <span data-ttu-id="31346-137">그러면 새 행이 테이블에 추가되고 업데이트된 정보가 기존 행에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-137">New rows will be added to the table, and updated information will be incorporated into existing rows.</span></span> <span data-ttu-id="31346-138">`Fill` 메서드는 `DataSet`에 있는 행과 `SelectCommand`에서 반환된 행의 기본 키 값을 검사하여 새 행을 추가할지 또는 기존 행을 업데이트할지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-138">The `Fill` method determines whether a new row will be added or an existing row will be updated by examining the primary key values of the rows in the `DataSet` and the rows returned by the `SelectCommand`.</span></span> <span data-ttu-id="31346-139">`Fill`가 반환한 결과 행의 기본 키 값과 일치하는 `DataSet` 행의 기본 키 값이 발견되면 `SelectCommand` 메서드는 기존 행을 `SelectCommand`가 반환한 행의 정보로 업데이트하고 기존 행의 <xref:System.Data.DataRow.RowState%2A>를 `Unchanged`로 설정합니다</span><span class="sxs-lookup"><span data-stu-id="31346-139">If the `Fill` method encounters a primary key value for a row in the `DataSet` that matches a primary key value from a row in the results returned by the `SelectCommand`, it updates the existing row with the information from the row returned by the `SelectCommand` and sets the <xref:System.Data.DataRow.RowState%2A> of the existing row to `Unchanged`.</span></span> <span data-ttu-id="31346-140">`SelectCommand`가 반환한 행의 기본 키 값이 `DataSet` 행의 기본 키 값과 일치하지 않으면 `Fill` 메서드는 `RowState`가 `Unchanged`인 새 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-140">If a row returned by the `SelectCommand` has a primary key value that does not match any of the primary key values of the rows in the `DataSet`, the `Fill` method adds a new row with a `RowState` of `Unchanged`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31346-141">`SelectCommand`가 OUTER JOIN의 결과를 반환하면 `DataAdapter`는 결과 `PrimaryKey`에 대해 `DataTable` 값을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-141">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` will not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="31346-142">행 중복 문제를 해결하려면 `PrimaryKey`를 직접 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-142">You must define the `PrimaryKey` yourself to ensure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="31346-143">자세한 내용은 참조 [기본 키 정의](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-143">For more information, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="31346-144">호출할 때 발생할 수 있는 예외를 처리 하는 `Update` 사용할 수는 `RowUpdated` 나타나는 순서 대로 행 업데이트 오류에 응답 하는 이벤트 (참조 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)), 또는 설정할 수 있습니다 `DataAdapter.ContinueUpdateOnError` 를`true` 호출 하기 전에 `Update`에 저장 된 오류 정보에 응답할는 `RowError` 업데이트가 완료 되 면 특정 행의 속성 (참조 [행 오류 정보](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)).</span><span class="sxs-lookup"><span data-stu-id="31346-144">To handle exceptions that may occur when calling the `Update` method, you can use the `RowUpdated` event to respond to row update errors as they occur (see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)), or you can set `DataAdapter.ContinueUpdateOnError` to `true` before calling `Update`, and respond to the error information stored in the `RowError` property of a particular row when the update is complete (see [Row Error Information](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)).</span></span>  
  
 <span data-ttu-id="31346-145">**참고** 호출 `AcceptChanges` 에 `DataSet`, `DataTable`, 또는 `DataRow` 하면 모든 `Original` 에 대 한 값는 `DataRow` 을 덮어쓸 수는 `Current` 에 대 한 값은 `DataRow`합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-145">**Note** Calling `AcceptChanges` on the `DataSet`, `DataTable`, or `DataRow` will cause all `Original` values for a `DataRow` to be overwritten with the `Current` values for the `DataRow`.</span></span> <span data-ttu-id="31346-146">행을 고유하게 식별하는 필드 값을 수정한 경우 `AcceptChanges`를 호출하면 `Original` 값이 데이터 소스의 값과 더 이상 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-146">If the field values that identify the row as unique have been modified, after calling `AcceptChanges` the `Original` values will no longer match the values in the data source.</span></span> <span data-ttu-id="31346-147">`AcceptChanges`는 `DataAdapter`의 Update 메서드를 호출하는 동안 각 행에 대해 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-147">`AcceptChanges` is called automatically for each row during a call to the Update method of a `DataAdapter`.</span></span> <span data-ttu-id="31346-148">먼저 `AcceptChangesDuringUpdate`의 `DataAdapter` 속성을 false로 설정하거나 `RowUpdated` 이벤트에 대한 이벤트 처리기를 만들고 <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A>를 <xref:System.Data.UpdateStatus.SkipCurrentRow>로 설정하면 Update 메서드를 호출할 때 원래 값을 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-148">You can preserve the original values during a call to the Update method by first setting the `AcceptChangesDuringUpdate` property of the `DataAdapter` to false, or by creating an event handler for the `RowUpdated` event and setting the <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> to <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span></span> <span data-ttu-id="31346-149">자세한 내용은 참조 [데이터 집합 콘텐츠 병합](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md) 및 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-149">For more information, see [Merging DataSet Contents](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md) and [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31346-150">예</span><span class="sxs-lookup"><span data-stu-id="31346-150">Example</span></span>  
 <span data-ttu-id="31346-151">다음 예에서는 명시적으로 설정 하 여 수정 된 행에 대 한 업데이트를 수행 하는 방법을 보여 줍니다는 `UpdateCommand` 의 `DataAdapter` 호출 하 고 해당 `Update` 메서드.</span><span class="sxs-lookup"><span data-stu-id="31346-151">The following examples demonstrate how to perform updates to modified rows by explicitly setting the `UpdateCommand` of a `DataAdapter` and calling its `Update` method.</span></span> <span data-ttu-id="31346-152">UPDATE 문의 WHERE 절에 지정된 매개 변수는 `Original`의 `SourceColumn` 값을 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-152">Notice that the parameter specified in the WHERE clause of the UPDATE statement is set to use the `Original` value of the `SourceColumn`.</span></span> <span data-ttu-id="31346-153">`Current` 값이 수정되어 데이터 소스에 있는 값과 일치하지 않을 수 있기 때문에 이 설정은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-153">This is important, because the `Current` value may have been modified and may not match the value in the data source.</span></span> <span data-ttu-id="31346-154">`Original` 값은 데이터 소스에서 `DataTable`을 채우는 데 사용한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31346-154">The `Original` value is the value that was used to populate the `DataTable` from the data source.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]  
  
## <a name="autoincrement-columns"></a><span data-ttu-id="31346-155">AutoIncrement 열</span><span class="sxs-lookup"><span data-stu-id="31346-155">AutoIncrement Columns</span></span>  
 <span data-ttu-id="31346-156">데이터 소스의 테이블에 자동 증분 열이 있으면 저장 프로시저의 출력 매개 변수로 자동 증분 값을 반환하여 테이블의 열에 매핑하거나, 저장 프로시저 또는 SQL 문에서 반환된 결과 집합의 첫 번째 행에 있는 자동 증분 값을 반환하거나, `DataSet`의 `RowUpdated` 이벤트를 통해 추가적인 SELECT 문을 실행하여 `DataAdapter`의 열을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-156">If the tables from your data source have auto-incrementing columns, you can fill the columns in your `DataSet` either by returning the auto-increment value as an output parameter of a stored procedure and mapping that to a column in a table, by returning the auto-increment value in the first row of a result set returned by a stored procedure or SQL statement, or by using the `RowUpdated` event of the `DataAdapter` to execute an additional SELECT statement.</span></span> <span data-ttu-id="31346-157">자세한 내용 및 예제에 대 한 참조 [검색 Id 또는 일련 번호 값](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-157">For more information and an example, see [Retrieving Identity or Autonumber Values](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).</span></span>  
  
## <a name="ordering-of-inserts-updates-and-deletes"></a><span data-ttu-id="31346-158">삽입, 업데이트 및 삭제 순서</span><span class="sxs-lookup"><span data-stu-id="31346-158">Ordering of Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="31346-159">대부분의 경우에는 `DataSet`을 통해 변경된 내용이 데이터 소스에 전송되는 순서가 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-159">In many circumstances, the order in which changes made through the `DataSet` are sent to the data source is important.</span></span> <span data-ttu-id="31346-160">예를 들어 기존 행의 기본 키 값을 업데이트하고 새 기본 키 값이 외래 키로 지정된 새 행을 추가하는 경우에는 삽입하기 전에 업데이트를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-160">For example, if a primary key value for an existing row is updated, and a new row has been added with the new primary key value as a foreign key, it is important to process the update before the insert.</span></span>  
  
 <span data-ttu-id="31346-161">`Select`의 `DataTable` 메서드를 사용하여 특정 `DataRow`의 행만 참조하는 `RowState` 배열을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-161">You can use the `Select` method of the `DataTable` to return a `DataRow` array that only references rows with a particular `RowState`.</span></span> <span data-ttu-id="31346-162">그런 다음 반환된 `DataRow` 배열을 `Update`의 `DataAdapter` 메서드에 전달하여 수정된 행을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-162">You can then pass the returned `DataRow` array to the `Update` method of the `DataAdapter` to process the modified rows.</span></span> <span data-ttu-id="31346-163">업데이트될 행의 하위 집합을 지정하여 삽입, 업데이트 및 삭제가 처리되는 순서를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-163">By specifying a subset of rows to be updated, you can control the order in which inserts, updates, and deletes are processed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31346-164">예제</span><span class="sxs-lookup"><span data-stu-id="31346-164">Example</span></span>  
 <span data-ttu-id="31346-165">예를 들어, 다음 코드에서는 테이블의 삭제된 행이 먼저 처리되고 업데이트된 행과 삽입된 행이 차례로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-165">For example, the following code ensures that the deleted rows of the table are processed first, then the updated rows, and then the inserted rows.</span></span>  
  
```vb  
Dim table As DataTable = dataSet.Tables("Customers")  
  
' First process deletes.  
dataSet.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Deleted))  
  
' Next process updates.  
adapter.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.ModifiedCurrent))  
  
' Finally, process inserts.  
dataAdapater.Update(table.Select(Nothing, Nothing, _  
  DataViewRowState.Added))  
```  
  
```csharp  
DataTable table = dataSet.Tables["Customers"];  
  
// First process deletes.  
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));  
  
// Next process updates.  
adapter.Update(table.Select(null, null,   
  DataViewRowState.ModifiedCurrent));  
  
// Finally, process inserts.  
adapter.Update(table.Select(null, null, DataViewRowState.Added));  
```  
  
## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a><span data-ttu-id="31346-166">DataAdapter를 사용하여 데이터 검색 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="31346-166">Use a DataAdapter to Retrieve and Update Data</span></span>  
 <span data-ttu-id="31346-167">DataAdapter를 사용하여 데이터를 검색하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-167">You can use a DataAdapter to retrieve and update the data.</span></span>  
  
-   <span data-ttu-id="31346-168">이 샘플에서는 DataAdapter.AcceptChangesDuringFill을 사용하여 데이터베이스의 데이터를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-168">The sample uses DataAdapter.AcceptChangesDuringFill to clone the data in the database.</span></span> <span data-ttu-id="31346-169">이 속성이 false로 설정되어 있으면 테이블을 채울 때 AcceptChanges가 호출되지 않으며 새로 추가된 행은 삽입된 행으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="31346-169">If the property is set as false, AcceptChanges is not called when filling the table, and the newly added rows are treated as inserted rows.</span></span> <span data-ttu-id="31346-170">따라서 이 샘플에서는 이러한 행을 사용하여 새 행을 데이터베이스에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-170">So, the sample uses these rows to insert the new rows into the database.</span></span>  
  
-   <span data-ttu-id="31346-171">이 샘플에서는 DataAdapter.TableMappings를 사용하여 소스 테이블과 DataTable 간의 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-171">The samples uses DataAdapter.TableMappings to define the mapping between the source table and DataTable.</span></span>  
  
-   <span data-ttu-id="31346-172">이 샘플에서는 DataAdapter.FillLoadOption을 사용하여 어댑터가 DbDataReader에서 DataTable을 채우는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-172">The sample uses DataAdapter.FillLoadOption to determine how the adapter fills the DataTable from the DbDataReader.</span></span> <span data-ttu-id="31346-173">DataTable을 만드는 경우 이 속성을 LoadOption.Upsert 또는 LoadOption.PreserveChanges로 설정하여 현재 버전이나 원래 버전에 데이터베이스의 데이터를 쓸 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31346-173">When you create a DataTable, you can only write the data from database to the current version or the original version by setting the property as the LoadOption.Upsert or the LoadOption.PreserveChanges.</span></span>  
  
-   <span data-ttu-id="31346-174">또한 이 샘플에서는 DbDataAdapter.UpdateBatchSize를 사용하여 배치 작업을 수행하는 방법으로 테이블을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-174">The sample will also update the table by using DbDataAdapter.UpdateBatchSize to perform batch operations.</span></span>  
  
 <span data-ttu-id="31346-175">샘플을 컴파일 및 실행하기 전에 다음과 같이 샘플 데이터베이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-175">Before you compile and run the sample, you need to create the sample database:</span></span>  
  
```  
USE [master]  
GO  
  
CREATE DATABASE [MySchool]   
  
GO  
  
USE [MySchool]  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,  
[Year] [smallint] NOT NULL,  
[Title] [nvarchar](100) NOT NULL,  
[Credits] [int] NOT NULL,  
[DepartmentID] [int] NOT NULL,  
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED  
(  
[CourseID] ASC,  
[Year] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
SET ANSI_NULLS ON  
GO  
SET QUOTED_IDENTIFIER ON  
GO  
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,  
[Name] [nvarchar](50) NOT NULL,  
[Budget] [money] NOT NULL,  
[StartDate] [datetime] NOT NULL,  
[Administrator] [int] NULL,  
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED  
(  
[DepartmentID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)  
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)  
  
SET IDENTITY_INSERT [dbo].[Department] ON   
  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)  
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)  
SET IDENTITY_INSERT [dbo].[Department] OFF  
  
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])  
REFERENCES [dbo].[Department] ([DepartmentID])  
GO  
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]  
GO  
```  
  
 <span data-ttu-id="31346-176">이 코드 예제와 함께 C# 및 Visual Basic 프로젝트에서 확인할 수 있습니다 [개발자 코드 샘플](http://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D)합니다.</span><span class="sxs-lookup"><span data-stu-id="31346-176">C# and Visual Basic projects with this code sample can be found on [Developer Code Samples](http://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Common;  
using System.Data.SqlClient;  
using System.Linq;  
using CSDataAdapterOperations.Properties;  
  
namespace CSDataAdapterOperations.Properties {  
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {  
  
      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));  
  
      public static Settings Default {  
         get {  
            return defaultInstance;  
         }  
      }  
  
      [global::System.Configuration.ApplicationScopedSettingAttribute()]  
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]  
      public string MySchoolConnectionString {  
         get {  
            return ((string)(this["MySchoolConnectionString"]));  
         }  
      }  
   }  
}  
  
class Program {  
   static void Main(string[] args) {  
      Settings settings = new Settings();  
  
      // Copy the data from the database.  Get the table Department and Course from the database.  
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]  
                                     FROM [MySchool].[dbo].[Department];  
  
                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],  
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]  
                                   FROM [MySchool].[dbo].[Course]  
                                   Group by [CourseID]";  
  
      DataSet mySchool = new DataSet();  
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);  
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);  
  
      // Use DataTableMapping to map the source tables and the destination tables.  
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};  
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);  
  
      Console.WriteLine("The following tables are from the database.");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      // Roll back the changes  
      DataTable department = mySchool.Tables["Department"];  
      DataTable course = mySchool.Tables["Course"];  
  
      department.Rows[0]["Name"] = "New" + department.Rows[0][1];  
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];  
      course.Rows[0]["Credits"] = 10;  
  
      Console.WriteLine("After we changed the tables:");  
      foreach (DataTable table in mySchool.Tables) {  
         Console.WriteLine(table.TableName);  
         ShowDataTable(table);  
      }  
  
      department.RejectChanges();  
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");  
      ShowDataTable(department);  
  
      DataColumn[] primaryColumns = { course.Columns["CourseID"] };  
      DataColumn[] resetColumns = { course.Columns["Title"] };  
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);  
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");  
      ShowDataTable(course);  
  
      // Batch update the table.  
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],   
                                   [Credits],[DepartmentID])   
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";  
      SqlCommand insertCommand = new SqlCommand(insertString);  
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");  
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");  
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");  
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");  
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");  
  
      const Int32 batchSize = 10;  
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);  
   }  
  
   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);  
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a   
            // DataRow after it is added to the DataTable during any of the Fill operations.  
            adapter.AcceptChangesDuringFill = false;  
  
            adapter.Fill(dataSet);  
         }  
      }  
   }  
  
   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.  
   private static void ResetCourse(DataTable table, String connectionString,  
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {  
      table.PrimaryKey = primaryColumns;  
  
      // Build the query string  
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));  
      String resetCols = String.Join(",", resetColumns.Select(col => "Max(" + col.ColumnName + ") as " + col.ColumnName));  
  
      String selectString = String.Format("Select {0},{1} from Course Group by {0}", primaryCols, resetCols);  
  
      SqlCommand selectCommand = new SqlCommand(selectString);  
  
      ResetDataTable(table, connectionString, selectCommand);  
   }  
  
   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges   
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges  
   // The ResetDataTable method rolls back one or more columns of data.  
   private static void ResetDataTable(DataTable table, String connectionString,  
       SqlCommand selectCommand) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         selectCommand.Connection = connection;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {  
            // The incoming values for this row will be written to the current version of each   
            // column. The original version of each column's data will not be changed.  
            adapter.FillLoadOption = LoadOption.Upsert;  
  
            adapter.Fill(table);  
         }  
      }  
   }  
  
   private static void BatchInsertUpdate(DataTable table, String connectionString,  
       SqlCommand insertCommand, Int32 batchSize) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         insertCommand.Connection = connection;  
         // When setting UpdateBatchSize to a value other than 1, all the commands   
         // associated with the SqlDataAdapter have to have their UpdatedRowSource   
         // property set to None or OutputParameters. An exception is thrown otherwise.  
         insertCommand.UpdatedRowSource = UpdateRowSource.None;  
  
         connection.Open();  
  
         using (SqlDataAdapter adapter = new SqlDataAdapter()) {  
            adapter.InsertCommand = insertCommand;  
            // Gets or sets the number of rows that are processed in each round-trip to the server.  
            // Setting it to 1 disables batch updates, as rows are sent one at a time.  
            adapter.UpdateBatchSize = batchSize;  
  
            adapter.Update(table);  
  
            Console.WriteLine("Successfully to update the table.");  
         }  
      }  
   }  
  
   private static void ShowDataTable(DataTable table) {  
      foreach (DataColumn col in table.Columns) {  
         Console.Write("{0,-14}", col.ColumnName);  
      }  
      Console.WriteLine("{0,-14}", "RowState");  
  
      foreach (DataRow row in table.Rows) {  
         foreach (DataColumn col in table.Columns) {  
            if (col.DataType.Equals(typeof(DateTime)))  
               Console.Write("{0,-14:d}", row[col]);  
            else if (col.DataType.Equals(typeof(Decimal)))  
               Console.Write("{0,-14:C}", row[col]);  
            else  
               Console.Write("{0,-14}", row[col]);  
         }  
         Console.WriteLine("{0,-14}", row.RowState);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31346-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31346-177">See Also</span></span>  
 [<span data-ttu-id="31346-178">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="31346-178">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="31346-179">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="31346-179">Row States and Row Versions</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="31346-180">AcceptChanges 및 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="31346-180">AcceptChanges and RejectChanges</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 [<span data-ttu-id="31346-181">데이터 집합 콘텐츠 병합</span><span class="sxs-lookup"><span data-stu-id="31346-181">Merging DataSet Contents</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 [<span data-ttu-id="31346-182">ID 또는 일련 번호 값 검색</span><span class="sxs-lookup"><span data-stu-id="31346-182">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 [<span data-ttu-id="31346-183">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="31346-183">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
