---
title: "DataSet 내용 복사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# DataSet 내용 복사
<xref:System.Data.DataSet>의 복사본을 만들어 원래 데이터에는 영향을 주지 않고 데이터로 작업하거나 **DataSet**에 들어 있는 데이터의 하위 집합으로 작업할 수 있습니다.  **DataSet**을 복사하면 다음 작업을 수행할 수 있습니다.  
  
-   스키마, 데이터, 행 상태 정보 및 행 버전을 포함하여 **DataSet**과 똑같은 복사본을 만듭니다.  
  
-   기존 **DataSet**의 스키마는 포함하지만 수정된 행만 포함하는 **DataSet**을 만듭니다.  수정된 모든 행을 반환하거나 특정 **DataRowState**를 지정할 수 있습니다.  행 상태에 대한 자세한 내용은 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)을 참조하세요.  
  
-   행은 복사하지 않고 **DataSet**의 스키마나 관계형 구조만 복사합니다.  <xref:System.Data.DataTable.ImportRow%2A>를 사용하여 행을 기존 <xref:System.Data.DataTable>로 가져올 수 있습니다.  
  
 스키마와 데이터가 모두 포함된 **DataSet**과 동일한 복사본을 만들려면 **DataSet**의 <xref:System.Data.DataSet.Copy%2A> 메서드를 사용합니다.  다음 코드 예제에서는 **DataSet**과 동일한 복사본을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 스키마와 **Added**, **Modified** 또는 **Deleted** 행을 나타내는 데이터만 포함된 **DataSet**의 복사본을 만들려면 **DataSet**의 <xref:System.Data.DataSet.GetChanges%2A> 메서드를 사용합니다.  또한 **GetChanges**를 사용하여 **GetChanges**를 호출할 때 **DataRowState** 값을 전달하여 지정한 행 상태의 행만 반환할 수 있습니다.  다음 코드 예제에서는 **GetChanges**를 호출할 때 **DataRowState**를 전달하는 방법을 보여 줍니다.  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 스키마만 포함하는 **DataSet**의 복사본을 만들려면 **DataSet**의 <xref:System.Data.DataSet.Clone%2A> 메서드를 사용합니다.  **DataTable**의 **ImportRow** 메서드를 사용하여 기존 행을 복제된 **DataSet**에 추가할 수도 있습니다.  **ImportRow**는 데이터, 행 상태 및 행 버전 정보를 지정한 테이블에 추가합니다.  열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.  
  
 다음 코드 예제에서는 **DataSet**의 복제를 만든 다음 원래 **DataSet**의 행을 **CountryRegion** 열 값이 "Germany"인 고객의 **DataSet** 복제에 있는 **Customers** 테이블에 추가합니다.  
  
```vb  
  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## 참고 항목  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)