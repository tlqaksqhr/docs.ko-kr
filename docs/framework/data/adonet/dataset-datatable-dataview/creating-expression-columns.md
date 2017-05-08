---
title: "식 열 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 식 열 만들기
테이블에서 같은 행의 다른 열 값이나 여러 행의 열 값에서 계산한 값을 포함할 수 있도록 열에 대한 식을 정의할 수 있습니다.  계산할 식을 정의하려면 대상 열의 <xref:System.Data.DataColumn.Expression%2A> 속성과 <xref:System.Data.DataColumn.ColumnName%2A> 속성을 사용하여 식에서 다른 열을 참조합니다.  식 열의 <xref:System.Data.DataColumn.DataType%2A>은 이 식에서 반환되는 값에 적합해야 합니다.  
  
 다음 표에서는 식 열을 사용할 수 있는 몇 가지 방법의 목록을 보여 줍니다.  
  
|식 형식|예제|  
|----------|--------|  
|비교|"Total \>\= 500"|  
|계산|"UnitPrice \* Quantity"|  
|집계|Sum\(Price\)|  
  
 다음 예제에서와 같이 기존 **DataColumn** 개체의 **Expression** 속성을 설정하거나 세 번째 인수가 <xref:System.Data.DataColumn> 생성자로 전달될 때 해당 속성을 포함할 수 있습니다.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 식은 다른 식 열을 참조할 수 있습니다. 그러나 두 식이 서로를 참조하는 순환 참조에서는 예외가 발생합니다.  식 작성 규칙에 대한 자세한 내용은 **DataColumn** 클래스의 <xref:System.Data.DataColumn.Expression%2A> 속성을 참조하세요.  
  
## 참고 항목  
 <xref:System.Data.DataColumn>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)