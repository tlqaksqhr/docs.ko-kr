---
title: "DataRelation 중첩"
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
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db7df753bf6066d3a89c46a82b66e47281076f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nesting-datarelations"></a>DataRelation 중첩
데이터의 관계형 표현에서 각 테이블에는 열이나 열 집합을 사용하여 서로 연결시키는 행이 포함되어 있습니다. ADO.NET <xref:System.Data.DataSet>에서 각 테이블 사이의 관계는 <xref:System.Data.DataRelation>을 사용하여 구현됩니다. 만들 때 한 **DataRelation**, 열의 부모-자식 관계는 관계를 통해서만 관리 됩니다. 테이블과 열은 별개의 엔터티입니다. XML에서 제공하는 데이터의 계층적 표현에서 부모-자식 관계는 중첩된 자식 요소를 포함하는 부모 요소에 의해 표현됩니다.  
  
 자식 개체의 중첩을 용이 하 게 하려면 때는 **DataSet** 와 동기화 되는 <xref:System.Xml.XmlDataDocument> 사용 하 여 XML 데이터로 작성 또는 **WriteXml**, **DataRelation** 노출 된 **Nested** 속성입니다. 설정의 **중첩** 속성은 **DataRelation** 를 **true** 하면 자식 XML 데이터로 작성 될 때 부모 열 내에 중첩 될 해당 관계의 행은 또는 와 동기화는 **XmlDataDocument**합니다. **Nested** 의 속성은 **DataRelation** 은 **false**, 기본적으로 합니다.  
  
 예를 들어, 다음 사항을 고려 **DataSet**합니다.  
  
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
  
 때문에 **중첩** 의 속성은 **DataRelation** 개체로 설정 되지 않은 **true** 이 **데이터 집합**, 자식 개체는 서로 일치 하지 부모 요소에 있는 경우이 **데이터 집합** XML 데이터로 표현 합니다. XML 표현을 변형 한 **데이터 집합** 포함 된 관련 **데이터 집합**중첩 되지 않은 데이터의 성능이 저하 될 수 있습니다. 데이터 관계를 중첩하는 것이 좋습니다. 이 위해 설정 된 **Nested** 속성을 **true**합니다. 그런 다음 XSLT 스타일시트에서 하향 계층 구조적인 XPath 쿼리 식을 사용하여 데이터를 찾고 변형하는 코드를 작성합니다.  
  
 다음 코드 예제에서는 호출의 결과로 **WriteXml** 에 **DataSet**합니다.  
  
```xml  
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
  
 **고객** 요소 및 **Orders** 요소는 형제 요소로 표시 됩니다. 필요한 경우는 **Orders** 자신의 해당 부모 요소의 자식으로 표시 하는 요소는 **Nested** 속성의는 **DataRelation** 로설정해야합니다**true** 다음을 추가 합니다.  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 다음 코드 보여 결과 출력은와 **Orders** 요소가 자신의 해당 부모 요소를 중첩 합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataRelation 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
