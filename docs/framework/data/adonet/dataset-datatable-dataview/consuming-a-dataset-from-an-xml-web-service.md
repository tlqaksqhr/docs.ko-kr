---
title: "XML Web Services에서 DataSet 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# XML Web Services에서 DataSet 사용
<xref:System.Data.DataSet>은 인터넷에서 데이터 전송을 쉽게 할 수 있도록 비연결 디자인으로 설계되었습니다.  **DataSet**은 XML Web services와 클라이언트 간에 **DataSet**의 내용을 스트리밍하기 위한 추가 코딩 없이도 XML Web services의 입력 또는 출력으로 지정될 수 있다는 점에서 "직렬화"합니다.  **DataSet**은 DiffGram 형식을 사용하여 암시적으로 XML 스트림으로 변환되어 네트워크를 통해 전송된 다음, XML 스트림에서 **DataSet**으로 수신자 쪽에서 다시 생성됩니다.  이렇게 하여 간단하고 융통성 있는 방법으로 XML Web services를 사용하여 관계형 데이터를 전송하고 반환할 수 있습니다.  DiffGram 형식에 대한 자세한 내용은 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)를 참조하세요.  
  
 다음 예제에서는 **DataSet**을 사용하여 관계형 데이터 및 해당 데이터의 수정 내용을 전송하고 모든 업데이트를 원본 데이터 소스에 다시 적용하는 XML Web services 및 클라이언트를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  XML Web services를 만들 때는 항상 보안 측면을 고려하는 것이 좋습니다.  XML Web services 보안에 대한 자세한 내용은 [Securing XML Web Services Created Using ASP.NET](http://msdn.microsoft.com/ko-kr/354b2ab1-2782-4542-b32a-dc560178b90c)을 참조하세요.  
  
### DataSet을 반환하고 사용하는 XML Web services를 만들려면  
  
1.  XML Web services를 만듭니다.  
  
     아래의 예제에서 만들어지는 XML Web services는 데이터를 반환\(이 경우 **Northwind** 데이터베이스의 고객 목록\)하고 데이터가 업데이트된 **DataSet**을 수신하여 업데이트를 원본 데이터 소스에 적용합니다.  
  
     XML Web services는 두 개의 메서드를 사용하는데, **GetCustomers** 메서드로는 고객 목록을 반환하고 **UpdateCustomers** 메서드로는 업데이트를 데이터 소스에 적용합니다.  XML Web services는 웹 서버에 있는 DataSetSample.asmx라는 파일로 저장됩니다.  다음 코드는 DataSetSample.asmx의 내용을 요약한 것입니다.  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     일반적인 시나리오에서는 **UpdateCustomers** 메서드를 작성하여 낙관적 동시성 위반을 캐치하지만,  위의 예제에서는 내용을 간단하게 하기 위해 제외되었습니다.  낙관적 동시성에 대한 자세한 내용은 [낙관적 동시성](../../../../../docs/framework/data/adonet/optimistic-concurrency.md)를 참조하세요.  
  
2.  XML Web services 프록시를 만듭니다.  
  
     XML Web services의 클라이언트는 SOAP 프록시가 있어야 노출된 메서드를 사용할 수 있습니다.  Visual Studio로 이 프록시를 생성할 수 있습니다.  웹 참조를 Visual Studio 내의 기존 웹 서비스로 설정하면 이 단계에 기술된 모든 동작이 투명하게 일어납니다.  프록시 클래스를 직접 만들려면 추가 설명이 필요합니다.  그러나 대부분의 경우에는 Visual Studio를 사용하여 클라이언트 응용 프로그램용 프록시 클래스를 만드는 것으로 충분합니다.  
  
     프록시는 웹 서비스 설명 언어 도구를 사용하여 만들 수 있습니다.  예를 들어, XML Web services가 http:\/\/myserver\/data\/DataSetSample.asmx라는 URL에 있는 경우 다음과 같은 명령을 실행하여 네임스페이스가 **WebData.DSSample**인 Visual Basic .NET 프록시를 만들어 sample.vb 파일에 저장합니다.  
  
    ```  
    wsdl /l:VB /out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     다음 명령을 실행하면 sample.cs에 C\# 프록시를 만들 수 있습니다.  
  
    ```  
    wsdl /l:CS /out:sample.cs http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     그런 다음 프록시를 라이브러리로 컴파일하여 XML Web services 클라이언트에 가져올 수 있습니다.  다음 명령을 실행하면 sample.vb에 저장된 Visual Basic .NET 프록시 코드를 sample.dll로 컴파일할 수 있습니다.  
  
    ```  
    vbc /t:library /out:sample.dll sample.vb /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
     다음 명령을 실행하면 sample.cs에 저장된 C\# 프록시 코드를 sample.dll로 컴파일할 수 있습니다.  
  
    ```  
    csc /t:library /out:sample.dll sample.cs /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
3.  XML Web services 클라이언트를 만듭니다.  
  
     Visual Studio를 사용하여 웹 서비스 프록시 클래스를 생성하려면 클라이언트 프로젝트를 만들고 솔루션 탐색기 창에서 해당 프로젝트를 마우스 오른쪽 단추로 클릭하고 **웹 참조 추가**를 클릭한 다음 사용 가능한 웹 서비스 목록에서 웹 서비스를 선택합니다. 웹 서비스를 현재 솔루션 또는 현재 컴퓨터에서 사용할 수 없는 경우 웹 서비스 끝점 주소를 제공해야 합니다. 이전 단계의 설명에 따라 XML Web services 프록시를 직접 만드는 경우 프록시를 클라이언트 코드에 가져와 XML Web services 메서드를 사용합니다.  다음 샘플 코드에서는 프록시 라이브러리를 가져오고 **GetCustomers**를 호출하여 고객 목록을 가져오며, 새 고객을 추가한 다음 **UpdateCustomers**의 업데이트가 들어 있는 **DataSet**을 반환합니다.  
  
     수정된 행만 **UpdateCustomers**에 전달하면 되므로, 이 예제에서는 **DataSet.GetChanges**에서 반환한 **DataSet**을 **UpdateCustomers**에 전달합니다.  **UpdateCustomers**는 적용된 **DataSet**을 반환하며, 사용자는 이를 기존 **DataSet**에 **Merge**하여 업데이트에서 적용된 변경 내용 및 모든 행 오류 정보를 통합할 수 있습니다.  다음 코드에서는 Visual Studio를 사용하여 웹 참조를 만들고 **웹 참조 추가** 대화 상자에서 웹 참조의 이름을 DsSample로 바꾼 것으로 가정합니다.  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =   
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     프록시 클래스를 직접 만드는 경우 다음 추가 단계를 수행해야 합니다.  샘플을 컴파일하려면 앞에서 만든 프록시 라이브러리\(sample.dll\)와 관련 .NET 라이브러리를 제공합니다.  다음 명령을 실행하면 client.vb 파일에 저장된 샘플의 Visual Basic .NET 버전을 컴파일할 수 있습니다.  
  
    ```  
    vbc client.vb /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
     다음 명령을 실행하면 client.cs 파일에 저장된 샘플의 C\# 버전을 컴파일할 수 있습니다.  
  
    ```  
    csc client.cs /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
## 참고 항목  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [DataAdapters를 사용하여 데이터 소스 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)   
 [DataAdapter 매개 변수](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)   
 [Web Services Description Language Tool \(Wsdl.exe\)](http://msdn.microsoft.com/ko-kr/b9210348-8bc2-4367-8c91-d1a04b403e88)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)