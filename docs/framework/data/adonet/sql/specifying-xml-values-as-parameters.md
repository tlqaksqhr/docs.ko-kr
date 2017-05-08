---
title: "XML 값을 명령 매개 변수로 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2c4d08b8-fc29-4614-97fa-29c8ff7ca5b3
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# XML 값을 명령 매개 변수로 지정
쿼리에 값이 XML 문자열인 매개 변수가 필요한 경우 개발자는 **SqlXml** 데이터 형식의 인스턴스를 사용하여 이 값을 제공할 수 있습니다.  여기에 까다로운 기법이 적용되는 것은 아니며 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 XML 열은 다른 데이터 형식과 똑같은 방법으로 매개 변수 값을 받아들입니다.  
  
## 예제  
 다음 콘솔 응용 프로그램에서는 **AdventureWorks** 데이터베이스에 새 테이블을 만듭니다.  이 새 테이블에는 **SalesID**라는 열과 **SalesInfo**라는 XML 열이 포함되어 있습니다.  
  
> [!NOTE]
>  **AdventureWorks** 샘플 데이터베이스는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]를 설치할 때 기본적으로 설치되지 않으며  SQL Server 설치 프로그램을 실행하여 설치할 수 있습니다.  
  
 이 예제에서는 <xref:System.Data.SqlClient.SqlCommand> 개체를 통해 새 테이블에 행을 삽입하도록 준비합니다.  저장된 파일에서는 **SalesInfo** 열에 필요한 XML 데이터를 제공합니다.  
  
 예제를 실행시키는 데 필요한 파일을 만들려면 프로젝트와 동일한 폴더에 새 텍스트 파일을 만듭니다.  파일의 이름을 MyTestStoreData.xml로 지정하고  파일을 메모장에서 연 후 다음 텍스트를 복사하여 붙여 넣습니다.  
  
```  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>International Bank</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1970</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>7000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>T1</Internet>  
  <NumberEmployees>2</NumberEmployees>  
</StoreSurvey>  
```  
  
 \[Visual Basic\]  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Xml  
  
Module Module1  
    Sub Main()  
  
        Using connection As SqlConnection = New SqlConnection(GetConnectionString())  
        connection.Open()  
  
        ' Create a sample table (dropping first if it already  
        ' exists.)  
        Dim commandNewTable As String = _  
         "IF EXISTS (SELECT * FROM dbo.sysobjects " & _  
         "WHERE id = object_id(N'[dbo].[XmlDataTypeSample]') " & _  
         "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " & _  
         "DROP TABLE [dbo].[XmlDataTypeSample];" & _  
         "CREATE TABLE [dbo].[XmlDataTypeSample](" & _  
         "[SalesID] [int] IDENTITY(1,1) NOT NULL, " & _  
         "[SalesInfo] [xml])"  
  
        Dim commandAdd As New _  
         SqlCommand(commandNewTable, connection)  
        commandAdd.ExecuteNonQuery()  
  
        Dim commandText As String = _  
         "INSERT INTO [dbo].[XmlDataTypeSample] " & _  
           "([SalesInfo] ) " & _  
           "VALUES(@xmlParameter )"  
  
        Dim command As New SqlCommand(commandText, connection)  
  
        ' Read the saved XML document as a   
        ' SqlXml-data typed variable.  
        Dim newXml As SqlXml = _  
         New SqlXml(New XmlTextReader("MyTestStoreData.xml"))  
  
        ' Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml)  
  
        Dim result As Integer = command.ExecuteNonQuery()  
        Console.WriteLine(result & " row was added.")  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Using  
End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks"  
    End Function  
End Module  
```  
  
 \[C\#\]  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Xml;  
using System.Data.SqlTypes;  
  
class Class1  
{  
    static void Main()  
    {  
        using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
       {  
        connection.Open();  
        //  Create a sample table (dropping first if it already  
        //  exists.)  
  
        string commandNewTable =   
            "IF EXISTS (SELECT * FROM dbo.sysobjects " +   
            "WHERE id = " +  
                  "object_id(N'[dbo].[XmlDataTypeSample]') " +   
            "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " +   
            "DROP TABLE [dbo].[XmlDataTypeSample];" +   
            "CREATE TABLE [dbo].[XmlDataTypeSample](" +   
            "[SalesID] [int] IDENTITY(1,1) NOT NULL, " +   
            "[SalesInfo] [xml])";  
        SqlCommand commandAdd =   
                   new SqlCommand(commandNewTable, connection);  
        commandAdd.ExecuteNonQuery();  
        string commandText =   
            "INSERT INTO [dbo].[XmlDataTypeSample] " +   
            "([SalesInfo] ) " +   
            "VALUES(@xmlParameter )";  
        SqlCommand command =   
                  new SqlCommand(commandText, connection);  
  
        //  Read the saved XML document as a   
        //  SqlXml-data typed variable.  
        SqlXml newXml =   
            new SqlXml(new XmlTextReader("MyTestStoreData.xml"));  
  
        //  Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml);  
  
        int result = command.ExecuteNonQuery();  
        Console.WriteLine(result + " row was added.");  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,              
        // you can retrieve it from a configuration file.   
        return "Data Source=(local);Integrated Security=true;" +  
        "Initial Catalog=AdventureWorks; ";  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Data.SqlTypes.SqlXml>   
 [SQL Server의 XML 데이터](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)