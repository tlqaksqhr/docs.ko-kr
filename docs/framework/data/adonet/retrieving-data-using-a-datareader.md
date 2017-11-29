---
title: "DataReader를 사용하여 데이터 검색"
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
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0b66ca2fbcc760598b771b4c02a46acc3c9c1d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-data-using-a-datareader"></a>DataReader를 사용하여 데이터 검색
사용 하 여 데이터를 검색 하는 **DataReader** 의 인스턴스를 만들고는 **명령** 개체 어셈블리 한 후 한 **DataReader** 호출 하 여  **Command.ExecuteReader** 데이터 원본에서 행을 검색 합니다. 다음 예제에서는 사용 하 여는 **DataReader** 여기서 `reader` 유효한 DataReader 나타냅니다 및 `command` 유효한 명령 개체를 나타냅니다.  
  
```  
reader = command.ExecuteReader();  
```  
  
 사용 된 **읽기** 의 메서드는 **DataReader** 개체를 쿼리 결과에서 행을 가져옵니다. 이름이 나 열을 서 수 참조를 전달 하 여 반환된 된 행의 각 열에 액세스할 수 있습니다는 **DataReader**합니다. 그러나 최고의 성능을 위해는 **DataReader** 일련의 네이티브 데이터 형식으로의 열 값에 액세스할 수 있도록 하는 메서드를 제공 합니다. (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**등). 공급자 관련 데이터에 대 한 형식화 된 접근자 메서드 목록을 **DataReaders**, 참조 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.SqlClient.SqlDataReader>합니다. 기본 데이터 형식을 알고 있는 경우 형식화된 접근자 메서드를 사용하면 열 값을 검색할 때 필요한 형식 변환의 양이 줄어듭니다.  
  
> [!NOTE]
>  .NET Framework의 Windows Server 2003 릴리스에에 대 한 추가 속성을 포함 되어는 **DataReader**, **HasRows**, 하는 경우를 확인할 수 있습니다는 **DataReader**가에서 읽기 전에 결과 반환 합니다.  
  
 다음 코드 예제에서는 반복는 **DataReader** 개체 및 각 행에서 두 열을 반환 합니다.  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader** 절차적 논리를 효율적으로 데이터 소스에서 결과 순차적으로 처리할 수 있는 데이터의 버퍼링 되지 않은 스트림을 제공 합니다. **DataReader** 데이터가 메모리에 캐시 되지 않으면 때문에 많은 양의 데이터를 검색할 때이 좋은 대안입니다.  
  
## <a name="closing-the-datareader"></a>DataReader 닫기  
 항상 호출 해야는 **닫기** 메서드를 사용 하 여 완료 되 면는 **DataReader** 개체입니다.  
  
 경우에 **명령** 출력을 포함 매개 변수 또는 반환 값 됩니다 때까지 사용할 수는 **DataReader** 닫혀 있습니다.  
  
 하지만 한 **DataReader** 열려는 **연결** 에서 단독으로 사용 중인 **DataReader**합니다. 에 대 한 모든 명령을 실행할 수 없습니다는 **연결**, 하는 등 다른 **DataReader**, 원래 될 때까지 **DataReader** 닫혀 있습니다.  
  
