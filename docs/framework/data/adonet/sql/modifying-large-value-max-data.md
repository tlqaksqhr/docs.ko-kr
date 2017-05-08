---
title: "ADO.NET에서 큰 값(max) 데이터 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# ADO.NET에서 큰 값(max) 데이터 수정
LOB\(Large Object\) 데이터 형식은 최대 행 크기 8KB를 초과하는 형식입니다.  SQL Server에서는 `varchar`, `nvarchar` 및 `varbinary` 데이터 형식에 사용할 수 있는 `max` 지정자를 제공하여 2^32바이트에 이르는 큰 값도 저장할 수 있습니다.  테이블 열 및 Transact\-SQL 변수에서는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 데이터 형식을 지정할 수 있습니다.  ADO.NET에서는 `DataReader`를 사용하여 `max` 데이터 형식을 가져올 수 있을 뿐 아니라 특별한 처리 없이도 입력 및 출력 매개 변수 값을 모두 지정할 수 있습니다.  큰 `varchar` 데이터 형식의 경우에는 데이터를 점진적으로 검색하고 업데이트할 수 있습니다.  
  
 `max` 데이터 형식은 비교 및 연결 작업에 사용할 수 있으며, 비교를 수행할 경우에는 Transact\-SQL 변수로 사용합니다.  또한 SELECT 문의 DISTINCT, ORDER BY, GROUP BY 절에는 물론 집계, 조인 및 하위 쿼리에도 사용할 수 있습니다.  
  
 다음 표에는 SQL Server 온라인 설명서의 문서에 대한 링크가 나와 있습니다.  
  
 **SQL Server 온라인 설명서**  
  
