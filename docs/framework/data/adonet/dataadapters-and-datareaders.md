---
title: "DataAdapters 및 DataReaders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataAdapters 및 DataReaders
ADO.NET **DataReader**를 사용하여 데이터베이스에서 앞으로만 이동 가능한 읽기 전용 데이터 스트림을 검색할 수 있습니다.  결과는 쿼리를 실행할 때 반환되며 **DataReader**의 **Read** 메서드를 사용하여 이를 요청할 때까지 클라이언트의 네트워크 버퍼에 저장됩니다.  **DataReader**를 사용하면 사용이 가능해지는 즉시 데이터를 검색하고 기본적으로 메모리에 한 번에 행 하나씩만 저장하여 시스템 오버헤드를 줄임으로써 응용 프로그램의 성능을 향상시킬 수 있습니다.  
  
 <xref:System.Data.Common.DataAdapter>는 데이터 소스에서 데이터를 검색하고 <xref:System.Data.DataSet> 내의 테이블을 채우는 데 사용됩니다.  `DataAdapter`는 `DataSet`의 변경 내용을 다시 데이터 소스에 적용합니다.  `DataAdapter`는 .NET Framework 데이터 공급자의 `Connection` 개체를 사용하여 데이터 소스에 연결하며 `Command` 개체를 사용하여 데이터 소스에서 데이터를 검색하고 변경 내용을 데이터 소스에 적용합니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbDataReader> 및 <xref:System.Data.Common.DbDataAdapter> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.OleDb.OleDbDataAdapter> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlDataReader> 및 <xref:System.Data.SqlClient.SqlDataAdapter> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcDataReader> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleDataReader> 및 <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 있습니다.  
  
## 단원 내용  
 [DataReader를 사용하여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 ADO.NET **DataReader** 개체 및 이 개체를 사용하여 데이터 소스에서 결과 스트림을 반환하는 방법을 설명합니다.  
  
 [DataAdapter에서 데이터 집합 채우기](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 `DataAdapter`를 사용하여 테이블, 열 및 행으로 `DataSet`을 채우는 방법을 설명합니다.  
  
 [DataAdapter 매개 변수](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 `DataSet`의 열 내용을 명령 매개 변수에 매핑하는 방법을 비롯하여 `DataAdapter`의 명령 속성에 매개 변수를 사용하는 방법을 설명합니다.  
  
 [DataSet에 기존 제약 조건 추가](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 `DataSet`에 기존 제약 조건을 추가하는 방법을 설명합니다.  
  
 [DataAdapter, DataTable 및 DataColumn 매핑](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 `DataAdapter`에 대해 `DataTableMappings` 및 `ColumnMappings`를 설정하는 방법을 설명합니다.  
  
 [쿼리 결과 페이징](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 쿼리 결과를 데이터 페이지로 보는 예제를 제공합니다.  
  
 [DataAdapters를 사용하여 데이터 소스 업데이트](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 `DataAdapter`를 사용하여 `DataSet`의 변경 내용을 데이터베이스에 적용하는 방법을 설명합니다.  
  
 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 `DataAdapter` 이벤트와 이벤트 사용 방법을 설명합니다.  
  
 [DataAdapters를 사용하여 배치 작업 수행](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 `DataSet`의 업데이트를 적용할 때 SQL Server로의 라운드트립 횟수를 줄여 응용 프로그램의 성능을 향상시키는 방법을 설명합니다.  
  
## 참고 항목  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [DataSets, DataTables 및 DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)