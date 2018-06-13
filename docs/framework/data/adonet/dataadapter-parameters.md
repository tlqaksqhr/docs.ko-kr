---
title: DataAdapter 매개 변수
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: ad046e4695365780bc6059617766a488ba85f642
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759373"
---
# <a name="dataadapter-parameters"></a><span data-ttu-id="63489-102">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="63489-102">DataAdapter Parameters</span></span>
<span data-ttu-id="63489-103"><xref:System.Data.Common.DbDataAdapter>에는 데이터 소스에서 데이터를 검색하고 업데이트하는 데 사용되는 다음과 같은 네 가지 속성이 있습니다. <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> 속성은 데이터 소스에서 데이터를 반환하며 <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 및 <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> 속성은 데이터 소스에서 변경 내용을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-103">The <xref:System.Data.Common.DbDataAdapter> has four properties that are used to retrieve data from and update data to the data source: the <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> property returns data from the data source; and the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, and <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> properties are used to manage changes at the data source.</span></span> <span data-ttu-id="63489-104">`SelectCommand` 속성은 `Fill`의 `DataAdapter` 메서드를 호출하기 전에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-104">The `SelectCommand` property must be set before you call the `Fill` method of the `DataAdapter`.</span></span> <span data-ttu-id="63489-105">`InsertCommand`, `UpdateCommand` 또는 `DeleteCommand` 속성은 `Update`의 `DataAdapter` 메서드가 호출되기 전에 설정해야 하며, <xref:System.Data.DataTable>의 데이터에 적용된 변경 내용에 따라 설정 값이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="63489-105">The `InsertCommand`, `UpdateCommand`, or `DeleteCommand` properties must be set before the `Update` method of the `DataAdapter` is called, depending on what changes were made to the data in the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="63489-106">예를 들어, 행이 추가되었으면 `InsertCommand`를 호출하기 전에 `Update`를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-106">For example, if rows have been added, the `InsertCommand` must be set before you call `Update`.</span></span> <span data-ttu-id="63489-107">`Update`가 삽입, 업데이트 또는 삭제된 행을 처리하는 동안 `DataAdapter`는 해당 `Command` 속성을 사용하여 동작을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-107">When `Update` is processing an inserted, updated, or deleted row, the `DataAdapter` uses the respective `Command` property to process the action.</span></span> <span data-ttu-id="63489-108">수정된 행에 대한 현재 정보는 `Command` 컬렉션을 통해 `Parameters` 개체에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-108">Current information about the modified row is passed to the `Command` object through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="63489-109">데이터 소스에서 행을 업데이트할 때는 업데이트된 테이블의 행을 고유 식별자로 식별하는 UPDATE 문을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-109">When you update a row at the data source, you call the UPDATE statement, which uses a unique identifier to identify the row in the table be updated.</span></span> <span data-ttu-id="63489-110">고유 식별자란 대개 기본 키 필드의 값을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-110">The unique identifier is typically the value of a primary key field.</span></span> <span data-ttu-id="63489-111">UPDATE 문은 다음의 Transact-SQL 문과 같이 고유 식별자와 업데이트된 열 및 값을 모두 포함하는 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-111">The UPDATE statement uses parameters that contain both the unique identifier and the columns and values to be updated, as shown in the following Transact-SQL statement.</span></span>  
  