1.  [큰 값 데이터 형식 사용](http://go.microsoft.com/fwlink/?LinkId=120498)  
  
## 큰 값 형식 제한 사항  
 다음 제한 사항은 `max` 데이터 형식에 적용되며, 보다 작은 데이터 형식에 대해서는 존재하지 않습니다.  
  
-   `sql_variant`에는 큰 `varchar` 데이터 형식이 포함될 수 없습니다.  
  
-   큰 `varchar` 열은 인덱스에 키 열로 지정할 수 없으며  클러스터링되지 않은 인덱스에 포함된 열에는 사용할 수 있습니다.  
  
-   큰 `varchar` 열은 키 열을 분할하는 데 사용할 수 없습니다.  
  
## Transact\-SQL에서 큰 값 형식 사용  
 Transact\-SQL `OPENROWSET` 함수는 원격 데이터 연결 및 액세스를 한 번에 실행합니다.  이 함수에는 OLE DB 데이터 소스에서 원격 데이터에 액세스하는 데 필요한 모든 연결 정보가 들어 있습니다.  `OPENROWSET`은 쿼리의 FROM 절에서 테이블 이름인 것처럼 참조할 수 있습니다.  또한 OLE DB 공급자의 기능에 따라 INSERT, UPDATE 또는 DELETE 문의 대상 테이블로 참조할 수도 있습니다.  
  
 `OPENROWSET` 함수에서는 `BULK` 행 집합 공급자를 추가하여 대상 테이블로 데이터를 로드하지 않고 파일에서 직접 데이터를 읽어올 수 있습니다.  따라서 간단한 INSERT SELECT 문에서 `OPENROWSET`을 사용할 수 있습니다.  
  
 `OPENROWSET`  `BULK` 선택적 인수를 사용하면 데이터 읽기의 시작 및 종료 지점, 오류 처리 방법 및 데이터 해석 방법을 효과적으로 제어할 수 있습니다.  예를 들어, 데이터 파일을 `varbinary`, `varchar` 또는 `nvarchar` 형식의 단일 행 및 단일 열 행 집합으로 읽도록 지정할 수 있습니다.  전체 구문과 옵션을 보려면 SQL Server 온라인 설명서를 참조하세요.  
  
 다음 예제에서는 AdventureWorks 샘플 데이터베이스의 ProductPhoto 테이블에 사진을 삽입합니다.  `BULK``OPENROWSET` 공급자를 사용하는 경우 모든 열에 값을 삽입하지 않더라도 명명된 열 목록을 제공해야 합니다.  이 경우 기본 키는 ID 열로 정의되며 열 목록에서 생략할 수 있습니다.  또한 `OPENROWSET` 문의 끝에 상관 관계 이름을 제공해야 하며, 이 경우 ThumbnailPhoto입니다.  이렇게 하면 파일이 로드되는 `ProductPhoto` 테이블의 열과 연결됩니다.  
  
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
  
## UPDATE .WRITE를 사용하여 데이터 업데이트  
 Transact\-SQL UPDATE 문에는 `varchar(max)`, `nvarchar(max)` 또는 `varbinary(max)` 열의 내용을 수정하기 위한 새로운 WRITE 구문이 들어 있습니다.  이 구문을 사용하면 데이터를 부분적으로 업데이트할 수 있습니다.  다음은 약식으로 나타낸 UPDATE .WRITE 구문입니다.  
  
 UPDATE  
  
 { *\<object\>* }  
  
 SET  
  
 { *column\_name* \= { .WRITE \( *expression* , @Offset , @Length \) }  
  
 WRITE 메서드에서는 *column\_name* 값의 일정 부분이 수정되도록 지정합니다.  식은 *column\_name*에 복사되는 값이고, `@Offset`은 식이 작성되는 시작점이며, `@Length` 인수는 열에 있는 일정 부분의 길이입니다.  
  
|조건|결과|  
|--------|--------|  
|식이 NULL로 설정된 경우|`@Length`가 무시되고 *column\_name*의 값은 지정된 `@Offset`에서 잘립니다.|  
|`@Offset`이 NULL인 경우|업데이트 작업을 통해 기존 *column\_name* 값의 끝에 식이 추가되고 `@Length`는 무시됩니다.|  
|`@Offset`이 column\_name 값의 길이보다 큰 경우|SQL Server에서 오류를 반환합니다.|  
|`@Length`이 NULL인 경우|업데이트 작업을 통해 `@Offset`부터 `column_name` 값 끝 사이에 있는 모든 데이터가 제거됩니다.|  
  
> [!NOTE]
>  `@Offset`과 `@Length`는 모두 음수일 수 없습니다.  
  
## 예제  
 이 Transact\-SQL 예제에서는 AdventureWorks 데이터베이스에 있는 Document 테이블의 `nvarchar(max)` 열인 DocumentSummary에서 값의 일부를 업데이트합니다.  'components'라는 단어는 대체 단어, 기존 데이터에서 대체할 단어의 시작 위치\(오프셋\) 및 대체할 문자 수\(길이\)를 지정하여 'features'라는 단어로 대체됩니다.  이 예제에는 결과를 비교하기 위해 UPDATE 문 앞뒤에 SELECT 문이 포함되어 있습니다.  
  
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
  
## ADO.NET에서 큰 값 형식 사용  
 ADO.NET에서는 <xref:System.Data.SqlClient.SqlDataReader>에서 <xref:System.Data.SqlClient.SqlParameter> `` 개체로 지정하여 결과 집합을 반환하거나 <xref:System.Data.SqlClient.SqlDataAdapter>를 사용하여 `DataSet`\/`DataTable`을 채우는 방식으로 큰 값 형식을 사용할 수 있습니다.  큰 값 형식과 관련된 작은 값의 데이터 형식을 작업하는 방식에는 차이가 없습니다.  
  
### GetSqlBytes를 사용하여 데이터 검색  
 <xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlBytes` 메서드를 사용하면 `varbinary(max)` 열의 내용을 검색할 수 있습니다.  다음 코드 조각에서는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체는 테이블에서 `varbinary(max)` 데이터를 선택하고 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체는 데이터를 <xref:System.Data.SqlTypes.SqlBytes>로 검색하는 것으로 가정합니다.  
  
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
  
### GetSqlChars를 사용하여 데이터 검색  
 <xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlChars` 메서드를 사용하면 `varchar(max)` 또는 `nvarchar(max)` 열의 내용을 검색할 수 있습니다.  다음 코드 조각에서는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체는 테이블에서 `nvarchar(max)` 데이터를 선택하고 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체는 데이터를 검색하는 것으로 가정합니다.  
  
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
  
### GetSqlBinary를 사용하여 데이터 검색  
 <xref:System.Data.SqlClient.SqlDataReader>의 `GetSqlBinary` 메서드를 사용하면 `varbinary(max)` 열의 내용을 검색할 수 있습니다.  다음 코드 조각에서는 `cmd`라는 <xref:System.Data.SqlClient.SqlCommand> 개체는 테이블에서 `varbinary(max)` 데이터를 선택하고 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체는 데이터를 <xref:System.Data.SqlTypes.SqlBinary> 스트림으로 검색하는 것으로 가정합니다.  
  
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
  
### GetBytes를 사용하여 데이터 검색  
 <xref:System.Data.SqlClient.SqlDataReader>의 `GetBytes` 메서드에서는 지정된 열 오프셋의 바이트 스트림을 지정된 배열 오프셋에서 시작하는 바이트 배열로 읽어들입니다.  다음 코드 조각에서는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체가 바이트 배열에서 바이트를 검색하는 것으로 가정합니다.  `GetSqlBytes`와 달리 `GetBytes`에는 배열 버퍼의 크기가 필요합니다.  
  
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
  
### GetValue를 사용하여 데이터 검색  
 <xref:System.Data.SqlClient.SqlDataReader>의 `GetValue` 메서드에서는 지정된 열 오프셋의 값을 배열로 읽어들입니다.  다음 코드 조각에서는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체가 첫 번째 열 오프셋에서 이진 데이터를 검색한 다음 두 번째 열 오프셋에서 문자열 데이터를 검색하는 것으로 가정합니다.  
  
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
  
## 큰 값 형식을 CLR 형식으로 변환  
 `ToString` 같은 문자열 변환 메서드를 사용하면 `varchar(max)` 또는 `nvarchar(max)` 열의 내용을 변환할 수 있습니다.  다음 코드 조각에서는 `reader`라는 <xref:System.Data.SqlClient.SqlDataReader> 개체가 데이터를 검색하는 것으로 가정합니다.  
  
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
  
### 예제  
 다음 코드에서는 `AdventureWorks` 데이터베이스의 `ProductPhoto` 테이블에서 이름과 `LargePhoto` 개체를 검색한 다음 이를 파일에 저장합니다.  어셈블리는 <xref:System.Drawing> 네임스페이스에 대한 참조로 컴파일해야 합니다.  <xref:System.Data.SqlClient.SqlDataReader>의 <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> 메서드는 `Stream` 속성을 노출하는 <xref:System.Data.SqlTypes.SqlBytes> 개체를 반환합니다.  코드에서는 이 개체를 사용하여 새 `Bitmap` 개체를 만든 다음 Gif`ImageFormat`으로 저장합니다.  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## 큰 값 형식 매개 변수 사용  
 <xref:System.Data.SqlClient.SqlParameter> 개체에 큰 값 형식을 사용하는 방식과 <xref:System.Data.SqlClient.SqlParameter> 개체에 작은 값 형식을 사용하는 방식은 같습니다.  다음 예제에서처럼 큰 값 형식은 <xref:System.Data.SqlClient.SqlParameter> `` 값으로 검색할 수 있습니다.  이 코드에서는 AdventureWorks 샘플 데이터베이스에 다음 GetDocumentSummary 저장 프로시저가 있는 것으로 가정합니다.  저장 프로시저는 @DocumentID라는 입력 매개 변수를 사용하여 @DocumentSummary 출력 매개 변수에 DocumentSummary 열의 내용을 반환합니다.  
  
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
  
### 예제  
 ADO.NET 코드에서는 <xref:System.Data.SqlClient.SqlConnection> 및 <xref:System.Data.SqlClient.SqlCommand> 개체를 만들어 GetDocumentSummary 저장 프로시저를 실행하고 큰 값 형식으로 저장되는 문서 요약을 검색할 수 있습니다.  이 코드에서는 @DocumentID 입력 매개 변수 값을 전달한 다음 콘솔 창에 @DocumentSummary 출력 매개 변수에 다시 전달된 결과를 표시합니다.  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## 참고 항목  
 [SQL Server 이진 데이터 및 큰 값 데이터](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [SQL Server 데이터 형식 매핑](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)   
 [ADO.NET의 SQL Server 데이터 작업](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)