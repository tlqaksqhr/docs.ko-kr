---
title: "DataTableReaders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTableReaders
<xref:System.Data.DataTableReader>는 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용을 하나 이상의 정방향 읽기 전용 결과 집합 형태로 제공합니다.  
  
 **DataTable**에서 **DataTableReader**를 만들면 결과 **DataTableReader** 개체에는 삭제된 것으로 표시된 행을 제외하고 생성된 **DataTable**과 데이터가 동일한 결과 집합 하나가 포함됩니다.  열은 원본 **DataTable**과 동일한 순서로 나타납니다.  
  
 <xref:System.Data.DataSet.CreateDataReader%2A>를 호출하여 **DataTableReader**를 만들었을 경우에는 여러 개의 결과 집합이 포함될 수 있습니다.  결과는 **DataSet** 개체의 <xref:System.Data.DataSet.Tables%2A> 컬렉션에 있는 **DataTables**와 동일한 순서로 나타납니다.  
  
## 단원 내용  
 [DataReader 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 **DataTableReader** 개체를 만드는 방법을 설명합니다.  
  
 [DataTables 탐색](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 **Read** 메서드를 사용하여 **DataTableReader**의 내용을 이동하는 방법을 설명합니다.  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)