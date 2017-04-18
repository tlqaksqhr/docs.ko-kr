---
title: "DataViews 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataViews 관리
<xref:System.Data.DataViewManager>를 사용하여 <xref:System.Data.DataView>의 모든 테이블에 대한 뷰 설정을 관리할 수 있습니다.  관계를 탐색하는 표와 같이 여러 테이블에 바인딩할 컨트롤이 있는 경우에는 **DataViewManager**가 가장 적합합니다.  
  
 **DataViewManager**에는 <xref:System.Data.DataSet>의 테이블에 대한 뷰 설정에 사용되는 <xref:System.Data.DataViewSetting> 개체의 컬렉션이 있습니다.  <xref:System.Data.DataViewSettingCollection>에는 **DataSet**의 각 테이블에 대해 하나의 <xref:System.Data.DataViewSetting> 개체가 있습니다.  **DataViewSetting**을 사용하면 참조된 테이블의 기본 **ApplyDefaultSort**, **Sort**, **RowFilter** 및 **RowStateFilter** 속성을 설정할 수 있습니다.  이름 또는 서수 참조별로 또는 해당 특정 테이블 개체에 대한 참조를 전달하여 특정 테이블에 대한 **DataViewSetting**을 참조할 수 있습니다.  또한 **DataViewSettings** 속성을 사용하면 **DataViewManager**에 있는 **DataViewSetting** 개체의 컬렉션에 액세스할 수 있습니다.  
  
 다음 코드 예제에서는 SQL Server **Northwind** 데이터베이스의 **Customers**, **Orders** 및 **Order Details** 테이블로 **DataSet**을 채우고, 이들 테이블 간에 관계를 만들며, **DataViewManager**를 사용하여 기본 **DataView** 설정을 구성하고, **DataViewManager**에 **DataGrid**를 바인딩합니다.  이 예제에서는 **DataSet**의 모든 테이블에 대한 기본 **DataView** 설정을 기본 키에 따라 정렬하도록 구성한 다음\(**ApplyDefaultSort** \= **true**\), **Customers** 테이블의 정렬 순서를 수정하여 **CompanyName**에 따라 정렬합니다.  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## 참고 항목  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataViewManager>   
 <xref:System.Data.DataViewSetting>   
 <xref:System.Data.DataViewSettingCollection>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)