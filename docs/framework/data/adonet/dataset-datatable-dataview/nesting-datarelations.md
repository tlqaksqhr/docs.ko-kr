---
title: "DataRelations 중첩 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataRelations 중첩
데이터의 관계형 표현에서 각 테이블에는 열이나 열 집합을 사용하여 서로 연결시키는 행이 포함되어 있습니다.  ADO.NET <xref:System.Data.DataSet>에서 각 테이블 사이의 관계는 <xref:System.Data.DataRelation>을 사용하여 구현됩니다.  **DataRelation**을 만들 때 열의 부모\-자식 관계는 관계를 통해서만 관리됩니다.  테이블과 열은 별개의 엔터티입니다.  XML에서 제공하는 데이터의 계층적 표현에서 부모\-자식 관계는 중첩된 자식 요소를 포함하는 부모 요소에 의해 표현됩니다.  
  
 **DataSet**이 <xref:System.Xml.XmlDataDocument>와 동기화되거나 **WriteXml**을 사용하여 XML 데이터로 작성될 때 자식 개체의 중첩을 쉽게 표현하기 위해 **DataRelation**은 **Nested** 속성을 노출합니다.  **DataRelation**의 **Nested** 속성을 **true**로 설정하면 해당 관계의 자식 행은 XML 데이터로 작성되거나 **XmlDataDocument**와 동기화될 때 부모 열 내에 중첩됩니다.  기본적으로 **DataRelation**의 **Nested** 속성은 **false**입니다.  
  
 예를 들어, 다음 **DataSet**을 고려하세요.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 **DataRelation** 개체의 **Nested** 속성이 이 **DataSet**에 대해 **true**로 설정되어 있지 않기 때문에 이 **DataSet**이 XML 데이터로 표현될 때 자식 개체가 부모 요소 내에 중첩되지 않습니다.  관련 **DataSet**을 포함하나 데이터 관계가 중첩되지 않은 **DataSet**의 XML 표현을 변환하면 성능이 느려질 수 있습니다.  데이터 관계를 중첩하는 것이 좋습니다.  이 작업을 수행하려면 **Nested** 속성을 **true**로 설정하세요.  그런 다음 XSLT 스타일시트에서 하향 계층 구조적인 XPath 쿼리 식을 사용하여 데이터를 찾고 변환하는 코드를 작성합니다.  
  
 다음 코드 예제에서는 **DataSet**에 **WriteXml**을 호출하여 나타나는 결과를 보여 줍니다.  
  
```  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 **Customers** 요소와 **Orders** 요소는 형제 요소로 나타납니다.  **Orders** 요소가 자신의 해당 부모 요소의 자식으로 나타나도록 만들려면 **DataRelation**의 **Nested** 속성을 **true**로 설정한 후 다음을 추가합니다.  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 다음 코드 예제에서는 결과로 나타나는 출력을 보여 줍니다. 여기서 **Orders** 요소는 자신의 해당 부모 요소 내에 중첩되어 있습니다.  
  
```  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## 참고 항목  
 [DataSet에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataRelations 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)