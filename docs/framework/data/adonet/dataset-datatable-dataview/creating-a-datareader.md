---
title: "DataReader 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DataReader 만들기
<xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스에는 <xref:System.Data.DataTable>의 내용이나 <xref:System.Data.DataSet> 개체의 <xref:System.Data.DataSet.Tables%2A> 컬렉션 내용을 하나 이상의 정방향 읽기 전용 커서로 반환하는 <xref:System.Data.DataTable.CreateDataReader%2A> 메서드가 있습니다.  
  
## 예제  
 다음 콘솔 응용 프로그램에서는 <xref:System.Data.DataTable> 인스턴스를 만듭니다.  그런 다음 이 예제에서는 채워진 <xref:System.Data.DataTable>을 <xref:System.Data.DataTable.CreateDataReader%2A> 메서드를 호출하는 프로시저로 전달하여 <xref:System.Data.DataTableReader> 내에 포함된 결과를 반복합니다.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 이 예제에서는 콘솔 창에 다음 출력을 표시합니다.  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## 참고 항목  
 <xref:System.Data.DataTable.CreateDataReader%2A>   
 <xref:System.Data.DataSet.CreateDataReader%2A>   
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)