---
title: "CommandBuilder를 사용하여 명령 생성"
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
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e945b4b6c646a0210f781d1ba43b5cd931cfef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generating-commands-with-commandbuilders"></a><span data-ttu-id="afc94-102">CommandBuilder를 사용하여 명령 생성</span><span class="sxs-lookup"><span data-stu-id="afc94-102">Generating Commands with CommandBuilders</span></span>
<span data-ttu-id="afc94-103">사용자가 입력하는 텍스트 명령을 사용하는 쿼리 도구를 통해 지정하는 경우와 같이 `SelectCommand` 속성이 런타임에 동적으로 지정되는 경우에는 디자인 타임에 적절한 `InsertCommand`, `UpdateCommand` 또는 `DeleteCommand`를 지정하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-103">When the `SelectCommand` property is dynamically specified at run time, such as through a query tool that takes a textual command from the user, you may not be able to specify the appropriate `InsertCommand`, `UpdateCommand`, or `DeleteCommand` at design time.</span></span> <span data-ttu-id="afc94-104"><xref:System.Data.DataTable>이 단일 데이터베이스 테이블에 매핑되거나 단일 데이터베이스 테이블에서 생성된 경우에는 <xref:System.Data.Common.DbCommandBuilder> 개체를 사용하여 `DeleteCommand`의 `InsertCommand`, `UpdateCommand` 및 <xref:System.Data.Common.DbDataAdapter>를 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-104">If your <xref:System.Data.DataTable> maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` of the <xref:System.Data.Common.DbDataAdapter>.</span></span>  
  
 <span data-ttu-id="afc94-105">자동 명령 생성이 작동하도록 하려면 최소한 `SelectCommand` 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-105">As a minimum requirement, you must set the `SelectCommand` property in order for automatic command generation to work.</span></span> <span data-ttu-id="afc94-106">`SelectCommand` 속성에서 검색하는 테이블 스키마에 따라 자동으로 생성되는 INSERT, UPDATE 및 DELETE 문의 구문이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-106">The table schema retrieved by the `SelectCommand` property determines the syntax of the automatically generated INSERT, UPDATE, and DELETE statements.</span></span>  
  
 <span data-ttu-id="afc94-107"><xref:System.Data.Common.DbCommandBuilder>는 INSERT, UPDATE 및 DELETE SQL 명령을 생성하는 데 필요한 메타데이터를 반환하기 위해 `SelectCommand`를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-107">The <xref:System.Data.Common.DbCommandBuilder> must execute the `SelectCommand` in order to return the metadata necessary to construct the INSERT, UPDATE, and DELETE SQL commands.</span></span> <span data-ttu-id="afc94-108">결과적으로 데이터 소스에 추가로 이동해야 하므로 성능이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-108">As a result, an extra trip to the data source is necessary, and this can hinder performance.</span></span> <span data-ttu-id="afc94-109">최적의 성능을 얻으려면 <xref:System.Data.Common.DbCommandBuilder>를 사용하는 대신 명령을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-109">To achieve optimal performance, specify your commands explicitly rather than using the <xref:System.Data.Common.DbCommandBuilder>.</span></span>  
  
 <span data-ttu-id="afc94-110">또한 `SelectCommand`는 기본 키 열이나 고유 열을 하나 이상 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-110">The `SelectCommand` must also return at least one primary key or unique column.</span></span> <span data-ttu-id="afc94-111">이러한 열이 없으면 `InvalidOperation` 예외가 생성되고 명령은 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-111">If none are present, an `InvalidOperation` exception is generated, and the commands are not generated.</span></span>  
  
 <span data-ttu-id="afc94-112">`DataAdapter`와 연결되어 있는 경우 <xref:System.Data.Common.DbCommandBuilder>는 `InsertCommand`의 `UpdateCommand`, `DeleteCommand` 및 `DataAdapter` 속성을 자동으로 생성합니다(속성이 null 참조인 경우).</span><span class="sxs-lookup"><span data-stu-id="afc94-112">When associated with a `DataAdapter`, the <xref:System.Data.Common.DbCommandBuilder> automatically generates the `InsertCommand`, `UpdateCommand`, and `DeleteCommand` properties of the `DataAdapter` if they are null references.</span></span> <span data-ttu-id="afc94-113">속성에 대한 `Command`가 이미 있으면 기존 `Command`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-113">If a `Command` already exists for a property, the existing `Command` is used.</span></span>  
  
 <span data-ttu-id="afc94-114">테이블을 두 개 이상 조인하여 만든 데이터베이스 뷰는 단일 데이터베이스 테이블로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-114">Database views that are created by joining two or more tables together are not considered a single database table.</span></span> <span data-ttu-id="afc94-115">이 경우 <xref:System.Data.Common.DbCommandBuilder>를 사용하여 명령을 자동으로 생성할 수 없으므로 명시적으로 명령을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-115">In this instance you cannot use the <xref:System.Data.Common.DbCommandBuilder> to automatically generate commands; you must specify your commands explicitly.</span></span> <span data-ttu-id="afc94-116">명령에 대 한 업데이트를 해결 하려면 명시적으로 설정 하는 방법에 대 한 정보에 대 한 한 `DataSet` 를 데이터 소스 참조 [Dataadapter로 데이터 원본 업데이트](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-116">For information about explicitly setting commands to resolve updates to a `DataSet` back to the data source, see [Updating Data Sources with DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="afc94-117">출력 매개 변수를 `DataSet`의 업데이트된 행에 다시 매핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-117">You might want to map output parameters back to the updated row of a `DataSet`.</span></span> <span data-ttu-id="afc94-118">일반적인 작업은 자동으로 생성된 ID 필드의 값이나 타임스탬프를 데이터 소스에서 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-118">One common task would be retrieving the value of an automatically generated identity field or time stamp from the data source.</span></span> <span data-ttu-id="afc94-119"><xref:System.Data.Common.DbCommandBuilder>는 기본적으로 출력 매개 변수를 업데이트된 행의 열에 매핑하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-119">The <xref:System.Data.Common.DbCommandBuilder> will not map output parameters to columns in an updated row by default.</span></span> <span data-ttu-id="afc94-120">이 경우 사용자가 명시적으로 명령을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-120">In this instance you must specify your command explicitly.</span></span> <span data-ttu-id="afc94-121">삽입된 된 행의 열에 다시 자동으로 생성된 된 id 필드를 매핑의 예제를 보려면 [검색 Id 또는 일련 번호 값](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-121">For an example of mapping an automatically generated identity field back to a column of an inserted row, see [Retrieving Identity or Autonumber Values](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).</span></span>  
  
## <a name="rules-for-automatically-generated-commands"></a><span data-ttu-id="afc94-122">자동 생성된 명령에 대한 규칙</span><span class="sxs-lookup"><span data-stu-id="afc94-122">Rules for Automatically Generated Commands</span></span>  
 <span data-ttu-id="afc94-123">다음 표에서는 자동 생성된 명령을 생성하는 방법에 대한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-123">The following table shows the rules for how automatically generated commands are generated.</span></span>  
  
|<span data-ttu-id="afc94-124">명령</span><span class="sxs-lookup"><span data-stu-id="afc94-124">Command</span></span>|<span data-ttu-id="afc94-125">규칙</span><span class="sxs-lookup"><span data-stu-id="afc94-125">Rule</span></span>|  
|-------------|----------|  
|`InsertCommand`|<span data-ttu-id="afc94-126"><xref:System.Data.DataRow.RowState%2A>의 <xref:System.Data.DataRowState.Added>를 사용하여 테이블의 모든 행에 대해 데이터 소스에 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-126">Inserts a row at the data source for all rows in the table with a <xref:System.Data.DataRow.RowState%2A> of <xref:System.Data.DataRowState.Added>.</span></span> <span data-ttu-id="afc94-127">ID, 식 또는 타임스탬프와 같은 열이 아니라 업데이트할 수 있는 모든 열의 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-127">Inserts values for all columns that are updateable (but not columns such as identities, expressions, or timestamps).</span></span>|  
|`UpdateCommand`|<span data-ttu-id="afc94-128">`RowState`의 <xref:System.Data.DataRowState.Modified>를 사용하여 테이블의 모든 행에 대해 데이터 소스의 행을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-128">Updates rows at the data source for all rows in the table with a `RowState` of <xref:System.Data.DataRowState.Modified>.</span></span> <span data-ttu-id="afc94-129">ID 또는 식과 같이 업데이트할 수 없는 열을 제외한 모든 열의 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-129">Updates the values of all columns except for columns that are not updateable, such as identities or expressions.</span></span> <span data-ttu-id="afc94-130">데이터 소스의 열 값이 해당 행의 기본 키 열 값과 일치하고 데이터 소스의 나머지 열이 해당 행의 원래 값과 일치하는 모든 행을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-130">Updates all rows where the column values at the data source match the primary key column values of the row, and where the remaining columns at the data source match the original values of the row.</span></span> <span data-ttu-id="afc94-131">자세한 내용은 이 항목 뒷부분의 "업데이트 및 삭제에 대한 낙관적 동시성 모델"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afc94-131">For more information, see "Optimistic Concurrency Model for Updates and Deletes," later in this topic.</span></span>|  
|`DeleteCommand`|<span data-ttu-id="afc94-132">`RowState`의 <xref:System.Data.DataRowState.Deleted>를 사용하여 테이블의 모든 행에 대해 데이터 소스의 행을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-132">Deletes rows at the data source for all rows in the table with a `RowState` of <xref:System.Data.DataRowState.Deleted>.</span></span> <span data-ttu-id="afc94-133">열 값이 해당 행의 기본 키 열 값과 일치하고 데이터 소스의 나머지 열이 해당 행의 원래 값과 일치하는 모든 행을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-133">Deletes all rows where the column values match the primary key column values of the row, and where the remaining columns at the data source match the original values of the row.</span></span> <span data-ttu-id="afc94-134">자세한 내용은 이 항목 뒷부분의 "업데이트 및 삭제에 대한 낙관적 동시성 모델"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afc94-134">For more information, see "Optimistic Concurrency Model for Updates and Deletes," later in this topic.</span></span>|  
  
## <a name="optimistic-concurrency-model-for-updates-and-deletes"></a><span data-ttu-id="afc94-135">업데이트 및 삭제에 대한 낙관적 동시성 모델</span><span class="sxs-lookup"><span data-stu-id="afc94-135">Optimistic Concurrency Model for Updates and Deletes</span></span>  
 <span data-ttu-id="afc94-136">UPDATE 및 DELETE 문에 대 한 자동 명령 생성 논리 기반 *낙관적 동시성*-즉, 레코드 편집을 위해 잠겨 있지 않은 고 언제 든 지 다른 사용자나 프로세스에서 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-136">The logic for generating commands automatically for UPDATE and DELETE statements is based on *optimistic concurrency*--that is, records are not locked for editing and can be modified by other users or processes at any time.</span></span> <span data-ttu-id="afc94-137">SELECT 문에서 반환된 후 UPDATE 또는 DELETE 문이 발행되기 전에 레코드를 수정할 수 있었으므로 자동으로 생성되는 UPDATE 또는 DELETE 문에는 행이 원래 값을 모두 포함하고 데이터 소스에서 삭제되지 않은 경우에만 업데이트되도록 지정하는 WHERE 절이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-137">Because a record could have been modified after it was returned from the SELECT statement, but before the UPDATE or DELETE statement is issued, the automatically generated UPDATE or DELETE statement contains a WHERE clause, specifying that a row is only updated if it contains all original values and has not been deleted from the data source.</span></span> <span data-ttu-id="afc94-138">따라서 새 데이터를 덮어쓰는 상황이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-138">This is done to avoid overwriting new data.</span></span> <span data-ttu-id="afc94-139">자동 생성된 업데이트가 삭제되었거나 <xref:System.Data.DataSet>에 있는 원래 값을 포함하지 않는 행을 업데이트하려고 하는 경우 이 명령은 모든 레코드에 영향을 주지 않으며 <xref:System.Data.DBConcurrencyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-139">Where an automatically generated update attempts to update a row that has been deleted or that does not contain the original values found in the <xref:System.Data.DataSet>, the command does not affect any records, and a <xref:System.Data.DBConcurrencyException> is thrown.</span></span>  
  
 <span data-ttu-id="afc94-140">원래 값에 관계없이 UPDATE나 DELETE가 완료되도록 하려면 자동 명령 생성을 사용하는 대신 `UpdateCommand`에 대해 `DataAdapter`를 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-140">If you want the UPDATE or DELETE to complete regardless of original values, you must explicitly set the `UpdateCommand` for the `DataAdapter` and not rely on automatic command generation.</span></span>  
  
## <a name="limitations-of-automatic-command-generation-logic"></a><span data-ttu-id="afc94-141">자동 명령 생성 논리의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="afc94-141">Limitations of Automatic Command Generation Logic</span></span>  
 <span data-ttu-id="afc94-142">자동 명령 생성에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-142">The following limitations apply to automatic command generation.</span></span>  
  
### <a name="unrelated-tables-only"></a><span data-ttu-id="afc94-143">관련되지 않은 테이블만 해당</span><span class="sxs-lookup"><span data-stu-id="afc94-143">Unrelated Tables Only</span></span>  
 <span data-ttu-id="afc94-144">자동 명령 생성 논리는 데이터 소스에 있는 다른 테이블과의 관계를 고려하지 않고 독립 실행형 테이블에 대해 INSERT, UPDATE 또는 DELETE 문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-144">The automatic command generation logic generates INSERT, UPDATE, or DELETE statements for stand-alone tables without taking into account any relationships to other tables at the data source.</span></span> <span data-ttu-id="afc94-145">결과적으로 데이터베이스에서 외래 키 제약 조건에 참여하는 열에 대한 변경 내용을 전송하기 위해 `Update`를 호출하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-145">As a result, you may encounter a failure when calling `Update` to submit changes for a column that participates in a foreign key constraint in the database.</span></span> <span data-ttu-id="afc94-146">이 예외가 발생하지 않도록 하려면 외래 키 제약 조건에 관련된 열을 업데이트하는 데 <xref:System.Data.Common.DbCommandBuilder>를 사용하는 대신 해당 작업을 수행하는 데 사용되는 문을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-146">To avoid this exception, do not use the <xref:System.Data.Common.DbCommandBuilder> for updating columns involved in a foreign key constraint; instead, explicitly specify the statements used to perform the operation.</span></span>  
  
### <a name="table-and-column-names"></a><span data-ttu-id="afc94-147">테이블 및 열 이름</span><span class="sxs-lookup"><span data-stu-id="afc94-147">Table and Column Names</span></span>  
 <span data-ttu-id="afc94-148">열 이름이나 테이블 이름에 공백, 마침표, 인용 부호 및 기타 영숫자가 아닌 문자 등의 특수 문자가 있으면 이러한 문자가 대괄호로 구분되어 있더라도 자동 명령 생성 논리가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-148">Automatic command generation logic may fail if column names or table names contain any special characters, such as spaces, periods, quotation marks, or other nonalphanumeric characters, even if delimited by brackets.</span></span> <span data-ttu-id="afc94-149">공급자에 따라서는 QuotePrefix 및 QuoteSuffix 매개 변수를 설정함으로써 생성 논리에서 공백이 허용되도록 할 수 있지만 특수 문자를 이스케이프할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-149">Depending on the provider, setting the QuotePrefix and QuoteSuffix parameters may allow the generation logic to process spaces, but it cannot escape special characters.</span></span> <span data-ttu-id="afc94-150">정규화 된 형식으로 테이블 이름을 *catalog.schema.table* 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-150">Fully qualified table names in the form of *catalog.schema.table* are supported.</span></span>  
  
## <a name="using-the-commandbuilder-to-automatically-generate-an-sql-statement"></a><span data-ttu-id="afc94-151">CommandBuilder를 사용하여 SQL 문 자동 생성</span><span class="sxs-lookup"><span data-stu-id="afc94-151">Using the CommandBuilder to Automatically Generate an SQL Statement</span></span>  
 <span data-ttu-id="afc94-152">`DataAdapter`에 대한 SQL 문을 자동으로 생성하려면 먼저 `SelectCommand`의 `DataAdapter` 속성을 설정한 다음 `CommandBuilder` 개체를 만들고 `DataAdapter`에서 SQL 문을 자동으로 생성할 `CommandBuilder`를 인수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-152">To automatically generate SQL statements for a `DataAdapter`, first set the `SelectCommand` property of the `DataAdapter`, then create a `CommandBuilder` object, and specify as an argument the `DataAdapter` for which the `CommandBuilder` will automatically generate SQL statements.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object   
' inside of a Using block.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", connection)  
Dim builder As SqlCommandBuilder = New SqlCommandBuilder(adapter)  
builder.QuotePrefix = "["  
builder.QuoteSuffix = "]"  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object  
// inside of a using block.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", connection);  
SqlCommandBuilder builder = new SqlCommandBuilder(adapter);  
builder.QuotePrefix = "[";  
builder.QuoteSuffix = "]";  
```  
  
