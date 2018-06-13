---
title: ADO.NET에서 큰 값(최대값) 데이터 수정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 285803d92474efd3268816d1af06eb3ff4abbc79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365594"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="71b57-102">ADO.NET에서 큰 값(최대값) 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="71b57-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="71b57-103">LOB(Large Object) 데이터 형식은 최대 행 크기 8KB를 초과하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="71b57-104">SQL Server에서는 `max`, `varchar` 및 `nvarchar` 데이터 형식에 사용할 수 있는 `varbinary` 지정자를 제공하여 2^32바이트에 이르는 큰 값도 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="71b57-105">테이블 열 및 Transact-SQL 변수에서는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="71b57-106">ADO.NET에서는 `max`를 사용하여 `DataReader` 데이터 형식을 가져올 수 있을 뿐 아니라 특별한 처리 없이도 입력 및 출력 매개 변수 값을 모두 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="71b57-107">큰 `varchar` 데이터 형식의 경우에는 데이터를 점진적으로 검색하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="71b57-108">`max` 데이터 형식은 비교 및 연결 작업에 사용할 수 있으며, 비교를 수행할 경우에는 Transact-SQL 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="71b57-109">또한 SELECT 문의 DISTINCT, ORDER BY, GROUP BY 절에는 물론 집계, 조인 및 하위 쿼리에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="71b57-110">다음 표에는 SQL Server 온라인 설명서의 문서에 대한 링크가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="71b57-111">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="71b57-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="71b57-112">큰 값 데이터 형식 사용</span><span class="sxs-lookup"><span data-stu-id="71b57-112">Using Large-Value Data Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="71b57-113">큰 값 형식 제한 사항</span><span class="sxs-lookup"><span data-stu-id="71b57-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="71b57-114">다음 제한 사항은 `max` 데이터 형식에 적용되며, 보다 작은 데이터 형식에 대해서는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
-   <span data-ttu-id="71b57-115">`sql_variant`에는 큰 `varchar` 데이터 형식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
-   <span data-ttu-id="71b57-116">큰 `varchar` 열은 인덱스에 키 열로 지정할 수 없으며</span><span class="sxs-lookup"><span data-stu-id="71b57-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="71b57-117">클러스터링되지 않은 인덱스에 포함된 열에는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
-   <span data-ttu-id="71b57-118">큰 `varchar` 열은 키 열을 분할하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="71b57-119">Transact-SQL에서 큰 값 형식 사용</span><span class="sxs-lookup"><span data-stu-id="71b57-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="71b57-120">Transact-SQL `OPENROWSET` 함수는 원격 데이터 연결 및 액세스를 한 번에 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="71b57-121">이 함수에는 OLE DB 데이터 소스에서 원격 데이터에 액세스하는 데 필요한 모든 연결 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="71b57-122">`OPENROWSET`은 쿼리의 FROM 절에서 테이블 이름인 것처럼 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="71b57-123">또한 OLE DB 공급자의 기능에 따라 INSERT, UPDATE 또는 DELETE 문의 대상 테이블로 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="71b57-124">`OPENROWSET` 함수에서는 `BULK` 행 집합 공급자를 추가하여 대상 테이블로 데이터를 로드하지 않고 파일에서 직접 데이터를 읽어올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="71b57-125">따라서 간단한 INSERT SELECT 문에서 `OPENROWSET`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="71b57-126">`OPENROWSET``BULK` 옵션 인수는 시작 및 종료 지점 데이터를 읽을 수 있는 위치, 오류 처리 하는 방법 및 데이터를 해석 하는 방법에 대 한 상당한 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-126">The `OPENROWSET``BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="71b57-127">예를 들어, 데이터 파일을 `varbinary`, `varchar` 또는 `nvarchar` 형식의 단일 행 및 단일 열 행 집합으로 읽도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="71b57-128">전체 구문과 옵션을 보려면 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71b57-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="71b57-129">다음 예제에서는 AdventureWorks 샘플 데이터베이스의 ProductPhoto 테이블에 사진을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="71b57-130">사용 하는 경우는 `BULK``OPENROWSET` 공급자, 모든 열에 값을 삽입 하지도 열의 명명 된 목록을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-130">When using the `BULK``OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="71b57-131">이 경우 기본 키는 ID 열로 정의되며 열 목록에서 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="71b57-132">또한 `OPENROWSET` 문의 끝에 상관 관계 이름을 제공해야 하며, 이 경우 ThumbnailPhoto입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="71b57-133">이렇게 하면 파일이 로드되는 `ProductPhoto` 테이블의 열과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="71b57-134">UPDATE .WRITE를 사용하여 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="71b57-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="71b57-135">Transact-SQL UPDATE 문에는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 열의 내용을 수정하기 위한 새로운 WRITE 구문이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="71b57-136">이 구문을 사용하면 데이터를 부분적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="71b57-137">다음은 약식으로 나타낸 UPDATE .WRITE 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="71b57-138">업데이트</span><span class="sxs-lookup"><span data-stu-id="71b57-138">UPDATE</span></span>  
  
 <span data-ttu-id="71b57-139">{  *\<개체 >* }</span><span class="sxs-lookup"><span data-stu-id="71b57-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="71b57-140">SET</span><span class="sxs-lookup"><span data-stu-id="71b57-140">SET</span></span>  
  
 <span data-ttu-id="71b57-141">{ *column_name* = {합니다. 쓰기 ( *식* , @Offset , @Length )을 (를)</span><span class="sxs-lookup"><span data-stu-id="71b57-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="71b57-142">WRITE 메서드를 지정 하는 값의 섹션은 *column_name* 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="71b57-143">식은에 복사 될 값의 *column_name*, `@Offset` 되는 식이 작성 되, 시작 지점 및 `@Length` 인수는 열에 있는 부분의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="71b57-144">조건</span><span class="sxs-lookup"><span data-stu-id="71b57-144">If</span></span>|<span data-ttu-id="71b57-145">결과</span><span class="sxs-lookup"><span data-stu-id="71b57-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="71b57-146">식이 NULL로 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="71b57-146">The expression is set to NULL</span></span>|<span data-ttu-id="71b57-147">`@Length` 무시 됩니다에 값 *column_name* 잘렸습니다. 지정 된 위치에서 `@Offset`합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="71b57-148">`@Offset`이 NULL인 경우</span><span class="sxs-lookup"><span data-stu-id="71b57-148">`@Offset` is NULL</span></span>|<span data-ttu-id="71b57-149">업데이트 작업에서 기존의 끝에 식이 추가 *column_name* 값 및 `@Length` 는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="71b57-150">`@Offset`이 column_name 값의 길이보다 큰 경우</span><span class="sxs-lookup"><span data-stu-id="71b57-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="71b57-151">SQL Server에서 오류를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="71b57-152">`@Length`이 NULL인 경우</span><span class="sxs-lookup"><span data-stu-id="71b57-152">`@Length` is NULL</span></span>|<span data-ttu-id="71b57-153">업데이트 작업을 통해 `@Offset`부터 `column_name` 값 끝 사이에 있는 모든 데이터가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="71b57-154">`@Offset`과 `@Length`는 모두 음수일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71b57-155">예제</span><span class="sxs-lookup"><span data-stu-id="71b57-155">Example</span></span>  
 <span data-ttu-id="71b57-156">이 Transact-SQL 예제에서는 AdventureWorks 데이터베이스에 있는 Document 테이블의 `nvarchar(max)` 열인 DocumentSummary에서 값의 일부를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="71b57-157">'components'라는 단어는 대체 단어, 기존 데이터에서 대체할 단어의 시작 위치(오프셋) 및 대체할 문자 수(길이)를 지정하여 'features'라는 단어로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="71b57-158">이 예제에는 결과를 비교하기 위해 UPDATE 문 앞뒤에 SELECT 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```  
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="71b57-159">ADO.NET에서 큰 값 형식 사용</span><span class="sxs-lookup"><span data-stu-id="71b57-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="71b57-160">ADO.NET에서 큰 값 형식으로 큰 값 형식을 지정 하 여 작업할 수 <xref:System.Data.SqlClient.SqlParameter> 개체에 <xref:System.Data.SqlClient.SqlDataReader> , 집합 또는 사용 하 여 결과 반환 하는 <xref:System.Data.SqlClient.SqlDataAdapter> 채울는 `DataSet` / `DataTable`합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="71b57-161">큰 값 형식과 관련된 작은 값의 데이터 형식을 작업하는 방식에는 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="71b57-162">GetSqlBytes를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="71b57-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="71b57-163">`GetSqlBytes`의 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 사용하면 `varbinary(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="71b57-164">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlCommand>라는 `cmd` 개체는 테이블에서 `varbinary(max)` 데이터를 선택하고 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체는 데이터를 <xref:System.Data.SqlTypes.SqlBytes>로 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="71b57-165">GetSqlChars를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="71b57-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="71b57-166">`GetSqlChars`의 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 사용하면 `varchar(max)` 또는 `nvarchar(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="71b57-167">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlCommand>라는 `cmd` 개체는 테이블에서 `nvarchar(max)` 데이터를 선택하고 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체는 데이터를 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="71b57-168">GetSqlBinary를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="71b57-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="71b57-169">`GetSqlBinary`의 <xref:System.Data.SqlClient.SqlDataReader> 메서드를 사용하면 `varbinary(max)` 열의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="71b57-170">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlCommand>라는 `cmd` 개체는 테이블에서 `varbinary(max)` 데이터를 선택하고 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체는 데이터를 <xref:System.Data.SqlTypes.SqlBinary> 스트림으로 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="71b57-171">GetBytes를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="71b57-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="71b57-172">`GetBytes`의 <xref:System.Data.SqlClient.SqlDataReader> 메서드에서는 지정된 열 오프셋의 바이트 스트림을 지정된 배열 오프셋에서 시작하는 바이트 배열로 읽어들입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="71b57-173">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체가 바이트 배열에서 바이트를 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="71b57-174">`GetSqlBytes`와 달리 `GetBytes`에는 배열 버퍼의 크기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="71b57-175">GetValue를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="71b57-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="71b57-176">`GetValue`의 <xref:System.Data.SqlClient.SqlDataReader> 메서드에서는 지정된 열 오프셋의 값을 배열로 읽어들입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="71b57-177">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체가 첫 번째 열 오프셋에서 이진 데이터를 검색한 다음 두 번째 열 오프셋에서 문자열 데이터를 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="71b57-178">큰 값 형식을 CLR 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="71b57-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="71b57-179">`varchar(max)` 같은 문자열 변환 메서드를 사용하면 `nvarchar(max)` 또는 `ToString` 열의 내용을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="71b57-180">다음 코드 조각에서는 <xref:System.Data.SqlClient.SqlDataReader>라는 `reader` 개체가 데이터를 검색하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="71b57-181">예제</span><span class="sxs-lookup"><span data-stu-id="71b57-181">Example</span></span>  
 <span data-ttu-id="71b57-182">다음 코드에서는 `LargePhoto` 데이터베이스의 `ProductPhoto` 테이블에서 이름과 `AdventureWorks` 개체를 검색한 다음 이를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="71b57-183">어셈블리는 <xref:System.Drawing> 네임스페이스에 대한 참조로 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="71b57-184"><xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>의 <xref:System.Data.SqlClient.SqlDataReader> 메서드는 <xref:System.Data.SqlTypes.SqlBytes> 속성을 노출하는 `Stream` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="71b57-185">코드를 사용 하 여이 새 `Bitmap` 개체를 다음 gif에서 저장 `ImageFormat`합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="71b57-186">큰 값 형식 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="71b57-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="71b57-187"><xref:System.Data.SqlClient.SqlParameter> 개체에 큰 값 형식을 사용하는 방식과 <xref:System.Data.SqlClient.SqlParameter> 개체에 작은 값 형식을 사용하는 방식은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="71b57-188">큰 값 형식을 검색할 수 있습니다 <xref:System.Data.SqlClient.SqlParameter> 다음 예제와 같이 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="71b57-189">이 코드에서는 AdventureWorks 샘플 데이터베이스에 다음 GetDocumentSummary 저장 프로시저가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="71b57-190">라는 입력된 매개 변수를 사용 하는 저장된 프로시저 @DocumentID 에 DocumentSummary 열의 내용을 반환 하 고는 @DocumentSummary 출력 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```  
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="71b57-191">예제</span><span class="sxs-lookup"><span data-stu-id="71b57-191">Example</span></span>  
 <span data-ttu-id="71b57-192">ADO.NET 코드에서는 <xref:System.Data.SqlClient.SqlConnection> 및 <xref:System.Data.SqlClient.SqlCommand> 개체를 만들어 GetDocumentSummary 저장 프로시저를 실행하고 큰 값 형식으로 저장되는 문서 요약을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="71b57-193">에 대 한 값을 전달 하는 코드는 @DocumentID 입력 매개 변수 및 결과에서 다시 전달 표시는 @DocumentSummary 콘솔 창에서 매개 변수를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b57-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="71b57-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71b57-194">See Also</span></span>  
 [<span data-ttu-id="71b57-195">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="71b57-195">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="71b57-196">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="71b57-196">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="71b57-197">ADO.NET에서 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="71b57-197">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="71b57-198">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="71b57-198">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
