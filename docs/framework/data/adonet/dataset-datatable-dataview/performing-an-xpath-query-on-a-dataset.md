---
title: "DataSet에 XPath 쿼리 수행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet에 XPath 쿼리 수행
동기화된 <xref:System.Data.DataSet> 및 <xref:System.Xml.XmlDataDocument> 간의 관계를 통해 XPath\(XML Path Language\) 쿼리와 같은 XML 서비스를 사용할 수 있습니다. 이 서비스를 통해 **XmlDataDocument**에 액세스하고 **DataSet**을 직접 액세스할 때보다 더 편리하게 특정 기능을 수행할 수 있습니다.  예를 들어, <xref:System.Data.DataTable>의 **Select** 메서드를 사용하여 **DataSet**의 다른 테이블에 대한 관계를 탐색하는 대신 **DataSet**과 동기화된 **XmlDataDocument**에 XPath 쿼리를 수행하여 <xref:System.Xml.XmlNodeList> 형태의 XML 요소 목록을 얻을 수 있습니다.  <xref:System.Xml.XmlElement> 노드로 캐스팅되는 **XmlNodeList**의 노드는 **XmlDataDocument**의 **GetRowFromElement** 메서드로 전달되어 동기화된 **DataSet** 내의 테이블 행에 대해 일치하는 <xref:System.Data.DataRow> 참조를 반환할 수 있습니다.  
  
 예를 들어, 다음 코드 샘플에서는 "최하위" XPath 쿼리를 수행합니다.  **DataSet**은 **Customers**, **Orders** 및 **OrderDetails** 등 세 개의 테이블로 채워집니다.  이 예제에서 부모\-자식 관계는 먼저 **Customers** 및 **Orders** 테이블 사이에 만들어진 다음 **Orders** 및 **OrderDetails** 테이블 사이에 만들어집니다.  그런 다음 XPath 쿼리가 수행되어 최하위 **OrderDetails** 노드가 값이 43인 **ProductID** 노드를 갖는 **Customers** 노드의 **XmlNodeList**를 반환합니다.  기본적으로 이 예제에서는 XPath 쿼리를 사용하여 **ProductID**가 43인 제품을 주문한 고객을 확인합니다.  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## 참고 항목  
 [DataSet 및 XmlDataDocument 동기화](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)