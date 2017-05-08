---
title: "DataReader를 사용하여 데이터 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataReader를 사용하여 데이터 검색
**DataReader**를 사용한 데이터 검색 작업에는 **Command** 개체의 인스턴스를 만든 후 **Command.ExecuteReader** 호출을 통해 **DataReader**를 만들어 데이터 소스에서 행을 검색하기까지의 작업이 포함됩니다.  다음 예제에서는 `reader`가 올바른 DataReader를 나타내고 `command`가 올바른 Command 개체를 나타낼 때 **DataReader**를 사용하는 방법을 보여 줍니다.  
  
```  
reader = command.ExecuteReader();  
```  
  
 **DataReader** 개체의 **Read** 메서드를 사용하여 쿼리 결과에서 행을 가져올 수 있습니다.  열 이름이나 서수 참조를 **DataReader**에 전달하여 반환된 행의 각 열에 액세스할 수 있습니다.  그러나 최고의 성능을 위해 **DataReader**는 **GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32** 등의 네이티브 데이터 형식의 열 값에 액세스할 수 있도록 하는 일련의 메서드를 제공합니다.  데이터 공급자별 **DataReaders**의 형식화된 접근자 메서드 목록을 보려면 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.SqlClient.SqlDataReader>를 참조하세요.  기본 데이터 형식을 알고 있는 경우 형식화된 접근자 메서드를 사용하면 열 값을 검색할 때 필요한 형식 변환의 양이 줄어듭니다.  
  
> [!NOTE]
>  .NET Framework의 Windows Server 2003 릴리스에는 **DataReader**의 추가 속성인 **HasRows**가 있어 이 속성으로 결과를 읽기 전에 **DataReader**가 결과를 반환했는지 여부를 결정할 수 있습니다.  
  
 다음 코드 예제에서는 **DataReader** 개체를 전체 반복하고 각 행에서 두 열을 반환합니다.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader**는 프로시저 논리가 데이터 소스에서 순차적으로 가져오는 결과를 효율적으로 처리할 수 있도록 버퍼링되지 않은 데이터 스트림을 제공합니다.  대량의 데이터를 검색할 때에는 데이터가 메모리에 캐시되지 않으므로 **DataReader**를 선택하는 것이 좋습니다.  
  
## DataReader 닫기  
 **DataReader** 개체 사용을 완료하면 항상 **Close** 메서드를 호출해야 합니다.  
  
 **Command**에 출력 매개 변수나 반환 값이 들어 있는 경우 이러한 값을 사용하려면 먼저 **DataReader**를 닫아야 합니다.  
  
 **DataReader**가 열려 있는 동안은 **DataReader**에서 단독으로 **Connection**을 사용하고 있는 것입니다.  **DataReader**를 닫아야 다른 **DataReader**의 작성을 비롯하여 **Connection**에 대해 명령을 실행할 수 있습니다.  
  
> [!NOTE]
>  **Connection**, **DataReader** 또는 클래스의 **Finalize** 메서드에서 관리되는 다른 모든 개체에 대해 **Close** 또는 **Dispose**를 호출하지 마세요.  종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다.  클래스에 관리되지 않는 리소스가 없는 경우 클래스 정의에 **Finalize** 메서드를 포함하지 마세요.  자세한 내용은 [Garbage Collection](../../../../docs/standard/garbage-collection/index.md)을 참조하세요.  
  