> [!NOTE]
>  호출 하지 마십시오 **닫기** 또는 **Dispose** 에 **연결**, **DataReader**, 또는 다른 관리 되는 개체에는 **Finalize**  클래스의 메서드로 합니다. 종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다. 클래스에 관리 되지 않는 리소스가 없는 경우 포함 되지 않습니다는 **Finalize** 클래스 정의에 메서드. 자세한 내용은 참조 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>NextResult를 사용하여 여러 개의 결과 집합 검색  
 여러 개의 결과 집합이 반환 되는 경우는 **DataReader** 제공는 **NextResult** 결과 반복 하는 메서드 집합을 순서 대로 합니다. 다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>DataReader에서 스키마 정보 가져오기  
 반면는 **DataReader** 은 열려 가져오면 현재 결과 사용 하 여 집합에 대 한 스키마 정보는 **GetSchemaTable** 메서드. **GetSchemaTable** 반환는 <xref:System.Data.DataTable> 현재 결과 집합에 대 한 스키마 정보를 포함 하는 행과 열으로 채워진 개체입니다. **DataTable** 결과 집합의 각 열에 대해 하나의 행을 포함 합니다. 스키마 테이블 행의 각 열에 반환 된 열의 속성에 매핑됩니다 있는 결과 집합은 **ColumnName** 속성의 이름이 며 열의 값은 속성의 값입니다. 다음 코드 예제에 대 한 스키마 정보를 작성 **DataReader**합니다.  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>OLE DB 장 사용  
 계층적 행 집합 또는 장 (OLE DB 형식 **DBTYPE_HCHAPTER**, ADO 형식 **adChapter**)를 사용 하 여 검색할 수는 <xref:System.Data.OleDb.OleDbDataReader>합니다. 장을 포함 하는 쿼리로 반환 될 때는 **DataReader**에 있는 열으로 반환 되 **DataReader** 되어으로 노출 되는 **DataReader** 개체입니다.  
  
 ADO.NET **DataSet** 테이블 간의 부모-자식 관계를 사용 하 여 계층적 행 집합을 나타내는 데 사용할 수도 있습니다. 자세한 내용은 참조 [데이터 집합, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)합니다.  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Oracle REF CURSOR를 사용하여 결과 반환  
 .NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다. Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.  
  
 검색할 수 있습니다는 **OracleDataReader** 개체를 사용 하 여 Oracle REF CURSOR 나타내는 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 메서드를 지정할 수도 <xref:System.Data.OracleClient.OracleCommand> 으로 하나 이상의 Oracle REF Cursor를 반환 하는  **SelectCommand** 에 대 한 프로그램 <xref:System.Data.OracleClient.OracleDataAdapter> 채우는 데 사용 되는 <xref:System.Data.DataSet>합니다.  
  
 Oracle 데이터 원본에서 반환 된 REF CURSOR에 액세스 하려면 만듭니다는 **OracleCommand** 쿼리에 대 한 출력 매개 변수를 REF CURSOR를 참조 하는 추가 된 **매개 변수** 프로그램 의컬렉션 **OracleCommand**합니다. 매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다. 매개 변수의 유형을 설정 **OracleType.Cursor**합니다. **ExecuteReader** 방식의 프로그램 **OracleCommand** 돌아갑니다는 **OracleDataReader** REF CURSOR에 대 한 합니다.  
  
 경우에 **OracleCommand** 여러 multiple REF CURSOR를 반환 합니다. 여러 출력 매개 변수를 추가 합니다. 호출 하 여 서로 다른 REF Cursor에 액세스할 수 있습니다는 **OracleCommand.ExecuteReader** 메서드. 에 대 한 호출 **ExecuteReader** 반환는 **OracleDataReader** 첫 REF CURSOR를 참조 합니다. 호출할 수 있습니다는 **OracleDataReader.NextResult** 에 나오는 REF Cursor에 액세스할 수 있습니다. 하지만 매개 변수 여 **OracleCommand.Parameters** 컬렉션 REF CURSOR 출력 매개 변수 이름으로는 **OracleDataReader** 는 에추가된순서대로액세스 **매개 변수** 컬렉션입니다.  
  
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
  
 다음 코드에서는 **OracleCommand** 형식의 두 매개 변수를 추가 하 여 이전 Oracle 패키지에서 REF Cursor를 반환 하는 **OracleType.Cursor** 에 **매개변수** 컬렉션입니다.  
  
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
  
 사용 하 여 이전 명령의 결과 반환 하는 다음 코드는 **읽기** 및 **NextResult** 의 메서드는 **OracleDataReader**합니다. REF CURSOR 매개 변수가 순서대로 반환됩니다.  
  
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
  
 다음 예제에서는 이전 명령을 채우는 데 사용 하 여 한 **데이터 집합** Oracle 패키지의 결과입니다.  
  
> [!NOTE]
>  방지 하기 위해는 **OverflowException**, 모든에서 변환 Oracle NUMBER 형식 유효한.NET Framework 형식에 값을 저장 하기 전에 처리 하는 것이 좋습니다는 **DataRow**합니다. 사용할 수는 **FillError** 여부를 확인 하는 이벤트는 **OverflowException** 발생 했습니다. 대 한 자세한 내용은 **FillError** 이벤트 참조 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [DataReaders 작업](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Dataadapter 및 Datareader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
