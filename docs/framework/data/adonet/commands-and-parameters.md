---
title: "명령 및 매개 변수 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 명령 및 매개 변수
데이터 소스에 대한 연결을 설정한 후에는 <xref:System.Data.Common.DbCommand> 개체를 사용하여 명령을 실행하고 데이터 소스에서 결과를 반환할 수 있습니다.  명령은 현재 사용하는 .NET Framework 데이터 공급자의 명령 생성자 중 하나를 사용하여 만들 수 있습니다.  생성자는 데이터 소스에서 실행하는 SQL 문, <xref:System.Data.Common.DbConnection> 개체 또는 <xref:System.Data.Common.DbTransaction> 개체와 같은 선택적 인수를 사용할 수 있습니다.  이러한 개체를 명령의 속성으로 구성할 수도 있습니다.  또한 `DbConnection` 개체의 <xref:System.Data.Common.DbConnection.CreateCommand%2A> 메서드를 사용하여 특정 연결에 대한 명령을 만들 수 있습니다.  명령을 통해 실행되는 SQL 문은 <xref:System.Data.Common.DbCommand.CommandText%2A> 속성을 사용하여 구성할 수 있습니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 `Command` 개체가 있습니다.  .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbCommand> 개체가 있고, .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlCommand> 개체가 있으며, .NET Framework Data Provider for ODBC와 .NET Framework Data Provider for Oracle에는 각각 <xref:System.Data.Odbc.OdbcCommand> 개체와 <xref:System.Data.OracleClient.OracleCommand> 개체가 있습니다.  
  
## 단원 내용  
 [명령 실행](../../../../docs/framework/data/adonet/executing-a-command.md)  
 ADO.NET `Command` 개체 및 이 개체를 사용하여 데이터 소스에 대해 쿼리와 명령을 실행하는 방법을 설명합니다.  
  
 [매개 변수 및 매개 변수 데이터 형식 구성](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 방향, 데이터 형식 및 매개 변수 구문을 포함하여 `Command` 매개 변수로 작업하는 방법을 설명합니다.  
  
 [CommandBuilders를 사용하여 명령 생성](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 명령 작성기를 사용하여 단일 테이블 SELECT 명령이 들어 있는 `DataAdapter`에 대해 INSERT, UPDATE 및 DELETE 명령을 자동으로 생성하는 방법을 설명합니다.  
  
 [데이터베이스에서 단일 값 가져오기](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 `Command` 개체의 `ExecuteScalar` 메서드를 사용하여 데이터베이스 쿼리에서 단일 값을 반환하는 방법을 설명합니다.  
  
 [명령을 사용하여 데이터 수정](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 데이터 공급자를 사용하여 저장 프로시저 또는 DDL\(데이터 정의 언어\) 문을 실행하는 방법을 설명합니다.  
  
## 참고 항목  
 [DataAdapters 및 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [DataSets, DataTables 및 DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)