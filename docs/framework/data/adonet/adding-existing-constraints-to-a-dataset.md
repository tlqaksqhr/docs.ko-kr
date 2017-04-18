---
title: "DataSet에 기존 제약 조건 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet에 기존 제약 조건 추가
**DataAdapter**의 **Fill** 메서드는 데이터 소스의 테이블 열과 행으로만 <xref:System.Data.DataSet>을 채웁니다. 제약 조건은 일반적으로 데이터 소스에서 설정하지만 **Fill** 메서드는 기본적으로 이 스키마 정보를 **DataSet**에 추가하지 않습니다.  데이터 소스의 기존 기본 키 제약 조건 정보로 **DataSet**을 채우려면 **DataAdapter**의 **FillSchema** 메서드를 호출하거나 **Fill**을 호출하기 전에 **DataAdapter**의 **MissingSchemaAction** 속성을 **AddWithKey**로 설정합니다.  이렇게 하면 **DataSet**의 기본 키 제약 조건이 데이터 소스의 해당 제약 조건을 반영합니다.  외래 키 제약 조건 정보는 포함되지 않으므로 [DataTable 제약 조건](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)에 나와 있는 대로 명시적으로 만들어야 합니다.  
  
 **DataSet**을 데이터로 채우기 전에 스키마 정보를 추가하면 기본 키 제약 조건이 <xref:System.Data.DataTable> 개체와 함께 **DataSet**에 포함됩니다.  결과적으로 **DataSet**의 Fill에 대한 추가 호출이 있으면 기본 키 열 정보를 사용하여 데이터 소스의 새 행을 각 **DataTable**의 현재 행과 일치시키고 해당 테이블의 현재 데이터를 데이터 소스의 데이터로 덮어씁니다.  스키마 정보가 없으면 데이터 소스의 새 행이 **DataSet**에 추가되어 결국 행이 중복됩니다.  
  
> [!NOTE]
>  데이터 소스의 열이 자동 증분 열로 식별되면 **FillSchema** 메서드 또는 **AddWithKey**의 **MissingSchemaAction** 속성이 있는 **Fill** 메서드는 **AutoIncrement** 속성이 `true`로 설정된 **DataColumn**을 만듭니다.  그러나 **AutoIncrementStep**과 **AutoIncrementSeed** 값은 직접 설정해야 합니다.  자동 증분 열에 대한 자세한 내용은 [AutoIncrement 열 만들기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)를 참조하세요.  
  
 **FillSchema**를 사용하거나 **MissingSchemaAction**을 **AddWithKey**로 설정하려면 기본 키 열 정보를 확인하기 위해 데이터 소스에서 추가 처리를 수행해야 합니다.  이러한 추가 처리로 인해 성능이 낮아질 수 있습니다.  디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다.  테이블의 기본 키 정보를 명시적으로 설정하는 방법은 [기본 키 정의](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)를 참조하세요.  
  
 다음 코드 예제에서는 **FillSchema**를 사용하여 스키마 정보를 **DataSet**에 추가하는 방법을 보여 줍니다.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 다음 코드 예제에서는 **Fill** 메서드의 **MissingSchemaAction.AddWithKey** 속성을 사용하여 스키마 정보를 **DataSet**에 추가하는 방법을 보여 줍니다.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## 여러 개의 결과 집합 처리  
 **DataAdapter**는 **SelectCommand**에서 반환된 여러 개의 결과 집합이 발생하면 **DataSet**에 여러 개의 테이블을 만듭니다.  테이블에는 0부터 시작하되 "Table0"이 아니라 **Table**로 시작하는 증분 기본 이름 **Table** *N*이 지정됩니다.  테이블 이름이 **FillSchema** 메서드에 인수로 전달되는 경우 테이블에는 0부터 시작하되 "TableName0"이 아니라 **TableName**으로 시작하는 증분 기본 이름 **TableName** *N*이 지정됩니다.  
  
> [!NOTE]
>  여러 결과 집합을 반환하는 명령에 대해 **OleDbDataAdapter** 개체의 **FillSchema** 메서드가 호출되면 첫째 결과 집합의 스키마 정보만 반환됩니다.  **OleDbDataAdapter**를 사용하여 여러 결과 집합에 대한 스키마 정보를 반환할 경우 **AddWithKey**의 **MissingSchemaAction**을 지정하고 **Fill** 메서드를 호출할 때 스키마 정보를 가져오는 것이 좋습니다.  
  
## 참고 항목  
 [DataAdapters 및 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [DataSets, DataTables 및 DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)