## <a name="modifying-the-selectcommand"></a><span data-ttu-id="afc94-153">SelectCommand 수정</span><span class="sxs-lookup"><span data-stu-id="afc94-153">Modifying the SelectCommand</span></span>  
 <span data-ttu-id="afc94-154">INSERT, UPDATE 또는 DELETE 명령이 자동으로 생성된 후에 `CommandText`의 `SelectCommand` 수정하면 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-154">If you modify the `CommandText` of the `SelectCommand` after the INSERT, UPDATE, or DELETE commands have been automatically generated, an exception may occur.</span></span> <span data-ttu-id="afc94-155">수정된 `SelectCommand.CommandText`에 Insert, Update 또는 Delete 명령이 자동으로 생성되었을 때 사용한 `SelectCommand.CommandText`와 일치하지 않는 스키마 정보가 들어 있으면 이후 `DataAdapter.Update` 메서드를 호출할 때 `SelectCommand`가 참조하는 현재 테이블에 더 이상 없는 열에 액세스하려고 할 수 있으므로 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-155">If the modified `SelectCommand.CommandText` contains schema information that is inconsistent with the `SelectCommand.CommandText` used when the insert, update, or delete commands were automatically generated, future calls to the `DataAdapter.Update` method may attempt to access columns that no longer exist in the current table referenced by the `SelectCommand`, and an exception will be thrown.</span></span>  
  
 <span data-ttu-id="afc94-156">`CommandBuilder`의 `RefreshSchema` 메서드를 호출함으로써 `CommandBuilder`에서 사용하는 스키마 정보를 새로 고쳐 명령을 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-156">You can refresh the schema information used by the `CommandBuilder` to automatically generate commands by calling the `RefreshSchema` method of the `CommandBuilder`.</span></span>  
  
 <span data-ttu-id="afc94-157">자동으로 생성되는 명령이 어떤 것인지 확인하려는 경우 `GetInsertCommand` 개체의 `GetUpdateCommand`, `GetDeleteCommand` 및 `CommandBuilder` 메서드를 사용하고 관련 명령의 `CommandText` 속성을 확인하여 자동으로 생성된 명령에 대한 참조를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-157">If you want to know what command was automatically generated, you can obtain a reference to the automatically generated commands by using the `GetInsertCommand`, `GetUpdateCommand`, and `GetDeleteCommand` methods of the `CommandBuilder` object and checking the `CommandText` property of the associated command.</span></span>  
  
 <span data-ttu-id="afc94-158">다음 코드 예제에서는 자동 생성된 UPDATE 명령을 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-158">The following code example writes to the console the update command that was automatically generated.</span></span>  
  
