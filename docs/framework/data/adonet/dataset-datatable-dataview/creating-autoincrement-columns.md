---
title: "AutoIncrement 열 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# AutoIncrement 열 만들기
열에 고유 값을 지정하려면 테이블에 새 행을 추가할 때 열 값이 자동으로 증가하도록 설정합니다.  자동 증분 <xref:System.Data.DataColumn>을 만들려면 열의 <xref:System.Data.DataColumn.AutoIncrement%2A> 속성을 **true**로 설정합니다.  그러면 <xref:System.Data.DataColumn>은 <xref:System.Data.DataColumn.AutoIncrementSeed%2A> 속성에 정의된 값으로 시작하고, 각 행이 추가될 때마다 **AutoIncrement** 열의 값은 열의 <xref:System.Data.DataColumn.AutoIncrementStep%2A> 속성에 정의된 값만큼 증가하게 됩니다.  
  
 **AutoIncrement** 열의 경우 **DataColumn**의 <xref:System.Data.DataColumn.ReadOnly%2A> 속성을 **true**로 설정하는 것이 좋습니다.  
  
 다음 예제에서는 200으로 시작하여 3씩 증가하여 추가되는 열을 만드는 방법을 보여 줍니다.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## 참고 항목  
 <xref:System.Data.DataColumn>   
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)