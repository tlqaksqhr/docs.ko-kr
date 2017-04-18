---
title: "DataTables 탐색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataTables 탐색
<xref:System.Data.DataTableReader>는 하나 이상의 <xref:System.Data.DataTable> 개체 내용을 하나 이상의 앞으로만 이동 가능한 읽기 전용 결과 집합 형태로 가져옵니다.  
  
 <xref:System.Data.DataSet.CreateDataReader%2A> 메서드를 사용하여 <xref:System.Data.DataTableReader>를 만들 경우에는 여러 개의 결과 집합이 포함될 수 있습니다.  결과 집합이 둘 이상이면 <xref:System.Data.DataTableReader.NextResult%2A> 메서드는 커서를 다음 결과 집합으로 이동합니다.  이것은 앞으로만 이동 가능한 프로세스이며,  이전 결과 집합으로 돌아갈 수는 없습니다.  
  
## 예제  
 다음 예제에서 `TestConstructor` 메서드는 두 개의 <xref:System.Data.DataTable> `` 인스턴스를 만듭니다.  이 예제에서는 <xref:System.Data.DataTableReader> 클래스의 이 생성자를 보여 주기 위해 두 개의 **DataTables**가 포함된 배열을 기반으로 새 **DataTableReader**를 만들고, 처음 몇 개의 열에서 콘솔 창으로 내용을 인쇄하는 간단한 작업을 수행합니다.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## 참고 항목  
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)