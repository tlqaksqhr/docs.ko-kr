---
title: "데이터 원본에서 데이터 업데이트"
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
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c83b137f0de5ee165d110706dc286d13a084427c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="updating-data-in-a-data-source"></a>데이터 원본에서 데이터 업데이트
INSERT, UPDATE 또는 DELETE와 같이 데이터를 수정하는 SQL 문은 행을 반환하지 않습니다. 마찬가지로 대부분의 저장 프로시저도 동작을 수행하기는 하지만 행을 반환하지는 않습니다. 행을 반환 하지 않는 명령을 실행 하려면 만듭니다는 **명령** 개체를 적절 한 SQL 명령으로는 및 **연결**를 비롯 한 모든 필수 **매개 변수**합니다. 사용 하 여 명령을 실행의 **ExecuteNonQuery** 의 메서드는 **명령** 개체입니다.  
  
 **ExecuteNonQuery** 메서드 문 또는 실행 된 저장된 프로시저에 영향을 받은 행 수를 나타내는 정수를 반환 합니다. 여러 문을 실행하는 경우 반환되는 값은 실행된 모든 문에 의해 영향을 받는 레코드의 합계입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 실행에 사용 하 여 데이터베이스 레코드를 삽입 하기 위해 INSERT 문을 **ExecuteNonQuery**합니다.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 다음 코드 예제에서는 샘플 코드에 의해 생성 된 저장된 프로시저 실행 [카탈로그 작업 수행](../../../../docs/framework/data/adonet/performing-catalog-operations.md)합니다. 저장된 프로시저에서 아무 행도 반환 하므로 **ExecuteNonQuery** 메서드는 사용 되지 않지만 저장된 프로시저에서 입력된 매개 변수를 수신 하 고 출력 매개 변수 및 반환 값을 반환 합니다.  
  
 에 대 한는 <xref:System.Data.OleDb.OleDbCommand> 개체는 **ReturnValue** 매개 변수를 추가 해야 합니다는 **매개 변수** 컬렉션 첫 번째입니다.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a>참고 항목  
 [명령을 사용하여 데이터 수정](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [DataAdapter로 데이터 원본 업데이트](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