```  
UPDATE Customers SET CompanyName = @CompanyName   
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
>  <span data-ttu-id="63489-112">매개 변수 자리 표시자의 구문은 데이터 소스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="63489-112">The syntax for parameter placeholders depends on the data source.</span></span> <span data-ttu-id="63489-113">이 예제에서는 SQL Server 데이터 소스용 자리 표시자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63489-113">This example shows placeholders for a SQL Server data source.</span></span> <span data-ttu-id="63489-114"><xref:System.Data.OleDb> 및 <xref:System.Data.Odbc> 매개 변수의 경우 물음표(?) 자리 표시자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-114">Use question mark (?) placeholders for <xref:System.Data.OleDb> and <xref:System.Data.Odbc> parameters.</span></span>  
  
 <span data-ttu-id="63489-115">이 Visual Basic 예제에서는 `CompanyName` 필드의 값으로 업데이트 됩니다는 `@CompanyName` 행에 대 한 매개 변수 있는 `CustomerID` 의 값과 같으면는 `@CustomerID` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-115">In this Visual Basic example, the `CompanyName` field is updated with the value of the `@CompanyName` parameter for the row where `CustomerID` equals the value of the `@CustomerID` parameter.</span></span> <span data-ttu-id="63489-116">사용 하 여 수정 된 행에서 정보를 검색 하는 매개 변수는 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> 의 속성은 <xref:System.Data.SqlClient.SqlParameter> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-116">The parameters retrieve information from the modified row using the <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> property of the <xref:System.Data.SqlClient.SqlParameter> object.</span></span> <span data-ttu-id="63489-117">다음은 앞에 나온 샘플 UPDATE 문에 대한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-117">The following are the parameters for the previous sample UPDATE statement.</span></span> <span data-ttu-id="63489-118">이 코드에서는 `adapter` 변수가 올바른 <xref:System.Data.SqlClient.SqlDataAdapter> 개체를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-118">The code assumes that the variable `adapter` represents a valid <xref:System.Data.SqlClient.SqlDataAdapter> object.</span></span>  
  
```  
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 <span data-ttu-id="63489-119">`Add` 컬렉션의 `Parameters` 메서드는 매개 변수 이름, 데이터 형식, 크기(해당 형식에 적용되는 경우) 및 <xref:System.Data.Common.DbParameter.SourceColumn%2A>의 `DataTable` 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-119">The `Add` method of the `Parameters` collection takes the name of the parameter, the data type, the size (if applicable to the type), and the name of the <xref:System.Data.Common.DbParameter.SourceColumn%2A> from the `DataTable`.</span></span> <span data-ttu-id="63489-120"><xref:System.Data.Common.DbParameter.SourceVersion%2A> 매개 변수의 `@CustomerID`은 `Original`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-120">Notice that the <xref:System.Data.Common.DbParameter.SourceVersion%2A> of the `@CustomerID` parameter is set to `Original`.</span></span> <span data-ttu-id="63489-121">그러면 식별하는 열 값이 수정된 <xref:System.Data.DataRow>에서 변경된 경우 데이터 소스의 기존 행이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-121">This guarantees that the existing row in the data source is updated if the value of the identifying column or columns has been changed in the modified <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="63489-122">이 경우 `Original` 행 값은 데이터 소스의 현재 값과 일치하고 `Current` 행 값에는 업데이트된 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-122">In that case, the `Original` row value would match the current value at the data source, and the `Current` row value would contain the updated value.</span></span> <span data-ttu-id="63489-123">`SourceVersion` 매개 변수의 `@CompanyName`은 설정되어 있지 않으므로 기본값인 `Current` 행 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-123">The `SourceVersion` for the `@CompanyName` parameter is not set and uses the default, `Current` row value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63489-124">`Fill`의 `DataAdapter` 작업과 `Get`의 `DataReader` 메서드 모두에서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자로부터 반환된 형식에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-124">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type is inferred from the type returned from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="63489-125">유추 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식 및 Microsoft SQL Server, OLE DB 및 ODBC 데이터 형식에 대 한 접근자 메서드는에 설명 된 [ADO.NET에서 데이터 형식 매핑을](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-125">The inferred [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and accessor methods for Microsoft SQL Server, OLE DB, and ODBC data types are described in [Data Type Mappings in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md).</span></span>  
  
## <a name="parametersourcecolumn-parametersourceversion"></a><span data-ttu-id="63489-126">Parameter.SourceColumn, Parameter.SourceVersion</span><span class="sxs-lookup"><span data-stu-id="63489-126">Parameter.SourceColumn, Parameter.SourceVersion</span></span>  
 <span data-ttu-id="63489-127">`SourceColumn` 및 `SourceVersion`은 `Parameter` 생성자에 인수로 전달되거나 기존 `Parameter`의 속성으로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63489-127">The `SourceColumn` and `SourceVersion` may be passed as arguments to the `Parameter` constructor, or set as properties of an existing `Parameter`.</span></span> <span data-ttu-id="63489-128">`SourceColumn`은 <xref:System.Data.DataColumn> 값이 검색될 <xref:System.Data.DataRow>의 `Parameter` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-128">The `SourceColumn` is the name of the <xref:System.Data.DataColumn> from the <xref:System.Data.DataRow> where the value of the `Parameter` will be retrieved.</span></span> <span data-ttu-id="63489-129">`SourceVersion`에서는 `DataRow`가 값을 검색하기 위해 사용하는 `DataAdapter` 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-129">The `SourceVersion` specifies the `DataRow` version that the `DataAdapter` uses to retrieve the value.</span></span>  
  
 <span data-ttu-id="63489-130">다음 표에서는 <xref:System.Data.DataRowVersion>에 사용할 수 있는 `SourceVersion` 열거형 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63489-130">The following table shows the <xref:System.Data.DataRowVersion> enumeration values available for use with `SourceVersion`.</span></span>  
  
|<span data-ttu-id="63489-131">DataRowVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="63489-131">DataRowVersion Enumeration</span></span>|<span data-ttu-id="63489-132">설명</span><span class="sxs-lookup"><span data-stu-id="63489-132">Description</span></span>|  
|--------------------------------|-----------------|  
|`Current`|<span data-ttu-id="63489-133">열의 현재 값을 사용하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-133">The parameter uses the current value of the column.</span></span> <span data-ttu-id="63489-134">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-134">This is the default.</span></span>|  
|`Default`|<span data-ttu-id="63489-135">열의 `DefaultValue`를 사용하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-135">The parameter uses the `DefaultValue` of the column.</span></span>|  
|`Original`|<span data-ttu-id="63489-136">열의 원래 값을 사용하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-136">The parameter uses the original value of the column.</span></span>|  
|`Proposed`|<span data-ttu-id="63489-137">제안된 값을 사용하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="63489-137">The parameter uses a proposed value.</span></span>|  
  
 <span data-ttu-id="63489-138">다음 단원의 `SqlClient` 코드 예제에서는 <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 열이 두 매개 변수 `CustomerID`(`SourceColumn`) 및 `@CustomerID` (`SET CustomerID = @CustomerID`)에 대한 `@OldCustomerID`으로 사용되는 `WHERE CustomerID = @OldCustomerID`의 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-138">The `SqlClient` code example in the next section defines a parameter for an <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in which the `CustomerID` column is used as a `SourceColumn` for two parameters: `@CustomerID` (`SET CustomerID = @CustomerID`), and `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span></span> <span data-ttu-id="63489-139">`@CustomerID` 매개 변수 업데이트에 사용 되는 **CustomerID** 열에 현재 값으로는 `DataRow`합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-139">The `@CustomerID` parameter is used to update the **CustomerID** column to the current value in the `DataRow`.</span></span> <span data-ttu-id="63489-140">결과적으로 `CustomerID` `SourceColumn` 와 `SourceVersion` 의 `Current` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-140">As a result, the `CustomerID` `SourceColumn` with a `SourceVersion` of `Current` is used.</span></span> <span data-ttu-id="63489-141">*@OldCustomerID* 매개 변수를 사용 하는 데이터 원본에서 현재 행을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-141">The *@OldCustomerID* parameter is used to identify the current row in the data source.</span></span> <span data-ttu-id="63489-142">행의 `Original` 버전에 일치하는 열 값이 있으므로 `SourceColumn`이 `CustomerID`인 동일한 `SourceVersion`(`Original`)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-142">Because the matching column value is found in the `Original` version of the row, the same `SourceColumn` (`CustomerID`) with a `SourceVersion` of `Original` is used.</span></span>  
  
## <a name="working-with-sqlclient-parameters"></a><span data-ttu-id="63489-143">SqlClient 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="63489-143">Working with SqlClient Parameters</span></span>  
 <span data-ttu-id="63489-144">다음 예제에서는 데이터베이스에서 추가적인 스키마 정보를 검색하기 위해 <xref:System.Data.SqlClient.SqlDataAdapter>를 만들고 <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A>을 <xref:System.Data.MissingSchemaAction.AddWithKey>로 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63489-144">The following example demonstrates how to create a <xref:System.Data.SqlClient.SqlDataAdapter> and set the <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> to <xref:System.Data.MissingSchemaAction.AddWithKey> in order to retrieve additional schema information from the database.</span></span> <span data-ttu-id="63489-145"><xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> 및 <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> 속성이 설정되고 해당 <xref:System.Data.SqlClient.SqlParameter> 개체가 <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-145">The <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties set and their corresponding <xref:System.Data.SqlClient.SqlParameter> objects added to the <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection.</span></span> <span data-ttu-id="63489-146">메서드에서 `SqlDataAdapter` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-146">The method returns a `SqlDataAdapter` object.</span></span>  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a><span data-ttu-id="63489-147">OleDb 매개 변수 자리 표시자</span><span class="sxs-lookup"><span data-stu-id="63489-147">OleDb Parameter Placeholders</span></span>  
 <span data-ttu-id="63489-148"><xref:System.Data.OleDb.OleDbDataAdapter> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체의 경우 물음표(?) 자리 표시자를 사용하여 매개 변수를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-148">For the <xref:System.Data.OleDb.OleDbDataAdapter> and <xref:System.Data.Odbc.OdbcDataAdapter> objects, you must use question mark (?) placeholders to identify the parameters.</span></span>  
  
```vb  
Dim selectSQL As String = _  
  "SELECT CustomerID, CompanyName FROM Customers " & _  
  "WHERE CountryRegion = ? AND City = ?"  
Dim insertSQL AS String = _  
  "INSERT INTO Customers (CustomerID, CompanyName) VALUES (?, ?)"  
Dim updateSQL AS String = _  
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " & _  
  WHERE CustomerID = ?"  
Dim deleteSQL As String = "DELETE FROM Customers WHERE CustomerID = ?"  
```  
  
```csharp  
string selectSQL =   
  "SELECT CustomerID, CompanyName FROM Customers " +  
  "WHERE CountryRegion = ? AND City = ?";  
string insertSQL =   
  "INSERT INTO Customers (CustomerID, CompanyName) " +  
  "VALUES (?, ?)";  
string updateSQL =   
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " +  
  "WHERE CustomerID = ? ";  
string deleteSQL = "DELETE FROM Customers WHERE CustomerID = ?";  
```  
  
 <span data-ttu-id="63489-149">매개 변수가 있는 쿼리 문에서는 만들어야 할 입력 및 출력 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-149">The parameterized query statements define which input and output parameters must be created.</span></span> <span data-ttu-id="63489-150">매개 변수를 만들려면 `Parameters.Add` 메서드나 `Parameter` 생성자를 사용하여 열 이름, 데이터 형식 및 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-150">To create a parameter, use the `Parameters.Add` method or the `Parameter` constructor to specify the column name, data type, and size.</span></span> <span data-ttu-id="63489-151">`Integer`와 같은 내장 데이터 형식의 경우 크기를 포함할 필요가 없거나 기본 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63489-151">For intrinsic data types, such as `Integer`, you do not have to include the size, or you can specify the default size.</span></span>  
  
 <span data-ttu-id="63489-152">다음 코드 예제에서는 SQL 문에 대한 매개 변수를 만들고 `DataSet`을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="63489-152">The following code example creates the parameters for a SQL statement and then fills a `DataSet`.</span></span>  
  
## <a name="oledb-example"></a><span data-ttu-id="63489-153">OleDb 예제</span><span class="sxs-lookup"><span data-stu-id="63489-153">OleDb Example</span></span>  
  
```vb  
' Assumes that connection is a valid OleDbConnection object.  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter   
  
Dim selectCMD AS OleDbCommand = New OleDbCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add parameters and set values.  
selectCMD.Parameters.Add( _  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add( _  
  "@City", OleDbType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OleDbConnection object.  
OleDbDataAdapter adapter = new OleDbDataAdapter();  
  
OleDbCommand selectCMD = new OleDbCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
// Add parameters and set values.  
selectCMD.Parameters.Add(  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add(  
  "@City", OleDbType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
## <a name="odbc-parameters"></a><span data-ttu-id="63489-154">Odbc 매개 변수</span><span class="sxs-lookup"><span data-stu-id="63489-154">Odbc Parameters</span></span>  
  
```vb  
' Assumes that connection is a valid OdbcConnection object.  
Dim adapter As OdbcDataAdapter = New OdbcDataAdapter  
  
Dim selectCMD AS OdbcCommand = New OdbcCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OdbcConnection object.  
OdbcDataAdapter adapter = new OdbcDataAdapter();  
  
OdbcCommand selectCMD = new OdbcCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
//Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="63489-155">매개 변수에 대해 매개 변수 이름이 제공 되지 않은 매개 변수가 매개 변수는 증분 기본 이름인 제공 됩니다*N* *,* "Parameter1"로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-155">If a parameter name is not supplied for a parameter, the parameter is given an incremental default name of Parameter*N* *,* starting with "Parameter1".</span></span> <span data-ttu-id="63489-156">매개 변수를 방지 하는 것이 좋습니다*N* 명명 규칙 매개 변수 이름을 제공 하면 사용자가 제공한 이름에 있는 기존의 기본 매개 변수 이름과 충돌할 수 있기 때문에 `ParameterCollection`합니다.</span><span class="sxs-lookup"><span data-stu-id="63489-156">We recommend that you avoid the Parameter*N* naming convention when you supply a parameter name, because the name that you supply might conflict with an existing default parameter name in the `ParameterCollection`.</span></span> <span data-ttu-id="63489-157">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="63489-157">If the supplied name already exists, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63489-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63489-158">See Also</span></span>  
 [<span data-ttu-id="63489-159">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="63489-159">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="63489-160">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="63489-160">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="63489-161">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="63489-161">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="63489-162">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="63489-162">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="63489-163">ADO.NET에서 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="63489-163">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="63489-164">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="63489-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