```  
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```  
  
 <span data-ttu-id="afc94-159">다음 예제에서는 `Customers` 데이터 집합에 `custDS` 테이블을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-159">The following example recreates the `Customers` table in the `custDS` dataset.</span></span> <span data-ttu-id="afc94-160">**RefreshSchema** 메서드를 호출 하는 자동 생성 된 명령을 새 열 정보를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="afc94-160">The **RefreshSchema** method is called to refresh the automatically generated commands with this new column information.</span></span>  
  
```vb  
' Assumes an open SqlConnection and SqlDataAdapter inside of a Using block.  
adapter.SelectCommand.CommandText = _  
  "SELECT CustomerID, ContactName FROM dbo.Customers"  
builder.RefreshSchema()  
  
custDS.Tables.Remove(custDS.Tables("Customers"))  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
// Assumes an open SqlConnection and SqlDataAdapter inside of a using block.  
adapter.SelectCommand.CommandText =   
  "SELECT CustomerID, ContactName FROM dbo.Customers";  
builder.RefreshSchema();  
  
custDS.Tables.Remove(custDS.Tables["Customers"]);  
adapter.Fill(custDS, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="afc94-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afc94-161">See Also</span></span>  
 [<span data-ttu-id="afc94-162">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="afc94-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="afc94-163">명령 실행</span><span class="sxs-lookup"><span data-stu-id="afc94-163">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="afc94-164">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="afc94-164">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="afc94-165">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="afc94-165">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
