---
title: "ADO.NET 코드 예제 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# ADO.NET 코드 예제
이 항목에 나열된 코드에서는 다음과 같은 ADO.NET 기술을 사용하여 데이터베이스에서 데이터를 검색하는 방법을 보여 줍니다.  
  
-   ADO.NET 데이터 공급자  
  
    -   [SqlClient](#_SqlClient) (`System.Data.SqlClient`)  
  
    -   [OleDb](#_OleDb) (`System.Data.OleDb`)  
  
    -   [Odbc](#_Odbc) (`System.Data.Odbc`)  
  
    -   [OracleClient](#_OracleClient) (`System.Data.OracleClient`)  
  
-   ADO.NET Entity Framework:  
  
    -   [LINQ to Entities](#_LINQ)  
  
    -   [형식화 된 ObjectQuery](#_QBM)  
  
    -   [EntityClient](#_EntityClient) (`System.Data.EntityClient`)  
  
-   [LINQ to SQL](#_LINQ2SQL)  
  
## <a name="adonet-data-provider-examples"></a>ADO.NET 데이터 공급자 예제  
 다음에 나열된 코드에서는 ADO.NET 데이터 공급자를 사용하여 데이터베이스에서 데이터를 검색하는 방법을 보여 줍니다. 데이터는 `DataReader`에서 반환됩니다. 자세한 내용은 참조 [DataReader를 사용 하 여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)합니다.  
  
<a name="_SqlClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 이 예제 코드에서는 Microsoft `Northwind`에서 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 샘플 데이터베이스에 연결할 수 있다고 가정합니다. 코드를 만듭니다는 <xref:System.Data.SqlClient.SqlCommand> Products 테이블에서 행을 선택 추가 <xref:System.Data.SqlClient.SqlParameter> 여 UnitPrice 지정한 매개 변수 값이 경우 5 보다 큰을 가진 행을 결과 제한할 수 있습니다. <xref:System.Data.SqlClient.SqlConnection> 내부에 열릴는 `using` 리소스가 닫히고 삭제 코드가 종료 될 때 블록입니다. 코드를 사용 하 여 명령을 실행 한 <xref:System.Data.SqlClient.SqlDataReader>, 콘솔 창에 결과 표시 합니다.  
  
  [DataWorks SampleApp.SqlClient#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient#1)]  
  
 [[Top]](#_TOP)  
  
<a name="_OleDb"></a>   
### <a name="oledb"></a>OleDb  
 이 예제 코드에서는 Microsoft Access Northwind 샘플 데이터베이스에 연결할 수 있다고 가정합니다. 코드를 만듭니다를 <xref:System.Data.OleDb.OleDbCommand> Products 테이블에서 행을 선택 추가 <xref:System.Data.OleDb.OleDbParameter> 여 UnitPrice 지정한 매개 변수 값이 경우 5 보다 큰을 가진 행을 결과 제한할 수 있습니다. <xref:System.Data.OleDb.OleDbConnection> 내부에 열릴는 `using` 리소스가 닫히고 삭제 코드가 종료 될 때 블록입니다. 코드를 사용 하 여 명령을 실행 한 <xref:System.Data.OleDb.OleDbDataReader>, 콘솔 창에 결과 표시 합니다.  
  
  [DataWorks SampleApp.OleDb#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb#1)]  
  
 [[Top]](#_TOP)  
  
<a name="_Odbc"></a>   
### <a name="odbc"></a>Odbc  
 이 예제 코드에서는 Microsoft Access Northwind 샘플 데이터베이스에 연결할 수 있다고 가정합니다. 코드를 만듭니다를 <xref:System.Data.Odbc.OdbcCommand> Products 테이블에서 행을 선택 추가 <xref:System.Data.Odbc.OdbcParameter> 여 UnitPrice 지정한 매개 변수 값이 경우 5 보다 큰을 가진 행을 결과 제한할 수 있습니다. <xref:System.Data.Odbc.OdbcConnection> 내부에 열릴는 `using` 리소스가 닫히고 삭제 코드가 종료 될 때 블록입니다. 사용 하 여 명령을 실행 한 <xref:System.Data.Odbc.OdbcDataReader>, 콘솔 창에 결과 표시 합니다.  
  
<!-- TODO: review snippet reference  [!CODE [DataWorksSampleApp.Odbc#1](DataWorksSampleApp.Odbc#1)]  -->  
  
 [[Top]](#_TOP)  
  
<a name="_OracleClient"></a>   
### <a name="oracleclient"></a>OracleClient  
 이 예제 코드에서는 Oracle 서버에서 DEMO.CUSTOMER에 연결할 수 있다고 가정합니다. 또한 System.Data.OracleClient.dll에 대한 참조를 추가해야 합니다. 에 데이터를 반환 하는 코드는 <xref:System.Data.OracleClient.OracleDataReader>합니다.  
  
  [DataWorks SampleApp.Oracle#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle#1)]  
  
 [[Top]](#_TOP)  
  
## <a name="entity-framework-examples"></a>Entity Framework 예제  
 다음에 나열된 코드에서는 EDM(엔터티 데이터 모델)의 엔터티를 쿼리하여 데이터 소스에서 데이터를 검색하는 방법을 보여 줍니다. 이 예제에서는 사용 된 [Northwind 모델](http://msdn.microsoft.com/ko-kr/74521f8c-e974-48cb-8858-c08deff52638)합니다. 자세한 내용은 참조 [Entity Framework 개요](../../../../docs/framework/data/adonet/ef/overview.md)합니다.  
  
<a name="_LINQ"></a>   
### <a name="linq-to-entities"></a>LINQ to Entities  
 이 예제 코드에서는 LINQ 쿼리를 사용하여 CategoryID와 CategoryName 속성만 포함된 익명 형식으로 프로젝션된 Categories 개체로 데이터를 반환합니다. 자세한 내용은 참조 [LINQ to Entities 개요](http://msdn.microsoft.com/ko-kr/86d87a27-c17a-45ac-b28d-72c8500333c6)합니다.  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Linq  
Imports System.Data.Objects  
Imports NorthwindModel  
  
Class LinqSample  
    Public Shared Sub ExecuteQuery()  
        Using context As NorthwindEntities = New NorthwindEntities()  
            Try  
                Dim query = From category In context.Categories _  
                            Select New With _  
                            { _  
                                .categoryID = category.CategoryID, _  
                                .categoryName = category.CategoryName _  
                            }  
  
                For Each categoryInfo In query  
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                        categoryInfo.categoryID, categoryInfo.categoryName)  
                Next  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
        End Using  
    End Sub  
End Class  
```  
  
 C#:  
  
```  
using System;  
using System.Linq;  
using System.Data.Objects;  
using NorthwindModel;  
  
class LinqSample  
{  
    public static void ExecuteQuery()  
    {  
        using (NorthwindEntities context = new NorthwindEntities())  
        {  
            try  
            {  
                var query = from category in context.Categories  
                            select new  
                            {  
                                categoryID = category.CategoryID,  
                                categoryName = category.CategoryName  
                            };  
  
                foreach (var categoryInfo in query)  
                {  
                    Console.WriteLine("\t{0}\t{1}",  
                        categoryInfo.categoryID, categoryInfo.categoryName);  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
 [[Top]](#_TOP)  
  
<a name="_QBM"></a>   
### <a name="typed-objectquery"></a>형식화된 ObjectQuery  
 이 예제의 코드를 사용 하는 <xref:System.Data.Objects.ObjectQuery%601> Categories 개체로 데이터를 반환 합니다. 자세한 내용은 참조 [개체 쿼리](http://msdn.microsoft.com/ko-kr/0768033c-876f-471d-85d5-264884349276)합니다.  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Objects  
Imports NorthwindModel  
  
Class ObjectQuerySample  
    Public Shared Sub ExecuteQuery()  
        Using context As NorthwindEntities = New NorthwindEntities()  
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories  
  
            For Each category As Categories In _  
                categoryQuery.Execute(MergeOption.AppendOnly)  
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                    category.CategoryID, category.CategoryName)  
            Next  
        End Using  
    End Sub  
End Class  
```  
  
 C#:  
  
```  
using System;  
using System.Data.Objects;  
using NorthwindModel;  
  
class ObjectQuerySample  
{  
    public static void ExecuteQuery()  
    {  
        using (NorthwindEntities context = new NorthwindEntities())  
        {  
            ObjectQuery<Categories> categoryQuery = context.Categories;  
  
            foreach (Categories category in   
                categoryQuery.Execute(MergeOption.AppendOnly))  
            {  
                Console.WriteLine("\t{0}\t{1}",  
                    category.CategoryID, category.CategoryName);  
            }  
        }  
    }  
}  
```  
  
 [[Top]](#_TOP)  
  
<a name="_EntityClient"></a>   
### <a name="entityclient"></a>EntityClient  
 이 예제의 코드를 사용 하는 <xref:System.Data.EntityClient.EntityCommand> Entity SQL 쿼리를 실행 합니다. 이 쿼리는 Categories 엔터티 형식의 인스턴스를 나타내는 레코드 목록을 반환합니다. <xref:System.Data.EntityClient.EntityDataReader> 결과 집합의 데이터 레코드에 액세스 하는 데 사용 됩니다. 자세한 내용은 참조 [Entity Framework 용 EntityClient 공급자](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data  
Imports System.Data.Common  
Imports System.Data.EntityClient  
Imports NorthwindModel  
  
Class EntityClientSample  
    Public Shared Sub ExecuteQuery()  
        Dim queryString As String = _  
            "SELECT c.CategoryID, c.CategoryName " & _  
                "FROM NorthwindEntities.Categories AS c"  
  
        Using conn As EntityConnection = _  
            New EntityConnection("name=NorthwindEntities")  
  
            Try  
                conn.Open()  
                Using query As EntityCommand = _  
                New EntityCommand(queryString, conn)  
                    Using rdr As DbDataReader = _  
                        query.ExecuteReader(CommandBehavior.SequentialAccess)  
                        While rdr.Read()  
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                                              rdr(0), rdr(1))  
                        End While  
                    End Using  
                End Using  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
        End Using   
    End Sub  
End Class  
```  
  
 C#:  
  
```  
using System;  
using System.Data;  
using System.Data.Common;  
using System.Data.EntityClient;  
using NorthwindModel;  
  
class EntityClientSample  
{  
    public static void ExecuteQuery()  
    {  
        string queryString =  
            @"SELECT c.CategoryID, c.CategoryName   
                FROM NorthwindEntities.Categories AS c";  
  
        using (EntityConnection conn =  
            new EntityConnection("name=NorthwindEntities"))  
        {  
            try  
            {  
                conn.Open();  
                using (EntityCommand query = new EntityCommand(queryString, conn))  
                {  
                    using (DbDataReader rdr =   
                        query.ExecuteReader(CommandBehavior.SequentialAccess))  
                    {  
                        while (rdr.Read())  
                        {  
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);  
                        }  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
 [[Top]](#_TOP)  
  
<a name="_LINQ2SQL"></a>   
## <a name="linq-to-sql"></a>LINQ to SQL  
 이 예제 코드에서는 LINQ 쿼리를 사용하여 CategoryID와 CategoryName 속성만 포함된 익명 형식으로 프로젝션된 Categories 개체로 데이터를 반환합니다. 이 예제는 Northwind 데이터 컨텍스트를 기반으로 합니다. 자세한 내용은 참조 [시작](../../../../docs/framework/data/adonet/sql/linq/getting-started.md)합니다.  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports Northwind  
  
Class LinqSqlSample  
    Public Shared Sub ExecuteQuery()  
        Using db As NorthwindDataContext = New NorthwindDataContext()  
            Try  
                Dim query = From category In db.Categories _  
                                Select New With _  
                                { _  
                                    .categoryID = category.CategoryID, _  
                                    .categoryName = category.CategoryName _  
                                }  
  
                For Each categoryInfo In query  
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _  
                            categoryInfo.categoryID, categoryInfo.categoryName)  
                Next  
            Catch ex As Exception  
                Console.WriteLine(ex.Message)  
            End Try  
            End Using   
    End Sub  
End Class  
```  
  
 C#:  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Northwind;  
  
    class LinqSqlSample  
    {  
        public static void ExecuteQuery()  
        {  
            using (NorthwindDataContext db = new NorthwindDataContext())  
            {  
                try  
                {  
                    var query = from category in db.Categories  
                                select new  
                                {  
                                    categoryID = category.CategoryID,  
                                    categoryName = category.CategoryName  
                                };  
  
                    foreach (var categoryInfo in query)  
                    {  
                        Console.WriteLine("vbTab {0} vbTab {1}",  
                            categoryInfo.categoryID, categoryInfo.categoryName);  
                    }  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex.Message);  
                }  
            }  
        }  
    }  
```  
  
 [[Top]](#_TOP)  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [데이터 응용 프로그램 만들기](../Topic/Creating%20Data%20Applications.md)   
 [엔터티 데이터 모델 (Entity Framework 작업) 쿼리](http://msdn.microsoft.com/ko-kr/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)   
 [방법: 익명 형식 개체를 반환 하는 쿼리 실행](http://msdn.microsoft.com/ko-kr/3b264025-e911-4d73-90ce-992d2b9d189d)   
 [ADO.NET 관리 되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)