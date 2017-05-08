---
title: "GetSchema 및 스키마 컬렉션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# GetSchema 및 스키마 컬렉션
각 .NET Framework 관리 공급자의 **Connection** 클래스는 현재 연결된 데이터베이스에 대한 스키마 정보를 검색하는 데 사용되는 **GetSchema** 메서드를 구현하며 **GetSchema** 메서드에서 반환된 스키마 정보는 <xref:System.Data.DataTable> 형식으로 제공됩니다.  **GetSchema** 메서드는 스키마 컬렉션이 반환되도록 지정하고 반환되는 정보의 양을 제한하기 위한 선택적 매개 변수를 제공하는 오버로드 메서드입니다.  
  
## 스키마 컬렉션 지정  
 **GetSchema** 메서드의 첫 번째 선택적 매개 변수는 문자열로 지정되는 컬렉션 이름입니다.  스키마 컬렉션에는 모든 공급자에 공통되는 공통 스키마 컬렉션과 공급자마다 다른 특정 스키마 컬렉션의 두 가지 유형이 있습니다.  
  
 .NET Framework 관리 공급자를 쿼리하여 **GetSchema** 메서드를 인수 없이, 또는 "MetaDataCollections"라는 스키마 컬렉션으로 호출함으로써 지원되는 스키마 컬렉션의 목록을 확인할 수 있습니다.  그러면 지원되는 스키마 컬렉션의 목록, 각자 지원하는 제약 조건 수 및 사용하는 식별자 부분 수가 포함된 <xref:System.Data.DataTable>이 반환됩니다.  
  
### 스키마 컬렉션 검색 예제  
 다음 예제에서는 .NET Framework Data Provider for SQL Server <xref:System.Data.SqlClient.SqlConnection> 클래스의 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 메서드를 사용하여 **AdventureWorks** 샘플 데이터베이스에 포함된 모든 테이블에 대한 스키마 정보를 검색하는 방법을 보여 줍니다.  
  
 \[Visual Basic\]  
  
```  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
 \[C\#\]  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## 참고 항목  
 [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)