## NextResult를 사용하여 여러 개의 결과 집합 검색  
 여러 개의 결과 집합이 반환되면 **DataReader**는 **NextResult** 메서드를 제공하여 결과 집합을 순서대로 전체 반복합니다.  다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## DataReader에서 스키마 정보 가져오기  
 **DataReader**가 열려 있는 동안에는 **GetSchemaTable** 메서드를 사용하여 현재 결과 집합에 대한 스키마 정보를 검색할 수 있습니다.  **GetSchemaTable**은 현재 결과 집합에 대한 스키마 정보를 포함하는 행과 열로 채워진 <xref:System.Data.DataTable> 개체를 반환합니다.  **DataTable**은 결과 집합의 각 열마다 한 행씩 포함하게 됩니다.  스키마 테이블 행의 각 열은 결과 집합에 반환된 열의 속성에 매핑됩니다. 여기서 **ColumnName**은 속성 이름이고 열 값은 속성 값입니다.  다음 코드 예제에서는 **DataReader**에 대한 스키마 정보를 출력합니다.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## OLE DB 장 사용  
 계층적 행 집합 또는 장\(OLE DB 형식 **DBTYPE\_HCHAPTER**, ADO 형식 **adChapter**\)은 <xref:System.Data.OleDb.OleDbDataReader>를 사용하여 검색할 수 있습니다.  장을 포함하는 쿼리가 **DataReader**로 반환되면 **DataReader**의 열로 반환되고 **DataReader** 개체로 노출됩니다.  
  
 또한 테이블 간의 부모 자식 관계를 사용하여 계층적 행 집합을 나타내는 데 ADO.NET **DataSet**을 사용할 수 있습니다.  자세한 내용은 [DataSets, DataTables 및 DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)을 참조하세요.  
  
 다음 코드 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## Oracle REF CURSOR를 사용하여 결과 반환  
 .NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다.  Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.  
  
 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 메서드를 사용하여 Oracle REF CURSOR를 나타내는 **OracleDataReader** 개체를 검색할 수 있으며 <xref:System.Data.DataSet>을 채우는 데 사용되는 <xref:System.Data.OracleClient.OracleDataAdapter>에 대한 **SelectCommand**로서 하나 이상의 Oracle REF CURSOR를 반환하는 <xref:System.Data.OracleClient.OracleCommand>를 지정할 수도 있습니다.  
  
 Oracle 데이터 소스에서 반환된 REF CURSOR에 액세스하려면 쿼리용 **OracleCommand**를 만들고 REF CURSOR를 참조하는 출력 매개 변수를 **OracleCommand**의 **Parameters** 컬렉션에 추가합니다.  매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다.  매개 변수 형식을 **OracleType.Cursor**로 설정합니다.  **OracleCommand**의 **ExecuteReader** 메서드는 REF CURSOR의 **OracleDataReader**를 반환합니다.  
  
 **OracleCommand**에 의해 여러 REF CURSOR가 반환되면 여러 출력 매개 변수를 추가합니다.  **OracleCommand.ExecuteReader** 메서드를 호출하여 서로 다른 REF CURSOR에 액세스할 수 있습니다.  **ExecuteReader**를 호출하면 첫 REF CURSOR를 참조하는 **OracleDataReader**가 반환됩니다.  그런 다음 **OracleDataReader.NextResult** 메서드를 호출하여 뒤에 나오는 REF CURSOR에 액세스할 수 있습니다.  **OracleCommand.Parameters** 컬렉션의 매개 변수 이름이 REF CURSOR 출력 매개 변수 이름과 같기는 하지만 **Parameters** 컬렉션에 추가된 순서에 따라 **OracleDataReader**에 의해 액세스됩니다.  
  
 예를 들어, 다음과 같은 Oracle 패키지 및 패키지 본문이 있을 수 있습니다.  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 다음 코드에서는 **OracleType.Cursor** 형식의 두 매개 변수를 **Parameters** 컬렉션에 추가하여 이전 Oracle 패키지에서 REF CURSOR를 반환하는 **OracleCommand**를 만듭니다.  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 다음 코드에서는 **OracleDataReader**의 **Read** 및 **NextResult** 메서드를 사용하여 이전 명령의 결과를 반환합니다.  REF CURSOR 매개 변수가 순서대로 반환됩니다.  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 다음 예제에서는 위의 명령을 사용하여 **DataSet**에 Oracle 패키지의 결과를 채웁니다.  
  
> [!NOTE]
>  **OverflowException**을 방지하려면 **DataRow**에 값을 저장하기 전에 Oracle NUMBER 형식을 유효한 .NET Framework 형식으로 변환하는 것이 좋습니다.  **FillError** 이벤트를 사용하면 **OverflowException**의 발생 여부를 알 수 있습니다.  **FillError** 이벤트에 대한 자세한 내용은 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)을 참조하세요.  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## 참고 항목  
 [Working with DataReaders](http://msdn.microsoft.com/ko-kr/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [DataAdapters 및 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)